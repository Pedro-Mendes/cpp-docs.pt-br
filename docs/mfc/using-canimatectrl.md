---
title: Usando CAnimateCtrl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CAnimateCtrl
dev_langs:
- C++
helpviewer_keywords:
- animation controls [MFC], CAnimateCtrl class
- controls [MFC], animation
- CAnimateCtrl class [MFC], about CAnimateCtrl class [MFC]
ms.assetid: 696c0805-bef0-4e2e-a9e7-b37b9215b7f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b02a07b1f5a433ffa9525da8e8a7f942c9034d54
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398450"
---
# <a name="using-canimatectrl"></a>Usando CAnimateCtrl

Um controle de animação, representado pela classe [CAnimateCtrl](../mfc/reference/canimatectrl-class.md), é uma janela que exibe um clipe em formato de áudio vídeo intercalados (AVI) — o formato de áudio/vídeo do Windows padrão. Um clipe AVI é uma série de quadros de bitmap, como um filme.

Uma vez que o thread continua executando enquanto o clipe AVI é exibido, um uso comum para um controle de animação é indicar a atividade do sistema durante uma operação demorada. Por exemplo, a caixa de diálogo Localizar o Windows exibe uma lente de movimentação como o sistema procurará um arquivo.

Controles de animação só podem reproduzir clipes AVI simples, e eles não dão suporte a som. (Para obter uma lista completa de limitações, consulte [CAnimateCtrl](../mfc/reference/canimatectrl-class.md).) Uma vez que os recursos de um controle de animação são muito limitados e sujeitos a alterações, você deve usar uma alternativa como o controle MCIWnd se precisar de um controle para fornecer a reprodução de multimídia e/ou recursos de gravação. Para obter mais informações sobre o controle MCIWnd, consulte a documentação de multimídia.

## <a name="what-do-you-want-to-know-more-about"></a>O que você deseja saber mais sobre

- [Usando um controle de animação](../mfc/using-an-animation-control.md)

- [Notificações enviadas por controles de animação](../mfc/notifications-sent-by-animation-controls.md)

## <a name="see-also"></a>Consulte também

[Controles](../mfc/controls-mfc.md)

