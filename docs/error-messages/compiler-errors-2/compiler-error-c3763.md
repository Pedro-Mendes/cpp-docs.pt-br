---
title: Erro do compilador C3763 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3763
dev_langs:
- C++
helpviewer_keywords:
- C3763
ms.assetid: 58b1f079-cd1d-46e0-9431-ea18210106b7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: db0304cf0dca69c101ee3e559052ca139caa8be3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030256"
---
# <a name="compiler-error-c3763"></a>Erro do compilador C3763

'type': 'retval' e 'out' só pode aparecer em um tipo de ponteiro de dados

O [horizontalmente](../../windows/out-cpp.md) ou [retval](../../windows/retval.md) atributos só podem aparecer em parâmetros do tipo ponteiro. Remova o atributo ou tornar o parâmetro do tipo ponteiro.

O exemplo a seguir gera C3763:

```
// C3763.cpp
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlplus.h>
#include <atlcom.h>

[ module(name=test) ];

[ dispinterface, uuid("00000000-0000-0000-0000-000000000001") ]
__interface IF84 : IDispatch
{
   [id(0x00000002)]HRESULT m2([out]unsigned char);
};

[ coclass, uuid("00000000-0000-0000-0000-000000000002") ]
class CF84 : public IF84
{   // C3763
public:
   HRESULT __stdcall m2(unsigned char i)
   {
      return S_OK;
   }
};

int main()
{
}
```