---
title: "Exceções (C + + CX) | Microsoft Docs"
ms.custom: 
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6cbdc1f1-e4d7-4707-a670-86365146432f
caps.latest.revision: "22"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: b9b7a5af4816ff638918ccf7478465fe120e8e67
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="exceptions-ccx"></a>Exceções (C++/CX)

Tratamento de erros em C + + CX se baseia em exceções. O nível mais fundamental, os componentes de tempo de execução do Windows relatam erros como valores HRESULT. Em C + + CX, esses valores são convertidos em exceções fortemente tipadas que contêm um valor HRESULT e uma descrição de cadeia de caracteres que você pode acessar programaticamente.  As exceções são implementadas como `ref class` que deriva de `Platform::Exception`.  O namespace `Platform` define classes de exceção distinta para os valores HRESULT mais comuns; todos os outros valores são relatados por meio da classe `Platform::COMException` . Todas as classes de exceção têm um campo [Exception::HResult](platform-exception-class.md#hresult) que você pode usar para recuperar o HRESULT original. Você também pode examinar informações de pilha de chamadas para código de usuário no depurador que pode ajudar a identificar a origem da exceção, mesmo se ele foi originado no código escrito em um idioma diferente do C++.  
  
## <a name="exceptions"></a>Exceções  
 No seu programa C++, você pode gerar e capturar uma exceção proveniente de uma operação de tempo de execução do Windows, uma exceção que é derivada de `std::exception`, ou um tipo definido pelo usuário. Você tem que gerar uma exceção de tempo de execução do Windows somente quando ele for passar dos limites ABI (interface binária) do aplicativo, por exemplo, quando o código que captura sua exceção está escrito em JavaScript. Quando uma exceção do Windows em tempo de execução C++ alcança os limites de ABI, a exceção é convertida em um `Platform::FailureException` exceção, que representa um E_FAIL HRESULT. Para obter mais informações sobre a ABI, consulte [Creating Windows Runtime Components in C++](/MicrosoftDocs/windows-uwp/blob/docs/windows-apps-src/winrt-components/creating-windows-runtime-components-in-cpp.md).  
  
 Você pode declarar uma [Platform::Exception](platform-exception-class.md) usando um dos dois construtores que usam um parâmetro HRESULT, ou um parâmetro HRESULT e um parâmetro [Platform::String](platform-string-class.md)^ que possa ser passado pela ABI para qualquer aplicativo da Windows Store que o manipule. Ou pode declarar uma exceção usando uma de duas sobrecargas do [método Exception::CreateException](platform-exception-class.md#createexception) que adotam um parâmetro HRESULT, ou um parâmetro HRESULT e um parâmetro `Platform::String^` .  
  
## <a name="standard-exceptions"></a>Exceções padrão  
 C + + CX dá suporte a um conjunto de exceções padrão que representam erros HRESULT típicos. Cada exceção padrão é derivada de [Platform::COMException](platform-comexception-class.md), que, por sua vez, é derivada de `Platform::Exception`. Quando você gera uma exceção através dos limites da ABI, é necessário gerar uma das exceções padrão.  

 você não pode derivar seu próprio tipo de exceção de `Platform::Exception`. Para gerar uma exceção personalizada, use um HRESULT definido pelo usuário para construir um objeto `COMException` .  
  
 A tabela a seguir lista as exceções padrão.  
  
|Nome|HRESULT subjacente|Descrição|  
|----------|------------------------|-----------------|  
|COMException|*hresult definido pelo usuário*|Gerada quando um HRESULT não reconhecido é retornado de um chamada de método COM.|  
|AccessDeniedException|E_ACCESSDENIED|Gerada quando o acesso a um recurso é negado.|  
|ChangedStateException|E_CHANGED_STATE|Gerada quando métodos de um iterador de coleção ou uma exibição de coleção são chamados após a alteração da coleção pai, portanto, invalidando os resultados do método.|  
|ClassNotRegisteredException|REGDB_E_CLASSNOTREG|Gerada quando uma classe COM não foi registrada.|  
|DisconnectedException|RPC_E_DISCONNECTED|Gerada quando um objeto é desconectado de seus clientes.|  
|FailureException|E_FAIL|Gerada quando uma operação falha.|  
|InvalidArgumentException|E_INVALIDARG|Gerada quando um dos argumentos fornecidos a um método não é válido.|  
|InvalidCastException|E_NOINTERFACE|Gerada quando um tipo não pode ser convertido em outro tipo.|  
|NotImplementedException|E_NOTIMPL|Gerada se um método de interface não foi implementado em uma classe.|  
|NullReferenceException|E_POINTER|Gerada quando ocorre uma tentativa de cancelar a referência de um objeto de referência nula.|  
|ObjectDisposedException|RO_E_CLOSED|Gerada quando uma operação é executada em um objeto descartado.|  
|OperationCanceledException|E_ABORT|Gerada quando uma operação é anulada.|  
|OutOfBoundsException|E_BOUNDS|Gerada quando uma operação tenta acessar dados fora do intervalo válido.|  
|OutOfMemoryException|E_OUTOFMEMORY|Gerada quando a memória para concluir a operação é insuficiente.|  
|WrongThreadException|RPC_E_WRONG_THREAD|Gerada quando um thread chama via um ponteiro de interface, que destina-se a um objeto proxy que não pertence ao apartment do thread.|  
  
## <a name="hresult-and-message-properties"></a>Propriedades de HResult e de Message  
 Todas as exceções têm uma propriedade [HResult](platform-comexception-class.md#hresult) e uma propriedade [Message](platform-comexception-class.md#message) . A propriedade [Exception::HResult](platform-exception-class.md#hresult) obtém o valor HRESULT numérico subjacente da exceção. A propriedade [Exception::Message](platform-exception-class.md#message) obtém a cadeia de caracteres fornecida pelo sistema que descreve a exceção. No Windows 8, a mensagem está disponível somente no depurador e é somente leitura. Isso significa que você não pode alterá-la ao gerar novamente a exceção. No Windows 8.1, você pode acessar a cadeia de caracteres da mensagem programaticamente e fornecer uma nova mensagem se a exceção for gerada novamente. As melhores informações da pilha de chamadas também estão disponíveis no depurador, incluindo pilhas de chamadas de método assíncrono.  
  
### <a name="examples"></a>Exemplos  
 Este exemplo mostra como gerar uma exceção de tempo de execução do Windows para operações síncronas:  
  
 [!code-cpp[cx_exceptions#01](codesnippet/CPP/exceptiontest/class1.cpp#01)]  
  
 O exemplo a seguir mostra como capturar a exceção.  
  
 [!code-cpp[cx_exceptions#02](codesnippet/CPP/exceptiontest/class1.cpp#02)]  
  
 Para capturar exceções geradas durante uma operação assíncrona, use a classe task e adicione uma continuação de tratamento de erro. A continuação do tratamento de erro realiza marshaling das exceções que são geradas em outros threads de volta para o thread chamador, de modo que você possa tratar todas as exceções potenciais em apenas um ponto no seu código. Para obter mais informações, veja [Programação assíncrona em C++](http://msdn.microsoft.com/library/windows/apps/Hh780559.aspx).  
  
## <a name="unhandlederrordetected-event"></a>Evento UnhandledErrorDetected  
 No Windows 8.1, você pode assinar para o [Windows::ApplicationModel::Core::CoreApplication::UnhandledErrorDetected](http://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.core.coreapplication.unhandlederrordetected.aspx) evento estático, que fornece acesso aos erros não tratados que estão prestes a anular o processo. Independentemente da origem do erro, ele chega a esse manipulador como um objeto [Windows::ApplicationModel::Core::UnhandledError](http://msdnstage.redmond.corp.microsoft.com/library/windows/apps/windows.applicationmodel.core.unhandlederror.aspx) que é transmitido com os argumentos do evento. Quando você chama `Propagate` no objeto, ele cria e gera uma exceção `Platform::*Exception` do tipo correspondente ao código de erro. Nos blocos catch, você pode salvar o estado do usuário, se necessário, e permitir que o processo seja finalizado chamando `throw`ou fazendo algo para colocar o programa novamente em um estado conhecido. O exemplo a seguir mostra o padrão básico:  
  
```  
  
// In app.xaml.h:  
void OnUnhandledException(Platform::Object^ sender, Windows::ApplicationModel::Core::UnhandledErrorDetectedEventArgs^ e);  
  
// In app.xaml.cpp  
  
// Subscribe to the event, for example in the app class constructor:  
Windows::ApplicationModel::Core::CoreApplication::UnhandledErrorDetected += ref new EventHandler<UnhandledErrorDetectedEventArgs^>(this, &App::OnUnhandledException);  
  
// Event handler implementation:  
void App::OnUnhandledException(Platform::Object^ sender, Windows::ApplicationModel::Core::UnhandledErrorDetectedEventArgs^ e)  
{  
    auto err = e->UnhandledError;  
  
    if (!err->Handled) //Propagate has not been called on it yet.  
{  
     try  
    {  
        err->Propagate();  
    }  
    // Catch any specific exception types if you know how to handle them  
    catch (AccessDeniedException^ ex)  
    {  
        // TODO: Log error and either take action to recover  
        // or else re-throw exception to continue fail-fast  
    }  
  
}  
  
```  
  
### <a name="remarks"></a>Comentários  
 C + + CX não usa o `finally` cláusula.  
  
## <a name="see-also"></a>Consulte também  
 [Referência de linguagem do Visual C++](visual-c-language-reference-c-cx.md)   
 [Referência de namespaces](namespaces-reference-c-cx.md)