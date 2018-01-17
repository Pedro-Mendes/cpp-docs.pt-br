---
title: "Sequência de criação da janela geral | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- sequence [MFC], window creation
- frame windows [MFC], creating
- windows [MFC], creating
- sequence [MFC]
ms.assetid: 9cd8c7ea-5e24-429e-b6d9-d7b6041d8ba6
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 59bed4387a6b8e6edeb504e29d221e76a0b39d18
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="general-window-creation-sequence"></a>Sequência de criação da janela geral
Quando você cria uma janela de sua preferência, como um filho janela, a estrutura usa muito o mesmo processo descrito em [criação de documento/exibição](../mfc/document-view-creation.md).  
  
 Todas as classes de janela fornecidas pelo empregar MFC [construção de dois estágios](../mfc/one-stage-and-two-stage-construction-of-objects.md). Isto é, durante uma chamada de C++ **novo** operador, o construtor aloca e inicializa um objeto C++, mas não cria uma janela do Windows correspondente. Isso é feito depois chamando o [criar](../mfc/reference/cwnd-class.md#create) função membro de objeto de janela.  
  
 O **criar** função membro faz com que a janela do Windows e armazena seu `HWND` no membro de dados públicos do objeto C++ [m_hWnd](../mfc/reference/cwnd-class.md#m_hwnd). **Criar** oferece flexibilidade completa sobre os parâmetros de criação. Antes de chamar **criar**, talvez você queira registrar uma classe de janela com a função global [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) para definir os estilos de ícone e a classe do quadro.  
  
 Janelas com moldura, você pode usar o [LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) a função de membro em vez de **criar**. `LoadFrame`faz a janela do Windows usando menos parâmetros. Ele obtém muitos valores padrão de recursos, incluindo a legenda do quadro, ícone, tabela de Aceleradores e menu.  
  
> [!NOTE]
>  O ícone, tabela de Aceleradores e recursos de menu devem ter uma ID de recurso comuns, como **IDR_MAINFRAME**, para que eles possam ser carregados pelo LoadFrame.  
  
## <a name="what-do-you-want-to-know-more-about"></a>O que você deseja saber mais sobre  
  
-   [Objetos de janela](../mfc/window-objects.md)  
  
-   [Registrando "classes de janela"](../mfc/registering-window-classes.md)  
  
-   [Destruindo objetos de janela](../mfc/destroying-window-objects.md)  
  
-   [Criando janelas com moldura de documento](../mfc/creating-document-frame-windows.md)  
  
## <a name="see-also"></a>Consulte também  
 [Criando janelas](../mfc/creating-windows.md)
