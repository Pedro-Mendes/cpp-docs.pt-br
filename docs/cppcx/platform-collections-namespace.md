---
title: 'Namespace Platform:: Collections | Microsoft Docs'
ms.custom: 
ms.date: 01/25/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: collection/Platform::Collections
dev_langs: C++
helpviewer_keywords: Platform::Collections Namespace
ms.assetid: b5042864-5f22-40b7-b7a5-c0691f65cc47
caps.latest.revision: "9"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a93282a233f98d7a384d1fdad2ba6ca862e9e3f2
ms.sourcegitcommit: c2e990450ccd528d85b2783fbc63042612987cfd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2018
---
# <a name="platformcollections-namespace"></a>Namespace Platform::Collections
O namespace Platform:: Collections contém o `Map`, `MapView`, `Vector`, e `VectorView` classes. Essas classes são implementações concretas das interfaces correspondentes que são definidas no namespace [Windows::Foundation::Collections](http://go.microsoft.com/fwlink/p/?LinkId=262645) . Não é possível transmitir os tipos de coleção concretos pela ABI (por exemplo quando um programa Javascript ou C# é chamado em um componente C++), mas é possível convertê-los implicitamente nos seus tipos de interface correspondentes. Por exemplo, se você implementar um método público que popula e retorna uma coleção, use [Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) para implementar a coleção internamente e [Windows::Foundation::Collections::IVector](http://go.microsoft.com/fwlink/p/?LinkId=262410) como o tipo de retorno. Para obter mais informações, consulte [coleções](../cppcx/collections-c-cx.md) e [Criando componentes do tempo de execução do Windows em C++](/MicrosoftDocs/windows-uwp/blob/docs/windows-apps-src/winrt-components/creating-windows-runtime-components-in-cpp.md).  
  
 Você pode construir um Platform::Collections::Vector com base em um [std::vector](../standard-library/vector-class.md) e um [Platform::Collections::Map](../cppcx/platform-collections-map-class.md) com base em um [std::map](../standard-library/map-class.md).  
  
 Além disso, o namespace Platform:: Collections fornece suporte para inserção e entrados iteradores, e `Vector` e `VectorView` iteradores.  
  
 Você deve incluir (`#include`) o cabeçalho Collection. h para usar os tipos no namespace Platform:: Collections.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
  
#include <collection.h>  
using namespace Platform::Collections;  
```  
  
### <a name="members"></a>Membros  
 Esse namespace contém os membros a seguir.  
  
|Nome|Descrição|  
|----------|-----------------|  
|[Classe Platform::Collections::BackInsertIterator](../cppcx/platform-collections-backinsertiterator-class.md)|Representa um iterador que insere um elemento no final de uma coleção.|  
|[Classe Platform::Collections::InputIterator](../cppcx/platform-collections-inputiterator-class.md)|Representa um iterador que insere um elemento no início de uma coleção.|  
|[classe Platform::Collections::Map](../cppcx/platform-collections-map-class.md)|Representa uma coleção modificável de pares chave-valor que são acessados por uma chave. Semelhante a [std::map](../standard-library/map-class.md).|  
|[classe Platform::Collections::MapView](../cppcx/platform-collections-mapview-class.md)|Representa uma coleção somente leitura de pares chave-valor que são acessados por uma chave.|  
|[Platform::Collections::Vector Class](../cppcx/platform-collections-vector-class.md)|Representa uma sequência de elementos modificável. Semelhante a [std::vector](../standard-library/vector-class.md).|  
|[Classe Platform::Collections::VectorIterator](../cppcx/platform-collections-vectoriterator-class.md)|Representa um iterador que atravessa uma coleção `Vector` .|  
|[classe Platform::Collections::VectorView](../cppcx/platform-collections-vectorview-class.md)|Representa uma sequência de elementos somente leitura.|  
|[Classe Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md)|Representa um iterador que atravessa uma coleção `VectorView` .|  
  
## <a name="inheritance-hierarchy"></a>Hierarquia de herança  
 [Namespace de plataforma](../cppcx/platform-namespace-c-cx.md)  
  
### <a name="requirements"></a>Requisitos  
 **Metadados:** platform.winmd  
  
 **Namespace:** Platform::Collections  
  
 **Opção de compilador:** /ZW  
  
## <a name="see-also"></a>Consulte também  
 [Namespace de plataforma](../cppcx/platform-namespace-c-cx.md)