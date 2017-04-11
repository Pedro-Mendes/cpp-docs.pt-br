---
title: __crtLCMapStringW | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __crtLCMapStringW
apilocation:
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcrt.dll
- msvcr120.dll
- msvcr110.dll
- msvcr80.dll
apitype: DLLExport
f1_keywords:
- __crtLCMapStringW
dev_langs:
- C++
helpviewer_keywords:
- __crtLCMapStringW
ms.assetid: 45b4ac0e-438c-4fa3-b4d1-34195f4467d9
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 8383b6749d65bcc2ed23d62b08befb1a2276501b
ms.lasthandoff: 02/25/2017

---
# <a name="crtlcmapstringw"></a>__crtLCMapStringW
Mapeia uma cadeia de caracteres para outra, executando a transformação dependente de localidade especificada. Essa função também pode ser usada para gerar uma chave de classificação para a cadeia de caracteres de entrada.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
int __crtLCMapStringW(  
   LCID    Locale,  
   DWORD   dwMapFlags,  
   LPCWSTR lpSrcStr,  
   int     cchSrc,  
   LPWSTR  lpDestStr,  
   int     cchDest)  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `Locale`  
 Identificador de localidade. A localidade fornece um contexto para o mapeamento de cadeia de caracteres ou a geração de chaves de classificação. Um aplicativo pode usar a macro `MAKELCID` para criar um identificador de localidade.  
  
 `dwMapFlags`  
 O tipo de transformação a ser usado durante o mapeamento da cadeia de caracteres ou a geração da chave de classificação.  
  
 `lpSrcStr`  
 Ponteiro para uma cadeia de caracteres de origem que a função mapeia ou usa para geração de chave de classificação. Esse parâmetro é considerado uma cadeia de caracteres Unicode.  
  
 `cchSrc`  
 Tamanho, em caracteres, da cadeia de caracteres apontada pelo parâmetro `lpSrcStr`. Essa contagem pode incluir ou não o terminador NULO.  
  
 Um valor `cchSrc` de –&1; especifica que a cadeia de caracteres apontada por `lpSrcStr` é terminada em nulo. Se esse for o caso, e essa função estiver sendo usada no modo de mapeamento de cadeia de caracteres, a função calcula o comprimento da cadeia de caracteres e termina em nulo a cadeia de caracteres mapeada armazenada em `*lpDestStr`.  
  
 `lpDestStr`  
 Ponteiro longo para um buffer em que a função armazena a cadeia de caracteres ou chave de classificação mapeada.  
  
 `cchDest`  
 Tamanho, em caracteres, do buffer apontado por `lpDestStr`.  
  
## <a name="return-value"></a>Valor de retorno  
 Se o valor de `cchDest` for diferente de zero, o número de caracteres, ou bytes, se `LCMAP_SORTKEY` for especificado, gravados no buffer indica êxito. Essa contagem inclui espaço para um terminador NULO.  
  
 Se o valor de `cchDest` for zero, o tamanho do buffer em caracteres, ou bytes, se `LCMAP_SORTKEY` for especificado, necessário para receber a cadeia de caracteres ou chave de classificação traduzida indica êxito. Esse tamanho inclui espaço para um terminador NULO.  
  
 Zero indica uma falha. Para obter outras informações sobre o erro, chame a função `GetLastError`.  
  
## <a name="remarks"></a>Comentários  
 Se `cchSrc` for maior que zero e `lpSrcStr` for uma cadeia de caracteres terminada em nulo, `__crtLCMapStringW` define `cchSrc` para o comprimento da cadeia de caracteres. Em seguida, `__crtLCMapStringW` chama a versão de cadeia de caracteres larga (Unicode) da função `LCMapString` com os parâmetros especificados. Para obter mais informações sobre os parâmetros e o valor de retorno dessa função, confira a função `LCMapString` na [Biblioteca MSDN](http://go.microsoft.com/fwlink/?linkID=150542).  
  
## <a name="requirements"></a>Requisitos  
  
|Rotina|Cabeçalho necessário|  
|-------------|---------------------|  
|__crtLCMapStringW|awint.h|