---
title: Classe CMDIChildWndEx | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMDIChildWndEx
- AFXMDICHILDWNDEX/CMDIChildWndEx
- AFXMDICHILDWNDEX/CMDIChildWndEx::ActivateTopLevelFrame
- AFXMDICHILDWNDEX/CMDIChildWndEx::AddPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::AddTabbedPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::AdjustDockingLayout
- AFXMDICHILDWNDEX/CMDIChildWndEx::CanShowOnMDITabs
- AFXMDICHILDWNDEX/CMDIChildWndEx::CanShowOnTaskBarTabs
- AFXMDICHILDWNDEX/CMDIChildWndEx::CanShowOnWindowsList
- AFXMDICHILDWNDEX/CMDIChildWndEx::DockPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::DockPaneLeftOf
- AFXMDICHILDWNDEX/CMDIChildWndEx::EnableAutoHidePanes
- AFXMDICHILDWNDEX/CMDIChildWndEx::EnableDocking
- AFXMDICHILDWNDEX/CMDIChildWndEx::EnableTaskbarThumbnailClipRect
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetDockingManager
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetDocumentName
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetFrameIcon
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetFrameText
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetRelatedTabGroup
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTabbedPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTabProxyWnd
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTaskbarPreviewWnd
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTaskbarThumbnailClipRect
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetToolbarButtonToolTipText
- AFXMDICHILDWNDEX/CMDIChildWndEx::InsertPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::InvalidateIconicBitmaps
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsPointNearDockSite
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsReadOnly
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsRegisteredWithTaskbarTabs
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsTabbedPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsTaskbarTabsSupportEnabled
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled
- AFXMDICHILDWNDEX/CMDIChildWndEx::m_dwDefaultTaskbarTabPropertyFlags
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnGetIconicLivePreviewBitmap
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnGetIconicThumbnail
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnMoveMiniFrame
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnPressTaskbarThmbnailCloseButton
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnSetPreviewMode
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnTaskbarTabThumbnailActivate
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnTaskbarTabThumbnailStretch
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnUpdateFrameTitle
- AFXMDICHILDWNDEX/CMDIChildWndEx::PaneFromPoint
- AFXMDICHILDWNDEX/CMDIChildWndEx::RecalcLayout
- AFXMDICHILDWNDEX/CMDIChildWndEx::RegisterTaskbarTab
- AFXMDICHILDWNDEX/CMDIChildWndEx::RemovePaneFromDockManager
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetRelatedTabGroup
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarTabActive
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarTabOrder
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarTabProperties
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarThumbnailClipRect
- AFXMDICHILDWNDEX/CMDIChildWndEx::ShowPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::UnregisterTaskbarTab
- AFXMDICHILDWNDEX/CMDIChildWndEx::UpdateTaskbarTabIcon
dev_langs: C++
helpviewer_keywords:
- CMDIChildWndEx [MFC], ActivateTopLevelFrame
- CMDIChildWndEx [MFC], AddPane
- CMDIChildWndEx [MFC], AddTabbedPane
- CMDIChildWndEx [MFC], AdjustDockingLayout
- CMDIChildWndEx [MFC], CanShowOnMDITabs
- CMDIChildWndEx [MFC], CanShowOnTaskBarTabs
- CMDIChildWndEx [MFC], CanShowOnWindowsList
- CMDIChildWndEx [MFC], DockPane
- CMDIChildWndEx [MFC], DockPaneLeftOf
- CMDIChildWndEx [MFC], EnableAutoHidePanes
- CMDIChildWndEx [MFC], EnableDocking
- CMDIChildWndEx [MFC], EnableTaskbarThumbnailClipRect
- CMDIChildWndEx [MFC], GetDockingManager
- CMDIChildWndEx [MFC], GetDocumentName
- CMDIChildWndEx [MFC], GetFrameIcon
- CMDIChildWndEx [MFC], GetFrameText
- CMDIChildWndEx [MFC], GetPane
- CMDIChildWndEx [MFC], GetRelatedTabGroup
- CMDIChildWndEx [MFC], GetTabbedPane
- CMDIChildWndEx [MFC], GetTabProxyWnd
- CMDIChildWndEx [MFC], GetTaskbarPreviewWnd
- CMDIChildWndEx [MFC], GetTaskbarThumbnailClipRect
- CMDIChildWndEx [MFC], GetToolbarButtonToolTipText
- CMDIChildWndEx [MFC], InsertPane
- CMDIChildWndEx [MFC], InvalidateIconicBitmaps
- CMDIChildWndEx [MFC], IsPointNearDockSite
- CMDIChildWndEx [MFC], IsReadOnly
- CMDIChildWndEx [MFC], IsRegisteredWithTaskbarTabs
- CMDIChildWndEx [MFC], IsTabbedPane
- CMDIChildWndEx [MFC], IsTaskbarTabsSupportEnabled
- CMDIChildWndEx [MFC], IsTaskbarThumbnailClipRectEnabled
- CMDIChildWndEx [MFC], m_dwDefaultTaskbarTabPropertyFlags
- CMDIChildWndEx [MFC], OnGetIconicLivePreviewBitmap
- CMDIChildWndEx [MFC], OnGetIconicThumbnail
- CMDIChildWndEx [MFC], OnMoveMiniFrame
- CMDIChildWndEx [MFC], OnPressTaskbarThmbnailCloseButton
- CMDIChildWndEx [MFC], OnSetPreviewMode
- CMDIChildWndEx [MFC], OnTaskbarTabThumbnailActivate
- CMDIChildWndEx [MFC], OnTaskbarTabThumbnailMouseActivate
- CMDIChildWndEx [MFC], OnTaskbarTabThumbnailStretch
- CMDIChildWndEx [MFC], OnUpdateFrameTitle
- CMDIChildWndEx [MFC], PaneFromPoint
- CMDIChildWndEx [MFC], RecalcLayout
- CMDIChildWndEx [MFC], RegisterTaskbarTab
- CMDIChildWndEx [MFC], RemovePaneFromDockManager
- CMDIChildWndEx [MFC], SetRelatedTabGroup
- CMDIChildWndEx [MFC], SetTaskbarTabActive
- CMDIChildWndEx [MFC], SetTaskbarTabOrder
- CMDIChildWndEx [MFC], SetTaskbarTabProperties
- CMDIChildWndEx [MFC], SetTaskbarThumbnailClipRect
- CMDIChildWndEx [MFC], ShowPane
- CMDIChildWndEx [MFC], UnregisterTaskbarTab
- CMDIChildWndEx [MFC], UpdateTaskbarTabIcon
ms.assetid: d39fec06-0bd6-4271-917d-35aae3b24d8e
caps.latest.revision: "35"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c8259103f719fadb0543ae91ffc3334d38affdea
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="cmdichildwndex-class"></a>Classe CMDIChildWndEx
O `CMDIChildWndEx` classe fornece a funcionalidade de um Windows várias janelas do documento interface MDI filho. Ela estende a funcionalidade de [classe CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md). A estrutura requer esta classe quando um aplicativo MDI usa algumas classes MFC.  
 
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  

  
## <a name="syntax"></a>Sintaxe  
  
```  
class CMDIChildWndEx : public CMDIChildWnd  
```  
  
## <a name="members"></a>Membros  
  
### <a name="public-methods"></a>Métodos Públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CMDIChildWndEx::ActivateTopLevelFrame](#activatetoplevelframe)|Chamado internamente pelo framework para ativar o quadro de nível superior quando o aplicativo deve ser ativado de uma guia na barra de tarefas.|  
|`CMDIChildWndEx::AddDockSite`|Esse método não é usado ou implementado.|  
|[CMDIChildWndEx::AddPane](#addpane)|Adiciona um painel.|  
|[CMDIChildWndEx::AddTabbedPane](#addtabbedpane)|Adiciona um painel com guias.|  
|[CMDIChildWndEx::AdjustDockingLayout](#adjustdockinglayout)|Ajusta o layout de encaixe.|  
|[CMDIChildWndEx::CanShowOnMDITabs](#canshowonmditabs)||  
|[CMDIChildWndEx::CanShowOnTaskBarTabs](#canshowontaskbartabs)|Informa a estrutura se esse filho MDI pode ser exibido nas guias de barra de tarefas do Windows 7.|  
|[CMDIChildWndEx::CanShowOnWindowsList](#canshowonwindowslist)|Retorna `TRUE` se o nome da janela filho MDI pode ser exibido no [CMFCWindowsManagerDialog classe](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) caixa de diálogo. Caso contrário, retornará `FALSE`.|  
|`CMDIChildWndEx::CreateObject`|Chamado pelo framework para criar uma instância dinâmica desse tipo de classe.|  
|[CMDIChildWndEx::DockPane](#dockpane)|Encaixa um painel.|  
|[CMDIChildWndEx::DockPaneLeftOf](#dockpaneleftof)|Encaixa um painel à esquerda do outro painel.|  
|[CMDIChildWndEx::EnableAutoHidePanes](#enableautohidepanes)|Permite oculta automaticamente modo para painéis quando eles são encaixados nas laterais da janela especificadas.|  
|[CMDIChildWndEx::EnableDocking](#enabledocking)|Habilita de encaixe da janela filho para o quadro principal.|  
|[CMDIChildWndEx::EnableTaskbarThumbnailClipRect](#enabletaskbarthumbnailcliprect)|Habilita ou desabilita a seleção automática de uma parte da área de cliente da janela para exibir como miniatura da janela na barra de tarefas.|  
|[CMDIChildWndEx::GetDockingManager](#getdockingmanager)||  
|[CMDIChildWndEx::GetDocumentName](#getdocumentname)|Retorna o nome do documento que é exibido na janela filho MDI.|  
|[CMDIChildWndEx::GetFrameIcon](#getframeicon)|Chamado pelo framework para recuperar o ícone de janela filho MDI.|  
|[CMDIChildWndEx::GetFrameText](#getframetext)|Chamado pelo framework para recuperar o texto para a janela filho MDI.|  
|[CMDIChildWndEx::GetPane](#getpane)|Localiza um painel pela ID do controle especificado.|  
|[CMDIChildWndEx::GetRelatedTabGroup](#getrelatedtabgroup)||  
|[CMDIChildWndEx::GetTabbedPane](#gettabbedpane)|Retorna um ponteiro para um painel ancorado incorporado que foi convertido em um documento com guias.|  
|[CMDIChildWndEx::GetTabProxyWnd](#gettabproxywnd)|Retorna a janela de proxy, na verdade, registrada com guias de barra de tarefas do Windows 7 de guia.|  
|[CMDIChildWndEx::GetTaskbarPreviewWnd](#gettaskbarpreviewwnd)|Chamado pelo framework quando ele precisa obter uma janela filho (normalmente uma janela do divisor ou exibição) a ser exibida na miniatura de guia de barra de tarefas do Windows 7.|  
|[CMDIChildWndEx::GetTaskbarThumbnailClipRect](#gettaskbarthumbnailcliprect)|Chamado pelo framework quando for necessário selecionar uma parte da área de cliente da janela para exibir como miniatura da janela na barra de tarefas.|  
|`CMDIChildWndEx::GetThisClass`|Chamado pelo framework para obter um ponteiro para o [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) objeto associado esse tipo de classe.|  
|[CMDIChildWndEx::GetToolbarButtonToolTipText](#gettoolbarbuttontooltiptext)|Chamado pelo framework para recuperar uma dica de ferramenta para um botão de barra de ferramentas.|  
|[CMDIChildWndEx::InsertPane](#insertpane)|Registra o painel especificado com o Gerenciador de encaixe.|  
|[CMDIChildWndEx::InvalidateIconicBitmaps](#invalidateiconicbitmaps)|Invalida a representação de bitmap ícones de filho MDI.|  
|[CMDIChildWndEx::IsPointNearDockSite](#ispointneardocksite)|Determina se um ponto especificado é o local de encaixe próximo.|  
|[CMDIChildWndEx::IsReadOnly](#isreadonly)|Retorna `TRUE` se o documento que é exibido na janela filho é somente leitura. Caso contrário, retornará `FALSE`.|  
|[CMDIChildWndEx::IsRegisteredWithTaskbarTabs](#isregisteredwithtaskbartabs)|Retornará TRUE se filho MDI foi registrado com êxito com guias de barra de tarefas do Windows 7.|  
|[CMDIChildWndEx::IsTabbedPane](#istabbedpane)|Retorna `TRUE` se a janela filho MDI contém um painel ancorado. Caso contrário, retornará `FALSE`.|  
|[CMDIChildWndEx::IsTaskbarTabsSupportEnabled](#istaskbartabssupportenabled)|Indica se o filho MDI pode aparecer nas guias de barra de tarefas do Windows 7.|  
|[CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled](#istaskbarthumbnailcliprectenabled)|Indica se a seleção automática de uma parte da área de cliente da janela para exibir como miniatura da janela na barra de tarefas está habilitada ou desabilitada.|  
|[CMDIChildWndEx::m_dwDefaultTaskbarTabPropertyFlags](#m_dwdefaulttaskbartabpropertyflags)|Uma combinação de sinalizadores, que é passada pelo framework para o método SetTaskbarTabProperties, quando uma guia (filho MDI) está sendo registrada com guias de barra de tarefas do Windows 7. A combinação padrão é STPF_USEAPPTHUMBNAILWHENACTIVE &#124; STPF_USEAPPPEEKWHENACTIVE.|  
|[CMDIChildWndEx::OnGetIconicLivePreviewBitmap](#ongeticoniclivepreviewbitmap)|Chamado pelo framework quando ele precisa obter um bitmap para visualização ao vivo de filho MDI.|  
|[CMDIChildWndEx::OnGetIconicThumbnail](#ongeticonicthumbnail)|Chamado pelo framework quando ele precisa obter um bitmap para miniatura ícone de filho MDI.|  
|[CMDIChildWndEx::OnMoveMiniFrame](#onmoveminiframe)|Chamado pelo framework para mover uma janela do quadro simplificado.|  
|[CMDIChildWndEx::OnPressTaskbarThmbnailCloseButton](#onpresstaskbarthmbnailclosebutton)|Chamado pelo framework quando o usuário pressiona o botão Fechar na miniatura de guia de barra de tarefas.|  
|[CMDIChildWndEx::OnSetPreviewMode](#onsetpreviewmode)|Chamado pelo framework para entrar ou sair do modo de visualização de impressão.|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailActivate](#ontaskbartabthumbnailactivate)|Chamado pelo framework quando a miniatura de guia de tarefas deve processar a mensagem WM_ACTIVATE.|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate](#ontaskbartabthumbnailmouseactivate)|Chamado pelo framework quando a miniatura de guia de tarefas deve processar a mensagem WM_MOUSEACTIVATE.|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailStretch](#ontaskbartabthumbnailstretch)|Chamado pelo framework quando for necessário Alongar um bitmap para Windows 7 na barra de tarefas guia Visualização de miniatura de filho MDI.|  
|[CMDIChildWndEx::OnUpdateFrameTitle](#onupdateframetitle)|Chamado pelo framework para atualizar o título do quadro. (Substitui `CMDIChildWnd::OnUpdateFrameTitle`.)|  
|[CMDIChildWndEx::PaneFromPoint](#panefrompoint)|Retorna o painel que contém o ponto especificado.|  
|`CMDIChildWndEx::PreTranslateMessage`|Usado pela classe [CWinApp](../../mfc/reference/cwinapp-class.md) para converter as mensagens de janela antes de serem distribuídos para o [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) e [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) funções do Windows. (Substitui [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMDIChildWndEx::RecalcLayout](#recalclayout)|Recalcula o layout da janela.|  
|[CMDIChildWndEx::RegisterTaskbarTab](#registertaskbartab)|Registra o filho MDI com guias de barra de tarefas do Windows 7.|  
|[CMDIChildWndEx::RemovePaneFromDockManager](#removepanefromdockmanager)|Remove um painel do Gerenciador de encaixe.|  
|[CMDIChildWndEx::SetRelatedTabGroup](#setrelatedtabgroup)||  
|[CMDIChildWndEx::SetTaskbarTabActive](#settaskbartabactive)|Ativa o guia de barra de tarefas do Windows 7 correspondente.|  
|[CMDIChildWndEx::SetTaskbarTabOrder](#settaskbartaborder)|Insere o filho MDI antes da janela especificada nas guias de barra de tarefas do Windows 7.|  
|[CMDIChildWndEx::SetTaskbarTabProperties](#settaskbartabproperties)|Define propriedades para uma guia de barra de tarefas do Windows 7.|  
|[CMDIChildWndEx::SetTaskbarThumbnailClipRect](#settaskbarthumbnailcliprect)|Chamado internamente pelo framework para definir o retângulo de recorte para selecionar uma parte da área de cliente da janela para exibir como miniatura da janela na barra de tarefas.|  
|[CMDIChildWndEx::ShowPane](#showpane)||  
|[CMDIChildWndEx::UnregisterTaskbarTab](#unregistertaskbartab)|Remove o filho MDI de guias de barra de tarefas do Windows 7.|  
|[CMDIChildWndEx::UpdateTaskbarTabIcon](#updatetaskbartabicon)|Atualiza o ícone de guia de barra de tarefas do Windows 7.|  
  
## <a name="remarks"></a>Comentários  
 Para tirar proveito dos recursos avançados de encaixe em aplicativos MDI, derive a classe de janela filho MDI de seu aplicativo `CMDIChildWndEx` em vez de [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md).  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir deriva de uma classe de `CMDIChildWndEx`. Este trecho de código é proveniente do [VisualStudioDemo exemplo: aplicativo MFC do Visual Studio](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#3](../../mfc/codesnippet/cpp/cmdichildwndex-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Hierarquia de herança  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)  
  
 [CMDIChildWndEx](../../mfc/reference/cmdichildwndex-class.md)  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** afxMDIChildWndEx.h  
  
##  <a name="addpane"></a>CMDIChildWndEx::AddPane  
 Adiciona um painel.  
  
```  
BOOL AddPane(
    CBasePane* pControlBar,  
    BOOL bTail = TRUE);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pControlBar`  
 Um ponteiro para o painel.  
  
 [in] `bTail`  
 `TRUE`Para adicionar o painel ao final da lista de painéis para o Gerenciador do encaixe. Caso contrário, `FALSE`.  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se o painel foi registrado com êxito com o Gerenciador do encaixe. Caso contrário, `FALSE`.  
  
##  <a name="addtabbedpane"></a>CMDIChildWndEx::AddTabbedPane  
 Adiciona um painel com guias.  
  
```  
void AddTabbedPane(CDockablePane* pControlBar);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pControlBar`  
 Um ponteiro para o painel.  
  
##  <a name="adjustdockinglayout"></a>CMDIChildWndEx::AdjustDockingLayout  
 Ajusta o layout de encaixe.  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `hdwp`  
 Identificador para uma estrutura de posição de janela adiada.  
  
##  <a name="canshowonmditabs"></a>CMDIChildWndEx::CanShowOnMDITabs  

  
```  
virtual BOOL CanShowOnMDITabs();
```  
  
### <a name="return-value"></a>Valor de retorno  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="canshowonwindowslist"></a>CMDIChildWndEx::CanShowOnWindowsList  
 Especifica se o nome da janela filho MDI pode ser exibido no [CMFCWindowsManagerDialog classe](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) caixa de diálogo.  
  
```  
virtual BOOL CanShowOnWindowsList();
```  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se a janela pode ser exibida no **Windows** caixa de diálogo; caso contrário, `FALSE`.  
  
### <a name="remarks"></a>Comentários  
 Substitua este método em uma classe derivada e retornar `FALSE` se a janela não deve ser exibida no **Windows** caixa de diálogo. Essa função é chamada de `CMFCWindowsManagerDialog`.  
  
##  <a name="dockpane"></a>CMDIChildWndEx::DockPane  
 Encaixa um painel.  
  
```  
void DockPane(
    CBasePane* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pBar`  
 Um ponteiro para o painel.  
  
 [in] `nDockBarID`  
 A ID do painel.  
  
 [in] `lpRect`  
 Um ponteiro para um retângulo.  
  
### <a name="remarks"></a>Comentários  
 O `lpRect` parâmetro não for usado.  
  
##  <a name="dockpaneleftof"></a>CMDIChildWndEx::DockPaneLeftOf  
 Encaixa um painel à esquerda do outro painel.  
  
```  
BOOL DockPaneLeftOf(
    CPane* pBar,  
    CPane* pLeftOf);
```  
  
### <a name="parameters"></a>Parâmetros  
 `pBar`  
 Um ponteiro para o painel que deve ser encaixado.  
  
 `pLeftOf`  
 Um ponteiro para o painel que serve como o ponto de referência.  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`em caso de sucesso, `FALSE` em caso de falha.  
  
### <a name="remarks"></a>Comentários  
 Esse método usa o painel especificado por `pBar` e encaixa-lo no lado esquerdo do painel especificado pelo `pLeftOf`.  
  
 Chame este método quando desejar encaixar vários painéis em ordem predefinida.  
  
##  <a name="enableautohidepanes"></a>CMDIChildWndEx::EnableAutoHidePanes  
 Permite oculta automaticamente modo para painéis quando eles são encaixados nas laterais da janela especificadas.  
  
```  
BOOL EnableAutoHidePanes(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `dwDockStyle`  
 Especifica os lados da janela do quadro principal que está habilitado. Use um ou mais dos sinalizadores a seguir.  
  
- `CBRS_ALIGN_LEFT`  
  
- `CBRS_ALIGN_RIGHT`  
  
- `CBRS_ALIGN_TOP`  
  
- `CBRS_ALIGN_BOTTOM`  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se o método for bem-sucedido; Caso contrário, `FALSE`.  
  
##  <a name="enabledocking"></a>CMDIChildWndEx::EnableDocking  
 Habilita de encaixe da janela filho para o quadro principal.  
  
```  
BOOL EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `dwDockStyle`  
 Especifica o alinhamento de encaixe para habilitar.  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se o método for bem-sucedido; Caso contrário, `FALSE`.  
  
### <a name="remarks"></a>Comentários  
 Chame este método para habilitar o alinhamento de encaixe para o quadro principal. Você pode passar uma combinação de sinalizadores CBRS_ALIGN_ (para obter mais informações, consulte [CControlBar::EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking)).  
  
##  <a name="getdockingmanager"></a>CMDIChildWndEx::GetDockingManager  

  
```  
CDockingManager* GetDockingManager();
```  
  
### <a name="return-value"></a>Valor de retorno  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="getdocumentname"></a>CMDIChildWndEx::GetDocumentName  
 Retorna o nome do documento que é exibido na janela filho MDI.  
  
```  
virtual LPCTSTR GetDocumentName(CObject** pObj);
```  
  
### <a name="return-value"></a>Valor de retorno  
 Um ponteiro para uma cadeia de caracteres que contém o nome de um documento.  
  
### <a name="remarks"></a>Comentários  
 Um documento é o que exibe a janela filho MDI. Em geral, a janela exibe dados que são carregados do ou salvos em um arquivo. Portanto, o nome do documento é o nome do arquivo. A implementação padrão de `GetDocumentName` retorna uma cadeia de caracteres obtida `CDocument::GetPathName`.  
  
 Se a janela exibe um documento que não é carregado de um arquivo, substitua este método em uma classe derivada e retornar um identificador exclusivo do documento.  
  
 `GetDocumentName`é chamado pelo framework quando ele salva o estado de todos os documentos abertos. A cadeia de caracteres retornada é gravada no registro.  
  
 Quando a estrutura está restaurando o estado mais tarde, o nome do documento é lido no registro e passado para [CMDIFrameWndEx::CreateDocumentWindow](../../mfc/reference/cmdiframewndex-class.md#createdocumentwindow). Substitua este método em um [CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md)-classe derivada e criar ou abrir um documento que tem esse nome e ler o arquivo com esse nome. Se o documento não é baseado em um arquivo, crie o documento com base no identificador de documento em si. Você deve executar as ações anteriores somente se você pretende salvar e restaurar os documentos.  
  
### <a name="example"></a>Exemplo  
 O exemplo a seguir demonstra o uso do método `GetDocumentName`. Este trecho de código é proveniente do [VisualStudioDemo exemplo: aplicativo MFC do Visual Studio](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#17](../../mfc/codesnippet/cpp/cmdichildwndex-class_2.cpp)]  
  
##  <a name="getframeicon"></a>CMDIChildWndEx::GetFrameIcon  
 Chamado pelo framework para recuperar o ícone da janela filho MDI.  
  
```  
virtual HICON GetFrameIcon() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 Um identificador para o ícone de janela.  
  
### <a name="remarks"></a>Comentários  
 Este método é chamado pelo framework para determinar qual ícone deve ser exibido na guia MDI que contém a janela do quadro filho MDI.  
  
 Por padrão, esse método retorna o ícone de janela. Substituir `GetFrameIcon` em um `CMDIChildWndEx`-derivado da classe para personalizar esse comportamento.  
  
##  <a name="getframetext"></a>CMDIChildWndEx::GetFrameText  
 Chamado pelo framework para recuperar o texto para a janela filho MDI.  
  
```  
virtual CString GetFrameText() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 Uma cadeia de caracteres que contém o texto de janela do quadro.  
  
### <a name="remarks"></a>Comentários  
 Este método é chamado pelo framework para determinar o texto a ser exibido na guia MDI que contém a janela do quadro filho MDI.  
  
 Por padrão, esse método retorna o texto da janela. Substituir `GetFrameText` em um `CMDIChildWndEx`-derivado da classe para personalizar esse comportamento.  
  
##  <a name="getpane"></a>CMDIChildWndEx::GetPane  
 Localiza um painel pela ID do controle especificado.  
  
```  
CBasePane* GetPane(UINT nID);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `nID`  
 A ID do painel de controle para localizar.  
  
### <a name="return-value"></a>Valor de retorno  
 Um ponteiro para o painel se encontrado, caso contrário `NULL`.  
  
##  <a name="getrelatedtabgroup"></a>CMDIChildWndEx::GetRelatedTabGroup  

  
```  
CMFCTabCtrl* GetRelatedTabGroup();
```  
  
### <a name="return-value"></a>Valor de retorno  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="gettabbedpane"></a>CMDIChildWndEx::GetTabbedPane  
 Retorna um ponteiro para um painel que faz parte de um grupo de MDI de documentos com guias.  
  
```  
CDockablePane* GetTabbedPane() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 Um ponteiro para um painel que faz parte de um grupo de MDI documentos com guias.  
  
##  <a name="gettoolbarbuttontooltiptext"></a>CMDIChildWndEx::GetToolbarButtonToolTipText  
 Chamado pelo framework para recuperar uma dica de ferramenta para um botão de barra de ferramentas.  
  
```  
virtual BOOL GetToolbarButtonToolTipText(
    CMFCToolBarButton*, 
    CString&);
```  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se a dica de ferramenta foi exibida. A implementação padrão retorna `FALSE`.  
  
### <a name="remarks"></a>Comentários  
 Substitua este método se você deseja exibir dicas de ferramenta personalizada para os botões da barra de ferramentas.  
  
##  <a name="insertpane"></a>CMDIChildWndEx::InsertPane  
 Registra o painel especificado com o Gerenciador de encaixe.  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter = TRUE);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pControlBar`  
 Um ponteiro para o painel para inserir.  
  
 [in] `pTarget`  
 Um ponteiro para o painel adjacente.  
  
 [in] `bAfter`  
 Se `TRUE`, `pControlBar` é inserida depois `pTarget`. Se `FALSE`, `pControlBar` é inserida antes `pTarget`.  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se o método for bem-sucedido, `FALSE` caso contrário.  
  
##  <a name="ispointneardocksite"></a>CMDIChildWndEx::IsPointNearDockSite  
 Determina se um ponto especificado é o local de encaixe próximo.  
  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `point`  
 O ponto especificado.  
  
 [in] `dwBarAlignment`  
 Especifica que o ponto está próximo de borda. Os valores possíveis são `CBRS_ALIGN_LEFT`, `CBRS_ALIGN_RIGHT`, `CBRS_ALIGN_TOP`, e`CBRS_ALIGN_BOTTOM`  
  
 [in] `bOuterEdge`  
 `TRUE`Se o ponto está próximo a borda externa do site do encaixe; `FALSE` caso contrário.  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se o ponto está próximo do site de encaixe; Caso contrário, `FALSE`.  
  
### <a name="remarks"></a>Comentários  
 O ponto é o local de encaixe próximo quando ele está dentro da sensibilidade definida no Gerenciador de encaixe. A sensibilidade de padrão é 15 pixels.  
  
##  <a name="isreadonly"></a>CMDIChildWndEx::IsReadOnly  
 Especifica se o documento que é exibido na janela filho é somente leitura.  
  
```  
virtual BOOL IsReadOnly();
```  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se o documento é somente leitura; Caso contrário, `FALSE`.  
  
### <a name="remarks"></a>Comentários  
 Essa função é usada para evitar salvar documentos como somente leitura.  
  
### <a name="example"></a>Exemplo  
 O exemplo a seguir demonstra substituindo o `IsReadOnly` método. Este trecho de código é proveniente do [VisualStudioDemo exemplo: aplicativo MFC do Visual Studio](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#2](../../mfc/codesnippet/cpp/cmdichildwndex-class_3.cpp)]  
  
##  <a name="istabbedpane"></a>CMDIChildWndEx::IsTabbedPane  
 Especifica se a janela filho MDI contém um painel ancorado.  
  
```  
BOOL IsTabbedPane() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se a janela filho MDI contém um painel que foi convertido em um documento com guias. Caso contrário, `FALSE`.  
  
##  <a name="onmoveminiframe"></a>CMDIChildWndEx::OnMoveMiniFrame  
 Chamado pelo framework para mover uma janela do quadro simplificado.  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pFrame`  
 Um ponteiro para uma janela do quadro simplificado.  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se o método for bem-sucedido, caso contrário, `FALSE`.  
  
##  <a name="onsetpreviewmode"></a>CMDIChildWndEx::OnSetPreviewMode  
 Chamado pelo framework para entrar ou sair do modo de visualização de impressão.  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `bPreview`  
 Se `TRUE`, entrar no modo de visualização de impressão. Se `FALSE`, saia do modo de visualização de impressão.  
  
 [in] `pState`  
 Um ponteiro para a estrutura de estado de visualização de impressão.  
  
##  <a name="onupdateframetitle"></a>CMDIChildWndEx::OnUpdateFrameTitle  
 Chamado pelo framework para atualizar o título do quadro.  
  
```  
virtual void OnUpdateFrameTitle(BOOL bAddToTitle);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `bAddToTitle`  
 Se `TRUE`, adicione o nome do documento para o título.  
  
##  <a name="panefrompoint"></a>CMDIChildWndEx::PaneFromPoint  
 Retorna o painel que contém o ponto especificado.  
  
```  
CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    bool bExactBar,  
    CRuntimeClass* pRTCBarType) const;  
  
CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    DWORD& dwAlignment,  
    CRuntimeClass* pRTCBarType) const;  
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `point`  
 Especifica o ponto em coordenadas da tela, para verificar.  
  
 [in] `nSensitivity`  
 Aumente a área de pesquisa, esse valor. Um painel de acordo com os critérios de pesquisa se determinado ponto estiver na área de trabalho maior.  
  
 [in] `bExactBar`  
 `TRUE`para ignorar o `nSensitivity` parâmetro; caso contrário, `FALSE`.  
  
 [in] `pRTCBarType`  
 Se não for `NULL`, o método pesquisa somente os painéis do tipo especificado.  
  
 [in] `dwAlignment`  
 Se um painel é localizado no ponto especificado, este parâmetro contém o lado do painel que foi mais próximo para o ponto especificado. Para obter mais informações, consulte a seção Comentários.  
  
### <a name="return-value"></a>Valor de retorno  
 Um ponteiro para o `CBasePane`-derivados do objeto que contém o ponto específico, ou `NULL` se nenhum painel foi encontrado.  
  
### <a name="remarks"></a>Comentários  
 Chame este método para determinar se um painel que contém o ponto especificado de acordo com as condições especificadas como classe de tempo de execução e visibilidade.  
  
 Quando a função retorna e foi encontrado um painel, `dwAlignment` contém o alinhamento de ponto especificado. Por exemplo, se o ponto mais próximo à parte superior do painel, `dwAlignment` é definido como `CBRS_ALIGN_TOP`.  
  
##  <a name="recalclayout"></a>CMDIChildWndEx::RecalcLayout  
 Recalcula o layout da janela.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `bNotify`  
 Se `TRUE`, o item no local ativo para a janela recebe a notificação da alteração de layout.  
  
##  <a name="removepanefromdockmanager"></a>CMDIChildWndEx::RemovePaneFromDockManager  
 Remove um painel do Gerenciador de encaixe.  
  
```  
void RemovePaneFromDockManager(
    CBasePane* pControlBar,  
    BOOL bDestroy,  
    BOOL bAdjustLayout,  
    BOOL bAutoHide,  
    CBasePane* pBarReplacement);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pControlBar`  
 Um ponteiro para o painel para remover.  
  
 [in] `bDestroy`  
 Se `TRUE`, o painel removido é destruído.  
  
 [in] `bAdjustLayout`  
 Se `TRUE`, ajustar o layout de encaixe imediatamente.  
  
 [in] `bAutoHide`  
 Se `TRUE`, o layout de encaixe está relacionado à lista de barras de ocultar automaticamente. Se `FALSE`, o layout de encaixe está relacionado à lista de painéis regulares.  
  
 [in] `pBarReplacement`  
 Um ponteiro para um painel que substitui o painel removido.  
  
##  <a name="setrelatedtabgroup"></a>CMDIChildWndEx::SetRelatedTabGroup  

  
```  
void SetRelatedTabGroup(CMFCTabCtrl* p);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `p`  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="showpane"></a>CMDIChildWndEx::ShowPane  

  
```  
void ShowPane(
    CBasePane* pBar,  
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pBar`  
 [in] `bShow`  
 [in] `bDelay`  
 [in] `bActivate`  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="updatetaskbartabicon"></a>CMDIChildWndEx::UpdateTaskbarTabIcon  
 Atualiza o ícone de guia de barra de tarefas do Windows 7.  
  
```  
virtual void UpdateTaskbarTabIcon(HICON hIcon);
```  
  
### <a name="parameters"></a>Parâmetros  
 `hIcon`  
 Um identificador para um ícone a ser exibido na guia de barra de tarefas do Windows 7.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="unregistertaskbartab"></a>CMDIChildWndEx::UnregisterTaskbarTab  
 Remove o filho MDI de guias de barra de tarefas do Windows 7.  
  
```  
void UnregisterTaskbarTab(BOOL bCheckRegisteredMDIChildCount = TRUE);
```  
  
### <a name="parameters"></a>Parâmetros  
 `bCheckRegisteredMDIChildCount`  
 Especifica se essa função precisa verificar o número de filhos MDI registrado com guias MDI. Se esse número for 0, esta função remove o retângulo de recorte de miniatura de barra de tarefas do aplicativo.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="settaskbarthumbnailcliprect"></a>CMDIChildWndEx::SetTaskbarThumbnailClipRect  
 Chamado pelo framework para definir o retângulo de recorte para selecionar uma parte da área de cliente da janela para exibir como miniatura da janela na barra de tarefas.  
  
```  
virtual BOOL SetTaskbarThumbnailClipRect(CRect rect);
```  
  
### <a name="parameters"></a>Parâmetros  
 `rect`  
 Especifica o novo retângulo de recorte. Se o retângulo está vazio ou nulo, o recorte será removido.  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE` caso bem-sucedido; caso contrário, `FALSE`.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="settaskbartabproperties"></a>CMDIChildWndEx::SetTaskbarTabProperties  
 Define propriedades para uma guia de barra de tarefas do Windows 7.  
  
```  
void SetTaskbarTabProperties(DWORD dwFlags);
```  
  
### <a name="parameters"></a>Parâmetros  
 `dwFlags`  
 Uma combinação de valores STPFLAG. Para obter mais informações, consulte [ITaskbarList4::SetTabProperties](http://msdn.microsoft.com/library/dd562049\(vs.85\).aspx).  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="settaskbartaborder"></a>CMDIChildWndEx::SetTaskbarTabOrder  
 Insere o filho MDI antes do período especificado em guias de barra de tarefas do Windows 7.  
  
```  
void SetTaskbarTabOrder(CMDIChildWndEx* pWndBefore = NULL);
```  
  
### <a name="parameters"></a>Parâmetros  
 `pWndBefore`  
 Um ponteiro para a janela filho MDI cuja miniatura é inserida à esquerda. Esta janela já deve estar registrada por meio de `RegisterTaskbarTab`. Se esse valor for `NULL`, a miniatura do novo é adicionada ao final da lista.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="settaskbartabactive"></a>CMDIChildWndEx::SetTaskbarTabActive  
 Ativa a guia de barra de tarefas do Windows 7 correspondente.  
  
```  
void SetTaskbarTabActive();
```  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="registertaskbartab"></a>CMDIChildWndEx::RegisterTaskbarTab  
 Registra o filho MDI com guias de barra de tarefas do Windows 7.  
  
```  
virtual void RegisterTaskbarTab(CMDIChildWndEx* pWndBefore = NULL);
```  
  
### <a name="parameters"></a>Parâmetros  
 `pWndBefore`  
 Um ponteiro para a janela filho MDI cuja miniatura é inserida à esquerda. Esta janela já deve estar registrada por meio de `RegisterTaskbarTab`. Se esse valor for `NULL`, a miniatura do novo é adicionada ao final da lista.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="ontaskbartabthumbnailstretch"></a>CMDIChildWndEx::OnTaskbarTabThumbnailStretch  
 Chamado pelo framework quando for necessário Alongar um bitmap para Windows 7 na barra de tarefas guia miniaturas do filho MDI.  
  
```  
virtual BOOL OnTaskbarTabThumbnailStretch(
    HBITMAP hBmpDst,  
    const CRect& rectDst,  
    HBITMAP hBmpSrc,  
    const CRect& rectSrc);
```  
  
### <a name="parameters"></a>Parâmetros  
 `hBmpDst`  
 Um identificador para um bitmap de destino.  
  
 `rectDst`  
 Especifica o retângulo de destino.  
  
 `hBmpSrc`  
 Um identificador para um bitmap de origem.  
  
 `rectSrc`  
 Especifica o retângulo de origem.  
  
### <a name="remarks"></a>Comentários  
 Requirementher ou que ele ele ele ele ele que ele que ele **:** afxmdichildwndex.h  
  
##  <a name="ontaskbartabthumbnailmouseactivate"></a>CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate  
 Chamado pelo framework quando a miniatura de guia de tarefas deve processar a mensagem WM_MOUSEACTIVATE.  
  
```  
virtual int OnTaskbarTabThumbnailMouseActivate(
    CWnd* pDesktopWnd,  
    UINT nHitTest,  
    UINT message);
```  
  
### <a name="parameters"></a>Parâmetros  
 `pDesktopWnd`  
 Especifica um ponteiro para a janela pai de nível superior da janela que está sendo ativada. O ponteiro pode ser temporário e não deve ser armazenado.  
  
 `nHitTest`  
 Especifica o código de área de teste de hit. Um teste de clique é um teste que determina o local do cursor.  
  
 `message`  
 Especifica o número de mensagens de mouse.  
  
### <a name="remarks"></a>Comentários  
 A implementação padrão ativa o quadro de filho MDI relacionado.  
  
##  <a name="ontaskbartabthumbnailactivate"></a>CMDIChildWndEx::OnTaskbarTabThumbnailActivate  
 Chamado pelo framework quando a miniatura de guia de tarefas deve processar a mensagem WM_ACTIVATE.  
  
```  
virtual void OnTaskbarTabThumbnailActivate(
    UINT nState,  
    CWnd* pWndOther,  
    BOOL bMinimized);
```  
  
### <a name="parameters"></a>Parâmetros  
 `nState`  
 Especifica se o `CWnd` está sendo ativada ou desativada.  
  
 `pWndOther`  
 Ponteiro para o `CWnd` que está sendo ativada ou desativada. O ponteiro pode ser `NULL`, e pode ser temporário.  
  
 `bMinimized`  
 Especifica o estado minimizado o `CWnd` que está sendo ativada ou desativada. Um valor de `TRUE` indica que a janela está minimizada.  
  
### <a name="remarks"></a>Comentários  
 A implementação padrão ativa o quadro de filho MDI relacionado.  
  
##  <a name="onpresstaskbarthmbnailclosebutton"></a>CMDIChildWndEx::OnPressTaskbarThmbnailCloseButton  
 Chamado pelo framework quando o usuário pressiona o botão Fechar na miniatura de guia de barra de tarefas.  
  
```  
virtual void OnPressTaskbarThmbnailCloseButton();
```  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="ongeticonicthumbnail"></a>CMDIChildWndEx::OnGetIconicThumbnail  
 Chamado pelo framework quando ele precisa obter um bitmap para a miniatura ícone do filho MDI.  
  
```  
virtual HBITMAP OnGetIconicThumbnail(
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>Parâmetros  
 `nWidth`  
 Especifica a largura do bitmap necessária.  
  
 `nHeight`  
 Especifica a altura do bitmap necessária.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="ongeticoniclivepreviewbitmap"></a>CMDIChildWndEx::OnGetIconicLivePreviewBitmap  
 Chamado pelo framework quando ele precisa obter um bitmap para visualização ao vivo do filho MDI.  
  
```  
virtual HBITMAP OnGetIconicLivePreviewBitmap(
    BOOL bIsMDIChildActive,  
    CPoint& ptLocation);
```  
  
### <a name="parameters"></a>Parâmetros  
 `bIsMDIChildActive`  
 Esse parâmetro é `TRUE` se o bitmap for solicitado para o filho MDI, que está atualmente ativa e a janela principal não é minimizado. O padrão de processamento nesse caso tira um instantâneo da janela principal.  
  
 `ptLocation`  
 Especifica o local do bitmap no principal (nível superior) janela coordenadas do cliente. Esse ponto deve ser fornecido pelo destinatário.  
  
### <a name="return-value"></a>Valor de retorno  
 Se processado, retorna um identificador para um bitmap de 32 bpp válido, caso contrário, `NULL`.  
  
### <a name="remarks"></a>Comentários  
 Substitua este método em uma classe derivada e retornar um bitmap de 32 bpp válido para visualização ao vivo de filho MDI. Esse método é chamado apenas quando o filho MDI é exibido nas guias de barra de tarefas do Windows 7. Se você retornar `NULL`, MFC chama o manipulador padrão e obtenha bitmaps usando `PrintClient` ou `PrintWindow`.  
  
##  <a name="m_dwdefaulttaskbartabpropertyflags"></a>CMDIChildWndEx::m_dwDefaultTaskbarTabPropertyFlags  
 Uma combinação de sinalizadores, que é passada pelo framework para o `SetTaskbarTabProperties` método, quando uma guia (filho MDI) está sendo registrada com guias de barra de tarefas do Windows 7.  
  
```  
AFX_IMPORT_DATA static DWORD m_dwDefaultTaskbarTabPropertyFlags;  
```  
  
### <a name="remarks"></a>Comentários  
 A combinação padrão é STPF_USEAPPTHUMBNAILWHENACTIVE &#124; STPF_USEAPPPEEKWHENACTIVE.  
  
##  <a name="istaskbarthumbnailcliprectenabled"></a>CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled  
 Indica se a seleção automática de uma parte da área de cliente da janela para exibir como miniatura da janela na barra de tarefas está habilitada ou desabilitada.  
  
```  
BOOL IsTaskbarThumbnailClipRectEnabled() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna `TRUE` se a seleção automática de uma parte da área de cliente da janela para exibir estiver habilitada; caso contrário `FALSE`.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="istaskbartabssupportenabled"></a>CMDIChildWndEx::IsTaskbarTabsSupportEnabled  
 Indica se o filho MDI pode aparecer nas guias de barra de tarefas do Windows 7.  
  
```  
BOOL IsTaskbarTabsSupportEnabled();
```  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se o filho MDI pode aparecer nas guias de barra de tarefas do Windows 7; `FALSE` se o filho MDI não pode aparecer em guias de barra de tarefas do Windows 7.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="isregisteredwithtaskbartabs"></a>CMDIChildWndEx::IsRegisteredWithTaskbarTabs  
 Retorna `TRUE` se o filho MDI foi registrado com êxito com guias de barra de tarefas do Windows 7.  
  
```  
BOOL IsRegisteredWithTaskbarTabs();
```  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se o filho MDI está registrado com guias de barra de tarefas do Windows 7; Caso contrário, `FALSE`.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="invalidateiconicbitmaps"></a>CMDIChildWndEx::InvalidateIconicBitmaps  
 Invalida uma representação de bitmap ícones de um filho MDI.  
  
```  
BOOL InvalidateIconicBitmaps();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna `FALSE` se o suporte de barra de tarefas do Windows 7 está desabilitado ou o filho MDI não está registrado com guias de barra de tarefas do Windows 7; caso contrário, retornará `TRUE`.  
  
### <a name="remarks"></a>Comentários  
 Deve ser chamado quando o conteúdo ao vivo ou o tamanho de um filho MDI é alterado.  
  
##  <a name="gettaskbarthumbnailcliprect"></a>CMDIChildWndEx::GetTaskbarThumbnailClipRect  
 Chamado pelo framework quando for necessário selecionar uma parte da área de cliente da janela para exibir como miniatura da janela na barra de tarefas.  
  
```  
virtual CRect GetTaskbarThumbnailClipRect() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 Um retângulo nas coordenadas do windows. Esse retângulo é mapeado para a área cliente do quadro de nível superior. O retângulo deve estar vazio para limpar o retângulo de recorte.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="gettaskbarpreviewwnd"></a>CMDIChildWndEx::GetTaskbarPreviewWnd  
 Chamado pelo framework quando ele precisa obter uma janela filho (normalmente uma janela do divisor ou exibição) a ser exibido em uma miniatura de guia de barra de tarefas do Windows 7.  
  
```  
virtual CWnd* GetTaskbarPreviewWnd();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Deve retornar um ponteiro válido para uma `CWnd` objeto, cuja visualização deve ser exibida em uma guia de barra de tarefas do Windows 7 relacionados a esse filho MDI. A implementação padrão retorna uma janela filho dessa criança MDI com a ID de controle AFX_IDW_PANE_FIRST (que é geralmente um `CView`-classe derivada).  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="gettabproxywnd"></a>CMDIChildWndEx::GetTabProxyWnd  
 Retorna a janela de proxy de guia registrada com guias de barra de tarefas do Windows 7.  
  
```  
CMDITabProxyWnd* GetTabProxyWnd();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Um ponteiro para um `CMDITabProxyWnd` objeto, que é registrado com guias de barra de tarefas do Windows 7.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="enabletaskbarthumbnailcliprect"></a>CMDIChildWndEx::EnableTaskbarThumbnailClipRect  
 Habilita ou desabilita a seleção automática de uma parte da área de cliente da janela para exibir como miniatura da janela na barra de tarefas.  
  
```  
void EnableTaskbarThumbnailClipRect(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parâmetros  
 `bEnable`  
 Especifica se deseja habilitar ( `TRUE`), ou desabilitar ( `FALSE`) a seleção automática de uma parte da área de cliente da janela para exibir.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="canshowontaskbartabs"></a>CMDIChildWndEx::CanShowOnTaskBarTabs  
 Informa a estrutura se esse filho MDI pode ser exibido nas guias de barra de tarefas do Windows 7.  
  
```  
virtual BOOL CanShowOnTaskBarTabs();
```  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se o conteúdo do filho MDI pode ser exibido nas miniaturas de barra de tarefas do Windows 7.  
  
### <a name="remarks"></a>Comentários  
 Substitua este método em uma classe derivada e retornar `FALSE` para desabilitar a aparência desse filho MDI nas guias de barra de tarefas do Windows 7.  
  
##  <a name="activatetoplevelframe"></a>CMDIChildWndEx::ActivateTopLevelFrame  
 Chamado pelo framework para ativar o quadro de nível superior quando o aplicativo é ativado de uma guia na barra de tarefas.  
  
```  
virtual void ActivateTopLevelFrame();
```  
  
### <a name="remarks"></a>Comentários  
  
## <a name="see-also"></a>Consulte também  
 [Gráfico de hierarquia](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [Classe CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)   
 [Classe CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)   
 [Classe CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md)