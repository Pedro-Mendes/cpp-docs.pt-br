---
title: Erro do compilador C2057 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2057
dev_langs:
- C++
helpviewer_keywords:
- C2057
ms.assetid: 038a99d6-1f5a-42fa-8449-03b4ff11ee0b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fb9018224d10fa0104ee461e8bbeb659173fc9f0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051706"
---
# <a name="compiler-error-c2057"></a>Erro do compilador C2057

expressão de constante esperada

O contexto requer uma expressão constante, uma expressão cujo valor é conhecido no tempo de compilação.

O compilador deve saber o tamanho de um tipo em tempo de compilação para alocar espaço para uma instância desse tipo.

## <a name="example"></a>Exemplo

O exemplo a seguir gera C2057 e mostra como corrigi-lo:

```
// C2057.cpp
int i;
int b[i];   // C2057 - value of i is unknown at compile time
int main() {
   const int i = 8;
   int b[i]; // OK - value of i is fixed and known to compiler
}
```

## <a name="example"></a>Exemplo

C tem regras mais restritivas para expressões constantes.  O exemplo a seguir gera C2057 e mostra como corrigi-lo:

```
// C2057b.c
#define ArraySize1 10
int main() {
   const int ArraySize2 = 10;
   int h[ArraySize2];   // C2057 - C does not allow variables here
   int h[ArraySize1];   // OK - uses preprocessor constant
}
```