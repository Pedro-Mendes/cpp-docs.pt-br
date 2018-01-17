---
title: "Visão geral da biblioteca de classe | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.mfc
dev_langs: C++
helpviewer_keywords:
- grouping MFC classes
- MFC, class library
- classes [MFC], MFC
- class libraries, MFC
- class libraries
ms.assetid: 9b0e3152-ac39-4f52-91b4-f20aa3a674aa
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ce5a658c86611c9fdd0663145ae3c09ef6544aa0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="class-library-overview"></a>Visão geral da biblioteca de classes
Esta visão geral categoriza e descreve as classes do Microsoft Foundation Class Library (MFC) versão 9.0. As classes MFC, juntos, constituem uma estrutura de aplicativo — a estrutura de um aplicativo escrito para a API do Windows. A tarefa de programação é preencher o código que é específico para seu aplicativo.  
  
 Classes da biblioteca são apresentados aqui nas seguintes categorias:  
  
-   [Classe raiz: CObject](../mfc/root-class-cobject.md)  
  
-   [Classes de arquitetura do aplicativo MFC](../mfc/mfc-application-architecture-classes.md)  
  
    -   [Classes de suporte de thread e aplicativo](../mfc/application-and-thread-support-classes.md)  
  
    -   [Classes de roteamento do comando](../mfc/command-routing-classes.md)  
  
    -   [Classes de documento](../mfc/document-classes.md)  
  
    -   [Classes de exibição (arquitetura)](../mfc/view-classes-architecture.md)  
  
    -   [Classes de janela com moldura (arquitetura)](../mfc/frame-window-classes-architecture.md)  
  
    -   [Classes de modelo do documento](../mfc/document-template-classes.md)  
  
-   [Classes de janela, caixa de diálogo e controle](../mfc/window-dialog-and-control-classes.md)  
  
    -   [Classes de janela com moldura (Windows)](../mfc/frame-window-classes-windows.md)  
  
    -   [Classes de exibição (Windows)](../mfc/view-classes-windows.md)  
  
    -   [Classes da caixa de diálogo](../mfc/dialog-box-classes.md)  
  
    -   [Classes de controle](../mfc/control-classes.md)  
  
    -   [Classes da barra de controle](../mfc/control-bar-classes.md)  
  
-   [Classes de desenho e impressão](../mfc/drawing-and-printing-classes.md)  
  
    -   [Classes de saída (contexto do dispositivo)](../mfc/output-device-context-classes.md)  
  
    -   [Desenhando classes de ferramenta](../mfc/drawing-tool-classes.md)  
  
-   [Classes de tipo de dados simples](../mfc/simple-data-type-classes.md)  
  
-   [Classes Array, List e Map](../mfc/array-list-and-map-classes.md)  
  
    -   [Classes de modelo para matrizes, listas e mapas](../mfc/template-classes-for-arrays-lists-and-maps.md)  
  
    -   [Classes de matriz prontas para uso](../mfc/ready-to-use-array-classes.md)  
  
    -   [Classes de lista prontas para uso](../mfc/ready-to-use-list-classes.md)  
  
    -   [Classes de mapa prontas para uso](../mfc/ready-to-use-map-classes.md)  
  
-   [Classes de arquivo e banco de dados](../mfc/file-and-database-classes.md)  
  
    -   [Classes de e/s de arquivo](../mfc/file-i-o-classes.md)  
  
    -   [Classes DAO](../mfc/dao-classes.md)  
  
    -   [Classes ODBC](../mfc/odbc-classes.md)  
  
    -   [Classes de banco de dados OLE](../mfc/ole-db-classes.md)  
  
-   [Classes de Internet e rede](../mfc/internet-and-networking-classes.md)  
  
    -   [Classes de Windows Sockets](../mfc/windows-sockets-classes.md)  
  
    -   [Classes da Internet Win32](../mfc/win32-internet-classes.md)  
  
-   [Classes OLE](../mfc/ole-classes.md)  
  
    -   [Classes de contêiner OLE](../mfc/ole-container-classes.md)  
  
    -   [Classes de servidor OLE](../mfc/ole-server-classes.md)  
  
    -   [Classes de transferência de dados e do tipo "arrastar e soltar" do OLE](../mfc/ole-drag-and-drop-and-data-transfer-classes.md)  
  
    -   [Classes de caixa de diálogo comuns OLE](../mfc/ole-common-dialog-classes.md)  
  
    -   [Classes de automação do OLE](../mfc/ole-automation-classes.md)  
  
    -   [Classes de controle OLE](../mfc/ole-control-classes.md)  
  
    -   [Classes de documento ativo](../mfc/active-document-classes.md)  
  
    -   [Classes relacionadas a OLE](../mfc/ole-related-classes.md)  
  
-   [Classes de depuração e exceção](../mfc/debugging-and-exception-classes.md)  
  
    -   [Classes de suporte à depuração](../mfc/debugging-support-classes.md)  
  
    -   [Classes de exceção](../mfc/exception-classes.md)  
  
 A seção [geral filosofia de Design de classe](../mfc/general-class-design-philosophy.md) explica como a biblioteca do MFC foi criada.  
  
 Para obter uma visão geral do framework, consulte [usando as Classes para escrever aplicativos para Windows](../mfc/using-the-classes-to-write-applications-for-windows.md). Algumas das classes listadas acima são classes de uso gerais que podem ser usados fora do framework e fornecem abstrações úteis, como coleções, exceções, arquivos e cadeias de caracteres.  
  
 Para ver a herança de uma classe, use o [gráfico da hierarquia de classe](../mfc/hierarchy-chart.md).  
  
 Além das classes listadas nesta visão geral, a biblioteca do MFC contém um número de funções globais, variáveis globais e macros. Há uma visão geral e uma lista detalhada no tópico [Macros e globais MFC](../mfc/reference/mfc-macros-and-globals.md), que segue a referência alfabética para as classes do MFC.  
  
## <a name="see-also"></a>Consulte também  
 [Aplicativos da área de trabalho MFC](../mfc/mfc-desktop-applications.md)
