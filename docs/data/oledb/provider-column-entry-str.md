---
title: "PROVIDER_COLUMN_ENTRY_STR | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PROVIDER_COLUMN_ENTRY_STR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Macro PROVIDER_COLUMN_ENTRY_STR"
ms.assetid: f1c27dd6-9ab8-4821-8685-d4dd15e76e88
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# PROVIDER_COLUMN_ENTRY_STR
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Representa uma coluna específica com suporte do provedor.  
  
## Sintaxe  
  
```  
  
PROVIDER_COLUMN_ENTRY_STR(  
name  
, ordinal, member )  
```  
  
#### Parâmetros  
 *nome*  
 \[in\] o nome da coluna.  
  
 `ordinal`  
 \[in\] o número da coluna.  A menos que a coluna é uma coluna do indicador, o número da coluna não deve ser 0.  
  
 `member`  
 \[in\] a variável de membro na classe de dados que armazena os dados.  
  
## Comentários  
 Use esta macro quando os dados da coluna é assumido como [DBTYPE\_STR](https://msdn.microsoft.com/en-us/library/ms711251.aspx).  
  
## Exemplo  
 Consulte [BEGIN\_PROVIDER\_COLUMN\_MAP](../../data/oledb/begin-provider-column-map.md).  
  
## Requisitos  
 **Header:** atldb.h  
  
## Consulte também  
 [Macros para modelos de provedor de banco de dados OLE](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [Modelos de provedor de banco de dados OLE](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Arquitetura de modelo do provedor de banco de dados OLE](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Criando um provedor de banco de dados OLE](../../data/oledb/creating-an-ole-db-provider.md)