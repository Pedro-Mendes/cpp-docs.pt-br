---
title: "Recuperando dados do objeto de caixa de diálogo | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- dialog boxes [MFC], retrieving user data
- dialog box data [MFC]
- data [MFC], retrieving
- GetDlgItemText method [MFC]
- SetDlgItemText method [MFC]
- SetWindowText method [MFC]
- dialog box data [MFC], retrieving
- retrieving data [MFC]
- user input [MFC], retrieving from MFC dialog boxes
- capturing user input [MFC]
- dialog box controls [MFC], initializing values
- DDX (dialog data exchange) [MFC]
- MFC dialog boxes [MFC], retrieving user input
- data retrieval [MFC], dialog boxes
- data [MFC], dialog boxes
- DDX (dialog data exchange) [MFC], about DDX
- DDX (dialog data exchange) [MFC], retrieving data from Dialog object
- GetWindowText method [MFC]
ms.assetid: bdca2b61-6b53-4c2e-b426-8712c7a38ec0
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d4b50ae3036a6f262312c7a05c2de093a977a588
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="retrieving-data-from-the-dialog-object"></a>Recuperando dados a partir do objeto da caixa de diálogo
O framework fornece uma maneira fácil para inicializar valores de controles em uma caixa de diálogo e para recuperar os valores dos controles. A abordagem manual mais trabalhosa é chamar funções, como o `SetDlgItemText` e `GetDlgItemText` funções membro de classe `CWnd`, que se aplicam ao windows do controle. Com essas funções, você acessar cada controle individualmente para definir ou obter seu valor, chamar funções como `SetWindowText` e `GetWindowText`. Abordagem da estrutura automatiza a inicialização e recuperação.  
  
 Troca de dados de caixa de diálogo (DDX) permite a troca de dados entre os controles nas variáveis de membro e de caixa de diálogo no objeto de caixa de diálogo mais facilmente. Essa troca funciona de duas maneiras. Para inicializar os controles na caixa de diálogo, você pode definir os valores de membros de dados no objeto de caixa de diálogo e o framework transferirá os valores para os controles antes da caixa de diálogo é exibida. Em seguida, você pode a qualquer momento atualizar os membros de dados de caixa de diálogo com os dados inseridos pelo usuário. Nesse ponto, você pode usar os dados consultando as variáveis de membro de dados.  
  
 Você também pode organizar para os valores dos controles de caixa de diálogo para serem validados automaticamente com a validação de dados de caixa de diálogo (DDV).  
  
 DDX e DDV são explicados em mais detalhes em [troca de dados de caixa de diálogo e validação](../mfc/dialog-data-exchange-and-validation.md).  
  
 Para uma caixa de diálogo modal, você pode recuperar os dados que o usuário inseriu quando `DoModal` retorna **IDOK** , mas antes da caixa de diálogo objeto é destruído. Para uma caixa de diálogo sem janela restrita, você pode recuperar dados do objeto de caixa de diálogo a qualquer momento chamando `UpdateData` com o argumento **TRUE** e, em seguida, acessando variáveis de membro de classe de caixa de diálogo. Este assunto é discutido em mais detalhes em [troca de dados de caixa de diálogo e validação](../mfc/dialog-data-exchange-and-validation.md).  
  
## <a name="see-also"></a>Consulte também  
 [Ciclo de vida de uma caixa de diálogo](../mfc/life-cycle-of-a-dialog-box.md)
