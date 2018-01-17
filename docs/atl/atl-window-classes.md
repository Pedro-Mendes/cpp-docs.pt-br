---
title: Classes de janela ATL | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ATL, windows
- windows [C++], subclassing
- windows [C++], superclassing
- windows [C++], ATL
- subclassing ATL window classes
- superclassing
- superclassing, ATL
ms.assetid: 1d12b708-de3e-49d5-9e41-42fe4769fa62
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d4cce6fd98d4ea476900d8b248442fdddbe3c2d2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="atl-window-classes"></a>Classes de janela ATL
ATL inclui várias classes que permitem que você use e implementar o windows. Essas classes, como outras classes ATL, fornecem uma implementação eficiente que não impõe uma sobrecarga no seu código.  
  
 Esta seção descreve as classes de janela ATL e explica como usá-los.  
  
## <a name="in-this-section"></a>Nesta seção  
 [Introdução às classes de janela da ATL](../atl/introduction-to-atl-window-classes.md)  
 Resumidamente descreve cada classe de janela ATL e fornece links para o material de referência sobre eles.  
  
 [Usando uma janela](../atl/using-a-window.md)  
 Discute como usar `CWindow` para manipular uma janela.  
  
 [Implementando uma janela](../atl/implementing-a-window.md)  
 Discute os manipuladores de mensagens, mapas de mensagem e usando `CWindowImpl`. Inclui detalhes sobre superclassing e subclassificação.  
  
 [Implementando uma caixa de diálogo](../atl/implementing-a-dialog-box.md)  
 Aborda os dois métodos para adicionar uma classe de caixa de diálogo e mostra um exemplo de código.  
  
 [Usando janelas independentes](../atl/using-contained-windows.md)  
 Discute o windows independentes em ATL, que são janelas delegar suas mensagens para um objeto de contêiner em vez de tratá-las na própria classe.  
  
 [Noções básicas sobre as características da janela](../atl/understanding-window-traits.md)  
 Discute as classes de características de janela em ATL. Essas classes fornecem um método simples para padronizar os estilos usados para a criação de um objeto de janela.  
  
## <a name="related-sections"></a>Seções relacionadas  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Fornece links para tópicos conceituais sobre como programar usando o Active Template Library.  
  
 [Classes de suporte ao Windows](../atl/windows-support-classes.md)  
 Lista de classes ATL adicionais que dão suporte ao windows e mapas de mensagem em ATL.
