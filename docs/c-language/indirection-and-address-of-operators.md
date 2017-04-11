---
title: "Operadores de indireção e endereço de | Microsoft Docs"
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
- address-of operator (&)
- '* operator'
- operators [C++], address-of
- ampersand operator (&)
- '* operator, indirection operator'
- addresses [C++], indirection
- addresses [C++]
- indirection operator
- '& operator, address-of operator'
- null pointers [C++]
- '* operator, address-of operator'
- operators [C++], indirection
ms.assetid: 10d62b00-12ba-4ea9-a2d5-09ac29ca2232
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
ms.openlocfilehash: 5836bc6b7eb175f5f33046a4b45fd12f63f62979
ms.lasthandoff: 02/25/2017

---
# <a name="indirection-and-address-of-operators"></a>Operadores de indireção e endereço de
O operador de indireção (**\***) acessa um valor indiretamente, por meio de um ponteiro. O operando deve ser um valor de ponteiro. O resultado da operação é o valor resolvido pelo operando; isto é, o valor no endereço para o qual o operando aponta. O tipo do resultado é o tipo endereçado pelo operando.  
  
 Se o operando apontar para uma função, o resultado será um designador de função. Se ele apontar para um local de armazenamento, o resultado será um valor l que designa o local de armazenamento.  
  
 Se o valor do ponteiro for inválido, o resultado será indefinido. A lista a seguir inclui algumas das condições mais comuns que invalidam um valor de ponteiro.  
  
-   O ponteiro é um ponteiro nulo.  
  
-   O ponteiro especifica o endereço de um item local que não está visível no momento da referência.  
  
-   O ponteiro especifica um endereço que está alinhado de forma inadequada para o tipo do objeto apontado.  
  
-   O ponteiro especifica um endereço não usado pelo programa em execução.  
  
 O operador endereço de (**&**) fornece o endereço de seu operando. O operando do operador endereço de pode ser um designador de função ou um valor l que designa um objeto que não é um campo de bits e não é declarado com o especificador de classe de armazenamento **register**.  
  
 O resultado da operação de endereço é um ponteiro para o operando. O tipo endereçado pelo ponteiro é o tipo do operando.  
  
 O operador address-of pode ser aplicado somente a variáveis com tipos fundamentais, de estrutura ou união que são declarados no nível de escopo do arquivo, ou a referências de matriz subscrita. Nessas expressões, uma expressão constante que não inclui o operador address-of pode ser adicionada ou subtraída da expressão de endereço.  
  
## <a name="examples"></a>Exemplos  
 Os exemplos a seguir usam estas declarações:  
  
```  
int *pa, x;  
int a[20];  
double d;  
```  
  
 Esta instrução usa o operador address-of:  
  
```  
pa = &a[5];  
```  
  
 O operador endereço de (**&**) usa o endereço do sexto elemento da matriz `a`. O resultado é armazenado na variável de ponteiro `pa`.  
  
```  
x = *pa;  
```  
  
 O operador de indireção (**\***) é usado neste exemplo para acessar o valor `int` no endereço armazenado em `pa`. O valor é atribuído à variável de inteiro `x`.  
  
```  
if( x == *&x )  
    printf( "True\n" );  
```  
  
 Este exemplo imprime a palavra `True`, demonstrando que o resultado da aplicação do operador de indireção ao endereço de `x` é o mesmo que `x`.  
  
```  
int roundup( void );     /* Function declaration */  
  
int  *proundup  = roundup;  
int  *pround  = &roundup;  
```  
  
 Uma vez que a função `roundup` é declarada, dois ponteiros para `roundup` são declarados e inicializados. O primeiro ponteiro, `proundup`, é inicializado usando apenas o nome da função, enquanto o segundo, `pround`, usa o operador address-of na inicialização. As inicializações são equivalentes.  
  
## <a name="see-also"></a>Consulte também  
 [Operador de indireção: *](../cpp/indirection-operator-star.md)   
 [Operador endereço de: &](../cpp/address-of-operator-amp.md)