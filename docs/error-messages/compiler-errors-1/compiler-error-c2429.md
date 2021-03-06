---
title: C2429 de erro do compilador | Microsoft Docs
ms.custom: ''
ms.date: 11/16/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2429
dev_langs:
- C++
helpviewer_keywords:
- C2429
ms.assetid: 57ff6df9-5cf1-49f3-8bd8-4e550dfd65a0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 032df433b28e83f720fe76952a541b59bda889f5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33227805"
---
# <a name="compiler-error-c2429"></a>C2429 de erro do compilador

> '*recurso de idioma*'requer o sinalizador do compilador'*opção de compilador*'

O recurso de idioma requer uma opção de compilador específico para obter suporte.

O erro **C2429: o recurso de linguagem 'aninhado--definição de namespace' requer o sinalizador do compilador ' / std:c + + 17'** será gerado se você tentar definir um *composta namespace*, um namespace que contém um ou mais nomes de namespace escopo aninhado, a partir do Visual Studio 2015 atualização 5. (No Visual Studio 2017 versão 15,3, o **/std:c + + mais recente** comutador é necessário.) Composta namespace não são permitidas definições em C++ antes de C++ 17. O compilador suporta as definições do namespace composta quando o [/std:c + + 17](../../build/reference/std-specify-language-standard-version.md) opção de compilador é especificada:

```cpp
// C2429a.cpp
namespace a::b { int i; } // C2429 starting in Visual C++ 2015 Update 3.
                          // Use /std:c++17 to fix, or do this:
// namespace a { namespace b { int i; }}

int main() {
   a::b::i = 2;
}
```
