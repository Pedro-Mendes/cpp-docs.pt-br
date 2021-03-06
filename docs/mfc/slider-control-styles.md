---
title: Estilos de controle deslizante | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- slider controls [MFC], styles
- CSliderCtrl class [MFC], styles
- styles [MFC], CSliderCtrl
- styles [MFC], slider controls
ms.assetid: 64c491fc-5af1-4f97-ae30-854071b3dc02
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ddc96133f07011969e3d2afc4b1707e9f395e6b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424112"
---
# <a name="slider-control-styles"></a>Estilos de controle de controle deslizante

Controles deslizantes ([CSliderCtrl](../mfc/reference/csliderctrl-class.md)) pode ter uma orientação vertical ou horizontal. Eles podem ter marcas de escala em ambos os lados, os lados, ou nenhum dos dois. Eles também podem ser usados para especificar um intervalo de valores consecutivos. Essas propriedades são controladas usando estilos de controle deslizante, que você especifica ao criar o controle deslizante.

Os estilos TBS_HORZ e TBS_VERT determinam a orientação do controle deslizante. Se você não especificar uma orientação, o controle deslizante é orientado horizontalmente.

O estilo TBS_AUTOTICKS cria um controle deslizante que tem uma marca de escala para cada incremento em seu intervalo de valores. Essas marcas são adicionadas automaticamente quando você chama o [SetRange](../mfc/reference/csliderctrl-class.md#setrange) função de membro. Se você não especificar TBS_AUTOTICKS, você pode usar funções de membro, como [SetTic](../mfc/reference/csliderctrl-class.md#settic) e [SetTicFreq](../mfc/reference/csliderctrl-class.md#setticfreq), para especificar as posições das marcas de escala. Para criar um controle deslizante que não exibe marcas de escala, você pode usar o estilo TBS_NOTICKS.

Você pode exibir as marcas de escala em um ou ambos os lados do controle deslizante. Para controles de barra deslizante horizontal, você pode especificar o estilo TBS_BOTTOM ou TBS_TOP. Para controles slider vertical, você pode especificar o estilo TBS_RIGHT ou TBS_LEFT. (TBS_BOTTOM e TBS_RIGHT são as configurações padrão.) Para as marcas de escala em ambos os lados do controle deslizante em qualquer orientação, especifique o estilo TBS_BOTH.

Um controle deslizante pode exibir um intervalo de seleção somente se você especificar o estilo TBS_ENABLESELRANGE ao criá-lo. Quando um controle deslizante tem esse estilo, as marcas de escala nas posições inicial e finais de um intervalo de seleção são exibidas como triângulos (em vez de traços verticais) e o intervalo de seleção é realçado. Por exemplo, os intervalos de seleção podem ser útil em um aplicativo simples do agendamento. O usuário pode selecionar um intervalo de marcas de escala correspondente para horas em um dia para identificar um horário agendado.

Por padrão, o tamanho do controle deslizante de um controle deslizante varia à medida que as alterações de intervalo de seleção. Se o controle deslizante tem o estilo TBS_FIXEDLENGTH, o tamanho do controle deslizante permanece o mesmo, mesmo se o intervalo de seleção é alterado. Um controle deslizante que tem o estilo TBS_NOTHUMB não inclui um controle deslizante.

## <a name="see-also"></a>Consulte também

[Usando CSliderCtrl](../mfc/using-csliderctrl.md)<br/>
[Controles](../mfc/controls-mfc.md)

