---
title: sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _sscanf_s_l
- sscanf_s
- _swscanf_s_l
- swscanf_s
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
apitype: DLLExport
f1_keywords:
- _stscanf_s
- sscanf_s
- swscanf_s
- _swscanf_s_l
- _stscanf_s_l
- _sscanf_s_l
dev_langs:
- C++
helpviewer_keywords:
- stscanf_s_l function
- stscanf_s function
- swscanf_s function
- swscanf_s_l function
- sscanf_s_l function
- _stscanf_s_l function
- strings [C++], reading data from
- sscanf_s function
- _swscanf_s_l function
- _stscanf_s function
- reading data, strings
- strings [C++], reading
- _sscanf_s_l function
ms.assetid: 956e65c8-00a5-43e8-a2f2-0f547ac9e56c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 08cdc1b3fe2d190bdc4a6cbb3d505378e6dcf6ae
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/22/2018
ms.locfileid: "34451817"
---
# <a name="sscanfs-sscanfsl-swscanfs-swscanfsl"></a>sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l

Lê dados formatados de uma cadeia de caracteres. Estas versões de [sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md) têm aprimoramentos de segurança, conforme descrito em [Recursos de segurança no CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sintaxe

```C
int sscanf_s(
   const char *buffer,
   const char *format [,
   argument ] ...
);
int _sscanf_s_l(
   const char *buffer,
   const char *format,
   locale_t locale [,
   argument ] ...
);
int swscanf_s(
   const wchar_t *buffer,
   const wchar_t *format [,
   argument ] ...
);
int _swscanf_s_l(
   const wchar_t *buffer,
   const wchar_t *format,
   locale_t locale [,
   argument ] ...
);
```

### <a name="parameters"></a>Parâmetros

*buffer*<br/>
Dados armazenados

*format*<br/>
Cadeia de caracteres de controle de formato. Para obter mais informações, consulte [Campos de especificação de formato: funções scanf e wscanf](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).

*argument*<br/>
Argumentos opcionais

*locale*<br/>
A localidade a ser usada

## <a name="return-value"></a>Valor de retorno

Cada uma dessas funções retorna o número de campos que são convertidos e atribuídos com êxito; o valor retornado não inclui campos que foram lidos, mas não atribuídos. Um valor retornado igual a 0 indica que nenhum campo foi atribuído. O valor de retorno é **EOF** para um erro ou se o fim da cadeia de caracteres for atingido antes da conversão primeiro.

Se *buffer* ou *formato* é um **nulo** ponteiro, o manipulador de parâmetro inválido é invocado, conforme descrito em [validação do parâmetro](../../c-runtime-library/parameter-validation.md). Se a execução é permitida para continuar, essas funções retornam -1 e defina **errno** para **EINVAL**

Para obter mais informações sobre esses e outros códigos de erro, consulte [errno, _doserrno, _sys_errlist e _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Comentários

O **sscanf_s** função lê dados de *buffer* no local que é fornecido por cada *argumento*. Os argumentos após a cadeia de caracteres de formato especificam ponteiros para variáveis que têm um tipo que corresponde a um especificador de tipo na *formato*. Ao contrário da versão menos segura [sscanf](sscanf-sscanf-l-swscanf-swscanf-l.md), um parâmetro de tamanho do buffer é necessário quando você usar os caracteres de campo do tipo **c**, **C**, **s**, **S**, ou conjuntos de controle que são incluídos na cadeia de caracteres **[]**. O tamanho do buffer em caracteres deve ser fornecido como um parâmetro adicional imediatamente após cada parâmetro de buffer que precisa dele. Por exemplo, se você estiver lendo uma cadeia de caracteres, o tamanho do buffer para essa cadeia de caracteres será passado conforme demonstrado a seguir:

```C
wchar_t ws[10];
swscanf_s(in_str, L"%9s", ws, (unsigned)_countof(ws)); // buffer size is 10, width specification is 9
```

O tamanho do buffer inclui o nulo de terminação. Um campo de especificação de largura pode ser usado para garantir que o token lido caiba no buffer. Se nenhum campo de especificação de largura for usado e o token lido for muito grande para caber no buffer, nada será gravado no buffer.

No caso de caracteres, um único caractere pode ser lido como demonstrado a seguir:

```C
wchar_t wc;
swscanf_s(in_str, L"%c", &wc, 1);
```

Este exemplo lê um único caractere da cadeia de caracteres de entrada e o armazena em um buffer de caractere largo. Quando vários caracteres para cadeias de caracteres terminadas em não nulo são lidos, inteiros sem sinal são usados como a especificação de largura e o tamanho do buffer.

```C
char c[4];
sscanf_s(input, "%4c", &c, (unsigned)_countof(c)); // not null terminated
```

Para obter mais informações, consulte os caracteres de campo do tipo [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md) e [scanf](../../c-runtime-library/scanf-type-field-characters.md).

> [!NOTE]
> O parâmetro de tamanho é do tipo **sem sinal**, não **size_t**. Ao compilar para destinos de 64 bits, use uma conversão estática para converter **countof** ou **sizeof** resultados para o tamanho correto.

O *formato* controles de argumento a interpretação da entrada de campos e tem o mesmo formulário e funcionar como o *formato* argumento para o **scanf_s** função. Se ocorrer cópia entre cadeias de caracteres que se sobrepõem, o comportamento será indefinido.

**swscanf_s** é uma versão de caractere largo de **sscanf_s**; os argumentos para **swscanf_s** são cadeias de caracteres do caractere largo. **sscanf_s** não processa multibyte caracteres hexadecimais. **swscanf_s** não trata hexadecimal de largura inteira Unicode ou caracteres de "zona de compatibilidade". Caso contrário, **swscanf_s** e **sscanf_s** se comportam de forma idêntica.

As versões dessas funções que têm o **_l** sufixo são idênticas, exceto que eles usam o parâmetro de localidade que é transmitido em vez da localidade do thread atual.

### <a name="generic-text-routine-mappings"></a>Mapeamentos da rotina de texto genérico

|Rotina TCHAR.H|_UNICODE e _MBCS não definidos|_MBCS definido|_UNICODE definido|
|---------------------|------------------------------------|--------------------|-----------------------|
|**stscanf_s**|**sscanf_s**|**sscanf_s**|**swscanf_s**|
|**stscanf_s_l**|**_sscanf_s_l**|**_sscanf_s_l**|**_swscanf_s_l**|

## <a name="requirements"></a>Requisitos

|Rotina|Cabeçalho necessário|
|-------------|---------------------|
|**sscanf_s**, **sscanf_s_l**|\<stdio.h>|
|**swscanf_s**, **swscanf_s_l**|\<stdio.h> ou \<wchar.h>|

Para obter informações adicionais sobre compatibilidade, consulte [Compatibilidade](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Exemplo

```C
// crt_sscanf_s.c
// This program uses sscanf_s to read data items
// from a string named tokenstring, then displays them.

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   char  tokenstring[] = "15 12 14...";
   char  s[81];
   char  c;
   int   i;
   float fp;

   // Input various data from tokenstring:
   // max 80 character string plus null terminator
   sscanf_s( tokenstring, "%s", s, (unsigned)_countof(s) );
   sscanf_s( tokenstring, "%c", &c, (unsigned)sizeof(char) );
   sscanf_s( tokenstring, "%d", &i );
   sscanf_s( tokenstring, "%f", &fp );

   // Output the data read
   printf_s( "String    = %s\n", s );
   printf_s( "Character = %c\n", c );
   printf_s( "Integer:  = %d\n", i );
   printf_s( "Real:     = %f\n", fp );
}
```

```Output
String    = 15
Character = 1
Integer:  = 15
Real:     = 15.000000
```

## <a name="see-also"></a>Consulte também

[E/S de fluxo](../../c-runtime-library/stream-i-o.md)<br/>
[fscanf, _fscanf_l, fwscanf, _fwscanf_l](fscanf-fscanf-l-fwscanf-fwscanf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[snprintf, _snprintf, _snprintf_l, _snwprintf, _snwprintf_l](snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)<br/>
