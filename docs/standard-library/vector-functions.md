---
title: "Funções &lt;vector&gt; | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6cdcf043-eef6-4330-83f0-4596fb9f968a
caps.latest.revision: 10
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: bb62c0c4e5b2965438539b17ec5a2c465e647ed7
ms.lasthandoff: 02/25/2017

---
# <a name="ltvectorgt-functions"></a>Funções &lt;vetor&gt;

  
##  <a name="a-nameswapa--swap"></a><a name="swap"></a>  swap  
 Troca os elementos de dois vetores.  
  
```  
template <class Type, class Allocator>  
void swap(vector<Type, Allocator>& left, vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Parâmetros  
 ` right`  
 O vetor que fornece os elementos a serem trocados ou um vetor cujos elementos deverão ser trocados com aqueles do vetor ` left`.  
  
 ` left`  
 Um vetor cujos elementos deverão ser trocados por aqueles do vetor ` right`.  
  
### <a name="remarks"></a>Comentários  
 A função de modelo é um algoritmo especializado no vetor de classe de contêiner para executar a função membro ` left.` [vector::swap](../standard-library/vector-class.md) *( right*). Essas são instâncias de ordenação parcial de modelos de função pelo compilador. Quando as funções de modelo são sobrecarregadas de forma que a correspondência do modelo com a chamada de função não é exclusiva, o compilador seleciona a versão mais especializada do modelo de função. A versão geral da função de modelo, **template** \< **class T**> **void swap**( **T&**, **T&**), no algoritmo de classe funciona por atribuição e é uma operação lenta. A versão especializada em cada contêiner é muito mais rápida, uma vez que ela pode funcionar com a representação interna da classe de contêiner.  
  
### <a name="example"></a>Exemplo  
  Consulte o exemplo de código da função membro [vector::swap](../standard-library/vector-class.md) para obter um exemplo que usa a versão de modelo do `swap`.  
  
## <a name="see-also"></a>Consulte também  
 [\<vector>](../standard-library/vector.md)

