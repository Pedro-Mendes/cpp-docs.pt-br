---
title: CReBar vs. CReBarCtrl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CReBar
- CReBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- CReBar class [MFC], vs. CReBarCtrl
- rebar controls [MFC], CReBarCtrl class [MFC]
- GetReBarCtrl class [MFC]
ms.assetid: 7f9c1d7e-5d5f-4956-843c-69ed3df688d0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6133e298cd0bc5b497fbbba47982a755afeefb2e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442845"
---
# <a name="crebar-vs-crebarctrl"></a>CReBar vs. CReBarCtrl

MFC fornece classes para criar rebars: [CReBar](../mfc/reference/crebar-class.md) e [CReBarCtrl](../mfc/reference/crebarctrl-class.md) (que encapsula a API de controle comum do Windows). `CReBar` fornece toda a funcionalidade do controle rebar comum, e trata muitas das configurações necessárias de controle comuns e estruturas para você.

`CReBarCtrl` é uma classe wrapper para um controle rebar Win32 e, portanto, pode ser mais fácil de implementar se você não pretende integrar o rebar na arquitetura do MFC. Se você planeja usar `CReBarCtrl` e integrar o rebar na arquitetura do MFC, você deve tomar cuidado adicional para se comunicar manipulações de controle rebar ao MFC. Essa comunicação não é difícil; No entanto, ele é trabalho adicional é desnecessário quando você usar `CReBar`.

Visual C++ fornece duas maneiras de tirar proveito do controle rebar comuns.

- Criar o rebar usando `CReBar`e, em seguida, chame [CReBar::GetReBarCtrl](../mfc/reference/crebar-class.md#getrebarctrl) para obter acesso ao `CReBarCtrl` funções de membro.

    > [!NOTE]
    >  `CReBar::GetReBarCtrl` é uma função de membro embutida que projeta o **isso** ponteiro do objeto rebar. Isso significa que, em tempo de execução, a chamada de função tem sem sobrecarga.

- Criar o rebar usando [CReBarCtrl](../mfc/reference/crebarctrl-class.md)do construtor.

Qualquer um dos métodos lhe darão acesso às funções de membro do controle rebar. Quando você chama `CReBar::GetReBarCtrl`, ele retorna uma referência a um `CReBarCtrl` , você pode usar o conjunto de funções de membro de objeto. Ver [CReBar](../mfc/reference/crebar-class.md) para obter informações sobre como construir e criar um rebar usando `CReBar`.

## <a name="see-also"></a>Consulte também

[Usando CReBarCtrl](../mfc/using-crebarctrl.md)<br/>
[Controles](../mfc/controls-mfc.md)

