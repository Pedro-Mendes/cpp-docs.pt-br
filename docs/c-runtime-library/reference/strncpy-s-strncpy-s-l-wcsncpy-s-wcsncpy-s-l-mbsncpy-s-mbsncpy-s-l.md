---
title: "strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsncpy_s_l"
  - "wcsncpy_s"
  - "_strncpy_s_l"
  - "strncpy_s"
  - "_mbsncpy_s"
  - "_wcsncpy_s_l"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_tcsncpy_s"
  - "_wcsncpy_s_l"
  - "strncpy_s"
  - "_strncpy_s_l"
  - "wcsncpy_s"
  - "_tcsncpy_s_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_wcsncpy_s_l function"
  - "_mbsnbcpy_s function"
  - "_tcsncpy_s_l function"
  - "mbsncpy_s function"
  - "strncpy_s_l function"
  - "_strncpy_s_l function"
  - "strncpy_s function"
  - "mbsncpy_s_l function"
  - "wcsncpy_s function"
  - "copying strings"
  - "strings [C++], copying"
  - "_mbsnbcpy_s_l function"
  - "_tcsncpy_s function"
  - "wcsncpy_s_l function"
ms.assetid: a971c800-94d1-4d88-92f3-a2fe236a4546
caps.latest.revision: 47
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# <a name="strncpys-strncpysl-wcsncpys-wcsncpysl-mbsncpys-mbsncpysl"></a>strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l
Copia caracteres de uma cadeia de caracteres para outra.  Essas versões do [strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md) tem aprimoramentos de segurança, conforme descrito em [Recursos de Segurança no CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
> [!IMPORTANT]
>  `_mbsncpy_s` e `_mbsncpy_s_l` não podem ser usados em aplicativos executados no Windows Runtime. Para obter mais informações, consulte [Funções de CRT sem suporte com /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Sintaxe  
  
```  
errno_t strncpy_s(  
   char *strDest,  
   size_t numberOfElements,  
   const char *strSource,  
   size_t count  
);  
errno_t _strncpy_s_l(  
   char *strDest,  
   size_t numberOfElements,  
   const char *strSource,  
   size_t count,  
   _locale_t locale  
);  
errno_t wcsncpy_s(  
   wchar_t *strDest,  
   size_t numberOfElements,  
   const wchar_t *strSource,  
   size_t count   
);  
errno_t _wcsncpy_s_l(  
   wchar_t *strDest,  
   size_t numberOfElements,  
   const wchar_t *strSource,  
   size_t count,  
   _locale_t locale  
);  
errno_t _mbsncpy_s(  
   unsigned char *strDest,  
   size_t numberOfElements,  
   const unsigned char *strSource,  
   size_t count   
);  
errno_t _mbsncpy_s_l(  
   unsigned char *strDest,  
   size_t numberOfElements,  
   const unsigned char *strSource,  
   size_t count,  
   locale_t locale  
);  
template <size_t size>  
errno_t strncpy_s(  
   char (&strDest)[size],  
   const char *strSource,  
   size_t count  
); // C++ only  
template <size_t size>  
errno_t _strncpy_s_l(  
   char (&strDest)[size],  
   const char *strSource,  
   size_t count,  
   _locale_t locale  
); // C++ only  
template <size_t size>  
errno_t wcsncpy_s(  
   wchar_t (&strDest)[size],  
   const wchar_t *strSource,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _wcsncpy_s_l(  
   wchar_t (&strDest)[size],  
   const wchar_t *strSource,  
   size_t count,  
   _locale_t locale  
); // C++ only  
template <size_t size>  
errno_t _mbsncpy_s(  
   unsigned char (&strDest)[size],  
   const unsigned char *strSource,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _mbsncpy_s_l(  
   unsigned char (&strDest)[size],  
   const unsigned char *strSource,  
   size_t count,  
   locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `strDest`  
 Cadeia de caracteres de destino.  
  
 `numberOfElements`  
 O tamanho da cadeia de caracteres de destino, em caracteres.  
  
 `strSource`  
 Cadeia de caracteres de origem.  
  
 `count`  
 Número de caracteres a ser copiado ou [_TRUNCATE](../../c-runtime-library/truncate.md).  
  
 `locale`  
 A localidade a ser usada.  
  
## <a name="return-value"></a>Valor de retorno  
 Zero se tiver êxito, `STRUNCATE` se ocorreu truncamento, caso contrário, um código de erro.  
  
### <a name="error-conditions"></a>Condições de Erro  
  
|`strDest`|`numberOfElements`|`strSource`|Valor retornado|Conteúdo de `strDest`|  
|---------------|------------------------|-----------------|------------------|---------------------------|  
|`NULL`|qualquer|qualquer|`EINVAL`|não modificado|  
|qualquer|qualquer|`NULL`|`EINVAL`|`strDest`[0] definido como 0|  
|qualquer|0|qualquer|`EINVAL`|não modificado|  
|não é `NULL`|muito pequeno|qualquer|`ERANGE`|`strDest`[0] definido como 0|  
  
## <a name="remarks"></a>Comentários  
 Essas funções tentam copiar os primeiros `D` caracteres de `strSource` para `strDest`, em que `D` é inferior a `count` e o comprimento de `strSource`. Se esses `D` caracteres se ajustarão dentro de `strDest` (cujo tamanho é determinado como `numberOfElements`) e ainda deixam espaço para um terminador nulo, então, esses caracteres são copiados e uma nova terminação nula é anexada; caso contrário, `strDest`[0] é definido para o caractere nulo e o manipulador de parâmetro inválido é chamado, conforme descrito em [validação de parâmetro](../../c-runtime-library/parameter-validation.md).  
  
 Há uma exceção para o parágrafo acima. Se `count` é `_TRUNCATE`, então, a maioria de `strSource` que se ajustará em `strDest` é copiado enquanto ainda deixa espaço para a terminação nula que sempre é anexada.  
  
 Por exemplo,  
  
 `char dst[5];`  
  
 `strncpy_s(dst, 5, "a long string", 5);`  
  
 significa que, pedimos para `strncpy_s` copiar cinco caracteres em um buffer com cinco bytes de comprimento; isso não deixaria nenhum espaço para o terminador nulo, portanto, `strncpy_s` zera a cadeia de caracteres e chama o manipulador de parâmetro inválido.  
  
 Se for necessário o comportamento de truncamento, use `_TRUNCATE` ou (`size` – 1):  
  
 `strncpy_s(dst, 5, "a long string", _TRUNCATE);`  
  
 `strncpy_s(dst, 5, "a long string", 4);`  
  
 Observe que diferentemente de `strncpy`, se `count` é maior que o comprimento de `strSource`, a cadeia de caracteres de destino NÃO é preenchida com caracteres nulos até comprimento `count`.  
  
 O comportamento de `strncpy_s` é indefinido se as cadeias de origem e destino se sobrepõem.  
  
 Se `strDest` ou `strSource` for `NULL` ou `numberOfElements` é 0, o manipulador de parâmetro inválido é invocado. Se a execução puder continuar, a função retornará `EINVAL` e definirá `errno` como `EINVAL`.  
  
 `wcsncpy_s` e `_mbsncpy_s` são versões de caracteres largos e de caracteres multibyte de `strncpy_s`. Os argumentos e o valor retornado de `wcsncpy_s` e `mbsncpy_s` variam de acordo. Essas seis funções se comportam de forma idêntica.  
  
 O valor de saída é afetado pela configuração da categoria `LC_CTYPE` da localidade; consulte [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) para obter mais informações. As versões dessas funções sem o sufixo `_l` usam a localidade atual desse comportamento dependente da localidade. As versões com o sufixo `_l` são idênticas, exceto por usarem o parâmetro de localidade passado em seu lugar. Para obter mais informações, consulte [Localidade](../../c-runtime-library/locale.md).  
  
 Em C++, o uso dessas funções é simplificado pelas sobrecargas de modelo; as sobrecargas podem inferir o tamanho do buffer automaticamente (eliminando a necessidade de especificar um argumento de tamanho) e podem substituir automaticamente funções mais antigas e não seguras por suas equivalentes mais recentes e seguras. Para obter mais informações, consulte [Sobrecargas de modelo seguro](../../c-runtime-library/secure-template-overloads.md).  
  
 As versões de depuração dessas funções preenchem primeiro o buffer com 0xFD. Para desabilitar esse comportamento, use [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
### <a name="generic-text-routine-mappings"></a>Mapeamentos da rotina de texto genérico  
  
|Rotina TCHAR.H|_UNICODE e _MBCS não definidos|_MBCS definido|_UNICODE definido|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsncpy_s`|`strncpy_s`|`_mbsnbcpy_s`|`wcsncpy_s`|  
|`_tcsncpy_s_l`|`_strncpy_s_l`|`_mbsnbcpy_s_l`|`_wcsncpy_s_l`|  
  
> [!NOTE]
>  strncpy_s_l, `_wcsncpy_s_l` e `_mbsncpy_s_l` não têm nenhuma dependência de localidade e são fornecidas apenas para `_tcsncpy_s_l` e não se destinam a serem chamadas diretamente.  
  
## <a name="requirements"></a>Requisitos  
  
|Rotina|Cabeçalho necessário|  
|-------------|---------------------|  
|`strncpy_s`, `_strncpy_s_l`|\<string.h>|  
|`wcsncpy_s`, `_wcsncpy_s_l`|\<string.h> ou \<wchar.h>|  
|`_mbsncpy_s`, `_mbsncpy_s_l`|\<mbstring.h>|  
  
 Para obter mais informações sobre compatibilidade, consulte [Compatibilidade](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemplo  
  
```  
// crt_strncpy_s_1.cpp  
// compile with: /MTd  
  
// these #defines enable secure template overloads  
// (see last part of Examples() below)  
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES 1   
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT 1  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <string.h>  
#include <crtdbg.h>  // For _CrtSetReportMode  
#include <errno.h>  
  
// This example uses a 10-byte destination buffer.  
  
errno_t strncpy_s_tester( const char * src,  
                          int count )  
{  
   char dest[10];  
  
   printf( "\n" );  
  
   if ( count == _TRUNCATE )  
      printf( "Copying '%s' to %d-byte buffer dest with truncation semantics\n",  
               src, _countof(dest) );  
   else  
      printf( "Copying %d chars of '%s' to %d-byte buffer dest\n",  
              count, src, _countof(dest) );  
  
   errno_t err = strncpy_s( dest, _countof(dest), src, count );  
  
   printf( "    new contents of dest: '%s'\n", dest );  
  
   return err;  
}  
  
void Examples()  
{  
   strncpy_s_tester( "howdy", 4 );  
   strncpy_s_tester( "howdy", 5 );  
   strncpy_s_tester( "howdy", 6 );  
  
   printf( "\nDestination buffer too small:\n" );  
   strncpy_s_tester( "Hi there!!", 10 );  
  
   printf( "\nTruncation examples:\n" );  
  
   errno_t err = strncpy_s_tester( "How do you do?", _TRUNCATE );  
   printf( "    truncation %s occur\n", err == STRUNCATE ? "did"  
                                                       : "did not" );  
  
   err = strncpy_s_tester( "Howdy.", _TRUNCATE );  
   printf( "    truncation %s occur\n", err == STRUNCATE ? "did"  
                                                       : "did not" );  
  
   printf( "\nSecure template overload example:\n" );  
  
   char dest[10];  
   strncpy( dest, "very very very long", 15 );  
   // With secure template overloads enabled (see #defines at  
   // top of file), the preceding line is replaced by  
   //    strncpy_s( dest, _countof(dest), "very very very long", 15 );  
   // Instead of causing a buffer overrun, strncpy_s invokes  
   // the invalid parameter handler.  
   // If secure template overloads were disabled, strncpy would  
   // copy 15 characters and overrun the dest buffer.  
   printf( "    new contents of dest: '%s'\n", dest );  
}  
  
void myInvalidParameterHandler(  
   const wchar_t* expression,  
   const wchar_t* function,   
   const wchar_t* file,   
   unsigned int line,   
   uintptr_t pReserved)  
{  
   wprintf(L"Invalid parameter handler invoked: %s\n", expression);  
}  
  
int main( void )  
{  
   _invalid_parameter_handler oldHandler, newHandler;  
  
   newHandler = myInvalidParameterHandler;  
   oldHandler = _set_invalid_parameter_handler(newHandler);  
   // Disable the message box for assertions.  
   _CrtSetReportMode(_CRT_ASSERT, 0);  
  
   Examples();  
}  
```  
  
```Output  
Copying 4 chars of 'howdy' to 10-byte buffer dest  
    new contents of dest: 'howd'  
  
Copying 5 chars of 'howdy' to 10-byte buffer dest  
    new contents of dest: 'howdy'  
  
Copying 6 chars of 'howdy' to 10-byte buffer dest  
    new contents of dest: 'howdy'  
  
Destination buffer too small:  
  
Copying 10 chars of 'Hi there!!' to 10-byte buffer dest  
Invalid parameter handler invoked: (L"Buffer is too small" && 0)  
    new contents of dest: ''  
  
Truncation examples:  
  
Copying 'How do you do?' to 10-byte buffer dest with truncation semantics  
    new contents of dest: 'How do yo'  
    truncation did occur  
  
Copying 'Howdy.' to 10-byte buffer dest with truncation semantics  
    new contents of dest: 'Howdy.'  
    truncation did not occur  
  
Secure template overload example:  
Invalid parameter handler invoked: (L"Buffer is too small" && 0)  
    new contents of dest: ''  
```  
  
## <a name="example"></a>Exemplo  
  
```  
// crt_strncpy_s_2.c  
// contrasts strncpy and strncpy_s  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   char a[20] = "test";  
   char s[20];  
  
   // simple strncpy usage:  
  
   strcpy_s( s, 20, "dogs like cats" );  
   printf( "Original string:\n   '%s'\n", s );  
  
   // Here we can't use strncpy_s since we don't   
   // want null termination  
   strncpy( s, "mice", 4 );  
   printf( "After strncpy (no null-termination):\n   '%s'\n", s );  
   strncpy( s+5, "love", 4 );  
   printf( "After strncpy into middle of string:\n   '%s'\n", s );  
  
   // If we use strncpy_s, the string is terminated   
   strncpy_s( s, _countof(s), "mice", 4 );  
   printf( "After strncpy_s (with null-termination):\n   '%s'\n", s );  
  
}  
```  
  
```Output  
Original string:  
   'dogs like cats'  
After strncpy (no null-termination):  
   'mice like cats'  
After strncpy into middle of string:  
   'mice love cats'  
After strncpy_s (with null-termination):  
   'mice'  
```  
  
## <a name="net-framework-equivalent"></a>Equivalente ao .NET Framework  
 [System::String::Copy](https://msdn.microsoft.com/en-us/library/system.string.copy.aspx)  
  
## <a name="see-also"></a>Consulte também  
 [Manipulação de cadeias de caracteres](../../c-runtime-library/string-manipulation-crt.md)   
 [Localidade](../../c-runtime-library/locale.md)   
 [Interpretação de sequências de caracteres multibyte](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [_mbsnbcpy, _mbsnbcpy_l](../../c-runtime-library/reference/mbsnbcpy-mbsnbcpy-l.md)   
 [strcat_s, wcscat_s, _mbscat_s](../../c-runtime-library/reference/strcat-s-wcscat-s-mbscat-s.md)   
 [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strcpy_s, wcscpy_s, _mbscpy_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)   
 [strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l](../../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)   
 [strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn, wcsspn, _mbsspn, _mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)