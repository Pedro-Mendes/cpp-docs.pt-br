---
title: Compilador aviso (nível 1) C4190 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4190
dev_langs:
- C++
helpviewer_keywords:
- C4190
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d398331c159c6fc639160dbe54d6ab5f969d3dbd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46063730"
---
# <a name="compiler-warning-level-1-c4190"></a>Compilador aviso (nível 1) C4190

'identifier1' possui vínculo a C especificado, mas retorna UDT 'identifier2', que é incompatível com C

Uma função ou um ponteiro para função tem um UDT (definido pelo usuário type, que é uma classe, estrutura, enumeração ou união) como tipo de retorno e `extern` vínculo "C". Isso é legal se:

- Todas as chamadas para essa função ocorrerem do C++.

- É a definição da função em C++.

## <a name="example"></a>Exemplo

```cpp
// C4190.cpp
// compile with: /W1 /LD
struct X
{
   int i;
   X ();
   virtual ~X ();
};

extern "C" X func ();   // C4190
```