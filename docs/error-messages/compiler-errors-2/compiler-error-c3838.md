---
title: Erro do compilador C3838 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3838
dev_langs:
- C++
helpviewer_keywords:
- C3838
ms.assetid: d6f470c2-131a-4a8c-843a-254acd43da83
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dcf01ba87dc2e179e055417b6e2b78a90fd67cf5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46064185"
---
# <a name="compiler-error-c3838"></a>Erro do compilador C3838

explicitamente não pode herdar de 'type'

Especificado `type` não pode atuar como uma classe base em qualquer classe.

## <a name="example"></a>Exemplo

O exemplo a seguir gera C3838:

```
// C3838a.cpp
// compile with: /clr /c
public ref class B : public System::Enum {};   // C3838
```
