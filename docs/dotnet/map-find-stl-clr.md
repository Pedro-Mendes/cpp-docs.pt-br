---
title: 'Map:: Find (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::map::find
dev_langs: C++
helpviewer_keywords: find member [STL/CLR]
ms.assetid: 779dcbee-d584-4fbd-b788-481e094ece9d
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 805ddfc8e2e8194df38703011a90c62d96475ddd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="mapfind-stlclr"></a>map::find (STL/CLR)
Localiza um elemento que corresponde a uma chave especificada.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
iterator find(key_type key);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 key  
 O valor chave a ser pesquisado.  
  
## <a name="remarks"></a>Comentários  
 Se pelo menos um elemento na sequência controlada tem ordenação equivalente com `key`, a função de membro retorna um iterador designar um desses elementos; caso contrário, ele retorna [Map:: end (STL/CLR)](../dotnet/map-end-stl-clr.md)`()`. Você pode usá-lo para localizar um elemento no momento na sequência controlada que corresponde a uma chave especificada.  
  
## <a name="example"></a>Exemplo  
  
```  
// cliext_map_find.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("find {0} = {1}",   
        L'A', c1.find(L'A') != c1.end());   
  
    Mymap::iterator it = c1.find(L'b');   
    System::Console::WriteLine("find {0} = [{1} {2}]",   
        L'b', it->first, it->second);   
  
    System::Console::WriteLine("find {0} = {1}",   
        L'C', c1.find(L'C') != c1.end());   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
find A = False  
find b = [b 2]  
find C = False  
```  
  
## <a name="description"></a>Descrição  
 Observe que `find` não garante que vários elemento encontrar.  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** \<cliext/mapa >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Consulte também  
 [Map (STL/CLR)](../dotnet/map-stl-clr.md)   
 [Map:: equal_range (STL/CLR)](../dotnet/map-equal-range-stl-clr.md)   
 [Map:: lower_bound (STL/CLR)](../dotnet/map-lower-bound-stl-clr.md)   
 [map::upper_bound (STL/CLR)](../dotnet/map-upper-bound-stl-clr.md)