---
title: Erro do compilador C3488 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3488
dev_langs:
- C++
helpviewer_keywords:
- C3488
ms.assetid: 0a6fcd76-dd3b-48d7-abb3-22eccda96034
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 15e1a21781eed96ee3a2a1430da8e43013393912
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061773"
---
# <a name="compiler-error-c3488"></a>Erro do compilador C3488

'var' não é permitida quando o modo de captura padrão é por referência

Quando você especifica que o modo de captura padrão para uma expressão lambda por referência, você não pode passar uma variável por referência para a cláusula capture dessa expressão.

### <a name="to-correct-this-error"></a>Para corrigir este erro

- Não passar explicitamente a variável para a cláusula de captura ou

- Não especifique por referência como o modo de captura padrão, ou

- Especifique por valor como o modo de captura padrão, ou

- A variável passada por valor para a cláusula de captura. (Isso pode mudar o comportamento da expressão lambda).

## <a name="example"></a>Exemplo

O exemplo a seguir gera C3488 porque uma referência à variável `n` aparece na cláusula de captura de uma expressão lambda cujo padrão é por referência:

```
// C3488a.cpp

int main()
{
   int n = 5;
   [&, &n]() { return n; } (); // C3488
}
```

## <a name="example"></a>Exemplo

O exemplo a seguir mostra quatro possíveis resoluções para C3488:

```
// C3488b.cpp

int main()
{
   int n = 5;

   // Possible resolution 1:
   // Do not explicitly pass &n to the capture clause.
   [&]() { return n; } ();

   // Possible resolution 2:
   // Do not specify by-reference as the default capture mode.
   [&n]() { return n; } ();

   // Possible resolution 3:
   // Specify by-value as the default capture mode.
   [=, &n]() { return n; } ();

   // Possible resolution 4:
   // Pass n by value to the capture clause.
   [n]() { return n; } ();
}
```

## <a name="see-also"></a>Consulte também

[Expressões Lambda](../../cpp/lambda-expressions-in-cpp.md)