---
title: _mm_cvttss_si64x | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _mm_cvttss_si64x
dev_langs:
- C++
helpviewer_keywords:
- _mm_cvttss_si64x intrinsic
- cvttss2si instruction
ms.assetid: f9a3fd07-5bd8-4758-8744-6315c082cf87
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f8d863a485f6b3fa9648b74e8a438dcf5ef37be
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381349"
---
# <a name="mmcvttsssi64x"></a>_mm_cvttss_si64x

**Seção específica da Microsoft**

Emite x64 estendido versão de Convert com o número de ponto flutuante de precisão simples de truncamento em inteiro de 64 bits (`cvttss2si`) instrução.

## <a name="syntax"></a>Sintaxe

```
__int64 _mm_cvttss_si64x( 
   __m128 value 
);
```

#### <a name="parameters"></a>Parâmetros

*value*<br/>
[in] Um `__m128` estrutura que contém os valores de ponto flutuante de precisão simples.

## <a name="return-value"></a>Valor de retorno

O resultado da conversão do primeiro valor de ponto flutuante para um inteiro de 64 bits.

## <a name="requirements"></a>Requisitos

|Intrínseco|Arquitetura|
|---------------|------------------|
|`_mm_cvttss_si64x`|X64|

**Arquivo de cabeçalho** \<intrin. h >

## <a name="remarks"></a>Comentários

O intrínseco difere do `_mm_cvtss_si64x` somente em que conversões inexatos são truncadas em direção a zero. Porque o `__m128` estrutura representa um registro de registros de MMX, a instrução gerada move dados de um registro de registros de MMX na memória do sistema.

Essa rotina só está disponível como função intrínseca.

## <a name="example"></a>Exemplo

```
// _mm_cvttss_si64x.cpp
// processor: x64
#include <intrin.h>
#include <stdio.h>

#pragma intrinsic(_mm_cvttss_si64x)

int main()
{
    __m128 a;
    __int64 b = 54;

    // _mm_load_ps requires an aligned buffer.
    __declspec(align(16)) float af[4] = { 101.5, 200.75,
                                          300.5, 400.5 };

    // Load a with the floating point values.
    // The values will be copied to the XMM registers.
    a = _mm_load_ps(af);

    // Extract the first element of a and convert to an integer
    b = _mm_cvttss_si64x(a);

    printf_s("%I64d\n", b);
}
```

```Output
101
```

**Fim da seção específica da Microsoft**

## <a name="see-also"></a>Consulte também

[__m128](../cpp/m128.md)<br/>
[Intrínsecos do compilador](../intrinsics/compiler-intrinsics.md)