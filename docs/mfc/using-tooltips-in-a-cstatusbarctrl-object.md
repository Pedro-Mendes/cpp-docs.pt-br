---
title: Usando dicas de ferramenta em um objeto CStatusBarCtrl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- tool tips [MFC], using in status bars
- status bars [MFC], tool tips
- CStatusBarCtrl class [MFC], tool tips
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f17dff6680209664e9d029404e4ef012b9f12046
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392353"
---
# <a name="using-tooltips-in-a-cstatusbarctrl-object"></a>Usando dicas de ferramenta em um objeto CStatusBarCtrl

Para habilitar dicas de ferramenta para um controle de barra de status, crie o `CStatusBarCtrl` objeto com o estilo SBT_TOOLTIPS.

> [!NOTE]
>  Se você estiver usando um `CStatusBar` objeto para implementar sua barra de status, use o `CStatusBar::CreateEx` função. Ele permite que você especificar estilos adicionais para o embedded `CStatusBarCtrl` objeto.

Uma vez a `CStatusBarCtrl` objeto foi criado com êxito, use [CStatusBarCtrl::SetTipText](../mfc/reference/cstatusbarctrl-class.md#settiptext) e [CStatusBarCtrl::GetTipText](../mfc/reference/cstatusbarctrl-class.md#gettiptext) para definir e recuperar o texto da dica para um painel específico.

Depois que a dica de ferramenta tiver sido definida, ele é exibido somente se a parte tem um ícone e nenhum texto, ou se todo o texto não pode ser exibido dentro da parte. Não há suporte para dicas de ferramenta no modo simples.

## <a name="see-also"></a>Consulte também

[Usando CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)<br/>
[Controles](../mfc/controls-mfc.md)

