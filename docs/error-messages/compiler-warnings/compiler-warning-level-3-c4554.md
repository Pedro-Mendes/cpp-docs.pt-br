---
title: Compilador aviso (nível 3) C4554 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4554
dev_langs:
- C++
helpviewer_keywords:
- C4554
ms.assetid: 55bb68f0-2e80-4330-8921-51083c4f8d53
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b6349cada597b2089f03169071345a68179b24e3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114430"
---
# <a name="compiler-warning-level-3-c4554"></a>Compilador aviso (nível 3) C4554

'operator': Verifique a precedência do operador para possível erro; Use parênteses para esclarecer a precedência

O exemplo a seguir gera C4554:

```
// C4554.cpp
// compile with: /W3 /WX
int main() {
   int a = 0, b = 0, c = 0;
   a = a << b + c;   // C4554
   // probably intended (a << b) + c,
   // but will get a << (b + c)
}
```