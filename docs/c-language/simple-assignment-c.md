---
title: Atribuição simples (C) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- type conversion [C++], simple assignment
- data type conversion [C++], simple assignment
- operators [C], simple assignment
- assignment operators [C++], simple
- simple assignment operator
- equal sign
ms.assetid: e7140a0a-7104-4b3a-b293-7adcc1fdd52b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ff4e032e205680da84369075514e3177fa5fb33e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051016"
---
# <a name="simple-assignment-c"></a>Atribuição simples (C)

O operador de atribuição simples atribui o operando à direita ao operando à esquerda. O valor do operando à direita é convertido no tipo da expressão de atribuição e substituir o valor armazenado no objeto designado pelo operando à esquerda. As regras de conversão para a atribuição se aplicam (consulte [Conversões de atribuição](../c-language/assignment-conversions.md)).

```
double x;
int y;

x = y;
```

Neste exemplo, o valor de `y` é convertido para o tipo **double** e é atribuído a `x`.

## <a name="see-also"></a>Consulte também

[Operadores de atribuição C](../c-language/c-assignment-operators.md)