---
title: __set_app_type | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __set_app_type
- _set_app_type
apilocation:
- msvcr90.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcrt.dll
- msvcr120.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __set_app_type
dev_langs:
- C++
helpviewer_keywords:
- __set_app_type
ms.assetid: f0ac0f4d-70e6-4e96-9e43-eb9d1515490c
caps.latest.revision: 2
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
ms.openlocfilehash: 9c71510aa77a9d06dc1ec80971a6055c46cb7588

---
# <a name="setapptype"></a>__set_app_type
Define o tipo de aplicativo atual.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
void __set_app_type (  
   int at  
   )  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `at`  
 Um valor que indica o tipo de aplicativo. Os valores possíveis são:  
  
|Valor|Descrição|  
|-----------|-----------------|  
|_UNKNOWN_APP|Tipo de aplicativo desconhecido.|  
|_CONSOLE_APP|Aplicativo de console (linha de comando).|  
|_GUI_APP|Aplicativo GUI (Windows).|  
  
## <a name="remarks"></a>Comentários  
  
## <a name="requirements"></a>Requisitos  
  
|Rotina|Cabeçalho necessário|  
|-------------|---------------------|  
|__set_app_type|internal.h|


<!--HONumber=Feb17_HO4-->

