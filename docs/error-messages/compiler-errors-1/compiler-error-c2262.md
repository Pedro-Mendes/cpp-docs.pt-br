---
title: C2262 de erro do compilador | Documentos do Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2262
dev_langs:
- C++
helpviewer_keywords:
- C2262
ms.assetid: 727d1c6e-53e8-40e5-b7b8-6a7ac2011727
caps.latest.revision: 4
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
ms.openlocfilehash: b33219972998978c8c1373c4bb70f4cbddd48db0
ms.lasthandoff: 02/25/2017

---
# <a name="compiler-error-c2262"></a>C2262 de erro do compilador
'attribute_specifiers': declarações InternalsVisibleTo não podem ter uma arquitetura de versão, cultura ou processador especificada  
  
 O <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>atributo não foi especificado corretamente.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir gera C2262.  
  
```  
// C2262.cpp  
// compile with: /clr /c  
using namespace System::Runtime::CompilerServices;  
[assembly: InternalsVisibleTo("assembly_name, version=1.2.3.7")];   // C2262  
[assembly: InternalsVisibleTo("assembly_name ")];   // OK  
```