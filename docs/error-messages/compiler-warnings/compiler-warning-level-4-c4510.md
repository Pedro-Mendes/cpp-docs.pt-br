---
title: Compilador aviso (nível 4) C4510 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4510
dev_langs:
- C++
helpviewer_keywords:
- C4510
ms.assetid: fd28d1d4-ad27-4dad-94c0-9dba46c93180
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f2aaf7286c2e900629a18d7df5824ef4b7af1f5f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048962"
---
# <a name="compiler-warning-level-4-c4510"></a>Compilador aviso (nível 4) C4510

'class': não foi possível gerar um construtor padrão

O compilador não pode gerar um construtor padrão para a classe especificada e nenhum construtor definido pelo usuário foi criado. Você não poderá criar objetos desse tipo.

Há várias situações que impedem que o compilador gere um construtor padrão, incluindo:

- Um membro de dados const.

- Um membro de dados que é uma referência.

Você precisa criar um construtor padrão definido pelo usuário para a classe que inicializa esses membros.

O exemplo a seguir gera C4510:

```
// C4510.cpp
// compile with: /W4
struct A {
   const int i;
   int &j;
   A& operator=( const A& ); // C4510 expected
   // uncomment the following line to resolve this C4510
   // A(int ii, int &jj) : i(ii), j(jj) {}
};   // C4510

int main() {
}
```