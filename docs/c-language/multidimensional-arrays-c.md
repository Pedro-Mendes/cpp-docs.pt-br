---
title: Matrizes multidimensionais (C) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- arrays [C], multidimensional
- multidimensional arrays
- subscript expressions
ms.assetid: 4ba5c360-1f17-4575-b370-45f62e1f2bc2
caps.latest.revision: 7
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
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 51180f7ce6726473fa0172714b4186fff3d60f28
ms.lasthandoff: 02/25/2017

---
# <a name="multidimensional-arrays-c"></a>Matrizes multidimensionais (C)
Uma expressão subscrita também pode ter vários subscritos, como segue:  
  
```  
  
expression1  
[  
expression2  
] [  
expression3  
]...  
```  
  
 As expressões subscritas são associadas da esquerda para a direita. A expressão subscrita mais à esquerda, *expression1***[***expression2***]**, é avaliada primeiro. O endereço resultante da adição de *expression1* e *expression2* forma uma expressão do ponteiro; *expression3* é adicionada a essa expressão de ponteiro para formar uma nova expressão de ponteiro e assim por diante até que a última expressão subscrita seja adicionada. O operador de indireção (**\***) é aplicado depois que a última expressão subscrita é avaliada, a menos que o valor do ponteiro final trate de um tipo de matriz (veja os exemplos abaixo).  
  
 As expressões com vários subscritos referem-se aos elementos de "matrizes multidimensionais". Uma matriz multidimensional é uma matriz cujos elementos são matrizes. Por exemplo, o primeiro elemento de uma matriz tridimensional é uma matriz com duas dimensões.  
  
## <a name="examples"></a>Exemplos  
 Para os exemplos a seguir, uma matriz chamada `prop` é declarada com três elementos, cada um deles sendo uma matriz 4 por 6 de valores `int`.  
  
```  
int prop[3][4][6];  
int i, *ip, (*ipp)[6];  
```  
  
 Uma referência à matriz `prop` é semelhante a esta:  
  
```  
i = prop[0][0][1];  
```  
  
 O exemplo acima mostra como referenciar o segundo elemento individual `int` de `prop`. As matrizes são armazenadas por linha, de modo que o último subscrito varie mais rapidamente; a expressão `prop[0][0][2]` se refere ao próximo (terceiro) elemento da matriz, e assim por diante.  
  
```  
i = prop[2][1][3];  
```  
  
 Essa instrução é uma referência mais complexa a um elemento individual de `prop`. A expressão é avaliada como segue:  
  
1.  O primeiro subscrito, `2`, é multiplicado pelo tamanho de uma matriz `int` 4 por 6 e é adicionado ao valor do ponteiro `prop`. O resultado aponta para a terceira matriz 4 por 6 de `prop`.  
  
2.  O segundo subscrito, `1`, é multiplicado pelo tamanho da matriz `int` de 6 elementos e é adicionado ao endereço representado por `prop[2]`.  
  
3.  Cada elemento da matriz de 6 elementos é um valor `int`, então, o subscrito final, `3`, é multiplicado pelo tamanho de `int` antes de ser adicionado a `prop[2][1]`. O ponteiro resultante é pertinente ao quarto elemento da matriz de 6 elementos.  
  
4.  O operador de indireção é aplicado ao valor do ponteiro. O resultado é o elemento `int` nesse endereço.  
  
 Os dois próximos exemplos mostra casos em que o operador de indireção não é aplicado.  
  
```  
ip = prop[2][1];  
  
ipp = prop[2];  
```  
  
 Na primeira dessas instruções, a expressão `prop[2][1]` é uma referência válida para a matriz tridimensional `prop`; refere-se a uma matriz de 6 elementos (declarada acima). Como o valor do ponteiro é pertinente a uma matriz, o operador de indireção não é aplicado.  
  
 Da mesma forma, o resultado da expressão `prop[2]` na segunda instrução `ipp = prop[2];` é um valor de ponteiro pertinente a uma matriz bidimensional.  
  
## <a name="see-also"></a>Consulte também  
 [Operador subscript:](../cpp/subscript-operator.md)