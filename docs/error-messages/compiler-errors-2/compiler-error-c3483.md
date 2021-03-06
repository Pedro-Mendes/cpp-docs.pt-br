---
title: Erro do compilador C3483 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3483
dev_langs:
- C++
helpviewer_keywords:
- C3483
ms.assetid: 18b3a2c5-dfc9-4661-9653-08a5798474cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: decc04f25689b24c560f59a71fd22a9708754352
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091680"
---
# <a name="compiler-error-c3483"></a>Erro do compilador C3483

'var' já é parte da lista de captura de lambda

Você passou a mesma variável para a lista de captura de uma expressão lambda mais de uma vez.

### <a name="to-correct-this-error"></a>Para corrigir este erro

- Remova todas as instâncias adicionais da variável da lista de captura.

## <a name="example"></a>Exemplo

O exemplo a seguir gera C3483 porque a variável `n` aparece mais de uma vez na lista da expressão lambda captura:

```
// C3483.cpp

int main()
{
   int m = 6, n = 5;
   [m,n,n] { return n + m; }(); // C3483
}
```

## <a name="see-also"></a>Consulte também

[Expressões Lambda](../../cpp/lambda-expressions-in-cpp.md)