---
title: "Inicializando a caixa de diálogo | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- initializing dialog boxes [MFC]
- OnInitDialog method [MFC]
- modal dialog boxes [MFC], initializing
- modeless dialog boxes [MFC], initializing
- MFC dialog boxes [MFC], initializing
ms.assetid: 968142f5-19f9-4b34-a1d4-8e6412d4379b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2af05011e8f2af2993edf3ea2f82716137b17857
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="initializing-the-dialog-box"></a>Inicializando a caixa de diálogo
Depois da caixa de diálogo caixa e todos os seus controles são criados, mas antes da caixa de diálogo caixa (de qualquer tipo) é exibida na tela, o objeto de caixa de diálogo [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) é chamada de função de membro. Para uma caixa de diálogo modal, isso ocorre durante o `DoModal` chamar. Para uma caixa de diálogo sem janela restrita `OnInitDialog` é chamado quando **criar** é chamado. Você normalmente substitui `OnInitDialog` para inicializar os controles da caixa de diálogo, como definir o texto inicial de uma caixa de edição. Você deve chamar o `OnInitDialog` a função de membro da classe base, `CDialog`, do seu `OnInitDialog` substituir.  
  
 Se você deseja definir a cor de plano de fundo da caixa de diálogo (e que todas as outras caixas de diálogo em seu aplicativo), consulte [definindo a cor de plano de fundo da caixa de diálogo](../mfc/setting-the-dialog-boxs-background-color.md).  
  
## <a name="see-also"></a>Consulte também  
 [Ciclo de vida de uma caixa de diálogo](../mfc/life-cycle-of-a-dialog-box.md)
