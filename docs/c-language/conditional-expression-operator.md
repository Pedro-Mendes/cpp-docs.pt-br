---
title: "Operador de expressão condicional | Microsoft Docs"
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
- conditional operators
- operators [C++], conditional
- expressions [C++], conditional
ms.assetid: c4f1a5ca-0844-44a7-a384-eca584d4e3dd
caps.latest.revision: 8
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
ms.openlocfilehash: 01018685d7f66cfd9eafaddfee24d67792152c85
ms.lasthandoff: 02/25/2017

---
# <a name="conditional-expression-operator"></a>Operador de expressão condicional
C tem um operador ternário: o operador de expressão condicional (**?:**).  
  
## <a name="syntax"></a>Sintaxe  
 *conditional-expression*:  
 *logical-OR-expression*  
  
 *logical-OR expression*  **?**  *expression*  **:**  *conditional-expression*  
  
 A *logical-OR-expression* deve ter um tipo integral, de flutuação ou ponteiro. Ela é avaliada em termos de sua equivalência a 0. Um ponto de sequência vem após a *logical-OR-expression*. A avaliação dos operandos acontece da seguinte maneira:  
  
-   Se a *logical-OR-expression* não for igual a 0, a *expression* será avaliada. O resultado da avaliação da expressão é determinado pela *expression* não terminal. (Isso significa que a *expression* será avaliada apenas se a *logical-OR-expression* for verdadeira.)  
  
-   Se a *logical-OR-expression* for igual a 0, a *conditional-expression* será avaliada. O resultado da expressão será o valor da *conditional-expression*. (Isso significa que a *conditional-expression* será avaliada apenas se a *logical-OR-expression* for falsa.)  
  
 Observe que apenas a *expression* ou a *conditional-expression* é avaliada, mas não ambas.  
  
 O tipo de resultado de uma operação condicional depende do tipo do operando da *expression* ou *conditional-expression*, da seguinte maneira:  
  
-   Se a *expression* ou *conditional-expression* tiver o tipo integral ou flutuante (seus tipos podem ser diferentes), o operador executa conversões aritméticas comuns. O tipo do resultado é o tipo dos operandos após conversão.  
  
-   Se a *expression* e a *conditional-expression* tiverem a mesma estrutura, união ou tipo de ponteiro, o tipo de resultado é a mesma estrutura, união ou tipo de ponteiro.  
  
-   Se ambos os operandos tiverem o tipo `void`, o resultado tem o tipo `void`.  
  
-   Se qualquer operando for um ponteiro para um objeto de qualquer tipo e o outro operando for um ponteiro para `void`, o ponteiro para o objeto será convertido em um ponteiro para `void` e o resultado será um ponteiro para `void`.  
  
-   Se a *expression* ou *conditional-expression* for um ponteiro e o outro operando for uma expressão constante com o valor 0, o tipo de resultado será o tipo de ponteiro.  
  
 Na comparação do tipo para ponteiros, qualquer qualificador de tipo (**const** ou `volatile`) no tipo para o qual o ponteiro aponta é insignificante, mas o tipo de resultado herda os qualificadores de ambos os componentes da condicional.  
  
## <a name="examples"></a>Exemplos  
 Os exemplos a seguir mostram o uso do operador condicional:  
  
```  
j = ( i < 0 ) ? ( -i ) : ( i );  
```  
  
 Este exemplo atribui o valor absoluto de `i` a `j`. Se `i` for menor que 0, `-i` é atribuído a `j`. Se `i` for maior ou igual a 0, `i` é atribuído a `j`.  
  
```  
void f1( void );  
void f2( void );  
int x;  
int y;  
    .  
    .  
    .  
( x == y ) ? ( f1() ) : ( f2() );  
```  
  
 Neste exemplo, duas funções, `f1` e `f2`, e duas variáveis, `x` e `y`, são declaradas. Posteriormente no programa, se as duas variáveis tiverem o mesmo valor, a função `f1` será chamada. Caso contrário, `f2` é chamada.  
  
## <a name="see-also"></a>Consulte também  
 [Operador condicional: ? :](../cpp/conditional-operator-q.md)