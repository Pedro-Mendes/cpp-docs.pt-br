---
title: Erro do compilador C3495 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3495
dev_langs:
- C++
helpviewer_keywords:
- C3495
ms.assetid: 1fd40cb8-8373-403d-b8a8-f08424a50807
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dda1e2f2699969ad0bc446d9f79a0004e043998d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067383"
---
# <a name="compiler-error-c3495"></a>Erro do compilador C3495

'var': uma captura de lambda deve ter a duração de armazenamento automático

Não é possível capturar uma variável que não tem duração de armazenamento automático, como uma variável que é marcada `static` ou `extern`.

### <a name="to-correct-this-error"></a>Para corrigir este erro

- Não passe um `static` ou `extern` variável à lista de captura da expressão lambda.

## <a name="example"></a>Exemplo

O exemplo a seguir gera C3495 porque o `static` variável `n` aparece na lista de captura de uma expressão lambda:

```
// C3495.cpp

int main()
{
   static int n = 66;
   [&n]() { return n; }(); // C3495
}
```

## <a name="see-also"></a>Consulte também

[Expressões Lambda](../../cpp/lambda-expressions-in-cpp.md)


