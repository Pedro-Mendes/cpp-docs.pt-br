---
title: Erro do compilador C3204 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3204
dev_langs:
- C++
helpviewer_keywords:
- C3204
ms.assetid: 06e578da-0262-48c8-b2ae-be1cd6d28884
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1eb4ebc98f230074279e11692b647b4f7ba73918
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027811"
---
# <a name="compiler-error-c3204"></a>Erro do compilador C3204

alloca' não pode ser chamado de dentro de um bloco catch

Esse erro ocorre quando você usa uma chamada para [alloca](../../c-runtime-library/reference/alloca.md) de dentro de um bloco catch.

## <a name="example"></a>Exemplo

O exemplo a seguir gera C3204:

```
// C3204.cpp
// compile with: /EHsc
#include <malloc.h>

void ShowError(void)
{
   try
   {
   }
   catch(...)
   {
      _alloca(1);   // C3204
   }
}
```