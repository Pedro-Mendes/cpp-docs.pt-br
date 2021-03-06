---
title: gmtime, _gmtime32, _gmtime64 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _gmtime32
- gmtime
- _gmtime64
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- gmtime
- _gmtime32
- _gmtime64
dev_langs:
- C++
helpviewer_keywords:
- gmtime32 function
- _gmtime64 function
- gmtime function
- time functions
- _gmtime32 function
- gmtime64 function
- time structure conversion
ms.assetid: 315501f3-477e-475d-a414-ef100ee0db27
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 28ce8b8e2367e1d4dd26672206557867c07827e5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32403954"
---
# <a name="gmtime-gmtime32-gmtime64"></a>gmtime, _gmtime32, _gmtime64

Converte um **time_t** tempo valor para um **tm** estrutura. Versões mais seguras dessas funções estão disponíveis; consulte [gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md).

## <a name="syntax"></a>Sintaxe

```C
struct tm *gmtime( const time_t *sourceTime );
struct tm *_gmtime32( const __time32_t *sourceTime );
struct tm *_gmtime64( const __time64_t *sourceTime );
```

### <a name="parameters"></a>Parâmetros

*sourceTime*<br/>
Ponteiro para a hora armazenada. A hora é representada como os segundos transcorridos desde a meia-noite (00:00:00) de 1º de janeiro de 1970, no horário UTC (Tempo Universal Coordenado).

## <a name="return-value"></a>Valor de retorno

Um ponteiro para uma estrutura do tipo [tm](../../c-runtime-library/standard-types.md). Os campos da estrutura retornado de manter o valor avaliado do *sourceTime* argumento em UTC em vez de hora local. Cada um dos campos de estrutura é do tipo **int**, da seguinte maneira:

|Campo|Descrição|
|-|-|
|**tm_sec**|Segundos após minuto (0 - 59).|
|**tm_min**|Minutos após a hora (0 - 59).|
|**tm_hour**|Horas desde a meia-noite (0 - 23).|
|**tm_mday**|Dia do mês (1-31).|
|**tm_mon**|Mês (0 - 11; Janeiro = 0).|
|**tm_year**|Ano (ano atual menos 1900).|
|**tm_wday**|Dia da semana (0 - 6; Domingo = 0).|
|**tm_yday**|Dia do ano (0 - 365; 1 de janeiro = 0).|
|**tm_isdst**|Sempre 0 para **gmtime**.|

Ambas as versões de 32 bits e 64 bits do **gmtime**, [mktime](mktime-mktime32-mktime64.md), [mkgmtime](mkgmtime-mkgmtime32-mkgmtime64.md), e [localtime](localtime-localtime32-localtime64.md) usam um comum **tm**  estrutura por thread para a conversão. Cada chamada para uma dessas funções destrói o resultado de qualquer chamada anterior. Se *sourceTime* representa uma data anterior a 1º de janeiro de 1970, meia-noite **gmtime** retorna **nulo**. Nenhum erro é retornado.

**gmtime64**, que usa o **__time64_t** estrutura, permite que as datas sejam expressas backup por meio de 23:59:59, 31 de dezembro de 3000 a UTC, enquanto **gmtime32** representar apenas datas até 23:59:59 18 de janeiro de 2038, UTC. Meia-noite de 1º de janeiro de 1970 é o limite inferior do intervalo de datas para ambas as funções.

**gmtime** é uma função embutida que é avaliada como **gmtime64**, e **time_t** é equivalente a **__time64_t** , a menos que **_USE_32BIT_TIME_ T** está definido. Se você deve forçar o compilador a interpretar **time_t** como o antigo 32-bit **time_t**, você pode definir **_USE_32BIT_TIME_T**, mas fazendo causas caso **gmtime** ser embutida para **gmtime32** e **time_t** seja definido como **__time32_t**. É recomendável que você não faça isso, pois não é permitido em plataformas de 64 bits e, de qualquer forma, seu aplicativo pode falhar após 18 de janeiro de 2038.

Essas funções validam seus parâmetros. Se *sourceTime* é um ponteiro nulo, ou se o *sourceTime* valor for negativo, essas funções para chamar um manipulador de parâmetro inválido, conforme descrito em [validação do parâmetro](../../c-runtime-library/parameter-validation.md) . Se a execução é permitida para continuar, as funções retornam **nulo** e defina **errno** para **EINVAL**.

## <a name="remarks"></a>Comentários

O **gmtime32** função divide o *sourceTime* valor e o armazena em uma estrutura em alocados estaticamente do tipo **tm**, definida no momento. H. O valor de *sourceTime* normalmente é obtido de uma chamada para o [tempo](time-time32-time64.md) função.

> [!NOTE]
> Na maioria dos casos, o ambiente de destino tenta determinar se o horário de verão está em vigor. A biblioteca em tempo de execução C presume que serão usadas as regras dos Estados Unidos para implementar o cálculo do DST (horário de verão).

## <a name="requirements"></a>Requisitos

|Rotina|Cabeçalho C necessário|Cabeçalho C++ necessário|
|-------------|---------------------|-|
|**gmtime**, **gmtime32**, **gmtime64**|\<time.h>|\<ctime > ou \<time.h >|

Para obter informações adicionais sobre compatibilidade, consulte [Compatibilidade](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Exemplo

```C
// crt_gmtime.c
// compile with: /W3
// This program uses _gmtime64 to convert a long-
// integer representation of coordinated universal time
// to a structure named newtime, then uses asctime to
// convert this structure to an output string.

#include <time.h>
#include <stdio.h>

int main( void )
{
   struct tm *newtime;
   __int64 ltime;
   char buff[80];

   _time64( &ltime );

   // Obtain coordinated universal time:
   newtime = _gmtime64( &ltime ); // C4996
   // Note: _gmtime64 is deprecated; consider using _gmtime64_s
   asctime_s( buff, sizeof(buff), newtime );
   printf( "Coordinated universal time is %s\n", buff );
}
```

```Output
Coordinated universal time is Tue Feb 12 23:11:31 2002
```

## <a name="see-also"></a>Consulte também

[Gerenciamento de Tempo](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[_mkgmtime, _mkgmtime32, _mkgmtime64](mkgmtime-mkgmtime32-mkgmtime64.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
