---
title: Macros e globais MFC | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- MFC, global functions and variables
- MFC, macros
- global functions, MFC
- macros, MFC
- global functions
- global variables, MFC
- Afx naming convention
- macros
ms.assetid: add4e33f-0e62-4d27-be14-896cb8675d22
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: b943ef8dd652df061965fe81ecc9c08115636141
ms.openlocfilehash: 7dc1f904d1c3f76635a49db1747578e2ce0b0b3b
ms.lasthandoff: 04/04/2017

---
# <a name="mfc-macros-and-globals"></a>Macros e globais MFC
A biblioteca Microsoft Foundation Class pode ser dividida em duas seções principais: (1) as classes MFC e (2) macros e globais. Se uma função ou variável não for um membro de uma classe, é uma função global ou variável.  
  
 A biblioteca do MFC e a biblioteca de modelo ativa (ATL) compartilham macros de conversão de cadeia de caracteres. Para obter mais informações, consulte [Macros de conversão de cadeia de caracteres](../../atl/reference/string-conversion-macros.md) na documentação do ATL.  
  
 As macros e globais MFC oferecem funcionalidade nas categorias a seguir.  
  
## <a name="general-mfc"></a>MFC geral  
  
-   [Tipos de dados](data-types-mfc.md)  
  
-   [Conversão de tipos de objetos de classe MFC](type-casting-of-mfc-class-objects.md)  
  
-   [Serviços do modelo de objeto de tempo de execução](run-time-object-model-services.md)  
  
-   [Serviços de diagnóstico](diagnostic-services.md)  
  
-   [Processamento de exceção](exception-processing.md)  
  
-   [Formatação CString e exibição da caixa de mensagem](cstring-formatting-and-message-box-display.md)  
  
-   [Mapas de mensagem](message-map-macros-mfc.md)  

-   [Delegado e mapas de Interface](delegate-and-interface-maps.md)

-   [Módulos e DLLs](extension-dll-macros.md)
  
-   [Gerenciamento e informações do aplicativo](application-information-and-management.md)  
  
-   [IDs de comando e janela padrão](standard-command-and-window-ids.md)  
  
-   [Auxiliares da classe de coleção](collection-class-helpers.md)  
  
-   [Funções de bitmap cinza e pontilhado](gray-and-dithered-bitmap-functions.md)  
  
-   [Rotinas de troca (DDX) de dados de caixa de diálogo padrão](standard-dialog-data-exchange-routines.md)  
  
-   [Rotinas de validação (DDV) de dados de caixa de diálogo padrão](standard-dialog-data-validation-routines.md)  
  
-   [Mensagens AFX](afx-messages.md)  
  
-   [Estilos de controle de barra de ferramentas](toolbar-control-styles.md)  
  
-   [Enumeração CMFCImagePaintArea::IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md)  

  
## <a name="database"></a>Banco de Dados  
  
-   [Registrar funções de troca de campos (RFX)](record-field-exchange-functions.md) e [funções de troca de campos de registro em massa (RFX em massa)](record-field-exchange-functions.md) para as classes MFC ODBC  
  
-   [Registrar funções de troca (DFX) do campo](record-field-exchange-functions.md) para as classes DAO MFC  
  
-   [Funções de troca de dados de caixa de diálogo (DDX) para CRecordView e CDaoRecordView](dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md) (classes MFC ODBC e DAO)  
  
-   [Funções de troca (DDX) de dados de caixa de diálogo para controles OLE](dialog-data-exchange-functions-for-ole-controls.md)  
  
-   [Macros e globais para auxiliar na chamada de funções de conectividade de banco de dados aberto (ODBC) API diretamente](database-macros-and-globals.md)  
  
-   [Encerramento e inicialização do mecanismo de banco de dados DAO](dao-database-engine-initialization-and-termination.md)  
  
## <a name="internet"></a>Internet  
  
-   [URL da Internet globais de análise](internet-url-parsing-globals.md)  
  
## <a name="dhtml--dhtml-event-maps"></a>DHTML / mapas de evento DHTML  
  
-   [Macros de auxiliar (DDX) de troca de dados de caixa de diálogo DHTML](ddx-dhtml-helper-macros.md)  
  
-   [Mapas de evento DHTML](dhtml-event-maps.md)  
  
## <a name="ole"></a>OLE  
  
-   [Inicialização OLE](ole-initialization.md)  
  
-   [Controle de aplicativo](application-control.md)  
  
-   [Mapas de expedição](dispatch-maps.md)  
  
 Além disso, o MFC fornece uma função chamada [AfxEnableControlContainer](http://msdn.microsoft.com/library/7aa0b9d2-5329-4bc3-9d41-856e30fe2c2b) que permite que qualquer contêiner OLE desenvolvido com MFC 4.0 para dar suporte total inseridos controles OLE.  
  
## <a name="ole-controls"></a>Controles OLE  
  
-   [Constantes de tipo de parâmetro variante](variant-parameter-type-constants.md)  
  
-   [Acesso à biblioteca de tipos](type-library-access.md)  
  
-   [Páginas de propriedade](property-pages-mfc.md)  
  
-   [Mapas de evento](event-maps.md)  
  
-   [Mapas de coleta de eventos](event-sink-maps.md)  
  
-   [Mapas de Conexão](connection-maps.md)  
  
-   [Registrando controles OLE](registering-ole-controls.md)  
  
-   [Fábricas de classe e licenciamento](class-factories-and-licensing.md)  
  
-   [Persistência de controles OLE](persistence-of-ole-controls.md)  
  
 Rapidamente, a primeira parte desta seção descreve cada uma das categorias anteriores e lista as macros na categoria, juntamente com descrições breves de funcionalidade e globais. Após isso são as descrições das funções globais, variáveis globais e macros na biblioteca do MFC.  
  
> [!NOTE]
>  Muitas funções globais começam com o prefixo "Afx", mas alguns, por exemplo, as funções de dados de caixa de diálogo (DDX) do exchange e muitas das funções de banco de dados, não seguem a convenção. Todas as variáveis globais começar com "afx" como prefixo. Macros não iniciar com qualquer prefixo específico, mas eles são escritos em letras maiusculas.  
  
## <a name="see-also"></a>Consulte também  
 [Visão geral da classe](../../mfc/class-library-overview.md)



