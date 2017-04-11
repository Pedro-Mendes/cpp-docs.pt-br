---
title: Classe sync_none | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- stdext.sync_none
- sync_none
- allocators/stdext::sync_none
- stdext::sync_none
dev_langs:
- C++
helpviewer_keywords:
- sync_none class
ms.assetid: f7473cee-14f3-4fe1-88bc-68cd085e59e1
caps.latest.revision: 21
author: corob-msft
ms.author: corob
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 74947a6eb7c493ac019aed90aaf89e3436b4ceb1
ms.lasthandoff: 02/25/2017

---
# <a name="syncnone-class"></a>Classe sync_none
Descreve um [filtro de sincronização](../standard-library/allocators-header.md) que não fornece nenhuma sincronização.  
  
## <a name="syntax"></a>Sintaxe  
  
```
template <class Cache>  
class sync_none
```  
  
#### <a name="parameters"></a>Parâmetros  
  
|Parâmetro|Descrição|  
|---------------|-----------------|  
|`Cache`|O tipo de cache associado ao filtro de sincronização. Pode ser [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md) ou [cache_suballoc](../standard-library/cache-suballoc-class.md).|  
  
### <a name="member-functions"></a>Funções membro  
  
|||  
|-|-|  
|[allocate](#sync_none__allocate)|Aloca um bloco de memória.|  
|[deallocate](#sync_none__deallocate)|Libera um número especificado de objetos do armazenamento começando em uma posição especificada.|  
|[equals](#sync_none__equals)|Compara a igualdade de dois caches.|  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** \<allocators>  
  
 **Namespace:** stdext  
  
##  <a name="sync_none__allocate"></a>  sync_none::allocate  
 Aloca um bloco de memória.  
  
```
void *allocate(std::size_t count);
```  
  
### <a name="parameters"></a>Parâmetros  
  
|Parâmetro|Descrição|  
|---------------|-----------------|  
|`count`|O número de elementos na matriz a serem alocados.|  
  
### <a name="remarks"></a>Comentários  
 A função membro retorna `cache.allocate(count)`, em que `cache` é o objeto de cache.  
  
##  <a name="sync_none__deallocate"></a>  sync_none::deallocate  
 Libera um número especificado de objetos do armazenamento começando em uma posição especificada.  
  
```
void deallocate(void* ptr, std::size_t count);
```  
  
### <a name="parameters"></a>Parâmetros  
  
|Parâmetro|Descrição|  
|---------------|-----------------|  
|`ptr`|Um ponteiro para o primeiro objeto a ser desalocado do armazenamento.|  
|`count`|O número de objetos a serem desalocados do armazenamento.|  
  
### <a name="remarks"></a>Comentários  
 A função membro chama `cache.deallocate(ptr, count)`, em que `cache` representa o objeto de cache.  
  
##  <a name="sync_none__equals"></a>  sync_none::equals  
 Compara a igualdade de dois caches.  
  
```
bool equals(const sync<Cache>& Other) const;
```  
  
### <a name="parameters"></a>Parâmetros  
  
|Parâmetro|Descrição|  
|---------------|-----------------|  
|`Cache`|O objeto de cache do filtro de sincronização.|  
|`Other`|O objeto de cache a ser comparado quanto à igualdade.|  
  
### <a name="return-value"></a>Valor de retorno  
 A função membro sempre retorna `true`.  
  
### <a name="remarks"></a>Comentários  
  
## <a name="see-also"></a>Consulte também  
 [\<allocators>](../standard-library/allocators-header.md)



