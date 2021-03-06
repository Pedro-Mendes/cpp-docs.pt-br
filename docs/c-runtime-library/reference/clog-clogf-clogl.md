---
title: clog, clogf, clogl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- clog
- clogf
- clogl
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- clog
- clogf
- clogl
- complex/clog
- complex/clogf
- complex/clogl
dev_langs:
- C++
helpviewer_keywords:
- clog function
- clogf function
- clogl function
ms.assetid: 870b9b0b-6618-46f3-bfcf-da595cbd5e18
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ca1b5b917b48a0307b9bd2a362ac7eb6a21dca3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32394789"
---
# <a name="clog-clogf-clogl"></a>clog, clogf, clogl

Recupera o logaritmo natural de um número complexo, com uma ramificação cortada ao longo do eixo real negativo.

## <a name="syntax"></a>Sintaxe

```C
_Dcomplex clog(
   _Dcomplex z
);
_Fcomplex clog(
   _Fcomplex z
);  // C++ only
_Lcomplex clog(
   _Lcomplex z
);  // C++ only
_Fcomplex clogf(
   _Fcomplex z
);
_Lcomplex clogl(
   _Lcomplex z
);
```

### <a name="parameters"></a>Parâmetros

*z*<br/>
A base do logaritmo.

## <a name="return-value"></a>Valor de retorno

O logaritmo natural de *z*. O resultado é não vinculado ao longo do eixo real e no intervalo [-iπ, + iπ] ao longo do eixo imaginário.

Os valores de retorno possíveis são:

|Parâmetro z|Valor retornado|
|-----------------|------------------|
|Positivo|O logaritmo de base 10 de z|
|Zero|- ∞|
|Negativo|NaN|
|NaN|NaN|
|+ ∞|+ ∞|

## <a name="remarks"></a>Comentários

Como o C++ permite sobrecarga, você pode chamar sobrecargas de **clog** que levar e retornar **_Fcomplex** e **_Lcomplex** valores. Em um programa C, **clog** sempre usa e retorna um **_Dcomplex** valor.

## <a name="requirements"></a>Requisitos

|Rotina|Cabeçalho C|Cabeçalho C++|
|-------------|--------------|------------------|
|**clog**, **clogf**, **clogl**|\<complex.h>|\<ccomplex>|

Para obter mais informações sobre compatibilidade, consulte [Compatibilidade](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Consulte também

[Referência da Função Alfabética](crt-alphabetical-function-reference.md)<br/>
[cexp, cexpf, cexpl](cexp-cexpf-cexpl.md)<br/>
[cpow, cpowf, cpowl](cpow-cpowf-cpowl.md)<br/>
[clog10, clog10f, clog10l](clog10-clog10f-clog10l.md)<br/>
