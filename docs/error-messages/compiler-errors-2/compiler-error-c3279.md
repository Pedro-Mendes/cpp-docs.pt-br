---
title: Erro do compilador C3279 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3279
dev_langs:
- C++
helpviewer_keywords:
- C3279
ms.assetid: 639afc20-984c-4a95-be35-8bf9409f02d5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 89c537da9bcf91e7774353cc1516a4c44e28649c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056762"
---
# <a name="compiler-error-c3279"></a>Erro do compilador C3279

especializações parciais e explícitas, bem como instanciações explícitas de modelos de classe declaradas no namespace cli não são permitidas

O `cli` namespace é definida pela Microsoft e contém modelos de pseudo. O compilador do Visual C++ não permite especializações definidas pelo usuário, parciais e explícitas e instanciações explícitas de modelos de classe neste namespace.

O exemplo a seguir gera C3279:

```
// C3279.cpp
// compile with: /clr
namespace cli {
   template <> ref class array<int> {};   // C3279
   template <typename T> ref class array<T, 2> {};   // C3279
}
```