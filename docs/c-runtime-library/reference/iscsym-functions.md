---
title: iscsym, iscsymf, __iscsym, __iswcsym, __iscsymf, __iswcsymf, _iscsym_l, _iswcsym_l, _iscsymf_l, _iswcsymf_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _iswcsym_l
- __iswcsym
- __iscsym
- _iswcsymf_l
- _iscsym_l
- __iswcsymf
- __iscsymf
- _iscsymf_l
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _iswcsym_l
- _iswcsymf_l
- iscsymf
- iswcsymf
- __iswcsym
- __iswcsymf
- iscsym
- iswcsym
- __iscsym
- _iscsym_l
- _iscsymf_l
- __iscsymf
- ctype/iscsym
- ctype/iscsymf
- ctype/__iscsym
- ctype/__iscsymf
- ctype/__iscsym_l
- ctype/__iscsymf_l
- ctype/__iswcsym
- ctype/__iswcsymf
- ctype/__iswcsym_l
- ctype/__iswcsymf_l
dev_langs:
- C++
helpviewer_keywords:
- iscsymf_l function
- iswsym_l function
- _iswcsym_l function
- iscsym_l function
- _iscsymf_l function
- _iswcsymf_l function
- _iscsym_l function
- __iscsym function
- __iswcsymf function
- iswsymf_l function
- __iscsymf function
- __iswcsym function
- iscsym function
- iscsymf function
ms.assetid: 944dfb99-f2b8-498c-9f55-dbcf370d0a2c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b1561e93fc19832607d304f3d087ab33b04040de
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32401916"
---
# <a name="iscsym-iscsymf-iscsym-iswcsym-iscsymf-iswcsymf-iscsyml-iswcsyml-iscsymfl-iswcsymfl"></a>iscsym, iscsymf, __iscsym, __iswcsym, __iscsymf, __iswcsymf, _iscsym_l, _iswcsym_l, _iscsymf_l, _iswcsymf_l

Determine se um inteiro representa um caractere que pode ser usado em um identificador.

## <a name="syntax"></a>Sintaxe

```C
int __iscsym(
   int c
);
int __iswcsym(
   wint_t c
);
int __iscsymf(
   int c
);
int __iswcsymf(
   wint_t c
);
int _iscsym_l(
   int c,
   _locale_t locale
);
int _iswcsym_l(
   wint_t c,
   _locale_t locale
);
int _iscsymf_l(
   int c,
   _locale_t locale
);
int _iswcsymf_l(
   wint_t c,
   _locale_t locale
);
#define iscsym __iscsym
#define iscsymf __iscsymf
```

### <a name="parameters"></a>Parâmetros

*c*<br/>
Inteiro a ser testado. *c* deve estar no intervalo de 0 a 255 para a versão de caractere estreito da função.

*locale*<br/>
A localidade a ser usada.

## <a name="return-value"></a>Valor de retorno

Ambos **iscsym** e **iswcsym** retornar um valor diferente de zero se *c* é uma letra, um sublinhado ou um dígito. Ambos **iscsymf** e **iswcsymf** retornar um valor diferente de zero se *c* é uma letra ou um sublinhado. Cada uma dessas rotinas retornará 0 se *c* não satisfaz a condição de teste. As versões dessas funções com o **_l** sufixo são idênticas, exceto que eles usam o *localidade* passado em vez da localidade atual para o seu comportamento dependente de localidade. Para obter mais informações, consulte [Localidade](../../c-runtime-library/locale.md).

## <a name="remarks"></a>Comentários

Essas rotinas são definidas como macros, a menos que a macro do pré-processador _CTYPE_DISABLE_MACROS seja definida. Quando você usa as versões de macro dessas rotinas, os argumentos podem ser avaliados mais de uma vez. Tenha cuidado ao usar expressões que têm efeitos colaterais na lista de argumentos.

Para compatibilidade com versões anteriores, **iscsym** e **iscsymf** são definidos como macros somente quando [ &#95; &#95;STDC&#95; &#95; ](../../preprocessor/predefined-macros.md) não está definido ou está definido como 0; Caso contrário, eles são indefinidos.

## <a name="requirements"></a>Requisitos

|Rotina|Cabeçalho necessário|
|-------------|---------------------|
|**iscsym**, **iscsymf**, **iscsym**, **iswcsym**, **iscsymf**, **iswcsymf**, **iscsym_l**, **iswcsym_l**, **iscsymf_l**, **iswcsymf_l**|C: \<ctype.h><br /><br /> C++: \<cctype> ou \<ctype.h>|

O **iscsym**, **iscsymf**, **iscsym**, **iswcsym**, **iscsymf**, **_ iswcsymf**, **iscsym_l**, **iswcsym_l**, **iscsymf_l**, e **iswcsymf_l** são rotinas Específico da Microsoft. Para obter informações adicionais sobre compatibilidade, consulte [Compatibilidade](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Consulte também

[Classificação de caracteres](../../c-runtime-library/character-classification.md)<br/>
[Localidade](../../c-runtime-library/locale.md)<br/>
[Rotinas is, isw](../../c-runtime-library/is-isw-routines.md)<br/>
