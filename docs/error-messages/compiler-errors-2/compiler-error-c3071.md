---
title: Erro do compilador C3071 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3071
dev_langs:
- C++
helpviewer_keywords:
- C3071
ms.assetid: 69879e66-a60e-4058-9bbd-d5c5e2d8ee37
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5f004de3ed133ea77d543014ae1adcdc4e1eddef
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077796"
---
# <a name="compiler-error-c3071"></a>Erro do compilador C3071

o operador 'operator' só pode ser aplicado a uma instância de uma classe ref ou um tipo de valor

Um operador CLR não pode ser usado em um tipo nativo. O operador pode ser usado em uma classe ref ou uma struct de referência (um tipo de valor), mas não um tipo nativo, como int ou um alias para um tipo nativo como System::Int32. Esses tipos não podem ser convertidos de código C++ de forma que se refere à variável nativa, portanto, o operador não pode ser usado.

Para obter mais informações, consulte [operador de referência de acompanhamento](../../windows/tracking-reference-operator-cpp-component-extensions.md).

## <a name="example"></a>Exemplo

O exemplo a seguir gera C3071.

```
// C3071.cpp
// compile with: /clr
class N {};
ref struct R {};

int main() {
   N n;
   %n;   // C3071

   R r;
   R ^ r2 = %r;   // OK
}
```