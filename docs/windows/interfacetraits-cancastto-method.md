---
title: "Método Interfacetraits: | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::InterfaceTraits::CanCastTo
dev_langs: C++
helpviewer_keywords: CanCastTo method
ms.assetid: 275847cb-69ea-42bf-910f-05ba6ef8b48d
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3d8dfe6c1873d9cf897494eb6157c2be3baeb435
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="interfacetraitscancastto-method"></a>Método InterfaceTraits::CanCastTo
Oferece suporte à infraestrutura WRL e não se destina a ser usado diretamente no seu código.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
template<typename T>  
static __forceinline bool CanCastTo(  
   _In_ T* ptr,  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `ptr`  
 O nome de um ponteiro para um tipo.  
  
 `riid`  
 A ID de interface de `Base`.  
  
 `ppv`  
 Se essa operação for bem-sucedida, `ppv` aponta para a interface especificada pelo `Base`. Caso contrário, `ppv` é definido como `nullptr`.  
  
## <a name="return-value"></a>Valor de retorno  
 `true`Se essa operação for bem-sucedida e `ptr` é convertido para um ponteiro para `Base`; caso contrário, `false` .  
  
## <a name="remarks"></a>Comentários  
 Indica se o ponteiro especificado pode ser convertido em um ponteiro para `Base`.  
  
 Para obter mais informações sobre `Base`, consulte a seção de Typedefs públicos em [estrutura InterfaceTraits](../windows/interfacetraits-structure.md).  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Consulte também  
 [Estrutura InterfaceTraits](../windows/interfacetraits-structure.md)   
 [Namespace Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)