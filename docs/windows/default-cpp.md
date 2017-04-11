---
title: "default (C++) | Microsoft Docs"
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
  - "vc-attr.default"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "atributo padrão"
  - "atributos [c#], o atributo padrão"
  - "padrões de atributo padrão"
ms.assetid: 0cdca716-1ba8-46d7-9399-167e55492870
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# default (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Indica que a dispinterface definidos dentro de uma coclass ou personalizado representa a interface de programação padrão.  
  
## Sintaxe  
  
```  
  
[ default(  
interface1  
,  
   interface2  
) ]  
  
```  
  
#### Parâmetros  
 *Interface1*  
 A interface padrão que será disponibilizada para os ambientes de script que cria um objeto com base na classe definida com a **padrão** atributo.  
  
 Se nenhuma interface padrão for especificado, a primeira ocorrência de uma interface nonsource é usada como o padrão.  
  
 *interface2*\(opcional\)  
 A interface de origem padrão. Você também deve especificar essa interface com o [fonte](../Topic/source%20\(C++\).md) atributo.  
  
 Se nenhuma interface de origem padrão for especificado, a primeira interface de origem é usada como o padrão.  
  
## Comentários  
 A **padrão** C\+\+ atributo tem a mesma funcionalidade que o [padrão](http://msdn.microsoft.com/library/windows/desktop/aa366787) atributo MIDL. A **padrão** atributo também é usado com o [caso](../windows/case-cpp.md) atributo.  
  
## Exemplo  
 O código a seguir mostra como **padrão** é usado na definição de coclass para especificar **ICustomDispatch** como a interface de programação padrão:  
  
```  
// cpp_attr_ref_default.cpp  
// compile with: /LD  
#include "windows.h"  
[module(name="MyLibrary")];  
  
[object, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]  
__interface ICustom {  
   HRESULT Custom([in] long l, [out, retval] long *pLong);  
};  
  
[dual, uuid("9E66A291-4365-11D2-A997-00C04FA37DDB")]   
__interface IDual {  
   HRESULT Dual([in] long l, [out, retval] long *pLong);  
};  
  
[object, uuid("9E66A293-4365-11D2-A997-00C04FA37DDB")]  
__interface ICustomDispatch : public IDispatch {  
   HRESULT Dispatch([in] long l, [out, retval] long *pLong);  
};  
  
[   coclass,  
   default(ICustomDispatch),   
   source(IDual),  
   uuid("9E66A294-4365-11D2-A997-00C04FA37DDB")  
]  
class CClass : public ICustom, public IDual, public ICustomDispatch {  
   HRESULT Custom(long l, long *pLong) { return(S_OK); }  
   HRESULT Dual(long l, long *pLong) { return(S_OK); }  
   HRESULT Dispatch(long l, long *pLong) { return(S_OK); }  
};  
  
int main() {  
#if 0 // Can't instantiate without implementations of IUnknown/IDispatch  
   CClass *pClass = new CClass;  
  
   long llong;  
  
   pClass->custom(1, &llong);  
   pClass->dual(1, &llong);  
   pClass->dispinterface(1, &llong);  
   pClass->dispatch(1, &llong);  
  
   delete pClass;  
#endif  
   return(0);  
}  
```  
  
 O [fonte](../Topic/source%20\(C++\).md) atributo também tem um exemplo de como usar **padrão**.  
  
## Requisitos  
  
### Contexto de atributo  
  
|||  
|-|-|  
|**Aplica\-se a**|**classe**, `struct`, membro de dados|  
|**Repetível**|Não|  
|**Atributos necessários**|**coclass** \(quando aplicada ao **classe** ou `struct`\)|  
|**Atributos inválidos**|Nenhum|  
  
 Para obter mais informações, consulte [contextos de atributo](../windows/attribute-contexts.md).  
  
## Consulte também  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [coclass](../windows/coclass.md)   
 [Attributes Samples](http://msdn.microsoft.com/pt-br/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)