---
title: fma, fmaf, fmal | Microsoft Docs
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
- fma
- fmaf
- fmal
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
- fma
- fmaf
- fmal
- math/fma
- math/fmaf
- math/fmal
dev_langs:
- C++
helpviewer_keywords:
- fma function
- fmaf function
- fmal function
ms.assetid: 584a6037-da1e-4e86-9f0c-97aae86de0c0
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
ms.openlocfilehash: ea2fe8c416681e6076673236702deef3497638ac
ms.lasthandoff: 02/25/2017

---
# <a name="fma-fmaf-fmal"></a>fma, fmaf, fmal
Multiplica dois valores, adiciona um terceiro valor e arredonda o resultado, sem perder a precisão devido a um arredondamento intermediário.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
double fma(  
   double x,   
   double y,   
   double z  
);  
  
float fma(  
   float  x,   
   float  y,   
   float z  
); //C++ only  
  
long double fma(  
   long double  x,   
   long double  y,   
   long double z  
); //C++ only  
  
float fmaf(  
   float  x,   
   float  y,   
   float z  
);  
  
long double fmal(  
   long double  x,   
   long double  y,   
   long double z  
);  
  
```  
  
#### <a name="parameters"></a>Parâmetros  
 [in] `x`  
 O primeiro valor a ser multiplicado.  
  
 [in] `y`  
 O segundo valor a ser multiplicado.  
  
 [in] `z`  
 O valor a ser adicionado.  
  
## <a name="return-value"></a>Valor de retorno  
 Retorna (`x` ×    `y`) + `z`. O valor retornado é arredondado usando o formato de arredondamento atual.  
  
 Caso contrário, pode retornar um dos seguintes valores:  
  
|Problema|Valor de|  
|-----------|------------|  
|`x` = INFINITY, `y` = 0 ou<br /><br /> `x` = 0, `y` = INFINITY|NaN|  
|`x` ou `y` = exact ± INFINITY, `z` = INFINITY com o sinal oposto|NaN|  
|`x` ou `y` = NaN|NaN|  
|não (`x` = 0, `y`= indefinido) e `z` = NaN<br /><br /> não (`x`=indefinido, `y`=0) e `z` = NaN|NaN|  
|Erro de intervalo de estouro|±HUGE_VAL, ±HUGE_VALF ou ±HUGE_VALL|  
|Erro de intervalo de estouro negativo|valor correto, após o arredondamento.|  
  
 Os erros são relatados conforme especificado em [_matherr](../../c-runtime-library/reference/matherr.md).  
  
## <a name="remarks"></a>Comentários  
 Uma vez que C++ permite sobrecargas, é possível chamar sobrecargas de `fma` que utilizam e retornam tipos duplos flutuantes e longos. Em um programa C, `fma` sempre usa e retorna um duplo.  
  
 Esta função calcula o valor como se ele tivesse precisão infinita e arredonda o resultado final.  
  
## <a name="requirements"></a>Requisitos  
  
|Função|Cabeçalho C|Cabeçalho C++|  
|--------------|--------------|------------------|  
|`fma`,                `fmaf`,  `fmal`|\<math.h>|\<cmath>|  
  
 Para obter informações adicionais sobre compatibilidade, consulte [Compatibilidade](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Consulte também  
 [Referência da Função Alfabética](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [remainder, remainderf, remainderl](../../c-runtime-library/reference/remainder-remainderf-remainderl.md)   
 [remquo, remquof, remquol](../../c-runtime-library/reference/remquo-remquof-remquol.md)