---
title: Erro do compilador C3541 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3541
dev_langs:
- C++
helpviewer_keywords:
- C3541
ms.assetid: 252cfd4c-5fd2-415e-a17d-6b0c254350db
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a0f9cb18089bcf8ce1688cabb261f91f868da247
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021714"
---
# <a name="compiler-error-c3541"></a>Erro do compilador C3541

'type': typeid não pode ser aplicado a um tipo que contenha 'auto'

O [typeid](../../windows/typeid-cpp-component-extensions.md) operador não pode ser aplicado para o tipo indicado, porque ela contém o `auto` especificador.

## <a name="example"></a>Exemplo

O exemplo a seguir produz C3541.

```
// C3541.cpp
// Compile with /Zc:auto
#include <typeinfo>
int main() {
    auto x = 123;
    typeid(x);    // OK
    typeid(auto); // C3541
    return 0;
}
```

## <a name="see-also"></a>Consulte também

[Palavra-chave auto](../../cpp/auto-keyword.md)<br/>
[/Zc:auto (deduzir tipo de variável)](../../build/reference/zc-auto-deduce-variable-type.md)<br/>
[TypeId](../../windows/typeid-cpp-component-extensions.md)