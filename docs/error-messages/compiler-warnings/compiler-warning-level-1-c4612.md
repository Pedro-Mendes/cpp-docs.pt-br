---
title: Compilador aviso (nível 1) C4612 | Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4612
dev_langs:
- C++
helpviewer_keywords:
- C4612
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 10a0a5640386f5e5673f39d6c2c76ee18fcc7ba7
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43210724"
---
# <a name="compiler-warning-level-1-c4612"></a>Compilador aviso (nível 1) C4612

> Erro ao incluir o nome de arquivo

## <a name="remarks"></a>Comentários

Este aviso ocorre com **#pragma include_alias** quando um nome de arquivo está incorreta ou ausente.

Os argumentos para o **#pragma include_alias** instrução pode usar o formulário de cotação ("*filename*") ou a forma de colchete (\<*filename*>), mas ambas devem Use o mesmo formulário.

## <a name="example"></a>Exemplo

```cpp
// C4612.cpp
// compile with: /W1 /LD
#pragma include_alias("StandardIO", <stdio.h>) // C4612
```