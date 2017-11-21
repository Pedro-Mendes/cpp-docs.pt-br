---
title: BEGIN_COLUMN_MAP | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BEGIN_COLUMN_MAP
dev_langs: C++
helpviewer_keywords: BEGIN_COLUMN_MAP macro
ms.assetid: d6ffe633-e0da-4e33-8faa-f7f259d05420
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 29e62e08ef03d863b17ea0d269cf049b23602774
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="begincolumnmap"></a>BEGIN_COLUMN_MAP
Marca o início de uma entrada de mapa de coluna.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
BEGIN_COLUMN_MAP(  
x  
 )  
  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *x*  
 [in] O nome da classe de registro de usuário é derivado de `CAccessor`.  
  
## <a name="remarks"></a>Comentários  
 Essa macro é usada no caso de um único acessador em um conjunto de linhas. Se você tiver vários acessadores em um conjunto de linhas, use [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).  
  
 O `BEGIN_COLUMN_MAP` macro é concluída com o `END_COLUMN_MAP` macro. Essa macro é usada quando há apenas um acessador necessário no registro do usuário.  
  
 Colunas correspondem a campos no conjunto de linhas que você deseja vincular.  
  
## <a name="example"></a>Exemplo  
 Aqui está um exemplo de mapa de parâmetro e coluna:  
  
 <!--[!CODE [NVC_OLEDB_Consumer#16](../codesnippet/vs_snippets_cpp/nvc_oledb_consumer#16)]  -->
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** atldbcli.h  
  
## <a name="see-also"></a>Consulte também  
 [Macros e funções globais para modelos de consumidor OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [COLUMN_ENTRY_EX](../../data/oledb/column-entry-ex.md)