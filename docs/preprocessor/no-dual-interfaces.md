---
title: no_dual_interfaces | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- no_dual_interfaces
dev_langs:
- C++
helpviewer_keywords:
- no_dual_interfaces attribute
ms.assetid: 9acd5d9d-4a49-4cdc-9470-73a2c23cf512
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4eb26790a46f46638e4a4180ee2209efefda201c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46432211"
---
# <a name="nodualinterfaces"></a>no_dual_interfaces
**Específico do C++**  
  
Altera o modo como o compilador gerenciar funções wrapper para métodos da interface dupla.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
no_dual_interfaces  
```  
  
## <a name="remarks"></a>Comentários  
 
Normalmente, o wrapper chamará o método por meio da tabela de funções virtuais da interface. Com o **no_dual_interfaces**, o wrapper chama `IDispatch::Invoke` para invocar o método.  
  
**FIM de específico de C++**  
  
## <a name="see-also"></a>Consulte também  
 
[atributos de #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import diretiva](../preprocessor/hash-import-directive-cpp.md)