---
title: Erro do compilador C2010 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2010
dev_langs:
- C++
helpviewer_keywords:
- C2010
ms.assetid: 5795ed1d-e206-410b-b7b4-528d125c67b4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4be71136d02a563d4dde5d720fe5ae51e0c3c5b6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028955"
---
# <a name="compiler-error-c2010"></a>Erro do compilador C2010

'character': inesperado na lista de parâmetros formais de macro

O caractere é usado incorretamente em lista de parâmetros formais de uma definição de macro. Remova o caractere para resolver o erro.

O exemplo a seguir gera C2010:

```
// C2010.cpp
// compile with: /c
#define mymacro(a|) (2*a)   // C2010
#define mymacro(a) (2*a)   // OK
```