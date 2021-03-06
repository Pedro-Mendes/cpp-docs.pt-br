---
title: Compilador (nível 1) de aviso C4319 | Microsoft Docs
ms.custom: ''
ms.date: 1/18/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4319
dev_langs:
- C++
helpviewer_keywords:
- C4319
ms.assetid: 1fac8048-9bd6-4552-a21c-192c67772bb9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c1b5fe896ae7d8f43708b60ee4dda486ef08f428
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33284739"
---
# <a name="compiler-warning-level-1-c4319"></a>Compilador C4319 de aviso (nível 1)

> ' ~': zero estendendo '*type1*'para'*type2*' de tamanho maior

O resultado da **~** operador (complemento bit a bit) é não assinado e, em seguida, estendido de zero quando ele é convertido em um tipo maior.

## <a name="example"></a>Exemplo

No exemplo a seguir, `~(a - 1)` é avaliada como uma expressão longo não assinada de 32 bits e, em seguida, convertida em 64 bits pela extensão de zero. Isso pode levar a resultados de operação inesperado.

```cpp
// C4319.cpp
// compile with: cl /W4 C4319.cpp
int main() {
   unsigned long a = 0;
   unsigned long long q = 42;
   q = q & ~(a - 1);    // C4319 expected
}
```
