---
title: "Compilador aviso (nível 3) C4359 | Documentos do Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4359
dev_langs:
- C++
helpviewer_keywords:
- C4359
ms.assetid: d8fe993c-ef82-45a0-a43d-c29f9d1bacdb
caps.latest.revision: 5
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
ms.openlocfilehash: 294ba29c84c1b27f7e5aa1611b4ab143e9559c73
ms.lasthandoff: 02/25/2017

---
# <a name="compiler-warning-level-3-c4359"></a>Compilador C4359 de aviso (nível 3)
'type': alinhamento real (8) é maior que o valor especificado em __declspec(align())  
  
 O alinhamento especificado para um tipo é menor que o alinhamento do tipo de um de seus membros de dados.  Para obter mais informações, consulte [alinhar](../../cpp/align-cpp.md).  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir gera C4359.  
  
```  
// C4359.cpp  
// compile with: /W3 /c  
struct __declspec(align(8)) C8 { __int64 i; };  
struct __declspec(align(4)) C4  { C8 m8; };   // C4359  
struct __declspec(align(8)) C8_b  { C8 m8; };   // OK  
struct __declspec(align(16)) C16  { C8 m8; };   // OK  
```