---
title: log, logf, logl, log10, log10f, log10l | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- log10f
- logf
- log10
- log
- log10l
- logl
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- logf
- logl
- _log10l
- log
- _logl
- log10f
- log10l
- log10
dev_langs:
- C++
helpviewer_keywords:
- calculating logarithms
- log10f function
- log10 function
- log function
- log10l function
- logl function
- logf function
- logarithms
ms.assetid: 7adc77c2-04f7-4245-a980-21215563cfae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 12f475cde27d4660f4b4936f3f7717a665b70e86
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32402836"
---
# <a name="log-logf-logl-log10-log10f-log10l"></a>log, logf, logl, log10, log10f, log10l

Calcula logaritmos.

## <a name="syntax"></a>Sintaxe

```C
double log( double x );
float logf( float x );
long double logl( double x );
double log10( double x );
float log10f ( float x );
long double log10l( double x );
```

```cpp
float log( float x );  // C++ only
long double log( long double x );  // C++ only
float log10( float x );  // C++ only
long double log10( long double x );  // C++ only
```

### <a name="parameters"></a>Parâmetros

*x*<br/>
Valor cujo logaritmos deve ser localizado.

## <a name="return-value"></a>Valor de retorno

O **log** funções retornam o logaritmo natural (base *e*) de *x* se for bem-sucedido. O **log10** funções retornam o logaritmo de base 10. Se *x* é negativo, essas funções retornam uma (IND, indefinido) por padrão. Se *x* for 0, elas retornam infinito (INF).

|Entrada|Exceção SEH|Exceção Matherr|
|-----------|-------------------|-----------------------|
|± QNAN, IND|nenhum|_DOMAIN|
|± 0|ZERODIVIDE|_SING|
|*x* < 0|INVALID|_DOMAIN|

**log** e **log10** ter uma implementação que usa extensões Streaming SIMD 2 (SSE2). Para obter informações e restrições sobre como usar a implementação de SSE2, consulte [_set_SSE2_enable](set-sse2-enable.md).

## <a name="remarks"></a>Comentários

O C++ permite sobrecarga, portanto, você pode chamar sobrecargas de **log** e **log10** que levar e retornar **float** ou **long double** valores. Em um programa C, **log** e **log10** sempre levar e retornar um **duplo**.

## <a name="requirements"></a>Requisitos

|Rotina|Cabeçalho necessário|
|-------------|---------------------|
|**log**, **logf**, **logl**, **log10**, **log10f**, **log10l**|\<math.h>|

Para obter informações adicionais sobre compatibilidade, consulte [Compatibilidade](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Exemplo

```C
// crt_log.c
/* This program uses log and log10
* to calculate the natural logarithm and
* the base-10 logarithm of 9,000.
*/

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 9000.0;
   double y;

   y = log( x );
   printf( "log( %.2f ) = %f\n", x, y );
   y = log10( x );
   printf( "log10( %.2f ) = %f\n", x, y );
}
```

```Output
log( 9000.00 ) = 9.104980
log10( 9000.00 ) = 3.954243
```

Para gerar logaritmos para outras bases, use a relação matemática: log base b de a == log natural (a) / log natural (b).

```cpp
// logbase.cpp
#include <math.h>
#include <stdio.h>

double logbase(double a, double base)
{
   return log(a) / log(base);
}

int main()
{
   double x = 65536;
   double result;

   result = logbase(x, 2);
   printf("Log base 2 of %lf is %lf\n", x, result);
}
```

```Output
Log base 2 of 65536.000000 is 16.000000
```

## <a name="see-also"></a>Consulte também

[Suporte a ponto flutuante](../../c-runtime-library/floating-point-support.md) <br/>
[exp, expf, expl](exp-expf.md) <br/>
[_matherr](matherr.md) <br/>
[pow, powf, powl](pow-powf-powl.md) <br/>
[_CIlog](../../c-runtime-library/cilog.md) <br/>
[_CIlog10](../../c-runtime-library/cilog10.md)<br/>
