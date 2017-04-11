---
title: Macros de mapa COM | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, COM map macros
ms.assetid: 0f33656d-321f-4996-90cc-9a7f21ab73c3
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 1c8e73fc4d6cab2e9052e74d68bddbb5796ebfa8
ms.lasthandoff: 03/31/2017

---
# <a name="com-map-macros"></a>Macros de mapa COM
Essas macros definem mapas de interface COM.  
  
|||  
|-|-|  
|[BEGIN_COM_MAP](#begin_com_map)|Marca o início das entradas do mapa de interface COM.|  
|[END_COM_MAP](#end_com_map)|Marca o fim das entradas do mapa de interface COM.|  

## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** atlcom.h  
   
##  <a name="begin_com_map"></a>BEGIN_COM_MAP  
 O mapa COM é o mecanismo que expõe interfaces em um objeto para um cliente por meio de `QueryInterface`.  
  
```
BEGIN_COM_MAP(x)
```  
  
### <a name="parameters"></a>Parâmetros  
 *x*  
 [in] O nome do objeto de classe que você está expondo interfaces no.  
  
### <a name="remarks"></a>Comentários  
 [CComObjectRootEx::InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) retorna apenas os ponteiros para as interfaces no mapa de COM. Iniciar o mapa de interface com o `BEGIN_COM_MAP` macro, adicione entradas para cada uma das suas interfaces com o [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) macro ou uma de suas variantes e conclua o mapa com o [END_COM_MAP](#end_com_map) macro.  

  
### <a name="example"></a>Exemplo  
 Da ATL [PAGER](../../visual-cpp-samples.md) exemplo:  
  
 [!code-cpp[NVC_ATL_COM N º 1](../../atl/codesnippet/cpp/com-map-macros_1.h)]  
  

  
##  <a name="end_com_map"></a>END_COM_MAP  
 Finaliza a definição de seu mapa de interface COM.  
  
```
END_COM_MAP()
```  
  
## <a name="see-also"></a>Consulte também  
 [Macros](../../atl/reference/atl-macros.md)   
 [Funções globais de mapa COM](../../atl/reference/com-map-global-functions.md)
