---
title: catan, catanf, catanl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- catan
- catanf
- catanl
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
- catan
- catanf
- catanl
- complex/catan
- complex/catanf
- complex/catanl
dev_langs:
- C++
helpviewer_keywords:
- catan function
- catanf function
- catanl function
ms.assetid: 8415ed9c-7909-4d08-b532-4630bafdc7e8
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: cb516702a6fdb59eb2fbef2179fce76db8a32081
ms.lasthandoff: 02/25/2017

---
# <a name="catan-catanf-catanl"></a>catan, catanf, catanl
Recupera o arco tangente de um número complexo com cortes de ramificação fora do intervalo [−1; +1] ao longo do eixo imaginário.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
_Dcomplex catan(   
   _Dcomplex z   
);  
_Fcomplex catan(   
   _Fcomplex z   
);  // C++ only  
_Lcomplex catan(   
  _Lcomplex z   
);  // C++ only  
_Fcomplex catanf(   
   _Fcomplex z   
);  
_Lcomplex catanl(   
   _Lcomplex z   
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `z`  
 Um número complexo que representa um ângulo, em radianos.  
  
## <a name="return-value"></a>Valor retornado  
 O arco tangente de `z`, em radianos. O resultado é ilimitado ao longo do eixo imaginário e no intervalo [−π/2; +π/2] ao longo do eixo real.  
  
## <a name="remarks"></a>Comentários  
 Como C++ permite sobrecargas, é possível chamar sobrecargas de `catan` que tomam e retornam valores de `_Fcomplex` e `_Lcomplex`. Em um programa do C, `catan` sempre usa e retorna um valor `_Dcomplex`.  
  
## <a name="requirements"></a>Requisitos  
  
|Rotina|Cabeçalho C|Cabeçalho C++|  
|-------------|--------------|------------------|  
|`catan`,               `catanf`, `catanl`|\<complex.h>|\<ccomplex>|  
  
 Para obter mais informações sobre compatibilidade, consulte [Compatibilidade](../../c-runtime-library/compatibility.md) na Introdução.  
  
## <a name="see-also"></a>Consulte também  
 [Referência da Função Alfabética](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [catanh, catanhf, catanhl](../../c-runtime-library/reference/catanh-catanhf-catanhl.md)   
 [ctanh, ctanhf, ctanhl](../../c-runtime-library/reference/ctanh-ctanhf-ctanhl.md)   
 [csinh, csinhf, csinhl](../../c-runtime-library/reference/csinh-csinhf-csinhl.md)   
 [casinh, casinhf, casinhl](../../c-runtime-library/reference/casinh-casinhf-casinhl.md)   
 [ccosh, ccoshf, ccoshl](../../c-runtime-library/reference/ccosh-ccoshf-ccoshl.md)   
 [cacosh, cacoshf, cacoshl](../../c-runtime-library/reference/cacosh-cacoshf-cacoshl.md)   
 [cacos, cacosf, cacosl](../../c-runtime-library/reference/cacos-cacosf-cacosl.md)   
 [ctan, ctanf, ctanl](../../c-runtime-library/reference/ctan-ctanf-ctanl.md)   
 [csin, csinf, csinl](../../c-runtime-library/reference/csin-csinf-csinl.md)   
 [casin, casinf, casinl](../../c-runtime-library/reference/casin-casinf-casinl.md)   
 [ccos, ccosf, ccosl](../../c-runtime-library/reference/ccos-ccosf-ccosl.md)   
 [csqrt, csqrtf, csqrtl](../../c-runtime-library/reference/csqrt-csqrtf-csqrtl.md)