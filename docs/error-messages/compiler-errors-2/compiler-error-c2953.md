---
title: Erro do compilador C2953 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2953
dev_langs:
- C++
helpviewer_keywords:
- C2953
ms.assetid: 8dbcfa24-8296-4e40-bdc4-5526c07d8892
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b1a22bfce625001c4e8130fa9ab7a9954d0cb0fd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068774"
---
# <a name="compiler-error-c2953"></a>Erro do compilador C2953

'identifier': template de classe já foi definido

Verifique o arquivo de origem e incluir arquivos para outras definições.

O exemplo a seguir gera C2953:

```
// C2953.cpp
// compile with: /c
template <class T>  class A {};
template <class T>  class A {};   // C2953
template <class T>  class B {};   // OK
```