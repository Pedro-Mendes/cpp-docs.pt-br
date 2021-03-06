---
title: _splitpath_s, _wsplitpath_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wsplitpath_s
- _splitpath_s
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wsplitpath_s
- splitpath_s
- _splitpath_s
- wsplitpath_s
dev_langs:
- C++
helpviewer_keywords:
- splitpath_s function
- pathnames
- _splitpath_s function
- _wsplitpath_s function
- path names
- wsplitpath_s function
ms.assetid: 30fff3e2-cd00-4eb6-b5a2-65db79cb688b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e5fd1407aa6c2b7630e0720eeec179ca27e7d31a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32417426"
---
# <a name="splitpaths-wsplitpaths"></a>_splitpath_s, _wsplitpath_s

Divide um nome de caminho em componentes. Estas são versões de [_splitpath, _wsplitpath](splitpath-wsplitpath.md) com aprimoramentos de segurança, conforme descrito em [Recursos de Segurança no CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sintaxe

```C
errno_t _splitpath_s(
   const char * path,
   char * drive,
   size_t driveNumberOfElements,
   char * dir,
   size_t dirNumberOfElements,
   char * fname,
   size_t nameNumberOfElements,
   char * ext,
   size_t extNumberOfElements
);
errno_t _wsplitpath_s(
   const wchar_t * path,
   wchar_t * drive,
   size_t driveNumberOfElements,
   wchar_t *dir,
   size_t dirNumberOfElements,
   wchar_t * fname,
   size_t nameNumberOfElements,
   wchar_t * ext,
   size_t extNumberOfElements
);
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>
errno_t _splitpath_s(
   const char *path,
   char (&drive)[drivesize],
   char (&dir)[dirsize],
   char (&fname)[fnamesize],
   char (&ext)[extsize]
); // C++ only
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>
errno_t _wsplitpath_s(
   const wchar_t *path,
   wchar_t (&drive)[drivesize],
   wchar_t (&dir)[dirsize],
   wchar_t (&fname)[fnamesize],
   wchar_t (&ext)[extsize]
); // C++ only
```

### <a name="parameters"></a>Parâmetros

*path*<br/>
Caminho completo.

*Dirigir*<br/>
Unidade de letra, seguida por dois-pontos (**:**). Você pode passar **nulo** para esse parâmetro se você não precisa a letra da unidade.

*driveNumberOfElements*<br/>
O tamanho do *unidade* buffer em caracteres de byte único ou grande. Se *unidade* é **nulo**, esse valor deve ser 0.

*dir*<br/>
Caminho do diretório, incluindo barra à direita. Barras duplas ( **/** ), barras invertidas ( **\\** ), ou ambos podem ser usadas. Você pode passar **nulo** para esse parâmetro se o caminho do diretório não é necessário.

*dirNumberOfElements*<br/>
O tamanho do *dir* buffer em caracteres de byte único ou grande. Se *dir* é **nulo**, esse valor deve ser 0.

*fname*<br/>
Nome de arquivo base (sem extensão). Você pode passar **nulo** para esse parâmetro se o nome do arquivo não é necessário.

*nameNumberOfElements*<br/>
O tamanho do *fname* buffer em caracteres de byte único ou grande. Se *fname* é **nulo**, esse valor deve ser 0.

*ext*<br/>
Extensão de nome de arquivo, incluindo à esquerda período (**.**). Você pode passar **nulo** para esse parâmetro se a extensão de nome de arquivo não é necessário.

*extNumberOfElements*<br/>
O tamanho de *ext* buffer em caracteres de byte único ou grande. Se *ext* é **nulo**, esse valor deve ser 0.

## <a name="return-value"></a>Valor de retorno

Zero se for bem-sucedido; um código de erro em caso de falha.

### <a name="error-conditions"></a>Condições de Erro

|Condição|Valor de retorno|
|---------------|------------------|
|*caminho* é **nulo**|**EINVAL**|
|*unidade* é **nulo**, *driveNumberOfElements* é diferente de zero|**EINVAL**|
|*unidade* é não -**nulo**, *driveNumberOfElements* é zero|**EINVAL**|
|*dir* é **nulo**, *dirNumberOfElements* é diferente de zero|**EINVAL**|
|*dir* é não -**nulo**, *dirNumberOfElements* é zero|**EINVAL**|
|*fname* é **nulo**, *nameNumberOfElements* é diferente de zero|**EINVAL**|
|*fname* é não -**nulo**, *nameNumberOfElements* é zero|**EINVAL**|
|*ext* é **nulo**, *extNumberOfElements* é diferente de zero|**EINVAL**|
|*ext* é não -**nulo**, *extNumberOfElements* é zero|**EINVAL**|

Se qualquer uma das condições acima ocorrer, o manipulador de parâmetro inválido será invocado, conforme descrito em [Validação de parâmetro](../../c-runtime-library/parameter-validation.md). Se a execução é permitida para continuar, essas funções definido **errno** para **EINVAL** e retornar **EINVAL**.

Se qualquer um dos buffers for muito curto para manter o resultado, essas funções limpar todos os buffers de cadeias de caracteres vazias, definir **errno** para **ERANGE**e retornar **ERANGE**.

## <a name="remarks"></a>Comentários

O **splitpath_s** função quebras de um caminho em quatro componentes. **splitpath_s** manipula automaticamente os argumentos da cadeia de caracteres multibyte conforme apropriado, reconhecer sequências de caracteres multibyte de acordo com a página de código multibyte em uso no momento. **wsplitpath_s** é uma versão de caractere largo de **splitpath_s**; os argumentos para **wsplitpath_s** são cadeias de caracteres do caractere largo. Caso contrário, essas funções se comportam de forma idêntica

### <a name="generic-text-routine-mappings"></a>Mapeamentos da rotina de texto genérico

|Rotina TCHAR.H|_UNICODE e _MBCS não definidos|_MBCS definido|_UNICODE definido|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsplitpath_s**|**_splitpath_s**|**_splitpath_s**|**_wsplitpath_s**|

Cada componente do caminho completo é armazenado em um buffer separado; as constantes de manifesto **max_drive**, **max_dir**, **max_fname**, e **max_ext** (definido em STDLIB. H) Especifique o tamanho máximo permitido para cada componente de arquivo. Componentes de arquivo maiores do que as constantes de manifesto correspondentes causam corrupção de heap.

A tabela a seguir lista os valores das constantes do manifesto.

|Nome|Valor|
|----------|-----------|
|_MAX_DRIVE|3|
|_MAX_DIR|256|
|_MAX_FNAME|256|
|_MAX_EXT|256|

Se o caminho completo não tem um componente (por exemplo, um nome de arquivo), **splitpath_s** atribui uma cadeia de caracteres vazia ao buffer correspondente.

No C++, o uso dessas funções é simplificado por sobrecargas de modelo. As sobrecargas podem inferir automaticamente o tamanho do buffer, eliminando a necessidade de especificar um argumento de tamanho. Para obter mais informações, consulte [Sobrecargas de modelo seguro](../../c-runtime-library/secure-template-overloads.md).

As versões de depuração dessas funções preenchem primeiro o buffer com 0xFD. Para desabilitar esse comportamento, use [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

## <a name="requirements"></a>Requisitos

|Rotina|Cabeçalho necessário|
|-------------|---------------------|
|**_splitpath_s**|\<stdlib.h>|
|**_wsplitpath_s**|\<stdlib.h> ou \<wchar.h>|

Para obter informações adicionais sobre compatibilidade, consulte [Compatibilidade](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Exemplo

Veja o exemplo de [_makepath_s, _wmakepath_s](makepath-s-wmakepath-s.md).

## <a name="see-also"></a>Consulte também

[Manipulação de Arquivos](../../c-runtime-library/file-handling.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
[_setmbcp](setmbcp.md)<br/>
