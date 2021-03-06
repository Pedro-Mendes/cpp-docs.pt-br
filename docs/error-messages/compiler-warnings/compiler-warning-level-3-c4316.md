---
title: Compilador aviso (nível 3) C4316 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4316
dev_langs:
- C++
helpviewer_keywords:
- C4316
ms.assetid: 10371f01-aeb8-40ac-a290-59e63efa5ad4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a4170481b95cca0d43aa03c776009a5030194a4c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032920"
---
# <a name="compiler-warning-level-3-c4316"></a>Compilador aviso (nível 3) C4316

Alocados no heap de objeto não pode ser alinhado para esse tipo.

Um objeto sobre-alinhado alocado usando `operator new` pode não ter o alinhamento especificado. Substituir [operador new](../../c-runtime-library/operator-new-crt.md) e [operador delete](../../c-runtime-library/operator-delete-crt.md) para tipos sobre-alinhados de modo que eles usam as rotinas de alocação alinhada — por exemplo, [aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) e [aligned_free](../../c-runtime-library/reference/aligned-free.md). O exemplo a seguir gera C4316:

```cpp
// C4316.cpp
// Test: cl /W3 /c C4316.cpp

__declspec(align(32)) struct S {}; // C4324

int main() {
    new S; // C4316
}
```