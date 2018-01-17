---
title: "Manipuladores para mensagens do Windows padrão | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: afx_msg
dev_langs: C++
helpviewer_keywords:
- Windows messages [MFC], handlers
- message handling [MFC], Windows message handlers
- handler functions, standard Windows messages
- functions [MFC], handler
- messages [MFC], Windows
ms.assetid: 19412a8b-2c38-4502-81da-13c823c7e36c
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 91df3462297c2a45a8938d815cc3b6a3b8ca6edb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="handlers-for-standard-windows-messages"></a>Manipuladores para mensagens do Windows padrão
Padrão de manipuladores de mensagens padrão do Windows (**WM _**) são predefinidos na classe `CWnd`. A biblioteca de classes bases nomes para esses manipuladores no nome da mensagem. Por exemplo, o manipulador para o `WM_PAINT` mensagem for declarada em `CWnd` como:  
  
 `afx_msg void OnPaint();`  
  
 O **afx_msg** palavra-chave sugere o efeito do C++ **virtual** palavra-chave por distinguir os manipuladores de outros `CWnd` funções de membro. No entanto, observe que essas funções não são realmente virtuais; em vez disso, eles são implementados por meio de mapas de mensagem. Mapas de mensagem dependem somente macros de pré-processador padrão, não em extensões para a linguagem C++. O **afx_msg** palavra-chave resolve para o espaço em branco depois de pré-processamento.  
  
 Para substituir um manipulador definido em uma classe base, defina uma função com o mesmo protótipo em sua classe derivada e para fazer uma entrada de mapa de mensagem para o manipulador. O manipulador "substitui" qualquer manipulador de mesmo nome em qualquer uma das classes base da classe.  
  
 Em alguns casos, o manipulador deve chamar o manipulador substituído na classe base para a classe base e o Windows pode operar na mensagem. Em que você chamar o manipulador da classe base na sua substituição depende das circunstâncias. Às vezes, você deve chamar o manipulador da classe base primeiro e último às vezes. Às vezes, você chama o manipulador da classe base condicionalmente, se você optar por não manipular a mensagem por conta própria. Às vezes, você deve chamar o manipulador da classe base e condicionalmente executar seu próprio código de manipulador, dependendo do valor ou o estado retornado pelo manipulador de classe base.  
  
> [!CAUTION]
>  Não é seguro modificar os argumentos passados para um manipulador, se você pretende passá-las para um manipulador de classe base. Por exemplo, você pode ser tentado para modificar o `nChar` argumento do `OnChar` manipulador (para converter em letras maiusculas, por exemplo). Esse comportamento é razoavelmente obscuro, mas se você precisa realizar esse efeito, use o `CWnd` função de membro **SendMessage** em vez disso.  
  
 Como determinar o modo adequado para substituir uma mensagem fornecida quando a janela Propriedades grava o esqueleto da função de manipulador para uma determinada mensagem — um `OnCreate` manipulador para `WM_CREATE`, por exemplo, ele esboços na forma de recomendada substituído a função de membro. O exemplo a seguir recomenda que o manipulador primeiro chamar o manipulador da classe base e continuar somente na condição de que ele não retornará -1.  
  
 [!code-cpp[NVC_MFCMessageHandling#3](../mfc/codesnippet/cpp/handlers-for-standard-windows-messages_1.cpp)]  
  
 Por convenção, os nomes desses manipuladores começam com o prefixo "On". Alguns desses manipuladores não usam argumentos, enquanto outras usam vários. Alguns também têm um tipo de retorno diferente de `void`. Os manipuladores de padrão para todos os **WM _** mensagens estão documentadas a *referência MFC* como funções de membro da classe `CWnd` cujos nomes começam com "On". As declarações de função de membro em `CWnd` são prefixados com **afx_msg**.  
  
## <a name="see-also"></a>Consulte também  
 [Declarando funções de manipulador de mensagens](../mfc/declaring-message-handler-functions.md)