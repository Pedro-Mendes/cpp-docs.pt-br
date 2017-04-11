---
title: Constantes globais no C++ | Documentos do Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- global constants
- constants, global
ms.assetid: df5a9bd4-d0a8-4c1c-956e-b481d0bded7d
caps.latest.revision: 9
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
ms.openlocfilehash: c1a1483a6d4c8c348ea0e57c3e387f9fa79c9433
ms.lasthandoff: 02/25/2017

---
# <a name="global-constants-in-c"></a>Constantes globais no C++
Constantes globais C++ têm vinculação estática. Isso é diferente de C. Se tentar usar um global constante em C++ em vários arquivos você obterá um erro externo não resolvido. O compilador otimiza constantes globais, não deixando nenhum espaço reservado para a variável.  
  
 Uma maneira de resolver esse erro é incluir as inicializações constantes em um arquivo de cabeçalho e incluir esse cabeçalho nos arquivos CPP quando necessário, como se fosse o protótipo de função. Outra possibilidade é tornar a variável não constante e usar uma referência constante ao avaliar a ele.  
  
 O exemplo a seguir gera C2019:  
  
```  
// global_constants.cpp  
// LNK2019 expected  
void test(void);  
const int lnktest1 = 0;  
  
int main() {  
   test();  
}  
```  
  
 E, em seguida,  
  
```  
// global_constants_2.cpp  
// compile with: global_constants.cpp  
extern int lnktest1;  
  
void test() {  
  int i = lnktest1;   // LNK2019  
}  
```  
  
## <a name="see-also"></a>Consulte também  
 [Erro das ferramentas de vinculador LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)