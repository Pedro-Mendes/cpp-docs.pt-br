---
title: Erro do compilador C3813 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3813
dev_langs:
- C++
helpviewer_keywords:
- C3813
ms.assetid: ffdbc489-71bf-4cd6-988c-f824c9ab3ceb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b8984feb5b657c26d2137eb9a3c648f1bcf442bf
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066265"
---
# <a name="compiler-error-c3813"></a>Erro do compilador C3813

uma declaração de propriedade só pode aparecer dentro da definição de um ou um tipo de WinRT

Um [propriedade](../../dotnet/how-to-use-properties-in-cpp-cli.md) só podem ser declarados dentro de um gerenciado ou tempo de execução do Windows tipo. Tipos nativos não dão suporte a `property` palavra-chave.

## <a name="example"></a>Exemplo

O exemplo a seguir gera C3813 e mostra como corrigi-lo:

```cpp
// C3813.cpp
// compile by using: cl /c /clr C3813.cpp
class A
{
   property int Int; // C3813
};

ref class B
{
   property int Int; // OK - declared within managed type
};
```