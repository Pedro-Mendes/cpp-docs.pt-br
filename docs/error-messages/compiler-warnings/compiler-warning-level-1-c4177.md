---
title: "Compilador aviso (nível 1) C4177 | Documentos do Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4177
dev_langs:
- C++
helpviewer_keywords:
- C4177
ms.assetid: 2b05a5b3-696e-4f21-818e-227b9335e748
caps.latest.revision: 7
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: d1940c450c21d43aa48fd2ea41190e90e9670121
ms.lasthandoff: 02/25/2017

---
# <a name="compiler-warning-level-1-c4177"></a>Compilador C4177 de aviso (nível 1)
\#pragma pragma deve estar no escopo global  
  
 O [pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md) pragma não deve ser usado em um escopo local. O **pragma** não será válida até que o escopo global é encontrado após o escopo atual.  
  
 O exemplo a seguir gera C4177:  
  
```  
// C4177.cpp  
// compile with: /W1  
// #pragma bss_seg("global")   // OK  
  
int main() {  
   #pragma bss_seg("local")    // C4177  
}  
```