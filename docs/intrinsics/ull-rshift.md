---
title: __ull_rshift | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __ull_rshift
dev_langs:
- C++
helpviewer_keywords:
- ull_rshift intrinsic
- __ull_rshift intrinsic
ms.assetid: b7ff5254-3540-4e6e-b57c-a6c4beb7dca2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4ebcd7a491941631db1e1c21d24a350eb2774de
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46402805"
---
# <a name="ullrshift"></a>__ull_rshift

**Seção específica da Microsoft**

no x64, desloca um valor de 64 bits especificado pelo primeiro parâmetro para a direita em um número de bits especificado pelo segundo parâmetro.

## <a name="syntax"></a>Sintaxe

```
unsigned __int64 __ull_rshift( 
   unsigned __int64 mask,  
   int nBit 
);
```

#### <a name="parameters"></a>Parâmetros

*Máscara*<br/>
[in] O valor de inteiro de 64 bits a deslocar para a direita.

*nBit*<br/>
[in] O número de bits a deslocar, 32 em x86 de módulo e módulo 64 em x64.

## <a name="return-value"></a>Valor de retorno

A máscara deslocados em `nBit` bits.

## <a name="requirements"></a>Requisitos

|Intrínseco|Arquitetura|
|---------------|------------------|
|`__ull_rshift`|x86, x64|

**Arquivo de cabeçalho** \<intrin. h >

## <a name="remarks"></a>Comentários

Se o segundo parâmetro é maior que 31 em x86 (63 em x64), esse número é tirado de módulo 32 (64 em x64) para determinar o número de bits a deslocar. O `ull` o nome indica `unsigned long long (unsigned __int64)`.

## <a name="example"></a>Exemplo

```
// ull_rshift.cpp
// compile with: /EHsc
// processor: x86, x64
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(__ull_rshift)

int main()
{
   unsigned __int64 mask = 0x100;
   int nBit = 8;
   mask = __ull_rshift(mask, nBit);
   cout << hex << mask << endl;
}
```

## <a name="output"></a>Saída

```
1
```

**Fim da seção específica da Microsoft**

## <a name="see-also"></a>Consulte também

[__ll_lshift](../intrinsics/ll-lshift.md)<br/>
[__ll_rshift](../intrinsics/ll-rshift.md)<br/>
[Intrínsecos do compilador](../intrinsics/compiler-intrinsics.md)