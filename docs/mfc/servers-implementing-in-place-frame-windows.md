---
title: 'Servidores: Implementando janelas com moldura no local | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- frame windows [MFC], implementing
- OLE server applications [MFC], frame windows
- servers, in-place frame windows
- frame windows [MFC], in-place
- in-place frame windows
ms.assetid: 09bde4d8-15e2-4fba-8d14-9b954d926b92
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7e26cbb0099f897c65ab3e39338f3c36e77112e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="servers-implementing-in-place-frame-windows"></a>Servidores: implementando janelas de quadro in-loco
Este artigo explica o que você deve fazer para implementar janelas com moldura no local em seu aplicativo de servidor de edição visual, se você não usar o Assistente de aplicativo para criar o aplicativo de servidor. Em vez de seguir o procedimento descrito neste artigo, você pode usar uma classe de janela com moldura no local existente de um aplicativo gerados pelo Assistente de aplicativo ou um exemplo fornecido com o Visual C++.  
  
#### <a name="to-declare-an-in-place-frame-window-class"></a>Para declarar uma classe de janela com moldura no local  
  
1.  Derivar uma classe de janela com moldura no local de `COleIPFrameWnd`.  
  
    -   Use o `DECLARE_DYNCREATE` macro em seu arquivo de cabeçalho de classe.  
  
    -   Use o `IMPLEMENT_DYNCREATE` macro em seu arquivo de implementação (. cpp) de classe. Isso permite que os objetos dessa classe a ser criado pela estrutura.  
  
2.  Declarar um `COleResizeBar` membro da classe de janela do quadro. Isso é necessário se você quiser oferecer suporte ao redimensionamento no local em aplicativos de servidor.  
  
     Declarar um `OnCreate` manipulador de mensagens (usando o **propriedades** janela) e chame **criar** para sua `COleResizeBar` membro, se você definiu.  
  
3.  Se você tiver uma barra de ferramentas, declare um `CToolBar` membro da classe de janela do quadro.  
  
     Substituir o `OnCreateControlBars` a função de membro para criar uma barra de ferramentas quando o servidor está ativo no local. Por exemplo:  
  
     [!code-cpp[NVC_MFCOleServer#1](../mfc/codesnippet/cpp/servers-implementing-in-place-frame-windows_1.cpp)]  
  
     Consulte a discussão sobre esse código após a etapa 5.  
  
4.  Inclua o arquivo de cabeçalho para esta classe de janela com moldura no local no arquivo. cpp principal.  
  
5.  Em `InitInstance` para sua classe de aplicativo, chame o `SetServerInfo` função do objeto de modelo de documento para especificar os recursos e a janela do quadro no local a ser usado na edição aberto e no local.  
  
 A série de função chama **se** instrução cria a barra de ferramentas dos recursos de servidor fornecido. Neste ponto, a barra de ferramentas é parte da hierarquia de janela do contêiner. Porque esta barra de ferramentas é derivada de `CToolBar`, ele passará suas mensagens por seu proprietário, a janela do quadro do aplicativo de contêiner, a menos que você altere o proprietário. É por isso que a chamada para `SetOwner` é necessário. Essa chamada altera a janela em que os comandos são enviados para a janela do quadro no local do servidor, fazendo com que as mensagens a serem passados para o servidor. Isso permite que o servidor reagir a operações na barra de ferramentas que ele oferece.  
  
 A ID para o bitmap de barra de ferramentas deve ser o mesmo que outros recursos no local definidos no seu aplicativo de servidor. Consulte [Menus e recursos: adições de servidor](../mfc/menus-and-resources-server-additions.md) para obter detalhes.  
  
 Para obter mais informações, consulte [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md), [COleResizeBar](../mfc/reference/coleresizebar-class.md), e [CDocTemplate::SetServerInfo](../mfc/reference/cdoctemplate-class.md#setserverinfo) no *referência da biblioteca de classe*.  
  
## <a name="see-also"></a>Consulte também  
 [Servidores](../mfc/servers.md)   
 [Servidores: Implementando um servidor](../mfc/servers-implementing-a-server.md)   
 [Servidores: Implementando documentos de servidor](../mfc/servers-implementing-server-documents.md)   
 [Servidores: itens de servidor](../mfc/servers-server-items.md)
