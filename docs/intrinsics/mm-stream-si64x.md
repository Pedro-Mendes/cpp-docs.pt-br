---
title: _mm_stream_si64x | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _mm_stream_si64x
dev_langs:
- C++
helpviewer_keywords:
- movnti instruction
- _mm_stream_si64x intrinsic
ms.assetid: 114c2cd0-085f-41aa-846e-87bdd56c9ee7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 568f1c32553a07de7f1ac7bf8ad3d0652e26d437
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417651"
---
# <a name="mmstreamsi64x"></a>_mm_stream_si64x

**Seção específica da Microsoft**

Gera a instrução de MOVNTI. Grava os dados `Source` para um local de memória especificado por `Dest`, sem poluir os caches.

## <a name="syntax"></a>Sintaxe

```
void _mm_stream_si64x( 
   __int64 * Dest, 
   __int64 Source 
);
```

#### <a name="parameters"></a>Parâmetros

*dest*<br/>
[out] Um ponteiro para o local para gravar os dados de origem.

*Source*<br/>
[in] Os dados serem gravados.

## <a name="requirements"></a>Requisitos

|Intrínseco|Arquitetura|
|---------------|------------------|
|`_mm_stream_si64x`|X64|

**Arquivo de cabeçalho** \<intrin. h >

## <a name="remarks"></a>Comentários

Essa rotina só está disponível como função intrínseca.

## <a name="example"></a>Exemplo

```C
// _mm_stream_si64x.c
// processor: x64

#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(_mm_stream_si64x)

int main()
{
    __int64 val = 0xFFFFFFFFFFFFI64;
    __int64 a[10];

    memset(a, 0, sizeof(a));
    _mm_stream_si64x(a+1, val);
    printf_s( "%I64x %I64x %I64x %I64x", a[0], a[1], a[2], a[3]);
}
```

```Output
0 ffffffffffff 0 0
```

**Fim da seção específica da Microsoft**

## <a name="see-also"></a>Consulte também

[Intrínsecos do compilador](../intrinsics/compiler-intrinsics.md)