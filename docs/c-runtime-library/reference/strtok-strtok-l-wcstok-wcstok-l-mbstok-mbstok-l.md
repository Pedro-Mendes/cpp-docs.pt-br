---
title: strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbstok_l
- _mbstok
- wcstok
- _mbstok
- strtok
- _wcstok_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _mbstok
- strtok
- _tcstok
- wcstok
dev_langs:
- C++
helpviewer_keywords:
- mbstok_l function
- strings [C++], searching
- tcstok function
- _tcstok function
- _strtok_l function
- strtok function
- mbstok function
- wcstok_l function
- _mbstok function
- tcstok_l function
- tokens, finding in strings
- _mbstok_l function
- wcstok function
- _wcstok_l function
- _tcstok_l function
- strtok_l function
ms.assetid: 904cb734-f0d7-4d77-ba81-4791ddf461ae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5b714d8b78ecfc28db9f6e69308777ed53be7987
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43210867"
---
# <a name="strtok-strtokl-wcstok-wcstokl-mbstok-mbstokl"></a>strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l

Localiza o próximo token em uma cadeia de caracteres usando a localidade atual ou uma localidade específica que é informada. Versões mais seguras dessas funções estão disponíveis; consulte [strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l](strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md).

> [!IMPORTANT]
> **mbstok** e **mbstok_l** não pode ser usado em aplicativos executados no tempo de execução do Windows. Para obter mais informações, confira [Funções do CRT sem suporte em aplicativos da Plataforma Universal do Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sintaxe

```C
char *strtok(
   char *strToken,
   const char *strDelimit
);
wchar_t *wcstok(
   wchar_t *strToken,
   const wchar_t *strDelimit
);
unsigned char *_mbstok(
   unsigned char*strToken,
   const unsigned char *strDelimit
);
unsigned char *_mbstok(
   unsigned char*strToken,
   const unsigned char *strDelimit,
   _locale_t locale
);
```

### <a name="parameters"></a>Parâmetros

*strToken*<br/>
Cadeia de caracteres que contém o token ou os tokens.

*strDelimit*<br/>
Conjunto de caracteres delimitadores.

*locale*<br/>
Localidade a usar.

## <a name="return-value"></a>Valor de retorno

Retorna um ponteiro para o próximo token encontrado no *strToken*. Elas retornam **nulo** quando não há mais tokens são encontradas. Cada chamada modifica *strToken* substituindo um caractere nulo para o primeiro delimitador que ocorre após o token retornado.

## <a name="remarks"></a>Comentários

O **strtok** função localiza o próximo token no *strToken*. O conjunto de caracteres em *strDelimit* Especifica possíveis delimitadores de token a ser localizado na *strToken* na chamada atual. **wcstok** e **mbstok** são versões de caractere largo e caracteres multibyte **strtok**. Os argumentos e o valor de retorno **wcstok** são largos cadeias de caracteres; aqueles de **mbstok** são cadeias de caracteres multibyte. Caso contrário, essas três funções se comportam de forma idêntica.

> [!IMPORTANT]
> Essas funções acarretam uma ameaça em potencial em relação ao problema de estouro de buffer. Os problemas de estouro de buffer são um método frequente de ataque ao sistema, resultando em uma elevação de privilégio sem garantia. Para obter mais informações, consulte [Avoiding Buffer Overruns](/windows/desktop/SecBP/avoiding-buffer-overruns) (Evitando estouros de buffer).

Na primeira chamada para **strtok**, a função ignora delimitadores à esquerda e retorna um ponteiro para o primeiro token no *strToken*, encerrando o token com um caractere nulo. Mais tokens podem ser divididos, fora o restante da *strToken* por uma série de chamadas para **strtok**. Cada chamada para **strtok** modifica *strToken* inserindo um caractere nulo após o **token** retornado pela chamada. Para ler o próximo token de *strToken*, chame **strtok** com um **nulo** valor para o *strToken* argumento. O **nulo** *strToken* faz com que o argumento **strtok** para procurar o próximo token no modificado *strToken*. O *strDelimit* argumento pode assumir qualquer valor de uma chamada para o próximo, de modo que o conjunto de delimitadores pode variar.

O valor de saída é afetado pela configuração da categoria **LC_CTYPE** da localidade. Consulte [setlocale](setlocale-wsetlocale.md) para obter mais informações. As versões dessas funções sem o sufixo **_l** usam a localidade atual desse comportamento dependente da localidade. As versões com o sufixo **_l** são idênticas, exceto por usarem o parâmetro de localidade passado em seu lugar. Para obter mais informações, consulte [Localidade](../../c-runtime-library/locale.md).

> [!NOTE]
> Cada função usa uma variável estática de thread local para classificar a cadeia de caracteres em tokens. Portanto, vários threads simultaneamente podem chamar essas funções sem efeitos indesejáveis. No entanto, em um único thread, chamadas intercaladas para uma dessas funções é tende muito a causar dados corrompidos e resultados imprecisos. Ao classificar cadeias de caracteres diferentes, termine de classificar uma cadeia de caracteres antes de começar a analisar a próxima. Além disso, fique ciente do potencial de risco ao chamar uma dessas funções de dentro de um loop em que outra função seja chamada. Se a outra função acaba usando uma dessas funções, uma sequência intercalada de chamadas resultará, disparando os dados corrompidos.

### <a name="generic-text-routine-mappings"></a>Mapeamentos da rotina de texto genérico

|Rotina TCHAR.H|_UNICODE e _MBCS não definidos|_MBCS definido|_UNICODE definido|
|---------------------|------------------------------------|--------------------|-----------------------|
|**tcstok**|**strtok**|**_mbstok**|**wcstok**|
|**tcstok**|**_strtok_l**|**_mbstok_l**|**_wcstok_l**|

## <a name="requirements"></a>Requisitos

|Rotina|Cabeçalho necessário|
|-------------|---------------------|
|**strtok**|\<string.h>|
|**wcstok**|\<string.h> ou \<wchar.h>|
|**mbstok**, **mbstok_l**|\<mbstring.h>|

Para obter informações adicionais sobre compatibilidade, consulte [Compatibilidade](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Exemplo

```C
// crt_strtok.c
// compile with: /W3
// In this program, a loop uses strtok
// to print all the tokens (separated by commas
// or blanks) in the string named "string".
//
#include <string.h>
#include <stdio.h>

char string[] = "A string\tof ,,tokens\nand some  more tokens";
char seps[]   = " ,\t\n";
char *token;

int main( void )
{
   printf( "Tokens:\n" );

   // Establish string and get the first token:
   token = strtok( string, seps ); // C4996
   // Note: strtok is deprecated; consider using strtok_s instead
   while( token != NULL )
   {
      // While there are tokens in "string"
      printf( " %s\n", token );

      // Get next token:
      token = strtok( NULL, seps ); // C4996
   }
}
```

```Output
Tokens:
A
string
of
tokens
and
some
more
tokens
```

## <a name="see-also"></a>Consulte também

[Manipulação de cadeias de caracteres](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Localidade](../../c-runtime-library/locale.md)<br/>
[Interpretação de sequências de caracteres multibyte](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
