---
title: "Combinando C (estruturada) e as exceções do C++ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- exceptions [C++], mixed C and C++
- C++ exception handling, mixed-language
- structured exception handling [C++], mixed C and C++
- catch keyword [C++], mixed
- try-catch keyword [C++], mixed-language
ms.assetid: a149154e-36dd-4d1a-980b-efde2a563a56
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2cb390fa0b6cf90a76d0b751b8bdce7d4a3e54b9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="mixing-c-structured-and-c-exceptions"></a>Combinação de exceções C (Estruturada) e C++
Se você quiser escrever um código mais portátil, não recomendamos o uso de tratamento de exceções estruturadas em um programa C/C++. No entanto, às vezes, convém compilar com **/EHa** misturar exceções estruturadas e código-fonte C++ e precisa de algum recurso para lidar com ambos os tipos de exceções. Como um manipulador de exceção estruturado não tem nenhum conceito de objetos ou exceções digitadas, ele não pode manipular exceções lançadas por código C++. No entanto, C++ **catch** manipuladores podem lidar com exceções estruturadas. Como tal, sintaxe de manipulação de exceção de C++ (**tente**, `throw`, **catch**) não é aceito pelo compilador C, mas a sintaxe de manipulação de exceção estruturada (`__try`, `__except`, `__finally`) há suporte para o compilador do C++.  
  
 Consulte [set_se_translator](../c-runtime-library/reference/set-se-translator.md) para obter informações sobre o tratamento de exceções estruturadas como exceções de C++.  
  
 Se você combinar exceções estruturadas e exceções C++, observe o seguinte:  
  
1.  As exceções C++ e as exceções estruturadas não podem ser combinadas na mesma função.  
  
2.  Os manipuladores de término (blocos `__finally`) são sempre executados, mesmo durante o desenrolamento depois que uma exceção é lançada.  
  
3.  Tratamento de exceções C++ pode capturar e preservar desenrolar semântica em todos os módulos compilados com o [/EH](../build/reference/eh-exception-handling-model.md) opção de compilador (esta opção ativa a semântica de liberação).  
  
4.  Pode haver algumas situações nas quais as funções de destruidor não sejam chamadas de todos os objetos. Por exemplo, se uma exceção estruturada ocorre ao tentar fazer uma chamada de função por meio de um ponteiro de função não inicializado, e essa função usar como parâmetros objetos que foram criados antes da chamada, os destruidores desses objetos não serão chamados durante o desenrolamento de pilha.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Que mais você deseja saber?  
  
-   [Usando setjmp ou longjmp em programas C++](../cpp/using-setjmp-longjmp.md)  
  
-   [Diferenças entre SEH e C++ EH](../cpp/exception-handling-differences.md)  
  
## <a name="see-also"></a>Consulte também  
 [Tratamento de exceções em C++](../cpp/cpp-exception-handling.md)