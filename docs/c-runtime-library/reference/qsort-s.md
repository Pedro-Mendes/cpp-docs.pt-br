---
title: qsort_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- qsort_s
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
- qsort_s
dev_langs:
- C++
helpviewer_keywords:
- arrays [C++], sorting
- quick-sort algorithm
- qsort_s function
- sorting arrays
ms.assetid: 6ee817b0-4408-4355-a5d4-6605e419ab91
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b136dc29431164de195eeebf9085c2377664f869
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44105673"
---
# <a name="qsorts"></a>qsort_s

Executa uma classificação rápida. Uma versão de [qsort](qsort.md) com melhorias de segurança, conforme descrito em [Recursos de segurança no CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sintaxe

```C
void qsort_s(
   void *base,
   size_t num,
   size_t width,
   int (__cdecl *compare )(void *, const void *, const void *),
   void * context
);
```

### <a name="parameters"></a>Parâmetros

*base*<br/>
Início da matriz de destino.

*número*<br/>
Tamanho da matriz nos elementos.

*width*<br/>
Tamanho do elemento em bytes.

*compare*<br/>
Função de comparação. O primeiro argumento é o *contexto* ponteiro. O segundo argumento é um ponteiro para o *chave* para a pesquisa. O terceiro argumento é um ponteiro para o elemento da matriz a ser comparado com *chave*.

*context*<br/>
Um ponteiro para um contexto, que pode ser qualquer objeto que o *comparar* rotina precisa acessar.

## <a name="remarks"></a>Comentários

O **qsort_s** função implementa um algoritmo de classificação rápida para classificar uma matriz de *número* elementos, cada um dos *largura* bytes. O argumento *base* é um ponteiro para a base da matriz a ser classificado. **qsort_s** substitui essa matriz pelos elementos classificados. O argumento *comparar* é um ponteiro para uma rotina fornecida pelo usuário que compara dois elementos de matriz e retorna um valor que especifica seu relacionamento. **qsort_s** chamadas a *comparar* rotina um ou mais vezes durante a classificação, passando ponteiros para dois elementos de matriz em cada chamada:

```C
compare( context, (void *) & elem1, (void *) & elem2 );
```

A rotina deve comparar os elementos e, em seguida, retornar um dos seguintes valores:

|Valor retornado|Descrição|
|------------------|-----------------|
|< 0|**elem1** menor que **elem2**|
|0|**elem1** equivalente a **elem2**|
|> 0|**elem1** maior que **elem2**|

A matriz é classificada em ordem crescente, conforme definido pela função de comparação. Para classificar uma matriz em ordem decrescente, inverta o sentido de “maior que” e “menor que” na função de comparação.

Se parâmetros inválidos forem passados para a função, o manipulador de parâmetro inválido será invocado, conforme descrito em [Validação de Parâmetro](../../c-runtime-library/parameter-validation.md). Se a execução puder continuar, a função retornará e **errno** é definido como **EINVAL**. Para obter mais informações, consulte [errno, _doserrno, _sys_errlist e _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

### <a name="error-conditions"></a>Condições de Erro

|key|base|compare|num|largura|errno|
|---------|----------|-------------|---------|-----------|-----------|
|**NULL**|qualquer|qualquer|qualquer|qualquer|**EINVAL**|
|qualquer|**NULL**|qualquer|!= 0|qualquer|**EINVAL**|
|qualquer|qualquer|qualquer|qualquer|<= 0|**EINVAL**|
|qualquer|qualquer|**NULL**|qualquer|qualquer|**EINVAL**|

**qsort_s** tem o mesmo comportamento que **qsort** , mas tem o *contexto* parâmetro e define **errno**. Passando um *contexto* parâmetro, funções de comparação podem usar um ponteiro de objeto para acessar a funcionalidade do objeto ou outras informações que não está acessíveis por meio de um ponteiro de elemento. A adição do *contexto* parâmetro torna **qsort_s** mais seguro, pois *contexto* pode ser usado para evitar bugs de reentrância introduzidos ao usar variáveis estáticas para tornar compartilhado informações disponíveis para o *comparar* função.

## <a name="requirements"></a>Requisitos

|Rotina|Cabeçalho necessário|
|-------------|---------------------|
|**qsort_s**|\<stdlib.h> e \<search.h>|

Para obter informações adicionais sobre compatibilidade, consulte [Compatibilidade](../../c-runtime-library/compatibility.md).

**Bibliotecas:** todas as versões dos [Recursos da Biblioteca CRT](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Exemplo

O exemplo a seguir demonstra como usar o *contexto* parâmetro na **qsort_s** função. O *contexto* parâmetro torna mais fácil realizar classificações thread-safe. Em vez de usar variáveis estáticas que devem ser sincronizadas para garantir acesso thread-safe, passe um diferentes *contexto* parâmetro em cada classificação. Neste exemplo, um objeto de localidade é usado como o *contexto* parâmetro.

```cpp
// crt_qsort_s.cpp
// compile with: /EHsc /MT
#include <stdlib.h>
#include <stdio.h>
#include <search.h>
#include <process.h>
#include <locale.h>
#include <locale>
#include <windows.h>
using namespace std;

// The sort order is dependent on the code page.  Use 'chcp' at the
// command line to change the codepage.  When executing this application,
// the command prompt codepage must match the codepage used here:

#define CODEPAGE_850

#ifdef CODEPAGE_850
// Codepage 850 is the OEM codepage used by the command line,
// so \x00e1 is the German Sharp S in that codepage and \x00a4
// is the n tilde.

char *array1[] = { "wei\x00e1", "weis", "annehmen", "weizen", "Zeit",
                   "weit" };
char *array2[] = { "Espa\x00a4ol", "Espa\x00a4" "a", "espantado" };
char *array3[] = { "table", "tableux", "tablet" };

#define GERMAN_LOCALE "German_Germany.850"
#define SPANISH_LOCALE "Spanish_Spain.850"
#define ENGLISH_LOCALE "English_US.850"

#endif

#ifdef CODEPAGE_1252
   // If using codepage 1252 (ISO 8859-1, Latin-1), use \x00df
   // for the German Sharp S and \x001f for the n tilde.
char *array1[] = { "wei\x00df", "weis", "annehmen", "weizen", "Zeit",
                   "weit" };
char *array2[] = { "Espa\x00f1ol", "Espa\x00f1" "a", "espantado" };
char *array3[] = { "table", "tableux", "tablet" };

#define GERMAN_LOCALE "German_Germany.1252"
#define SPANISH_LOCALE "Spanish_Spain.1252"
#define ENGLISH_LOCALE "English_US.1252"

#endif

// The context parameter lets you create a more generic compare.
// Without this parameter, you would have stored the locale in a
// static variable, thus making sort_array vulnerable to thread
// conflicts.

int compare( void *pvlocale, const void *str1, const void *str2)
{
    char s1[256];
    char s2[256];
    strcpy_s(s1, 256, *(char**)str1);
    strcpy_s(s2, 256, *(char**)str2);
    _strlwr_s( s1, sizeof(s1) );
    _strlwr_s( s2, sizeof(s2) );

    locale& loc = *( reinterpret_cast< locale * > ( pvlocale));

    return use_facet< collate<char> >(loc).compare(s1,
       &s1[strlen(s1)], s2, &s2[strlen(s2)]);

}

void sort_array(char *array[], int num, locale &loc)
{
    qsort_s(array, num, sizeof(char*), compare, &loc);
}

void print_array(char *a[], int c)
{
   for (int i = 0; i < c; i++)
      printf("%s ", a[i]);
   printf("\n");

}

void sort_german(void * Dummy)
{
   sort_array(array1, 6, locale(GERMAN_LOCALE));
}

void sort_spanish(void * Dummy)
{
   sort_array(array2, 3, locale(SPANISH_LOCALE));
}

void sort_english(void * Dummy)
{
   sort_array(array3, 3, locale(ENGLISH_LOCALE));
}

int main( )
{
   int i;
   HANDLE threads[3];

   printf("Unsorted input:\n");
   print_array(array1, 6);
   print_array(array2, 3);
   print_array(array3, 3);

   // Create several threads that perform sorts in different
   // languages at the same time.

   threads[0] = reinterpret_cast<HANDLE>(
                 _beginthread( sort_german , 0, NULL));
   threads[1] = reinterpret_cast<HANDLE>(
                 _beginthread( sort_spanish, 0, NULL));
   threads[2] = reinterpret_cast<HANDLE>(
                 _beginthread( sort_english, 0, NULL));

   for (i = 0; i < 3; i++)
   {
      if (threads[i] == reinterpret_cast<HANDLE>(-1))
      {
         printf("Error creating threads.\n");
         exit(1);
      }
   }

   // Wait until all threads have terminated.
   WaitForMultipleObjects(3, threads, true, INFINITE);

   printf("Sorted output: \n");

   print_array(array1, 6);
   print_array(array2, 3);
   print_array(array3, 3);
}
```

### <a name="sample-output"></a>Saída de Exemplo

```Output
Unsorted input:
weiß weis annehmen weizen Zeit weit
Español España espantado
table tableux tablet
Sorted output:
annehmen weiß weis weit weizen Zeit
España Español espantado
table tablet tableux
```

## <a name="see-also"></a>Consulte também

[Pesquisando e classificando](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch_s](bsearch-s.md)<br/>
[_lsearch_s](lsearch-s.md)<br/>
[qsort](qsort.md)<br/>
