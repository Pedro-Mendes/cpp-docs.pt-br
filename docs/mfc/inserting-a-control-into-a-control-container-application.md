---
title: "Contêineres de controle ActiveX: Inserindo um controle em um aplicativo de contêiner de controle | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ActiveX control containers [MFC], inserting controls
- ActiveX controls [MFC], adding to projects
ms.assetid: bbb617ff-872f-43d8-b4d6-c49adb16b148
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3cf288014f47ee1e497ca5a38a3c48368a3b1e6f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="activex-control-containers-inserting-a-control-into-a-control-container-application"></a>Contêineres de controle ActiveX: inserindo um controle em um aplicativo de contêiner de controle
Antes de poder acessar um controle ActiveX de um aplicativo de contêiner de controle ActiveX, você deve adicionar o controle ActiveX para o aplicativo de contêiner usando o [Inserir controle ActiveX](../windows/insert-activex-control-dialog-box.md) caixa de diálogo.  
  
 Para adicionar um controle ActiveX para o projeto de contêiner de controle ActiveX, consulte [exibindo e adicionando controles ActiveX a uma caixa de diálogo](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md).  
  
 Depois de adicionar o controle, você precisa adicionar uma variável de membro (do tipo do controle ActiveX) para a classe de caixa de diálogo. Para obter mais informações sobre esse procedimento, consulte [adicionar uma variável de membro](../ide/adding-a-member-variable-visual-cpp.md).  
  
 Depois de adicionar a variável de membro uma classe, conhecida como uma classe wrapper, é gerada automaticamente e adicionada ao seu projeto. Essa classe é usada como uma interface entre o contêiner de controle e o controle inserido.  
  
## <a name="see-also"></a>Consulte também  
 [Contêineres de controle ActiveX](../mfc/activex-control-containers.md)
