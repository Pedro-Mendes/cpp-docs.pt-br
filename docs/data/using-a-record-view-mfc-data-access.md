---
title: Usando uma exibição do registro (acesso a dados MFC) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- record views, customizing default code
ms.assetid: 91f2828f-0666-4273-ae28-e4703fd98521
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4107b5e19020843fa50495153841ebcba64301ad
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077679"
---
# <a name="using-a-record-view--mfc-data-access"></a>Usando uma exibição do registro (Acesso a dados MFC)

Este tópico explica como você pode personalizar o código padrão de exibições de registro que o assistente grava para você. Normalmente, você pode restringir a seleção de registro com um [filtro](../data/odbc/recordset-filtering-records-odbc.md) ou [parâmetros](../data/odbc/recordset-parameterizing-a-recordset-odbc.md), talvez [classificação](../data/odbc/recordset-sorting-records-odbc.md) os registros, personalizar a instrução SQL.  
  
Usando o `CRecordView` é muito semelhante a usar [CFormView](../mfc/reference/cformview-class.md). A abordagem básica é usar a exibição do registro para exibir e atualizar talvez os registros de um único conjunto de registros. Além disso, você talvez queira usar outros conjuntos de registros também, conforme discutido em [exibições de registro: preenchendo uma caixa de listagem de um segundo conjunto de registros](../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md).  
  
## <a name="see-also"></a>Consulte também  

[Exibição de registro (Acesso a dados MFC)](../data/record-views-mfc-data-access.md)<br/>
[Lista de drivers ODBC](../data/odbc/odbc-driver-list.md)