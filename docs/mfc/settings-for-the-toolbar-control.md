---
title: Configurações para o controle de barra de ferramentas | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- toolbar controls [MFC], about toolbar controls
- CToolBarCtrl class [MFC], settings
ms.assetid: 025ba920-b3ee-4d82-9367-e652cd7875b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 81631ba25f898e3740b82c0fab9d5af5da930117
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373342"
---
# <a name="settings-for-the-toolbar-control"></a>Configurações para o controle da barra de ferramentas

Os botões da barra de ferramentas podem exibir um bitmap, uma cadeia de caracteres ou ambos. Por padrão, o tamanho da imagem é definido para as dimensões de 16 por 15 pixels. Todos os botões têm a mesma largura, em pixels de 24 a 22 padrão. Altura da barra de ferramentas é determinada pela altura dos botões e largura da barra de ferramentas é o mesmo que a largura da área de cliente da janela pai, além disso, por padrão.

Uma barra de ferramentas pode ter recursos de personalização internas, incluindo uma caixa de diálogo de personalização definida pelo sistema que permitem ao usuário inserir, excluir ou reorganizar os botões da barra de ferramentas. Um aplicativo determina se os recursos de personalização disponíveis para o usuário e controla a extensão para o qual o usuário pode personalizar a barra de ferramentas. Para obter mais informações sobre como personalizar a barra de ferramentas, consulte a classe [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) na *referência da MFC*.

## <a name="see-also"></a>Consulte também

[Usando CToolBarCtrl](../mfc/using-ctoolbarctrl.md)<br/>
[Controles](../mfc/controls-mfc.md)

