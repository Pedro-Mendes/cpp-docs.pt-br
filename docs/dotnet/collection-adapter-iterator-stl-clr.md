---
title: collection_adapter::Iterator (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::collection_adapter::iterator
dev_langs: C++
helpviewer_keywords: iterator member [STL/CLR]
ms.assetid: b1078abd-e766-464e-9dc6-32e95ab50695
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2f30bc3434d1c7dabae2c378d483eb5f2afc8f3c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="collectionadapteriterator-stlclr"></a>collection_adapter::iterator (STL/CLR)
O tipo de um iterador para a sequência controlada.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
typedef T1 iterator;  
```  
  
## <a name="remarks"></a>Comentários  
 O tipo descreve um objeto do tipo especificado `T1` que pode servir como um iterador de entrada para a sequência controlada.  
  
## <a name="example"></a>Exemplo  
  
```  
// cliext_collection_adapter_iterator.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    Mycoll::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** \<cliext adaptador >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Consulte também  
 [collection_adapter (STL/CLR)](../dotnet/collection-adapter-stl-clr.md)