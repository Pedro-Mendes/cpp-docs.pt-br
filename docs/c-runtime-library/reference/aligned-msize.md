---
title: _aligned_msize | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _aligned_msize
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _aligned_msize
- aligned_msize
dev_langs:
- C++
helpviewer_keywords:
- aligned_msize function
- _aligned_msize function
ms.assetid: 10995edc-2110-4212-9ca9-5e0220a464f4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2375ec8f61a95ec018ea55cc1f891ad8049748c9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32393099"
---
# <a name="alignedmsize"></a>_aligned_msize

Retorna o tamanho de um bloco de memória alocado no heap.

## <a name="syntax"></a>Sintaxe

```C
size_t _msize(
   void *memblock,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>Parâmetros

*memblock*<br/>
Ponteiro para o bloco de memória.

*alignment*<br/>
O valor de alinhamento, que deve ser um inteiro elevado à segunda potência.

*deslocamento*<br/>
O deslocamento na alocação de memória para forçar o alinhamento.

## <a name="return-value"></a>Valor de retorno

Retorna o tamanho (em bytes) como um inteiro sem sinal.

## <a name="remarks"></a>Comentários

O **aligned_msize** função retorna o tamanho, em bytes, do bloco de memória alocada por uma chamada para [aligned_malloc](aligned-malloc.md) ou [aligned_realloc](aligned-realloc.md). O *alinhamento* e *deslocamento* valores devem ser o mesmo que os valores passados para a função que é alocada do bloco.

Quando o aplicativo está vinculado com uma versão de depuração das bibliotecas de tempo de execução do C, **aligned_msize** resolve [_aligned_msize_dbg](aligned-msize-dbg.md). Para obter mais informações sobre como o heap é gerenciado durante o processo de depuração, consulte [The CRT Debug Heap](/visualstudio/debugger/crt-debug-heap-details) (O heap de depuração do CRT).

Esta função valida seu parâmetro. Se *memblock* é um ponteiro nulo ou *alinhamento* não é uma potência de 2, **msize** invoca um manipulador de parâmetro inválido, conforme descrito em [validação de parâmetro ](../../c-runtime-library/parameter-validation.md). Se o erro é tratado, define a função **errno** para **EINVAL** e retorna -1.

## <a name="requirements"></a>Requisitos

|Rotina|Cabeçalho necessário|
|-------------|---------------------|
|**_msize**|\<malloc.h>|

Para obter mais informações sobre compatibilidade, consulte [Compatibilidade](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Libraries

Todas as versões das [bibliotecas em tempo de execução C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Consulte também

[Alocação de Memória](../../c-runtime-library/memory-allocation.md)<br/>
