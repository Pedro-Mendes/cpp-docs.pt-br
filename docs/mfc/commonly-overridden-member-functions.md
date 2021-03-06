---
title: Funções de membro normalmente substituídas | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CDialog class [MFC], members
- OnInitDialog function
- dialog classes [MFC], commonly overridden member functions
- OnCancel function
- overriding, dialog class members
- OnOK function
- MFC dialog boxes [MFC], overriding member functions
ms.assetid: 78eb566c-e361-4c86-8db5-c7e2791b249a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aabc88db4fcb2a484ca44feea8fcdf7727e23a16
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46431405"
---
# <a name="commonly-overridden-member-functions"></a>Funções de membro normalmente substituídas

Mais provavelmente, a seguinte tabela lista as funções de membro para substituir em seu `CDialog`-classe derivada.

### <a name="commonly-overridden-member-functions-of-class-cdialog"></a>Normalmente substituídas funções de membro de classe CDialog

|Função de membro|Ele responde de mensagem|Finalidade da substituição|
|---------------------|----------------------------|-----------------------------|
|`OnInitDialog`|**WM_INITDIALOG**|Inicialize os controles da caixa de diálogo.|
|`OnOK`|**BN_CLICKED** do botão **IDOK**|Responda quando o usuário clica no botão Okey.|
|`OnCancel`|**BN_CLICKED** do botão **IDCANCEL**|Responde quando o usuário clica no botão Cancelar.|

`OnInitDialog`, `OnOK`, e `OnCancel` são funções virtuais. Para substituí-las, você deve declarar uma função de substituição em sua classe derivada de caixa de diálogo usando o [janela de propriedades](/visualstudio/ide/reference/properties-window).

`OnInitDialog` é chamado antes que a caixa de diálogo é exibida. Você deve chamar o padrão `OnInitDialog` manipulador da sua substituição — normalmente, como a primeira ação no manipulador. Por padrão, `OnInitDialog` retorna **verdadeiro** para indicar que o foco deve ser definido como o primeiro controle na caixa de diálogo.

`OnOK` normalmente é substituído para caixas de diálogo sem janela restrita, mas não modal. Se você substituir esse manipulador para uma caixa de diálogo modal, chame a versão da classe base de sua substituição — para garantir que `EndDialog` é chamado — ou chamar `EndDialog` por conta própria.

`OnCancel` Normalmente, é substituído para caixas de diálogo sem janela restrita.

Para obter mais informações sobre essas funções de membro, consulte a classe [CDialog](../mfc/reference/cdialog-class.md) na *referência da MFC* e a discussão sobre [ciclo de vida de uma caixa de diálogo](../mfc/life-cycle-of-a-dialog-box.md).

## <a name="see-also"></a>Consulte também

[Caixas de diálogo](../mfc/dialog-boxes.md)<br/>
[Funções de membro normalmente adicionadas](../mfc/commonly-added-member-functions.md)
