---
title: Erro do compilador C2990 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2990
dev_langs:
- C++
helpviewer_keywords:
- C2990
ms.assetid: 674e9f6a-6743-4af0-a7ed-cbe11103a2f8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c0afceb82a58ee5c0a21e39fcaf4ba0a9ee9f2c4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066967"
---
# <a name="compiler-error-c2990"></a>Erro do compilador C2990

'class': tipo não classe já foi declarado como um tipo de classe

A classe de modelo ou não genérica redefine uma classe genérica ou modelo. Verifique os arquivos de cabeçalho para conflitos.

O exemplo a seguir gera C2990:

```
// C2990.cpp
// compile with: /c
template <class T>
class C{};
class C{};   // C2990
```

C2990 também podem ocorrer ao usar genéricos:

```
// C2990b.cpp
// compile with: /clr /c
generic <class T>
ref struct GC;

ref struct GC {};   // C2990
```

C2990 também pode ocorrer devido a uma alteração significativa no compilador do Visual C++ para Visual C++ 2005; o compilador agora exige que várias declarações para o mesmo tipo sejam idênticas em relação à especificação de modelo.

O exemplo a seguir gera C2990:

```
// C2990c.cpp
// compile with: /c
template<class T>
class A;

template<class T>
struct A2 {
   friend class A;   // C2990
};

// OK
template<class T>
struct B {
   template<class T>
   friend class A;
};
```