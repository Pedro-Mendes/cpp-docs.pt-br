---
title: Erro do compilador C2902 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2902
dev_langs:
- C++
helpviewer_keywords:
- C2902
ms.assetid: 89d78d0e-78e5-4c2c-a0f9-a60110e9395e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5997e9a038e4310ada42cdc371bc8f2c058a440a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46017425"
---
# <a name="compiler-error-c2902"></a>Erro do compilador C2902

'token': seguinte token inesperado 'template', identificador esperado

O token após a palavra-chave `template` não era um identificador.

O exemplo a seguir gera C2902:

```
// C2902.cpp
// compile with: /c
namespace N {
   template<class T> class X {};
   class Y {};
}
void g() {
   N::template + 1;   // C2902
}

void f() {
   N::template X<int> x1;   // OK
}
```

C2902 também podem ocorrer ao usar genéricos:

```
// C2902b.cpp
// compile with: /clr /c
namespace N {
   generic<class T> ref class GC {};
}

void f() {
   N::generic + 1;   // C2902
   N::generic GC<int>^ x;
}
```