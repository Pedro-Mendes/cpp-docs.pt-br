---
title: Compilador aviso (nível 1) C4109 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4109
dev_langs:
- C++
helpviewer_keywords:
- C4109
ms.assetid: 9e8d95c6-e05d-47e0-bd87-78974b3cc06c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a53af740cdc6652822da05a6591fd93063f2b4fa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46069918"
---
# <a name="compiler-warning-level-1-c4109"></a>Compilador aviso (nível 1) C4109

identificador inesperado 'identifier'

O pragma que contém o identificador inesperado é ignorado.

## <a name="example"></a>Exemplo

```
// C4109.cpp
// compile with: /W1 /LD
#pragma init_seg( abc ) // C4109
```