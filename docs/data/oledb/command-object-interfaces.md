---
title: Interfaces de objeto de comando | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- command object interfaces [C++]
- command objects [OLE DB]
- OLE DB [C++], command object interfaces
ms.assetid: dacff5ae-252c-4f20-9ad7-4e602cc48536
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ea824fda89ccf45c62145a0fe72e55edc614970a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106931"
---
# <a name="command-object-interfaces"></a>Interfaces de objeto do comando

O objeto de comando usa o `IAccessor` interface para especificar associações de parâmetro. O consumidor chama `IAccessor::CreateAccessor`, passando uma matriz de `DBBINDING` estruturas. `DBBINDING` contém informações sobre as associações de coluna (por exemplo, tipo e comprimento). O provedor recebe as estruturas e determina como os dados devem ser transferidos e se as conversões são necessárias.  
  
O `ICommandText` interface fornece uma maneira de especificar um comando de texto. O `ICommandProperties` interface manipula todas as propriedades de comando.  
  
## <a name="see-also"></a>Consulte também  

[Arquitetura de modelo do provedor do OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)