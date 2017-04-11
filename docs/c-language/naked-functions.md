---
title: "Funções naked | Microsoft Docs"
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
- naked functions
- functions [C++], naked
- prolog code
- epilog code
ms.assetid: 2543c8af-00d4-4a2a-8a87-e746da1f9929
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
ms.openlocfilehash: d7d82c7e350915469e378140771efccfe06b361c
ms.lasthandoff: 02/25/2017

---
# <a name="naked-functions"></a>Funções Naked
**Seção específica da Microsoft**  
  
 O atributo de classe de armazenamento `naked` é uma extensão específica da Microsoft na linguagem C. Para funções declaradas com o atributo de classe de armazenamento `naked`, o compilador gera um código sem código de prólogo e de epílogo. Você pode usar esse recurso para escrever suas próprias sequências de código de prólogo/epílogo usando o código de assembler embutido. As funções naked são particularmente úteis para escrever drivers para dispositivo virtuais.  
  
 Como o atributo `naked` é relevante apenas para a definição de uma função e não é um modificador de tipo, as funções naked devem usar a sintaxe de atributo estendido, descrita em [Atributos de classe de armazenamento estendidos](../c-language/c-extended-storage-class-attributes.md).  
  
 O seguinte exemplo define uma função com o atributo `naked`:  
  
```  
__declspec( naked ) int func( formal_parameters )  
{  
   /* Function body */  
}  
```  
  
 Ou, alternativamente:  
  
```  
#define Naked   __declspec( naked )  
  
Naked int func( formal_parameters )  
{  
   /* Function body */  
}  
```  
  
 O atributo `naked` afeta somente a natureza de geração de código do compilador para as sequências de prólogo e epílogo da função. Não afeta o código que é gerado pela chamada dessas funções. Assim, o atributo `naked` não é considerado parte do tipo de função, e os ponteiros da função não podem ter o atributo `naked`. Além disso, o atributo `naked` não pode ser aplicado a uma definição de dados. Por exemplo, o código a seguir gera erros:  
  
```  
__declspec( naked ) int i;  /* Error--naked attribute not */  
                            /* permitted on data declarations. */  
```  
  
 O atributo `naked` é relevante apenas à definição da função e não pode ser especificado no protótipo da função. Esta declaração gera um erro de compilador:  
  
```  
__declspec( naked ) int func();   /* Error--naked attribute not */  
                     /* permitted on function declarations.    */   \  
```  
  
 **Fim da seção específica da Microsoft**  
  
## <a name="see-also"></a>Consulte também  
 [Definições de função C](../c-language/c-function-definitions.md)