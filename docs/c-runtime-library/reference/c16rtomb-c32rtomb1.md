---
title: c16rtomb, c32rtomb1 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- c16rtomb
- c32rtomb
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- c16rtomb
- c32rtomb
- uchar/c16rtomb
- uchar/c32rtomb
dev_langs:
- C++
helpviewer_keywords:
- c16rtomb function
- c32rtomb function
ms.assetid: 7f5743ca-a90e-4e3f-a310-c73e16f4e14d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3282fb13e5b59ad3214c67410eef5186687114e9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32394532"
---
# <a name="c16rtomb-c32rtomb"></a>c16rtomb, c32rtomb

Converta um caractere largo UTF-16 ou UTF-32 em um caractere multibyte na localidade atual.

## <a name="syntax"></a>Sintaxe

```C
size_t c16rtomb(
    char *mbchar,
    char16_t wchar,
    mbstate_t *state
);
size_t c32rtomb(
    char *mbchar,
    char32_t wchar,
    mbstate_t *state
);
```

### <a name="parameters"></a>Parâmetros

*mbchar*<br/>
Ponteiro para uma matriz para armazenar o caractere multibyte convertido.

*wchar*<br/>
Um caractere largo a ser convertido.

*state*<br/>
Um ponteiro para um **mbstate_t** objeto.

## <a name="return-value"></a>Valor de retorno

O número de bytes armazenados no objeto de matriz *mbchar*, incluindo quaisquer sequências de turno. Se *wchar* não é um caractere largo válido, o valor (**size_t**)(-1) for retornado, **errno** é definido como **EILSEQ**e o valor de *estado* não está especificado.

## <a name="remarks"></a>Comentários

O **c16rtomb** função converte o caractere UTF-16 *wchar* à sequência de caractere estreito multibyte equivalente na localidade atual. Se *mbchar* não é um ponteiro nulo, os repositórios de função a sequência convertida no objeto de matriz apontada pelo *mbchar*. Até **MB_CUR_MAX** bytes são armazenados em *mbchar*, e *estado* é definido como o estado de shift multibyte resultante.    Se *wchar* é um caractere largo nulo, uma sequência necessário para restaurar o estado de shift inicial é armazenado, se necessário, seguido pelo caractere null, e *estado* está definido para o estado inicial de conversão. O **c32rtomb** função é idêntica, mas converte um caractere UTF-32.

Se *mbchar* é um ponteiro nulo, o comportamento é equivalente a uma chamada para a função que substitui um buffer interno para *mbchar* e um caractere null largo para *wchar*.

O *estado* objeto de estado de conversão permite que você faça chamadas subsequentes para essa função e outras funções reiniciáveis que mantêm o estado de shift dos caracteres multibyte de saída. Os resultados são indefinidos ao combinar o uso de funções reiniciáveis e não pode ser reiniciada, ou se uma chamada para **setlocale** é feita entre chamadas de função reiniciável.

## <a name="requirements"></a>Requisitos

|Rotina|Cabeçalho necessário|
|-------------|---------------------|
|**c16rtomb**, **c32rtomb**|C, C++: \<uchar.h>|

Para obter informações sobre compatibilidade, consulte [Compatibilidade](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Consulte também

[Conversão de Dados](../../c-runtime-library/data-conversion.md)<br/>
[Localidade](../../c-runtime-library/locale.md)<br/>
[Interpretação de sequências de caracteres multibyte](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbrtoc16, mbrtoc32](mbrtoc16-mbrtoc323.md)<br/>
[wcrtomb](wcrtomb.md)<br/>
[wcrtomb_s](wcrtomb-s.md)<br/>
