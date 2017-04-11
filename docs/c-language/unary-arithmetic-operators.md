---
title: "Operadores aritméticos unários | Microsoft Docs"
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
- operators [C], unary
- tilde (~) one's complement operator
- bitwise-complement operator
- arithmetic operators [C++], unary
- + operator, unary operators
- unary operators
- exclamation points
- ~ operator, one's complement operator
- logical negation
- '! operator, unary arithmetic operators'
ms.assetid: 78c91415-d469-499e-9dfe-4435350fd333
caps.latest.revision: 6
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
ms.openlocfilehash: 8b9e541b34adf81bfdcc4212972749f6e2052360
ms.lasthandoff: 02/25/2017

---
# <a name="unary-arithmetic-operators"></a>Operadores aritméticos unários
Vários operadores do C – unário de adição, de negação aritmética, de complemento e de negação lógica – são discutidos na lista a seguir:  
  
|Operador|Descrição|  
|--------------|-----------------|  
|**+**|O operador unário de adição que precede uma expressão entre parênteses força o agrupamento das operações incluídas. É usado com expressões que envolvem mais de um operador binário associativo ou comutativo. O operando deve ser do tipo aritmético. O resultado é o valor do operando. Um operando de integral passa por uma promoção de integral. O tipo do resultado é o tipo do operando promovido.|  
|**–**|O operador de negação aritmética produz o negativo (complemento de dois) do respectivo operando. O operando deve ser um valor de integral ou flutuante. Este operador executa as conversões aritméticas comuns.|  
|`~`|O operador de complemento bit a bit (ou NOT bit a bit) produz o complemento bit a bit do respectivo operando. O operando deve ser do tipo integral. Este operador executa as conversões aritméticas comuns; o resultado tem o tipo do operando após a conversão.|  
|**!**|O operador de negação lógica (NOT lógico) produz o valor 0 se o operando é verdadeiro (diferente de zero) e o valor 1 se o operando é falso (0). O resultado tem o tipo `int`. O operando deve ser um valor de ponteiro, integral ou flutuante.|  
  
 Operações aritméticas unárias em ponteiros não são válidas.  
  
## <a name="examples"></a>Exemplos  
 Os exemplos a seguir ilustram os operadores aritméticos unários:  
  
```  
short x = 987;  
    x = -x;  
```  
  
 No exemplo acima, o novo valor de `x` é o negativo de 987, ou seja, –987.  
  
```  
unsigned short y = 0xAAAA;  
    y = ~y;  
```  
  
 Nesse exemplo, o novo valor atribuído a `y` é o complemento de um do valor sem sinal 0xAAAA, ou 0x5555.  
  
```  
if( !(x < y) )  
```  
  
 Se `x` é maior ou igual a `y`, o resultado da expressão é 1 (verdadeiro). Se `x` é menor que `y`, o resultado é 0 (falso).  
  
## <a name="see-also"></a>Consulte também  
 [Expressões com operadores unários](../cpp/expressions-with-unary-operators.md)