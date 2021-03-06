---
title: Itens de retorno de chamada e a máscara de retorno de chamada | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- callback items in CListCtrl class [MFC]
- CListCtrl class [MFC], callback item and callback mask
ms.assetid: 67c1f76f-6144-453e-9376-6712f89430ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0711fccb142d9774c37f2cb2d8f576bf7fddd128
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422838"
---
# <a name="callback-items-and-the-callback-mask"></a>Itens e máscara de retorno de chamada

Para cada um de seus itens, um controle de exibição de lista normalmente armazena o texto do rótulo, o índice de imagem de lista de ícones do item, e um conjunto de bit de sinalizadores para o estado do item. Você pode definir itens individuais como itens de retorno de chamada, que são úteis se seu aplicativo já armazena algumas informações para um item.

Definir um item como um item de retorno de chamada, especificando os valores apropriados para o `pszText` e `iImage` os membros a **LV_ITEM** estrutura (consulte [CListCtrl::GetItem](../mfc/reference/clistctrl-class.md#getitem)). Se o aplicativo mantiver do item ou do subitem texto, especifique o **LPSTR_TEXTCALLBACK** valor para o `pszText` membro. Se o aplicativo mantém controle sobre o ícone do item, especifique o **I_IMAGECALLBACK** valor para o `iImage` membro.

Além de definir os itens de retorno de chamada, você também pode modificar a máscara de retorno de chamada do controle. Essa máscara é um conjunto de sinalizadores de bit que especificam os estados de item para o qual o aplicativo, em vez do controle, armazena os dados atuais. A máscara de retorno de chamada se aplica a todos os itens do controle, ao contrário de designação de item de retorno de chamada, que se aplica a um item específico. A máscara de retorno de chamada é zero por padrão, o que significa que o controle acompanha todos os estados de item. Para alterar esse comportamento padrão, inicialize a máscara para qualquer combinação dos valores a seguir:

- **LVIS_CUT** o item está marcado para uma operação recortar e colar.

- **LVIS_DROPHILITED** o item está realçado como um destino de arrastar e soltar.

- **LVIS_FOCUSED** o item tem o foco.

- **LVIS_SELECTED** o item está selecionado.

- **LVIS_OVERLAYMASK** o aplicativo armazena o índice de lista de imagem da imagem de sobreposição para cada item.

- **LVIS_STATEIMAGEMASK** o aplicativo armazena o índice de lista de imagens da imagem do estado atual para cada item.

Para obter mais informações sobre como recuperar e definir essa máscara, consulte [CListCtrl::GetCallbackMask](../mfc/reference/clistctrl-class.md#getcallbackmask) e [CListCtrl::SetCallbackMask](../mfc/reference/clistctrl-class.md#setcallbackmask).

## <a name="see-also"></a>Consulte também

[Usando CListCtrl](../mfc/using-clistctrl.md)<br/>
[Controles](../mfc/controls-mfc.md)

