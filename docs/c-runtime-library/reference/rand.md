---
title: rand | Microsoft Docs
ms.custom: ''
ms.date: 1/02/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- rand
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- rand
dev_langs:
- C++
helpviewer_keywords:
- generating pseudorandom numbers
- random numbers, generating
- numbers, pseudorandom
- rand function
- pseudorandom numbers
- numbers, generating pseudorandom
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 081e380dc639ed6a814913dd42c6fc1b55041b01
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43681129"
---
# <a name="rand"></a>rand

Gera um número pseudoaleatório, usando um algoritmo bem conhecido e totalmente reproduzível. Uma versão mais por meio de programação segura dessa função está disponível. ver [rand_s](rand-s.md). Os números gerados pelo **rand** não são criptograficamente seguros. Para mais criptograficamente a geração de números aleatórios, use [rand_s](rand-s.md) ou as funções declaradas na biblioteca padrão C++ em [ \<aleatório >](../../standard-library/random.md).

## <a name="syntax"></a>Sintaxe

```C
int rand( void );
```

## <a name="return-value"></a>Valor de retorno

**RAND** retorna um número pseudoaleatório, como descrito acima. Nenhum erro é retornado.

## <a name="remarks"></a>Comentários

O **rand** função retorna um inteiro pseudoaleatório no intervalo de 0 a **RAND_MAX** (32767). Use o [srand](srand.md) função para propagar o gerador de números pseudoaleatórios antes de chamar **rand**.

O **rand** função gera uma sequência bem conhecida e não é adequada para uso como uma função criptográfica. Para mais criptograficamente a geração de números aleatórios, use [rand_s](rand-s.md) ou as funções declaradas na biblioteca padrão C++ em [ \<aleatório >](../../standard-library/random.md). Para obter informações sobre o que há de errado com **rand** e como \<aleatório > lida com esses imprevistos, veja este vídeo intitulado [rand considerado prejudicial](https://channel9.msdn.com/Events/GoingNative/2013/rand-Considered-Harmful).

## <a name="requirements"></a>Requisitos

|Rotina|Cabeçalho necessário|
|-------------|---------------------|
|**rand**|\<stdlib.h>|

Para obter informações adicionais sobre compatibilidade, consulte [Compatibilidade](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Exemplo

```C
// crt_rand.c
// This program seeds the random-number generator
// with the time, then exercises the rand function.
//

#include <stdlib.h>
#include <stdio.h>
#include <time.h>

void SimpleRandDemo( int n )
{
   // Print n random numbers.
   int i;
   for( i = 0; i < n; i++ )
      printf( "  %6d\n", rand() );
}

void RangedRandDemo( int range_min, int range_max, int n )
{
   // Generate random numbers in the half-closed interval
   // [range_min, range_max). In other words,
   // range_min <= random number < range_max
   int i;
   for ( i = 0; i < n; i++ )
   {
      int u = (double)rand() / (RAND_MAX + 1) * (range_max - range_min)
            + range_min;
      printf( "  %6d\n", u);
   }
}

int main( void )
{
   // Seed the random-number generator with the current time so that
   // the numbers will be different every time we run.
   srand( (unsigned)time( NULL ) );

   SimpleRandDemo( 10 );
   printf("\n");
   RangedRandDemo( -100, 100, 10 );
}
```

```Output
22036
18330
11651
27464
18093
3284
11785
14686
11447
11285

   74
   48
   27
   65
   96
   64
   -5
  -42
  -55
   66
```

## <a name="see-also"></a>Consulte também

[Suporte a ponto flutuante](../../c-runtime-library/floating-point-support.md)<br/>
[srand](srand.md)<br/>
[rand_s](rand-s.md)<br/>
