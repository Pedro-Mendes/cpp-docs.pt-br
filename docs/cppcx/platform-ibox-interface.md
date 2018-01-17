---
title: 'Interface Platform:: ibox | Microsoft Docs'
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- VCCORLIB/Namespace not found::Platform
- VCCORLIB/Namespace not found::Platform::Value
dev_langs: C++
ms.assetid: 774df45d-f8a7-45a3-ae24-eecc3c681040
caps.latest.revision: "5"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8a86eca75bb5470585ba68fe3b7fcdb55c861434
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="platformibox-interface"></a>Interface Platform::IBox
A interface [Platform::IBox](../cppcx/platform-ibox-interface.md) é o nome em C++ para a interface `Windows::Foundation::IReference` .  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
template <typename T>  
interface class IBox  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `T`  
 O tipo do valor demarcado.  
  
### <a name="remarks"></a>Comentários  
 A interface `IBox<T>` é utilizada principalmente para representar tipos internos de valor nulo, como descrito em [Classes e estruturas de valor (C++/CX)](../cppcx/value-classes-and-structs-c-cx.md). A interface também é usada para demarcar tipos de valores transmitidos para métodos de C++ que obtêm parâmetros do tipo `Object^`. Você pode declarar explicitamente um parâmetro de entrada como `IBox<SomeValueType>`. Para obter um exemplo, consulte [Boxing](../cppcx/boxing-c-cx.md).  
  
### <a name="requirements"></a>Requisitos  
  
### <a name="members"></a>Membros  
 A interface `Platform::IBox` herda da interface [Platform::IValueType](../cppcx/platform-ivaluetype-interface.md) . `IBox` tem estes membros:  
  
 **Propriedades**  
  
|Método|Descrição|  
|------------|-----------------|  
|[Valor](#value)|Retorna o valor não demarcado que foi armazenado anteriormente nessa instância de `IBox` .|  

## <a name="value"></a>Propriedade ibox:: Value
Retorna o valor que foi originalmente armazenado neste objeto.  
  
### <a name="syntax"></a>Sintaxe  
  
```cpp  
property T Value {T get();}  
```  
  
### <a name="parameters"></a>Parâmetros  
 `T`  
 O tipo do valor demarcado.  
  
### <a name="property-valuereturn-value"></a>Valor da propriedade/valor de retorno  
 Retorna o valor que foi originalmente armazenado neste objeto.  
  
### <a name="remarks"></a>Comentários  
 Para obter um exemplo, consulte [Boxing](../cppcx/boxing-c-cx.md).  
  
  
## <a name="see-also"></a>Consulte também  
 [Namespace de plataforma](../cppcx/platform-namespace-c-cx.md)