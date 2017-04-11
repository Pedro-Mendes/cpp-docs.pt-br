---
title: "Usando matrizes (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "matrizes [C++]"
ms.assetid: 7818a7fe-7e82-4881-a3d1-7d25162b7fc7
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Usando matrizes (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Você pode acessar elementos individuais de uma matriz usando o operador de subscrito de matriz \(`[ ]`\).  Se uma matriz unidimensional for usada em uma expressão que não tenha subscritos, o nome da matriz será avaliado como um ponteiro para o primeiro elemento da matriz.  
  
```  
// using_arrays.cpp  
int main() {  
   char chArray[10];  
   char *pch = chArray;   // Evaluates to a pointer to the first element.  
   char   ch = chArray[0];   // Evaluates to the value of the first element.  
   ch = chArray[3];   // Evaluates to the value of the fourth element.  
}  
```  
  
 Ao usar matrizes multidimensionais, você pode usar diversas combinações em expressões.  
  
```  
// using_arrays_2.cpp  
// compile with: /EHsc /W1  
#include <iostream>  
using namespace std;  
int main() {  
   double multi[4][4][3];   // Declare the array.  
   double (*p2multi)[3];  
   double (*p1multi);  
  
   cout << multi[3][2][2] << "\n";   // C4700 Use three subscripts.  
   p2multi = multi[3];               // Make p2multi point to  
                                     // fourth "plane" of multi.  
   p1multi = multi[3][2];            // Make p1multi point to  
                                     // fourth plane, third row  
                                     // of multi.  
}  
```  
  
 No código acima, `multi` é uma matriz tridimensional do tipo `double`.  O ponteiro `p2multi` aponta para uma matriz do tipo `double` de tamanho três.  Nesse exemplo, a matriz é usada com um, dois e três subscritos.  Embora seja mais comum especificar todos os subscritos, como na instrução `cout`, às vezes, é útil selecionar um subconjunto específico de elementos da matriz, como mostrado nas instruções que se seguem a `cout`.  
  
## Consulte também  
 [Matrizes](../Topic/Arrays%20\(C++\).md)