---
title: cache_chunklist Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::cache_chunklist
- stdext.cache_chunklist
- stdext::cache_chunklist
- cache_chunklist
dev_langs:
- C++
helpviewer_keywords:
- cache_chunklist class
ms.assetid: af19eccc-4ae7-4a34-bbb2-81e397424cb9
caps.latest.revision: 17
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
ms.openlocfilehash: 6e25dd5424ad471bade7289db4ea0684fab1f689
ms.lasthandoff: 02/25/2017

---
# <a name="cachechunklist-class"></a>Classe cache_chunklist
Define um [alocador de blocos](../standard-library/allocators-header.md) que aloca e desaloca os blocos de memória de um único tamanho.  
  
## <a name="syntax"></a>Sintaxe  
  
```
template <std::size_t Sz, std::size_t Nelts = 20>  
class cache_chunklist
```  
  
#### <a name="parameters"></a>Parâmetros  
  
|Parâmetro|Descrição|  
|---------------|-----------------|  
|`Sz`|O número de elementos na matriz a serem alocados.|  
  
## <a name="remarks"></a>Comentários  
 Essa classe de modelo usa `operator new` para alocar partes de memória bruta, subalocando blocos para alocar armazenamento para um bloco de memória quando necessário; ela armazena os blocos de memória desalocados em uma lista livre separada para cada parte e usar `operator delete` para desalocar uma parte quando nenhum dos seus blocos de memória está em uso.  
  
 Cada bloco de memória contém `Sz` bytes de memória utilizável e um ponteiro para a parte à qual pertence. Cada parte contém `Nelts` blocos de memória, três ponteiros, int e os dados que `operator new` e `operator delete` exigem.  
  
### <a name="constructors"></a>Construtores  
  
|||  
|-|-|  
|[cache_chunklist](#cache_chunklist__cache_chunklist)|Constrói um objeto do tipo `cache_chunklist`.|  
  
### <a name="member-functions"></a>Funções membro  
  
|||  
|-|-|  
|[allocate](#cache_chunklist__allocate)|Aloca um bloco de memória.|  
|[deallocate](#cache_chunklist__deallocate)|Libera um número especificado de objetos do armazenamento começando em uma posição especificada.|  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** \<allocators>  
  
 **Namespace:** stdext  
  
##  <a name="cache_chunklist__allocate"></a>  cache_chunklist::allocate  
 Aloca um bloco de memória.  
  
```
void *allocate(std::size_t count);
```  
  
### <a name="parameters"></a>Parâmetros  
  
|Parâmetro|Descrição|  
|---------------|-----------------|  
|`count`|O número de elementos na matriz a serem alocados.|  
  
### <a name="return-value"></a>Valor de retorno  
 Um ponteiro para o objeto alocado.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="cache_chunklist__cache_chunklist"></a>  cache_chunklist::cache_chunklist  
 Constrói um objeto do tipo `cache_chunklist`.  
  
```
cache_chunklist();
```  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="cache_chunklist__deallocate"></a>  cache_chunklist::deallocate  
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
  
## <a name="see-also"></a>Consulte também  
 [\<allocators>](../standard-library/allocators-header.md)



