---
title: Compilador aviso (nível 1) C4606 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4606
dev_langs:
- C++
helpviewer_keywords:
- C4606
ms.assetid: c1b45fb6-672b-42eb-9e1c-c67b3e4150d3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bcdaba046f495dc3a29a7c9228edc561674f568f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035988"
---
# <a name="compiler-warning-level-1-c4606"></a>Compilador aviso (nível 1) C4606

\#Aviso de Pragma: 'warning_number' ignorado; Avisos da análise de código não estão associados com níveis de aviso

Avisos de análise de código, apenas `error`, `once`, e `default` são compatíveis com o [aviso](../../preprocessor/warning.md) pragma.

## <a name="example"></a>Exemplo

O exemplo a seguir gera C4606.

```
// C4606.cpp
// compile with: /c /W1
#pragma warning(1: 6001)   // C4606
#pragma warning(once: 6001)   // OK
```