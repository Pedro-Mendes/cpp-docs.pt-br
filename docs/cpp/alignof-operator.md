---
title: operador alignof | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- alignas_cpp
- __alignof_cpp
- alignof_cpp
dev_langs:
- C++
helpviewer_keywords:
- alignas [C++]
- alignment of structures
- __alignof keyword [C++]
- alignof [C++]
- types [C++], alignment requirements
ms.assetid: acb1eed7-6398-40bd-b0c5-684ceb64afbc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ffea0fdf40f7ef794563849f97b0b68631b9734e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099758"
---
# <a name="alignof-operator"></a>Operador __alignof

C++11 introduz o **alignof** operador que retorna o alinhamento, em bytes, do tipo especificado. Para fins de portabilidade máxima, você deve usar o operador alignof em vez do operador de alignof específico da Microsoft.

**Seção específica da Microsoft**

Retorna um valor do tipo `size_t` que é o requisito de alinhamento do tipo.

## <a name="syntax"></a>Sintaxe

```cpp
  __alignof( type )
```

## <a name="remarks"></a>Comentários

Por exemplo:

|Expressão|Valor|
|----------------|-----------|
|**__alignof( char )**|1|
|**__alignof( short )**|2|
|**__alignof( int )**|4|
|**__alignof( \__int64 )**|8|
|**__alignof( float )**|4|
|**alignof (double)**|8|
|**__alignof( char\* )**|4|

O **alignof** valor é igual ao valor de `sizeof` para tipos básicos. Considere, no entanto, este exemplo:

```cpp
typedef struct { int a; double b; } S;
// __alignof(S) == 8
```

Nesse caso, o **alignof** valor é o requisito de alinhamento do maior elemento na estrutura.

De maneira semelhante, para

```cpp
typedef __declspec(align(32)) struct { int a; } S;
```

`__alignof(S)` é igual a `32`.

Um uso para **alignof** seria como um parâmetro para uma das suas próprias rotinas de alocação de memória. Por exemplo, dada a seguinte estrutura definida `S`, você poderia chamar uma rotina de alocação de memória de nome `aligned_malloc` para alocar memória em um limite de alinhamento específico.

```cpp
typedef __declspec(align(32)) struct { int a; double b; } S;
int n = 50; // array size
S* p = (S*)aligned_malloc(n * sizeof(S), __alignof(S));
```

Para obter mais informações sobre como modificar o alinhamento, consulte:

- [pack](../preprocessor/pack.md)

- [align](../cpp/align-cpp.md)

- [__unaligned](../cpp/unaligned.md)

- [/Zp (alinhamento de membro do struct)](../build/reference/zp-struct-member-alignment.md)

- [Exemplos de alinhamento da estrutura](../build/examples-of-structure-alignment.md) (específico para x64)

Para obter mais informações sobre as diferenças no alinhamento no código para x86 e x64, consulte:

- [conflitos com o compilador x86](../build/conflicts-with-the-x86-compiler.md)

**Fim da seção específica da Microsoft**

## <a name="see-also"></a>Consulte também

[Expressões com operadores unários](../cpp/expressions-with-unary-operators.md)<br/>
[Palavras-chave](../cpp/keywords-cpp.md)