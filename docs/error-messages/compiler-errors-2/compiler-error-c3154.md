---
title: C3154 de erro do compilador | Documentos do Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3154
dev_langs:
- C++
helpviewer_keywords:
- C3154
ms.assetid: 78005c74-eaaf-4ac2-88ae-6c25d01a302a
caps.latest.revision: 7
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 93ccb3241e208fe91a2150f69e15fb262e0d9c78
ms.lasthandoff: 02/25/2017

---
# <a name="compiler-error-c3154"></a>C3154 de erro do compilador
Esperado ',' antes de reticências. Não-CSV reticências não tem suportada em funções de matriz de parâmetro.  
  
 Uma função de argumento variável não foi declarada corretamente.  
  
 Para obter mais informações, consulte [listas de argumentos variáveis (...) (C + + / CLI) ](../../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md).  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir gera C3154.  
  
```  
// C3154.cpp  
// compile with: /clr  
ref struct R {  
   void Func(int ... array<int> ^);   // C3154  
   void Func2(int i, ... array<int> ^){}   // OK  
   void Func3(array<int> ^){}   // OK  
   void Func4(... array<int> ^){}   // OK  
};  
  
int main() {  
   R ^ r = gcnew R;  
   r->Func4(1,2,3);  
}  
```