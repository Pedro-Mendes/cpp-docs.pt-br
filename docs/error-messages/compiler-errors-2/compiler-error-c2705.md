---
title: Erro do compilador C2705 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2705
dev_langs:
- C++
helpviewer_keywords:
- C2705
ms.assetid: 29249ea3-4ea7-4105-944b-bdb83e8d6852
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1c0eefd19645ee6ac06664249f7953d904cd5896
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093695"
---
# <a name="compiler-error-c2705"></a>Erro do compilador C2705

'Rótulo': salto ilegal para o escopo de 'block do manipulador de exceção'

Execução saltará para um rótulo dentro de um `try` / `catch`, `__try` / `__except`, `__try` / `__finally` bloco. Para saber mais, veja [Tratamento de exceção](../../cpp/exception-handling-in-visual-cpp.md).

O exemplo a seguir gera C2705:

```
// C2705.cpp
int main() {
goto trouble;
   __try {
      trouble: ;   // C2705
   }
   __finally {}

   // try the following line instead
   // trouble: ;
}
```