---
title: _configthreadlocale | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _configthreadlocale
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _configthreadlocale
- configthreadlocale
dev_langs:
- C++
helpviewer_keywords:
- configthreadlocale function
- locales, per-thread
- _configthreadlocale function
- per-thread locale
- thread locale
ms.assetid: 10e4050e-b587-4f30-80bc-6c76b35fc770
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7531a5849bc1e86d469a12747b5c4648b76c9117
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32395771"
---
# <a name="configthreadlocale"></a>_configthreadlocale

Configura operações de localidade por thread.

## <a name="syntax"></a>Sintaxe

```C
int _configthreadlocale( int per_thread_locale_type );
```

### <a name="parameters"></a>Parâmetros

*per_thread_locale_type*<br/>
A opção a ser definida. Uma das opções listadas na tabela a seguir.

## <a name="return-value"></a>Valor de retorno

O status de localidade por thread anterior (**_DISABLE_PER_THREAD_LOCALE** ou **_ENABLE_PER_THREAD_LOCALE**), ou -1 em caso de falha.

## <a name="remarks"></a>Comentários

O **_configurethreadlocale** função é usada para controlar o uso de localidades específicas de thread. Usar um desses *per_thread_locale_type* opções para especificar ou determinar o status de localidade por thread:

|||
|-|-|
**_ENABLE_PER_THREAD_LOCALE**|Faça o thread atual usar uma localidade específica do thread. As chamadas subsequentes para **setlocale** neste thread afeta somente a localidade do thread.
**_DISABLE_PER_THREAD_LOCALE**|Faça o thread atual usar a localidade global. As chamadas subsequentes para **setlocale** neste thread afetar outros threads usando a localidade global.
**0**|Recupera a configuração atual para este thread específico.

Essas funções afetam o comportamento de **setlocale**, **tsetlocale**, **wsetlocale**, e **setmbcp**. Quando a localidade por thread é desabilitada, qualquer subsequente chamada para **setlocale** ou **wsetlocale** altera a localidade de todos os threads que usam a localidade global. Quando a localidade por thread é habilitada, **setlocale** ou **wsetlocale** afeta somente a localidade do thread atual.

Se você usar **_configurethreadlocale** para habilitar uma localidade por thread, recomendamos que você chamar **setlocale** ou **wsetlocale** para definir a localidade preferencial nesse thread Depois disso.

Se *per_thread_locale_type* não é um dos valores listados na tabela, essa função invoca o manipulador de parâmetro inválido, conforme descrito em [validação do parâmetro](../../c-runtime-library/parameter-validation.md). Se a execução é permitida para continuar, esta função define **errno** para **EINVAL** e retorna -1.

## <a name="requirements"></a>Requisitos

|Rotina|Cabeçalho necessário|
|-------------|---------------------|
|**_configthreadlocale**|\<locale.h>|

## <a name="example"></a>Exemplo

```cpp
// crt_configthreadlocale.cpp
//
// This program demonstrates the use of _configthreadlocale when
// using two independent threads.
//
// Compile by using: cl /EHsc /W4 crt_configthreadlocale.cpp

#include <locale.h>
#include <mbctype.h>
#include <process.h>
#include <windows.h>
#include <stdio.h>
#include <time.h>

#define BUFF_SIZE 100

// Retrieve the date and time in the current
// locale's format.
int get_time(unsigned char* str)
{
    __time64_t  ltime;
    struct tm   thetime;

    // Retieve the time
    _time64(&ltime);
    _gmtime64_s(&thetime, &ltime);

    // Format the current time structure into a string
    // using %#x is the long date representation,
    // appropriate to the current locale
    if (!strftime((char *)str, BUFF_SIZE, "%#x",
                  (const struct tm*)&thetime))
    {
        printf("strftime failed!\n");
        return -1;
    }
    return 0;
}

// This thread sets its locale to German
// and prints the time.
unsigned __stdcall SecondThreadFunc( void* /*pArguments*/ )
{
    unsigned char str[BUFF_SIZE];

    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);

    // Set the thread code page
    _setmbcp(_MB_CP_ANSI);

    // Set the thread locale
    printf("The thread locale is now set to %s.\n",
           setlocale(LC_ALL, "German"));

    // Retrieve the time string from the helper function
    if (get_time(str) == 0)
    {
        printf("The time in German locale is: '%s'\n", str);
    }

    _endthreadex( 0 );
    return 0;
}

// The main thread spawns a second thread (above) and then
// sets the locale to English and prints the time.
int main()
{
    HANDLE          hThread;
    unsigned        threadID;
    unsigned char   str[BUFF_SIZE];

    // Enable per-thread locale causes all subsequent locale
    // setting changes in this thread to only affect this thread.
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);

    // Retrieve the time string from the helper function
    printf("The thread locale is now set to %s.\n",
           setlocale(LC_ALL, "English"));

    // Create the second thread.
    hThread = (HANDLE)_beginthreadex( NULL, 0, &SecondThreadFunc,
                                      NULL, 0, &threadID );

    if (get_time(str) == 0)
    {
        // Retrieve the time string from the helper function
        printf("The time in English locale is: '%s'\n\n", str);
    }

    // Wait for the created thread to finish.
    WaitForSingleObject( hThread, INFINITE );

    // Destroy the thread object.
    CloseHandle( hThread );
}
```

```Output
The thread locale is now set to English_United States.1252.
The time in English locale is: 'Wednesday, May 12, 2004'

The thread locale is now set to German_Germany.1252.
The time in German locale is: 'Mittwoch, 12. Mai 2004'
```

## <a name="see-also"></a>Consulte também

[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[_beginthread, _beginthreadex](beginthread-beginthreadex.md)<br/>
[Localidade](../../c-runtime-library/locale.md)<br/>
[Multithread e localidades](../../parallel/multithreading-and-locales.md)<br/>
