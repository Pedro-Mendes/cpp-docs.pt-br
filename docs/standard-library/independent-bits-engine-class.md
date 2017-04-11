---
title: Classe independent_bits_engine | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- independent_bits_engine
- std::independent_bits_engine
- random/std::independent_bits_engine
dev_langs:
- C++
helpviewer_keywords:
- independent_bits_engine class
ms.assetid: 889e9a82-f457-49a7-9d2e-26e0fc3cd907
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
ms.sourcegitcommit: 28baed4badda4f2c1d7e5b20235fe8d40c2a7195
ms.openlocfilehash: ca810e4918a31ebfbe6217de0eb3cc2f786188ac
ms.lasthandoff: 02/25/2017

---
# <a name="independentbitsengine-class"></a>Classe independent_bits_engine
Gera uma sequência aleatória de números com um número especificado de bits, recompactando bits de valores retornados pelo mecanismo básico.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
template <class Engine, size_t W, class UIntType>  
class independent_bits_engine;  
```  
  
### <a name="parameters"></a>Parâmetros  
 `Engine`  
 O tipo de mecanismo de base.  
  
 `W`  
 **Tamanho da palavra**. Tamanho, em bits, de cada número gerado. **Pré-condição**: `0 < W ≤ numeric_limits<UIntType>::digits`  
  
 `UIntType`  
 O tipo de resultado inteiro sem sinal. Para encontrar os tipos possíveis, consulte [\<random>](../standard-library/random.md).  
  
## <a name="members"></a>Membros  
  
||||  
|-|-|-|  
|`independent_bits_engine::independent_bits_engine`|`independent_bits_engine::base`|`independent_bits_engine::discard`|  
|`independent_bits_engine::operator()`|`independent_bits_engine::base_type`|`independent_bits_engine::seed`|  
  
 Para obter mais informações sobre membros do mecanismo, consulte [\<random>](../standard-library/random.md).  
  
## <a name="remarks"></a>Comentários  
 Essa classe de modelo descreve um *adaptador de mecanismo* que produz valores recompactando bits dos valores retornados pelo mecanismo básico, resultando em valores de `W` bits.  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** \<random>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Consulte também  
 [\<random>](../standard-library/random.md)

