---
title: "map::value_comp (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::map::value_comp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Membro value_comp [STL/CLR]"
ms.assetid: b0e53052-f3cc-48c8-8e29-1b151c23860a
caps.latest.revision: 8
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# map::value_comp (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Copia o representante de ordenação para dois valores do elemento.  
  
## Sintaxe  
  
```  
value_compare^ value_comp();  
```  
  
## Comentários  
 A função de membro retorna o delegado de classificação usado para ordenar a sequência controlada.  Você usará para comparar dois valores do elemento.  
  
## Exemplo  
  
```  
// cliext_map_value_comp.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
    Mymap c1;   
    Mymap::value_compare^ kcomp = c1.value_comp();   
  
    System::Console::WriteLine("compare([L'a', 1], [L'a', 1]) = {0}",   
        kcomp(Mymap::make_value(L'a', 1),   
            Mymap::make_value(L'a', 1)));   
    System::Console::WriteLine("compare([L'a', 1], [L'b', 2]) = {0}",   
        kcomp(Mymap::make_value(L'a', 1),   
            Mymap::make_value(L'b', 2)));   
    System::Console::WriteLine("compare([L'b', 2], [L'a', 1]) = {0}",   
        kcomp(Mymap::make_value(L'b', 2),   
            Mymap::make_value(L'a', 1)));   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **compare \(\[L'a, 1\], \[,\]\) L'a 1 \= false**  
**compare \(\[L'a, 1\], \[,\]\) L'b 2 \= retificam**  
**compare \(\[L'b, 2\], \[,\]\) L'a 1 \= false**   
## Requisitos  
 cliext \<\/mapa de**Cabeçalho:** \>  
  
 cliext de**Namespace:**  
  
## Consulte também  
 [map](../dotnet/map-stl-clr.md)   
 [map::value\_compare](../dotnet/map-value-compare-stl-clr.md)   
 [map::value\_type](../dotnet/map-value-type-stl-clr.md)