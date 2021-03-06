---
title: _aligned_free | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _aligned_free
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
- aligned_free
- _aligned_free
dev_langs:
- C++
helpviewer_keywords:
- _aligned_free function
- aligned_free function
ms.assetid: ed1ce952-cdfc-4682-85cc-f75d4101603d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 54700ad2a1eed391647a66a4c54a726b75e812f4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46069710"
---
# <a name="alignedfree"></a>_aligned_free

Libera um bloco de memória que foi alocado com [_aligned_malloc](aligned-malloc.md) ou [_aligned_offset_malloc](aligned-offset-malloc.md).

## <a name="syntax"></a>Sintaxe

```C
void _aligned_free (
   void *memblock
);
```

### <a name="parameters"></a>Parâmetros

*memblock*<br/>
Um ponteiro para o bloco de memória que foi retornado para a função `_aligned_malloc` ou `_aligned_offset_malloc`.

## <a name="remarks"></a>Comentários

**aligned_free** está marcado como `__declspec(noalias)`, que significa que a função não é garantido que modifica variáveis globais. Para obter mais informações, consulte [noalias](../../cpp/noalias.md).

Essa função não valida seu parâmetro, ao contrário das outras funções de CRT _aligned. Se *memblock* for um ponteiro nulo, essa função simplesmente não executará nenhuma ação. Ela não altera `errno` nem chama o manipulador de parâmetro inválido. Se ocorrer um erro na função porque as funções _aligned não foram usadas anteriormente para alocar o bloco de memória ou se ocorrer um desalinhamento de memória devido a algum problema imprevisto, a função gerará um relatório de depuração das [Macros _RPT, _RPTF, _RPTW, _RPTFW](rpt-rptf-rptw-rptfw-macros.md).

## <a name="requirements"></a>Requisitos

|Rotina|Cabeçalho necessário|
|-------------|---------------------|
|**_aligned_free**|\<malloc.h>|

## <a name="example"></a>Exemplo

Para obter mais informações, consulte [_aligned_malloc](aligned-malloc.md).

## <a name="see-also"></a>Consulte também

[Alinhamento de dados](../../c-runtime-library/data-alignment.md)