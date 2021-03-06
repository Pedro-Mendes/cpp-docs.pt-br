---
title: Trabalhando com um controle guia | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CTabCtrl class [MFC], using
- tab controls [MFC], working with
- tab controls [MFC], using
ms.assetid: 819488e3-4944-44b7-9483-195edb8e0aed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 12de4065774c4813eeb10fab902551db14d10d3a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420836"
---
# <a name="working-with-a-tab-control"></a>Trabalhando com um controle de guia

A maneira mais fácil de usar um controle de guia ([CTabCtrl](../mfc/reference/ctabctrl-class.md)) é ao adicioná-lo a um recurso de modelo de caixa de diálogo com o editor de caixa de diálogo. Você também pode usar um controle guia por si só. MFC chama `InitCommonControls` para você. As tarefas principais são da seguinte maneira:

- [Criando o controle de guia](../mfc/creating-the-tab-control.md)

- [Adicionando guias a um controle guia](../mfc/adding-tabs-to-a-tab-control.md)

- [Processando mensagens de notificação do controle de guia](../mfc/processing-tab-control-notification-messages.md)

Se o objeto de controle de guia é inserido em uma classe de exibição ou a caixa de diálogo pai, o controle é destruído quando o pai é destruído.

## <a name="see-also"></a>Consulte também

[Usando CTabCtrl](../mfc/using-ctabctrl.md)<br/>
[Controles](../mfc/controls-mfc.md)

