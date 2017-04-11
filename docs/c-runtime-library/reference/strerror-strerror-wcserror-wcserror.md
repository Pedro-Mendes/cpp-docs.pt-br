---
title: strerror, _strerror, _wcserror, __wcserror | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- strerror
- _strerror
- _wcserror
- __wcserror
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __sys_errlist
- wcserror
- _strerror
- __wcserror
- strerror
- __sys_nerr
- _tcserror
- _wcserror
- tcserror
dev_langs:
- C++
helpviewer_keywords:
- strerror function
- _strerror function
- __sys_errlist
- wcserror function
- error messages, printing
- __sys_nerr
- tcserror function
- printing error messages
- _wcserror function
- _tcserror function
- __wcserror function
- error messages, getting
ms.assetid: 27b72255-f627-43c0-8836-bcda8b003e14
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 8671b14d88848dff6961366d4ca059b3f1cf7c98
ms.lasthandoff: 02/25/2017

---
# <a name="strerror-strerror-wcserror-wcserror"></a>strerror, _strerror, _wcserror, __wcserror
Obtém uma cadeia de caracteres de mensagens de erro do sistema (`strerror`, `_wcserror`) ou formata uma cadeia caracteres de mensagens de erro fornecida pelo usuário (`_strerror`, `__wcserror`). Versões mais seguras dessas funções estão disponíveis; consulte [strerror_s, _strerror_s, _wcserror_s, \__wcserror_s](../../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md).  
  
## <a name="syntax"></a>Sintaxe  
  
```  
char *strerror(  
   int errnum   
);  
char *_strerror(  
   const char *strErrMsg   
);  
wchar_t * _wcserror(  
   int errnum   
);  
wchar_t * __wcserror(  
   const wchar_t *strErrMsg   
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `errnum`  
 Número do erro.  
  
 `strErrMsg`  
 Mensagem fornecida pelo usuário.  
  
## <a name="return-value"></a>Valor de retorno  
 Todas essas funções retornam um ponteiro para a cadeia de caracteres de mensagens de erro. Chamadas subsequentes podem substituir a cadeia de caracteres.  
  
## <a name="remarks"></a>Comentários  
 A função `strerror` mapeia `errnum` para uma cadeia de caracteres de mensagens de erro e retorna um ponteiro para a cadeia de caracteres. Nem `strerror` nem `_strerror` imprimem a mensagem: para fazer isso, você precisa chamar uma função de saída como [fprintf](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md):  
  
```  
if (( _access( "datafile",2 )) == -1 )  
   fprintf( stderr, _strerror(NULL) );  
```  
  
 Se `strErrMsg` for passado como `NULL`, `_strerror` retorna um ponteiro para uma cadeia de caracteres que contém a mensagem de erro do sistema para a última chamada da biblioteca que produziu um erro. A cadeia de caracteres de mensagens de erro é encerrada pelo caractere newline ('\n'). Se `strErrMsg` não for igual a `NULL`, então `_strerror` retorna um ponteiro para uma cadeia de caracteres que contém (nessa ordem) sua mensagem de cadeia de caracteres, dois-pontos, um espaço, a mensagem de erro do sistema para a última chamada da biblioteca que produz um erro e um caractere newline. Sua mensagem da cadeia de caracteres pode ter, no máximo, 94 caracteres de comprimento.  
  
 O número do erro real para `_strerror` é armazenado na variável [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Para produzir resultados precisos, chame `_strerror` imediatamente após uma rotina da biblioteca retornar um erro. Caso contrário, chamadas subsequentes para `strerror` ou `_strerror` podem substituir o valor `errno`.  
  
 `_wcserror` e `__wcserror` são as versões de caractere largo de `strerror` e `_strerror`, respectivamente.  
  
 `_strerror`, `_wcserror` e `__wcserror` não fazem parte da definição de ANSI; elas são extensões da Microsoft e recomendamos que não sejam utilizadas nos casos em que você deseja usar código portátil. No caso de compatibilidade com ANSI, ao invés disso, use `strerror`.  
  
 Para obter cadeias de caracteres de erros, recomendamos `strerror` ou `_wcserror` ao invés dos macros preteridos [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) e [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) e das funções internas preteridas `__sys_errlist` e `__sys_nerr`.  
  
### <a name="generic-text-routine-mappings"></a>Mapeamentos da rotina de texto genérico  
  
|Rotina TCHAR.H|_UNICODE e _MBCS não definidos|_MBCS definido|_UNICODE definido|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcserror`|`strerror`|`strerror`|`_wcserror`|  
  
## <a name="requirements"></a>Requisitos  
  
|Rotina|Cabeçalho necessário|  
|-------------|---------------------|  
|`strerror`|\<string.h>|  
|`_strerror`|\<string.h>|  
|`_wcserror`, `__wcserror`|\<string.h>|  
  
 Para obter mais informações sobre compatibilidade, consulte [Compatibilidade](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemplo  
 Veja o exemplo de [perror](../../c-runtime-library/reference/perror-wperror.md).  
  
## <a name="net-framework-equivalent"></a>Equivalente ao .NET Framework  
 [System::Exception::Message](https://msdn.microsoft.com/en-us/library/system.exception.message.aspx)  
  
## <a name="see-also"></a>Consulte também  
 [Manipulação de cadeias de caracteres](../../c-runtime-library/string-manipulation-crt.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror, _wperror](../../c-runtime-library/reference/perror-wperror.md)