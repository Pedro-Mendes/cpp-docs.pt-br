---
title: Compilador aviso (nível 1) C4508 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4508
dev_langs:
- C++
helpviewer_keywords:
- C4508
ms.assetid: c05f113b-b789-4df0-a4ef-78bce4767021
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e5abc1d81c3e94c02a63f73c84f3f5e5c7e9b0b0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46038928"
---
# <a name="compiler-warning-level-1-c4508"></a>Compilador aviso (nível 1) C4508

'function': função deve retornar um valor; supõe-se de tipo de retorno 'void'

A função não tem nenhum tipo de retorno especificado. Nesse caso, também deve ser disparado C4430 e o compilador implementa a correção relatada pelo C4430 (o valor padrão é int).

Para resolver este aviso, declare explicitamente o tipo de retorno de funções.

O exemplo a seguir gera C4508:

```
// C4508.cpp
// compile with: /W1 /c
#pragma warning (disable : 4430)
func() {}   // C4508
void func2() {}   // OK
```