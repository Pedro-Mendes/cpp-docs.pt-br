---
title: "Avaliação de tokens | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- tokens, evaluating
ms.assetid: 28870b62-dff6-4644-8b75-d58f340b48d2
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
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
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: e3195b466a73d79e2b2bbdb7dea064b4f195002b
ms.lasthandoff: 02/25/2017

---
# <a name="evaluation-of-tokens"></a>Avaliação de tokens
Quando o compilador interpreta tokens, ele inclui o máximo de caracteres possível em um único token antes seguir para o próximo token. Devido a esse comportamento, o compilador pode não interpretar tokens como você gostaria se eles não forem separados corretamente por um espaço em branco. Considere a seguinte expressão:  
  
```  
i+++j  
```  
  
 Neste exemplo, o compilador primeiro cria o operador mais longo possível (`++`) dos três sinais positivos, depois processa o sinal de positivo restante como um operador de adição (`+`). Assim, a expressão é interpretada como `(i++) + (j)`, não `(i) + (++j)`. Nesse e em casos semelhantes, use espaço em branco e parênteses para evitar ambiguidade e assegurar a avaliação apropriada da expressão.  
  
 **Seção específica da Microsoft**  
  
 O compilador C trata um caractere CTRL+Z como um indicador de fim do arquivo. Ignora qualquer texto após CTRL+Z.  
  
 **Fim da seção específica da Microsoft**  
  
## <a name="see-also"></a>Consulte também  
 [Tokens C](../c-language/c-tokens.md)