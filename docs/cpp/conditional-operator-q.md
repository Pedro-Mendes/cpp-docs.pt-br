---
title: "Operador condicional: ? : | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "?:"
  - "?"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Operador ? :"
  - "Operadores condicionais"
ms.assetid: 88643ee8-7100-4f86-880a-705ec22b6271
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Operador condicional: ? :
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Sintaxe  
  
```  
  
expression ? expression : expression  
```  
  
## Comentários  
 O operador condicional \(**?:**\) é um operador ternário \(utiliza três operandos\).  O operador condicional funciona desta forma:  
  
-   O primeiro operando é convertido implicitamente em `bool`.  É avaliado e todos os efeitos colaterais são concluídos antes de continuar.  
  
-   Se o primeiro operando é avaliado como **true** \(1\), o segundo operando é avaliado.  
  
-   Se o primeiro operando é avaliado como **false** \(0\), o terceiro operando é avaliado.  
  
 O resultado do operador condicional é o resultado de qualquer operando avaliado — o segundo ou o terceiro.  Somente um dos dois operandos dos dois mais recentes é avaliado em uma expressão condicional.  
  
 As expressões condicionais têm a capacidade da direita para a esquerda.  O primeiro operando deve ser do tipo integral ou ponteiro.  As seguintes regras se aplicam para o segundo e terceiro operandos:  
  
-   Se ambos os operandos forem do mesmo tipo, o resultado será desse tipo.  
  
-   Se ambos os operandos forem de tipos aritméticos ou de enumeração, conversões aritméticas usuais \(abordados [conversões aritméticas](../misc/arithmetic-conversions.md)\) são executadas para convertê\-los em um tipo comum.  
  
-   Se ambos os operandos forem de tipos de ponteiro ou se uma é um tipo de ponteiro e a outra é uma expressão constante que é avaliada como 0, as conversões de ponteiro são executadas para convertê\-los em um tipo comum.  
  
-   Se ambos os operandos forem de tipos de referência, conversões de referência são executadas para convertê\-los em um tipo comum.  
  
-   Se ambos os operandos forem do tipo void, o tipo comum será do tipo nulo.  
  
-   Se ambos os operandos forem do mesmo tipo definido pelo usuário, o tipo comum é desse tipo.  
  
-   Se os operandos têm tipos diferentes e pelo menos um dos operandos tem tipo definido pelo usuário, em seguida, as regras de idioma são usadas para determinar o tipo comum.  \(Consulte o aviso abaixo\).  
  
 Todas as combinações do segundo e do terceiro operando que não estiverem na lista anterior são ilegais.  O tipo de resultado é o tipo comum, e é um l\-value se o segundo e o terceiro operandos forem do mesmo tipo e ambos forem l\-values.  
  
> [!WARNING]
>  Se os tipos do segundo e terceiro operandos não forem idênticos, as regras de conversão de tipo complexo, conforme especificado no padrão do C\+\+, são chamadas.  Essas conversões podem resultar em comportamento inesperado incluindo construção e destruição de objetos temporários.  Por esse motivo, é altamente recomendável a um \(1\) evitar o uso de tipos definidos pelo usuário como operandos com o operador condicional ou \(2\) se você usar tipos definidos pelo usuário e converter explicitamente cada operando em um tipo comum.  
  
## Exemplo  
  
```  
// expre_Expressions_with_the_Conditional_Operator.cpp  
// compile with: /EHsc  
// Demonstrate conditional operator  
#include <iostream>  
using namespace std;  
int main() {  
   int i = 1, j = 2;  
   cout << ( i > j ? i : j ) << " is greater." << endl;  
}  
```  
  
## Consulte também  
 [Operadores C\+\+](../misc/cpp-operators.md)   
 [Operadores, precedência e associatividade C\+\+](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Operador de expressão condicional](../c-language/conditional-expression-operator.md)