---
title: 'Como: adicionar controles de faixa de opções e manipuladores de eventos | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- event handlers [MFC], adding
- ribbon controls [MFC], adding
ms.assetid: b31f25bc-ede7-49c3-9e3c-dffe4e174a69
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f3c4af695553bc97815915454bda2aae481543e9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427947"
---
# <a name="how-to-add-ribbon-controls-and-event-handlers"></a>Como adicionar controles de faixa de opções e manipuladores de evento

Controles da faixa de opções são elementos como botões e caixas de combinação, que você adiciona aos painéis. Painéis são áreas da barra de faixa de opções que exibem um grupo de controles relacionados.

Neste tópico, abra o Designer de faixa de opções, adicione um botão e, em seguida, vincule um evento que exibe "Hello World".

### <a name="to-open-the-ribbon-designer"></a>Para abrir o Designer de faixa de opções

1. No Visual Studio, sobre o **modo de exibição** menu, clique em **exibição de recurso**.

1. Na **exibição de recurso**, clique duas vezes no recurso de faixa de opções para exibi-lo na superfície de design.

### <a name="to-add-a-button-and-an-event-handler"></a>Para adicionar um botão e um manipulador de eventos

1. Dos **barra de ferramentas**, clique em **botão** e arraste-o para um painel na superfície de design.

1. Clique no botão e, em seguida, clique em **Adicionar manipulador de eventos**.

1. No **Assistente de manipulador de eventos**, confirme as configurações padrão e clique em **adicionar e editar**. Para obter mais informações, consulte [Assistente de manipulador de eventos](../ide/event-handler-wizard.md).

1. No editor de códigos, adicione o seguinte código para a função de manipulador:

```
    MessageBox((LPCTSTR)L"Hello World");

```

## <a name="see-also"></a>Consulte também

[Exemplo de gadget de fita: Aplicativo de gadget de faixa de opções](../visual-cpp-samples.md)<br/>
[Designer da faixa de opções (MFC)](../mfc/ribbon-designer-mfc.md)

