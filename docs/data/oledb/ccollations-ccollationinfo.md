---
title: CCollations, CCollationInfo | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- COLLATION_CATALOG
- m_szCatalog
- CCollationInfo
- CCollations
- CHARACTER_SET_NAME
- CHARACTER_SET_SCHEMA
- m_szCharSetName
- m_szSchema
- CHARACTER_SET_CATALOG
- m_szCharSetSchema
- m_szCharSetCatalog
- m_szPadAttribute
- COLLATION_NAME
- COLLATION_SCHEMA
- m_szName
- COLLATIONS
dev_langs: C++
helpviewer_keywords:
- m_szSchema
- COLLATION_SCHEMA
- m_szCharSetCatalog
- m_szCatalog
- COLLATIONS recordset
- COLLATION_CATALOG
- CCollationInfo parameter class
- m_szName
- COLLATION_NAME
- m_szPadAttribute
- CHARACTER_SET_NAME
- m_szCharSetName
- CHARACTER_SET_SCHEMA
- CHARACTER_SET_CATALOG
- m_szCharSetSchema
- CCollations typedef class
ms.assetid: d8b43c4d-9dd5-4043-b4c8-38c03bfa0c72
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1d393ea44c71b10adc1a748319df670f67b4953a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="ccollations-ccollationinfo"></a>CCollations, CCollationInfo
Chamar a classe typedef **CCollations** para implementar sua classe de parâmetro **CCollationInfo**.  
  
## <a name="remarks"></a>Comentários  
 Consulte [Classes de conjunto de linhas de esquema e Typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) para obter mais informações sobre como usar classes do typedef.  
  
 Essa classe identifica os agrupamentos de caracteres, definidos no catálogo, que são acessíveis para um determinado usuário.  
  
 A tabela a seguir lista os membros de dados de classe e o OLE DB colunas correspondentes. Consulte [AGRUPAMENTOS linhas](https://msdn.microsoft.com/en-us/library/ms715783.aspx) no *referência do programador de DB OLE* para obter mais informações sobre o esquema e as colunas.  
  
|Membros de dados|Colunas de banco de dados OLE|  
|------------------|--------------------|  
|m_szCatalog|COLLATION_CATALOG|  
|m_szSchema|COLLATION_SCHEMA|  
|m_szName|COLLATION_NAME|  
|m_szCharSetCatalog|CHARACTER_SET_CATALOG|  
|m_szCharSetSchema|CHARACTER_SET_SCHEMA|  
|m_szCharSetName|CHARACTER_SET_NAME|  
|m_szPadAttribute|PAD_ATTRIBUTE|  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** atldbsch.h  
  
## <a name="see-also"></a>Consulte também  
 [Classe CRestrictions](../../data/oledb/crestrictions-class.md)