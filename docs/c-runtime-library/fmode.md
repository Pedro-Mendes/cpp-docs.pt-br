---
title: _fmode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- fmode
- _fmode
dev_langs:
- C++
helpviewer_keywords:
- file translation [C++], default mode
- fmode function
- _fmode function
ms.assetid: ac6df9eb-e5cc-4c54-aff3-373c21983118
caps.latest.revision: 9
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 8de91088f9fd667e768a45d0f659a2effcd91a6f

---
# <a name="fmode"></a>_fmode
A variável `_fmode` define o modo de conversão de arquivo padrão como conversão de texto ou binária. Essa variável global foi preterida em favor das versões funcionais mais seguras [_get_fmode](../c-runtime-library/reference/get-fmode.md) e [_set_fmode](../c-runtime-library/reference/set-fmode.md), que devem ser usadas no lugar da variável global. Ela é declarada em Stdlib.h da seguinte maneira.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
extern int _fmode;  
```  
  
## <a name="remarks"></a>Comentários  
 A configuração padrão de `_fmode` é `_O_TEXT` para a conversão de modo de texto. `_O_BINARY` é a configuração para o modo binário.  
  
 É possível alterar o valor de `_fmode` de três maneiras:  
  
-   Link com Binmode.obj. Isso altera a configuração inicial de `_fmode` para `_O_BINARY`, fazendo com que todos os arquivos, exceto por `stdin`, `stdout` e `stderr`, sejam abertos no modo binário.  
  
-   Faça uma chamada para `_get_fmode` ou `_set_fmode` para obter ou definir a variável global `_fmode`, respectivamente.  
  
-   Altere o valor de `_fmode` diretamente configurando-o em seu programa.  
  
## <a name="see-also"></a>Consulte também  
 [Variáveis globais](../c-runtime-library/global-variables.md)   
 [_get_fmode](../c-runtime-library/reference/get-fmode.md)   
 [_set_fmode](../c-runtime-library/reference/set-fmode.md)


<!--HONumber=Feb17_HO4-->

