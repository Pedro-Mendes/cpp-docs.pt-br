---
title: Erro do compilador C2171 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2171
dev_langs:
- C++
helpviewer_keywords:
- C2171
ms.assetid: a80343b5-ab3f-4413-b6f1-3ce9d7e519e5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a5c2e3c87db5a82cc3606ebca049a35adec5fa61
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029241"
---
# <a name="compiler-error-c2171"></a>Erro do compilador C2171

'operator': inválido em operandos do tipo 'type'

Um operador unário é usado com um tipo de operando inválido.

## <a name="example"></a>Exemplo

O exemplo a seguir gera C2171.

```
// C2171.cpp
int main() {
   double d, d1;
   d = ~d1;   // C2171

   // OK
   int d2 = 0, d3 = 0;
   d2 = ~d3;
}
```

## <a name="example"></a>Exemplo

O exemplo a seguir gera C2171.

```
// C2171_b.cpp
// compile with: /c
class A {
public:
   A() { STF( &A::D ); }

   void D() {}
   void DTF() {
      (*TF)();   // C2171
      (this->*TF)();   // OK
   }

   void STF(void (A::*fnc)()) {
      TF = fnc;
   }

private:
   void (A::*TF)();
};
```