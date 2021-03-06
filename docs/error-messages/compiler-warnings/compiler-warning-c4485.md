---
title: Aviso do compilador C4485 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4485
dev_langs:
- C++
helpviewer_keywords:
- C4485
ms.assetid: a6f2b437-ca93-4dcd-b9cb-df415e10df86
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cb83700bf8ca79960599d85ed3d335f80c9fc7f2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117745"
---
# <a name="compiler-warning-c4485"></a>Aviso do compilador C4485

'override_function': corresponde ao método de classe ref base 'base_class_function', mas não está marcado como 'new' ou 'override'; 'new' (e 'virtual') são assumidos

Substitui um acessador, com ou sem o `virtual` palavra-chave, uma função de acessador de classe base, mas o `override` ou `new` especificador não era parte da assinatura de função de substituição. Adicione a `new` ou `override` especificador para resolver este aviso.

Ver [substituir](../../windows/override-cpp-component-extensions.md) e [novo (novo slot em vtable)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md) para obter mais informações.

C4485 sempre é emitido como um erro. Use o [aviso](../../preprocessor/warning.md) pragma para suprimir C4485.

## <a name="example"></a>Exemplo

O exemplo a seguir gera C4485

```
// C4485.cpp
// compile with: /clr
delegate void Del();

ref struct A {
   virtual event Del ^E;
};

ref struct B : A {
   virtual event Del ^E;   // C4485
};

ref struct C : B {
   virtual event Del ^E {
      void raise() override {}
      void add(Del ^) override {}
      void remove(Del^) override {}
   }
};
```