---
title: for_each (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::for_each
dev_langs: C++
helpviewer_keywords: for_each function [STL/CLR]
ms.assetid: 4c391ecf-cd35-499e-a3f5-35b965e0da9b
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fd29816817230c89f309340daf298569a16d0a8f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="foreach-stlclr"></a>for_each (STL/CLR)
Aplica um objeto de função especificado a cada elemento em uma ordem progressiva dentro de um intervalo e retorna o objeto de função.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
template<class _InIt, class _Fn1> inline  
    _Fn1 for_each(_InIt _First, _InIt _Last, _Fn1 _Func);  
```  
  
## <a name="remarks"></a>Comentários  
 Essa função se comporta como a função de biblioteca padrão C++ `for_each`. Para obter mais informações, consulte [for_each](../standard-library/algorithm-functions.md#for_each).  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** \<cliext/algoritmo >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Consulte também  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)