---
title: Erro do compilador C2678 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2678
dev_langs:
- C++
helpviewer_keywords:
- C2678
ms.assetid: 1f0a4e26-b429-44f5-9f94-cb66441220c8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b2af18a98304cafc70441acda7ef0ebb1a827d88
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035337"
---
# <a name="compiler-error-c2678"></a>Erro do compilador C2678

binário 'operator': Nenhum operador definido que usa um operando esquerdo do tipo 'type' (ou não há nenhuma conversão aceitável)

Para usar o operador, você deve sobrecarregá-lo para o tipo especificado ou definir uma conversão para um tipo para o qual o operador está definido.

## <a name="example"></a>Exemplo

C2678 pode ocorrer quando o operando esquerdo é qualificado como const, mas o operador está definido para usar um argumento não const.

O exemplo a seguir gera C2678 e mostra como corrigi-lo:

```
// C2678a.cpp
// Compile by using: cl /EHsc /W4 C2678a.cpp
struct Combo {
   int number;
   char letter;
};

inline Combo& operator+=(Combo& lhs, int rhs) {
   lhs.number += rhs;
   return lhs;
}

int main() {
   Combo const combo1{ 42, 'X' };
   Combo combo2{ 13, 'Z' };

   combo1 += 6; // C2678
   combo2 += 9; // OK - operator+= matches non-const Combo
}
```

## <a name="example"></a>Exemplo

C2678 também pode ocorrer se você não fixar um membro nativo antes de chamar uma função de membro.

O exemplo a seguir gera C2678 e mostra como corrigi-lo.

```
// C2678.cpp
// compile with: /clr /c
struct S { int _a; };

ref class C {
public:
   void M( S param ) {
      test = param;   // C2678

      // OK
      pin_ptr<S> ptest = &test;
      *ptest = param;
   }
   S test;
};
```
