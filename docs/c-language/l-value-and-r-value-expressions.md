---
title: Expressões L-Value e R-Value | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- L-values
- member-selection expressions
- R-value expressions
- subscript expressions
ms.assetid: b790303e-ec6f-4d0d-bc55-df42da267172
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 133a88494cfb318b39c5b16191ee8463037f1fac
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055250"
---
# <a name="l-value-and-r-value-expressions"></a>Expressões L-Value e R-Value

Expressões que fazem referência a locais de memória são chamadas de expressões “l-value”. Um l-value representa um valor de “localizador” da região de armazenamento ou um valor “à esquerda”, que indica que pode aparecer à esquerda do sinal de igual (**=**). Os l-values frequentemente são identificadores.

Expressões que fazem referência aos locais modificáveis são chamadas “l-values modificáveis”. Um l-value modificável não pode ter um tipo de matriz, um tipo incompleto ou um tipo com o atributo **const**. Para que as estruturas e uniões sejam l-values modificáveis, elas não devem ter membros com o atributo **const**. O nome do identificador denota um local de armazenamento, enquanto o valor da variável é o valor armazenado nesse local.

Um identificador é um l-value modificável se ele fizer referência a um local de memória e se seu tipo for aritmético, de estrutura, de união ou ponteiro. Por exemplo, se `ptr` for um ponteiro para uma região de armazenamento, então `*ptr` é um l-value modificável que designa a região de armazenamento para a qual `ptr` aponta.

Qualquer uma das seguintes expressões de C podem ser expressões l-value:

- Um identificador do tipo integral, flutuante, ponteiro, de estrutura ou de união

- Uma expressão subscrita (**[]**) que não seja avaliada como uma matriz

- Uma expressão de seleção de membros (**->** ou **.**)

- Uma expressão unary-indirection (<strong>\*</strong>) que não faz referência a uma matriz

- Uma expressão l-value entre parênteses

- Um objeto **const** (um valor l-value não modificável)

O termo “r-value” é usado às vezes para descrever o valor de uma expressão e para diferenciá-lo de um l-value. Todos os l-values são r-values mas nem todos r-values são l-values.

**Seção específica da Microsoft**

O Microsoft C inclui uma extensão do padrão ANSI C que permite que as conversões de l- values sejam usadas como l-values, desde que o tamanho do objeto não seja alongado na conversão. (Consulte [Conversões Type-Cast](../c-language/type-cast-conversions.md) para obter mais informações.) O exemplo a seguir ilustra esse recurso:

```
char *p ;
short  i;
long l;

(long *) p = &l ;       /* Legal cast   */
(long) i = l ;          /* Illegal cast */
```

O padrão do Microsoft C é que as extensões da Microsoft sejam habilitadas. Use a opção de compilador /Za para desativar essas extensões.

**Fim da seção específica da Microsoft**

## <a name="see-also"></a>Consulte também

[Operandos e expressões](../c-language/operands-and-expressions.md)