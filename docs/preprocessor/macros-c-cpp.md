---
title: Macros (C/C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- preprocessor
- preprocessor, macros
- Visual C++, preprocessor macros
ms.assetid: a7bfc5d4-2537-4fe0-bef0-70cec0b43388
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c6919f1e3670251b952ce797df5ad10b786b1bbd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="macros-cc"></a>Macros (C/C++)
Pré-processamento expande macros em todas as linhas que não são diretivas de pré-processador (linhas que não têm um  **#**  como o primeiro caractere que não esteja em branco) e em partes de algumas diretivas que não são ignoradas como parte de um compilação condicional. As políticas de “compilação condicional” permitem que você suprima a compilação de partes de um arquivo de origem testando uma expressão constante ou um identificador para determinar quais blocos de texto passam no compilador e que são removidos do arquivo de origem durante o pré-processamento.  
  
 A política `#define` normalmente é usada para associar identificadores significativos a constantes, palavras-chave e instruções ou expressões de uso geral. Os identificadores que representam constantes às vezes são chamados de “constantes simbólicas” ou “constantes de manifesto”. Os identificadores que representam instruções ou expressões são chamados de “macros”. Nesta documentação de pré-processador, somente o termo “macro” é usado.  
  
 Quando o nome da macro é reconhecido no texto de origem do programa ou nos argumentos de alguns outros comandos de pré-processador, ele é tratado como uma chamada para aquela macro. O nome da macro é substituído por uma cópia do corpo da macro. Se a macro aceitar argumentos, os argumentos reais após o nome da macro serão substituídos por parâmetros formais no corpo da macro. O processo de substituição de uma chamada de macro pela cópia processada do corpo é chamado de “expansão” da chamada de macro.  
  
 Em termos práticos, há dois tipos de macros. Macros "do tipo objeto" não aceitam argumentos, enquanto macros "do tipo função" pode ser definidas para aceitarem argumentos para que pareçam e ajam como chamadas de função. Como as macros não gerenciam chamadas de função reais, às vezes você pode fazer com que os programas sejam executados mais rapidamente substituindo chamadas de função por macros. (Em C++, as funções embutidas frequentemente são o método preferencial.) No entanto, as macros podem criar problemas se você não defini-las e usá-las com cuidado. Você pode precisar usar parênteses em definições de macro com argumentos para preservar a precedência apropriada em uma expressão. Além disso, as macros podem não manipular corretamente expressões com efeitos colaterais. Consulte o `getrandom` exemplo [o # diretiva define](../preprocessor/hash-define-directive-c-cpp.md) para obter mais informações.  
  
 Depois que você tiver definido uma macro, não poderá redefini-la como um valor diferente sem descartar primeiro a definição original. No entanto, você pode redefinir a macro com exatamente a mesma definição. Assim, a mesma definição pode aparecer mais de uma vez em um programa.  
  
 O #**undef** diretiva remove a definição de uma macro. Depois que você tiver removido a definição, poderá redefinir a macro com um valor diferente. [O # diretiva define](../preprocessor/hash-define-directive-c-cpp.md) e [a diretiva #undef](../preprocessor/hash-undef-directive-c-cpp.md) discutir o `#define` e `#undef` diretivas, respectivamente.  
  
 Para obter mais informações, consulte  
  
-   [Macros e C++](../preprocessor/macros-and-cpp.md)  
  
-   [Macros variadic](../preprocessor/variadic-macros.md)  
  
-   [Macros predefinidas](../preprocessor/predefined-macros.md)  
  
## <a name="see-also"></a>Consulte também  
 [Referência de pré-processador do C/C++](../preprocessor/c-cpp-preprocessor-reference.md)