---
title: auto_handle::operator! | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr.auto_handle.operator!
- msclr::auto_handle::operator!
- auto_handle.operator!
- auto_handle::operator!
dev_langs:
- C++
helpviewer_keywords:
- operator!
ms.assetid: 3f6c7729-3260-4842-87f9-c491c140b299
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 49dc8a0f1a2c6f7bbb3bf29b84d751d4b3faa48c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429338"
---
# <a name="autohandleoperator"></a>auto_handle::operator!

Operador para usar `auto_handle` em uma expressão condicional.

## <a name="syntax"></a>Sintaxe

```
bool operator!();
```

## <a name="return-value"></a>Valor de retorno

`true` Se o objeto encapsulado é inválido; `false` caso contrário.

## <a name="example"></a>Exemplo

```
// msl_auto_handle_operator_not.cpp
// compile with: /clr
#include <msclr\auto_handle.h>

using namespace System;
using namespace msclr;

int main() {
   auto_handle<String> s1;
   auto_handle<String> s2 = "something";
   if ( s1) Console::WriteLine( "s1 is valid" );
   if ( !s1 ) Console::WriteLine( "s1 is invalid" );
   if ( s2 ) Console::WriteLine( "s2 is valid" );
   if ( !s2 ) Console::WriteLine( "s2 is invalid" );
   s2.reset();
   if ( s2 ) Console::WriteLine( "s2 is now valid" );
   if ( !s2 ) Console::WriteLine( "s2 is now invalid" );
}
```

```Output
s1 is invalid
s2 is valid
s2 is now invalid
```

## <a name="requirements"></a>Requisitos

**Arquivo de cabeçalho** \<msclr\auto_handle.h >

**Namespace** msclr

## <a name="see-also"></a>Consulte também

[Membros auto_handle](../dotnet/auto-handle-members.md)<br/>
[auto_handle::operator bool](../dotnet/auto-handle-operator-bool.md)