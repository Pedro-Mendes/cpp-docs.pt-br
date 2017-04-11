---
title: "module (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.module"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "atributos de módulo"
ms.assetid: 02223b2a-62b5-4262-832f-564b1e11e58e
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# module (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Define o bloco de biblioteca no arquivo. idl.  
  
## Sintaxe  
  
```  
  
[ module (  
type  
=dll,  
name  
=  
string  
,  
version  
=1.0,  
   uuid=  
uuid  
,  
   lcid=  
integer  
,  
   control=  
boolean  
,  
   helpstring=  
string  
,  
helpstringdll  
=  
string  
,  
helpfile  
=  
string  
,  
helpcontext  
=  
integer  
,  
helpstringcontext  
=  
integer  
,  
hidden  
=  
boolean  
,  
restricted  
=  
boolean  
,  
custom  
=  
string  
,  
   resource_name=  
string  
,  
) ];  
  
```  
  
#### Parâmetros  
 ***tipo***  \(opcional\)  
 Pode ser uma das seguintes opções:  
  
-   **dll** adiciona funções e classes que permitem que a DLL resultante funcionar como um servidor de COM em processo. Esse é o valor padrão.  
  
-   **exe** adiciona funções e classes que permitem resultante executável para funcionarem como um limite de servidor COM de processo.  
  
-   **service** adiciona funções e classes que permitem resultante executável para funcionar como um serviço NT.  
  
-   **não especificado** desabilita a injeção de código ATL relacionada ao atributo de módulo: funções de ponto a injeção de classe de módulo ATL, \_AtlModule instância global e entrada.  Não desabilite a injeção de código ATL devido a outros atributos no projeto.  
  
 ***nome***  \(opcional\)  
 O nome do bloco de biblioteca.  
  
 ***versão***  \(opcional\)  
 O número de versão que você deseja atribuir ao bloco de biblioteca. O valor padrão é 1.0.  
  
 `uuid`  
 A ID exclusiva para a biblioteca. Se você omitir esse parâmetro, uma ID será gerada automaticamente para a biblioteca. Talvez você precise recuperar o *uuid* do seu bloco de biblioteca, que pode ser feito usando o identificador **uuidof \(***nome da biblioteca***\)**.  
  
 **lcid**  
 O parâmetro de localização. Consulte [lcid](http://msdn.microsoft.com/library/windows/desktop/aa367067) para obter mais informações.  
  
 **controle** \(opcional\)  
 Especifica que todos os coclasses na biblioteca de controles.  
  
 **helpstring**  
 Especifica a biblioteca de tipos.  
  
 ***helpstringdll***  \(opcional\)  
 Define o nome do arquivo. dll para usar para executar uma pesquisa de cadeia de caracteres do documento. Consulte [helpstringdll](http://msdn.microsoft.com/library/windows/desktop/aa366860) para obter mais informações.  
  
 **helpfile** \(opcional\)  
 O nome do arquivo de ajuda para a biblioteca de tipos.  
  
 **helpcontext** \(opcional\)  
 A identificação de ajuda para esta biblioteca de tipos.  
  
 **helpstringcontext** \(opcional\)  
 Consulte [helpstringcontext](../windows/helpstringcontext.md) para obter mais informações.  
  
 **oculta** \(opcional\)  
 Impede que a biblioteca inteira seja exibido. Esse uso é destinado ao uso com controles. Hosts precisam criar uma nova biblioteca de tipos que encapsula o controle com as propriedades estendidas. Consulte o [oculta](http://msdn.microsoft.com/library/windows/desktop/aa366861) atributo MIDL para obter mais informações.  
  
 **restrito** \(opcional\)  
 Membros da biblioteca não podem ser chamados arbitrariamente. Consulte o [restrito](http://msdn.microsoft.com/library/windows/desktop/aa367157) atributo MIDL para obter mais informações.  
  
 ***personalizado***  \(opcional\)  
 Um ou mais atributos; Isso é semelhante do [personalizado](../windows/custom-cpp.md) atributo. O primeiro parâmetro para `custom` é o GUID do atributo. Por exemplo:  
  
```  
[module(custom={guid,1}, custom={guid1,2})]  
```  
  
 **resource\_name**  
 A ID de recurso de cadeia de caracteres do arquivo. rgs usado para registrar a ID do aplicativo da DLL, executável ou de serviços. Quando o módulo é do tipo serviço, esse argumento é usado também para obter a ID da cadeia de caracteres que contém o nome do serviço.  
  
> [!NOTE]
>  O arquivo rgs e a cadeia de caracteres que contém o nome do serviço devem conter o mesmo valor numérico.  
  
## Comentários  
 A menos que você especifique o **restrito** parâmetro [emitidl](../windows/emitidl.md), **módulo** é necessária em qualquer programa que usa atributos de C\+\+.  
  
 Um bloco de biblioteca será criado se, além de **módulo** atributo, código\-fonte também usa [dispinterface](../windows/dispinterface.md), [dual](../Topic/dual.md), [objeto](../Topic/object%20\(C++\).md), ou um atributo que implica [coclass](../windows/coclass.md).  
  
 Um bloco de biblioteca é permitido em um arquivo. idl. Várias entradas do módulo no código\-fonte serão mescladas com os valores de parâmetro mais recentes que está sendo implementados.  
  
 Se esse atributo for usado em um projeto que usa o ATL, altera o comportamento do atributo. Além do comportamento acima, o atributo também insere um objeto global \(chamado **\_AtlModule**\) do tipo correto e código de suporte adicionais. Se o atributo for autônomo, ele insere uma classe derivada do tipo de módulo correto. Se o atributo é aplicado a uma classe, ele adiciona uma classe base do tipo de módulo correto. O tipo correto é determinado pelo valor da `type` parâmetro:  
  
-   `type` \= **dll**  
  
     [CAtlDllModuleT](../atl/reference/catldllmodulet-class.md) é usada como a classe base e a entrada DLL padrão pontos necessários para um servidor COM. Esses pontos de entrada são [DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583), [DllRegisterServer](http://msdn.microsoft.com/library/windows/desktop/ms682162), [DllUnRegisterServer](http://msdn.microsoft.com/library/windows/desktop/ms691457), [DllCanUnloadNow](http://msdn.microsoft.com/library/windows/desktop/ms690368), e [DllGetClassObject](http://msdn.microsoft.com/library/windows/desktop/dd797891).  
  
-   `type` \= **exe**  
  
     [CAtlExeModuleT](../atl/reference/catlexemodulet-class.md) é usada como a classe base e o ponto de entrada executáveis padrão [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559).  
  
-   `type` \= **service**  
  
     [CAtlServiceModuleT](../Topic/CAtlServiceModuleT%20Class.md) é usada como a classe base e o ponto de entrada executáveis padrão [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559).  
  
-   `type` \= **especificado**  
  
     Desabilita a injeção de código ATL relacionada ao atributo de módulo.  
  
## Exemplo  
 O código a seguir mostra como criar um bloco de biblioteca no arquivo. idl gerado.  
  
```  
// cpp_attr_ref_module1.cpp  
// compile with: /LD  
[module(name="MyLibrary", version="1.2", helpfile="MyHelpFile")];  
```  
  
 O código a seguir mostra o que você pode fornecer sua própria implementação de uma função que aparecem no código que foi injetado como resultado do uso **módulo**. Consulte [\/Fx](../build/reference/fx-merge-injected-code.md) para obter mais informações sobre como visualizar o código injetado. Para substituir uma das funções inseridas pelo **módulo** atributo, tornar uma classe que conterá a implementação da função e fazer a **módulo** atributo aplicado a essa classe.  
  
```  
// cpp_attr_ref_module2.cpp  
// compile with: /LD /link /OPT:NOREF  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlwin.h>  
#include <atltypes.h>  
#include <atlctl.h>  
#include <atlhost.h>  
#include <atlplus.h>  
  
// no semicolon after attribute block  
[module(dll, name="MyLibrary", version="1.2", helpfile="MyHelpFile")]   
// module attribute now applies to this class  
class CMyClass {  
public:  
BOOL WINAPI DllMain(DWORD dwReason, LPVOID lpReserved) {  
   // add your own code here  
   return __super::DllMain(dwReason, lpReserved);  
   }  
};  
```  
  
## Requisitos  
  
### Contexto de atributo  
  
|||  
|-|-|  
|**Aplica\-se a**|Em qualquer lugar|  
|**Repetível**|Não|  
|**Atributos necessários**|Nenhum|  
|**Atributos inválidos**|Nenhum|  
  
 Para obter mais informações, consulte [contextos de atributo](../windows/attribute-contexts.md).  
  
## Consulte também  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Stand\-Alone Attributes](../Topic/Stand-Alone%20Attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [usesgetlasterror](../windows/usesgetlasterror.md)   
 [biblioteca](http://msdn.microsoft.com/library/windows/desktop/aa367069)   
 [helpcontext](../windows/helpcontext.md)   
 [helpstring](../windows/helpstring.md)   
 [helpfile](../Topic/helpfile.md)   
 [version](../windows/version-cpp.md)   
 [Attributes Samples](http://msdn.microsoft.com/pt-br/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)