---
title: "Classe CWinAppEx é | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFrameWndEx
- AFXFRAMEWNDEX/CFrameWndEx
- AFXFRAMEWNDEX/CFrameWndEx::ActiveItemRecalcLayout
- AFXFRAMEWNDEX/CFrameWndEx::AddPane
- AFXFRAMEWNDEX/CFrameWndEx::AdjustDockingLayout
- AFXFRAMEWNDEX/CFrameWndEx::DelayUpdateFrameMenu
- AFXFRAMEWNDEX/CFrameWndEx::DockPane
- AFXFRAMEWNDEX/CFrameWndEx::DockPaneLeftOf
- AFXFRAMEWNDEX/CFrameWndEx::EnableAutoHidePanes
- AFXFRAMEWNDEX/CFrameWndEx::EnableDocking
- AFXFRAMEWNDEX/CFrameWndEx::EnableFullScreenMainMenu
- AFXFRAMEWNDEX/CFrameWndEx::EnableFullScreenMode
- AFXFRAMEWNDEX/CFrameWndEx::EnableLoadDockState
- AFXFRAMEWNDEX/CFrameWndEx::EnablePaneMenu
- AFXFRAMEWNDEX/CFrameWndEx::GetActivePopup
- AFXFRAMEWNDEX/CFrameWndEx::GetDefaultResId
- AFXFRAMEWNDEX/CFrameWndEx::GetDockingManager
- AFXFRAMEWNDEX/CFrameWndEx::GetMenuBar
- AFXFRAMEWNDEX/CFrameWndEx::GetPane
- AFXFRAMEWNDEX/CFrameWndEx::GetRibbonBar
- AFXFRAMEWNDEX/CFrameWndEx::GetTearOffBars
- AFXFRAMEWNDEX/CFrameWndEx::GetToolbarButtonToolTipText
- AFXFRAMEWNDEX/CFrameWndEx::InsertPane
- AFXFRAMEWNDEX/CFrameWndEx::IsFullScreen
- AFXFRAMEWNDEX/CFrameWndEx::IsMenuBarAvailable
- AFXFRAMEWNDEX/CFrameWndEx::IsPointNearDockSite
- AFXFRAMEWNDEX/CFrameWndEx::IsPrintPreview
- AFXFRAMEWNDEX/CFrameWndEx::LoadFrame
- AFXFRAMEWNDEX/CFrameWndEx::NegotiateBorderSpace
- AFXFRAMEWNDEX/CFrameWndEx::OnActivate
- AFXFRAMEWNDEX/CFrameWndEx::OnActivateApp
- AFXFRAMEWNDEX/CFrameWndEx::OnChangeVisualManager
- AFXFRAMEWNDEX/CFrameWndEx::OnClose
- AFXFRAMEWNDEX/CFrameWndEx::OnCloseDockingPane
- AFXFRAMEWNDEX/CFrameWndEx::OnCloseMiniFrame
- AFXFRAMEWNDEX/CFrameWndEx::OnClosePopupMenu
- AFXFRAMEWNDEX/CFrameWndEx::OnCmdMsg
- AFXFRAMEWNDEX/CFrameWndEx::OnContextHelp
- AFXFRAMEWNDEX/CFrameWndEx::OnCreate
- AFXFRAMEWNDEX/CFrameWndEx::OnDestroy
- AFXFRAMEWNDEX/CFrameWndEx::OnDrawMenuImage
- AFXFRAMEWNDEX/CFrameWndEx::OnDrawMenuLogo
- AFXFRAMEWNDEX/CFrameWndEx::OnDWMCompositionChanged
- AFXFRAMEWNDEX/CFrameWndEx::OnExitSizeMove
- AFXFRAMEWNDEX/CFrameWndEx::OnGetMinMaxInfo
- AFXFRAMEWNDEX/CFrameWndEx::OnIdleUpdateCmdUI
- AFXFRAMEWNDEX/CFrameWndEx::OnLButtonDown
- AFXFRAMEWNDEX/CFrameWndEx::OnLButtonUp
- AFXFRAMEWNDEX/CFrameWndEx::OnMenuButtonToolHitTest
- AFXFRAMEWNDEX/CFrameWndEx::OnMenuChar
- AFXFRAMEWNDEX/CFrameWndEx::OnMouseMove
- AFXFRAMEWNDEX/CFrameWndEx::OnMoveMiniFrame
- AFXFRAMEWNDEX/CFrameWndEx::OnNcActivate
- AFXFRAMEWNDEX/CFrameWndEx::OnNcCalcSize
- AFXFRAMEWNDEX/CFrameWndEx::OnNcHitTest
- AFXFRAMEWNDEX/CFrameWndEx::OnNcMouseMove
- AFXFRAMEWNDEX/CFrameWndEx::OnNcPaint
- AFXFRAMEWNDEX/CFrameWndEx::OnPaneCheck
- AFXFRAMEWNDEX/CFrameWndEx::OnPostPreviewFrame
- AFXFRAMEWNDEX/CFrameWndEx::OnPowerBroadcast
- AFXFRAMEWNDEX/CFrameWndEx::OnSetMenu
- AFXFRAMEWNDEX/CFrameWndEx::OnSetPreviewMode
- AFXFRAMEWNDEX/CFrameWndEx::OnSetText
- AFXFRAMEWNDEX/CFrameWndEx::OnShowCustomizePane
- AFXFRAMEWNDEX/CFrameWndEx::OnShowPanes
- AFXFRAMEWNDEX/CFrameWndEx::OnShowPopupMenu
- AFXFRAMEWNDEX/CFrameWndEx::OnSize
- AFXFRAMEWNDEX/CFrameWndEx::OnSizing
- AFXFRAMEWNDEX/CFrameWndEx::OnSysColorChange
- AFXFRAMEWNDEX/CFrameWndEx::OnTearOffMenu
- AFXFRAMEWNDEX/CFrameWndEx::OnToolbarContextMenu
- AFXFRAMEWNDEX/CFrameWndEx::OnToolbarCreateNew
- AFXFRAMEWNDEX/CFrameWndEx::OnToolbarDelete
- AFXFRAMEWNDEX/CFrameWndEx::OnUpdateFrameMenu
- AFXFRAMEWNDEX/CFrameWndEx::OnUpdateFrameTitle
- AFXFRAMEWNDEX/CFrameWndEx::OnUpdatePaneMenu
- AFXFRAMEWNDEX/CFrameWndEx::OnWindowPosChanged
- AFXFRAMEWNDEX/CFrameWndEx::PaneFromPoint
- AFXFRAMEWNDEX/CFrameWndEx::PreTranslateMessage
- AFXFRAMEWNDEX/CFrameWndEx::RecalcLayout
- AFXFRAMEWNDEX/CFrameWndEx::RemovePaneFromDockManager
- AFXFRAMEWNDEX/CFrameWndEx::SetDockState
- AFXFRAMEWNDEX/CFrameWndEx::SetPrintPreviewFrame
- AFXFRAMEWNDEX/CFrameWndEx::SetupToolbarMenu
- AFXFRAMEWNDEX/CFrameWndEx::ShowFullScreen
- AFXFRAMEWNDEX/CFrameWndEx::ShowPane
- AFXFRAMEWNDEX/CFrameWndEx::UpdateCaption
- AFXFRAMEWNDEX/CFrameWndEx::WinHelp
dev_langs: C++
helpviewer_keywords:
- CFrameWndEx [MFC], ActiveItemRecalcLayout
- CFrameWndEx [MFC], AddPane
- CFrameWndEx [MFC], AdjustDockingLayout
- CFrameWndEx [MFC], DelayUpdateFrameMenu
- CFrameWndEx [MFC], DockPane
- CFrameWndEx [MFC], DockPaneLeftOf
- CFrameWndEx [MFC], EnableAutoHidePanes
- CFrameWndEx [MFC], EnableDocking
- CFrameWndEx [MFC], EnableFullScreenMainMenu
- CFrameWndEx [MFC], EnableFullScreenMode
- CFrameWndEx [MFC], EnableLoadDockState
- CFrameWndEx [MFC], EnablePaneMenu
- CFrameWndEx [MFC], GetActivePopup
- CFrameWndEx [MFC], GetDefaultResId
- CFrameWndEx [MFC], GetDockingManager
- CFrameWndEx [MFC], GetMenuBar
- CFrameWndEx [MFC], GetPane
- CFrameWndEx [MFC], GetRibbonBar
- CFrameWndEx [MFC], GetTearOffBars
- CFrameWndEx [MFC], GetToolbarButtonToolTipText
- CFrameWndEx [MFC], InsertPane
- CFrameWndEx [MFC], IsFullScreen
- CFrameWndEx [MFC], IsMenuBarAvailable
- CFrameWndEx [MFC], IsPointNearDockSite
- CFrameWndEx [MFC], IsPrintPreview
- CFrameWndEx [MFC], LoadFrame
- CFrameWndEx [MFC], NegotiateBorderSpace
- CFrameWndEx [MFC], OnActivate
- CFrameWndEx [MFC], OnActivateApp
- CFrameWndEx [MFC], OnChangeVisualManager
- CFrameWndEx [MFC], OnClose
- CFrameWndEx [MFC], OnCloseDockingPane
- CFrameWndEx [MFC], OnCloseMiniFrame
- CFrameWndEx [MFC], OnClosePopupMenu
- CFrameWndEx [MFC], OnCmdMsg
- CFrameWndEx [MFC], OnContextHelp
- CFrameWndEx [MFC], OnCreate
- CFrameWndEx [MFC], OnDestroy
- CFrameWndEx [MFC], OnDrawMenuImage
- CFrameWndEx [MFC], OnDrawMenuLogo
- CFrameWndEx [MFC], OnDWMCompositionChanged
- CFrameWndEx [MFC], OnExitSizeMove
- CFrameWndEx [MFC], OnGetMinMaxInfo
- CFrameWndEx [MFC], OnIdleUpdateCmdUI
- CFrameWndEx [MFC], OnLButtonDown
- CFrameWndEx [MFC], OnLButtonUp
- CFrameWndEx [MFC], OnMenuButtonToolHitTest
- CFrameWndEx [MFC], OnMenuChar
- CFrameWndEx [MFC], OnMouseMove
- CFrameWndEx [MFC], OnMoveMiniFrame
- CFrameWndEx [MFC], OnNcActivate
- CFrameWndEx [MFC], OnNcCalcSize
- CFrameWndEx [MFC], OnNcHitTest
- CFrameWndEx [MFC], OnNcMouseMove
- CFrameWndEx [MFC], OnNcPaint
- CFrameWndEx [MFC], OnPaneCheck
- CFrameWndEx [MFC], OnPostPreviewFrame
- CFrameWndEx [MFC], OnPowerBroadcast
- CFrameWndEx [MFC], OnSetMenu
- CFrameWndEx [MFC], OnSetPreviewMode
- CFrameWndEx [MFC], OnSetText
- CFrameWndEx [MFC], OnShowCustomizePane
- CFrameWndEx [MFC], OnShowPanes
- CFrameWndEx [MFC], OnShowPopupMenu
- CFrameWndEx [MFC], OnSize
- CFrameWndEx [MFC], OnSizing
- CFrameWndEx [MFC], OnSysColorChange
- CFrameWndEx [MFC], OnTearOffMenu
- CFrameWndEx [MFC], OnToolbarContextMenu
- CFrameWndEx [MFC], OnToolbarCreateNew
- CFrameWndEx [MFC], OnToolbarDelete
- CFrameWndEx [MFC], OnUpdateFrameMenu
- CFrameWndEx [MFC], OnUpdateFrameTitle
- CFrameWndEx [MFC], OnUpdatePaneMenu
- CFrameWndEx [MFC], OnWindowPosChanged
- CFrameWndEx [MFC], PaneFromPoint
- CFrameWndEx [MFC], PreTranslateMessage
- CFrameWndEx [MFC], RecalcLayout
- CFrameWndEx [MFC], RemovePaneFromDockManager
- CFrameWndEx [MFC], SetDockState
- CFrameWndEx [MFC], SetPrintPreviewFrame
- CFrameWndEx [MFC], SetupToolbarMenu
- CFrameWndEx [MFC], ShowFullScreen
- CFrameWndEx [MFC], ShowPane
- CFrameWndEx [MFC], UpdateCaption
- CFrameWndEx [MFC], WinHelp
ms.assetid: 5830aca8-4a21-4f31-91f1-dd5477ffcc8d
caps.latest.revision: "39"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: de4de5d693e786cd2cb1f7e4a0e45c9f7df66d99
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="cframewndex-class"></a>Classe CWinAppEx é
Implementa a funcionalidade de uma janela única interface de documento (SDI) sobrepostas ou janela do quadro de janela pop-up e fornece membros para gerenciar a janela. Ele estende o [CFrameWnd](../../mfc/reference/cframewnd-class.md) classe.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
class CFrameWndEx : public CFrameWnd  
```  
  
## <a name="members"></a>Membros  
  
### <a name="public-methods"></a>Métodos Públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CFrameWndEx::ActiveItemRecalcLayout](#activeitemrecalclayout)|Ajusta o layout do item de cliente OLE e área do cliente do quadro.|  
|`CFrameWndEx::AddDockSite`|Esse método não é usado.|  
|[CFrameWndEx::AddPane](#addpane)|Registra uma barra de controle com o Gerenciador de encaixe.|  
|[CFrameWndEx::AdjustDockingLayout](#adjustdockinglayout)|Recalcula o layout de todos os painéis que está encaixada na janela do quadro.|  
|[CFrameWndEx::DelayUpdateFrameMenu](#delayupdateframemenu)|Define o menu do quadro e, em seguida, atualiza-la quando o processamento do comando estiver ocioso.|  
|[CFrameWndEx::DockPane](#dockpane)|Encaixa painel especificado para a janela do quadro.|  
|[CFrameWndEx::DockPaneLeftOf](#dockpaneleftof)|Encaixa um painel à esquerda do outro painel.|  
|[CFrameWndEx::EnableAutoHidePanes](#enableautohidepanes)|Habilita o modo de ocultar automaticamente para os painéis quando são encaixados ao lado da janela do quadro principal especificado.|  
|[CFrameWndEx::EnableDocking](#enabledocking)|Habilita o encaixe dos painéis que pertencem a janela do quadro.|  
|[CFrameWndEx::EnableFullScreenMainMenu](#enablefullscreenmainmenu)|Mostra ou oculta o menu principal em um modo de tela inteira.|  
|[CFrameWndEx::EnableFullScreenMode](#enablefullscreenmode)|Habilita o modo de tela inteira para a janela do quadro.|  
|[CFrameWndEx::EnableLoadDockState](#enableloaddockstate)|Habilita ou desabilita o carregamento do estado de encaixe.|  
|[CFrameWndEx::EnablePaneMenu](#enablepanemenu)|Habilita ou desabilita a manipulação automática de menu do painel.|  
|[CFrameWndEx::GetActivePopup](#getactivepopup)|Retorna um ponteiro para o menu pop-up exibido no momento.|  
|[CFrameWndEx::GetDefaultResId](#getdefaultresid)|Retorna a ID de recurso que você especificou quando a estrutura carregado a janela do quadro.|  
|[CFrameWndEx::GetDockingManager](#getdockingmanager)|Recupera o [CDockingManager classe](../../mfc/reference/cdockingmanager-class.md) objeto para a janela do quadro.|  
|[CFrameWndEx::GetMenuBar](#getmenubar)|Retorna um ponteiro para o objeto de barra de menu anexado para a janela do quadro.|  
|[CFrameWndEx::GetPane](#getpane)|Retorna um ponteiro para o painel que tem a ID especificada.|  
|[CFrameWndEx::GetRibbonBar](#getribbonbar)|Recupera o controle de barra de faixa de opções para o quadro.|  
|[CFrameWndEx::GetTearOffBars](#gettearoffbars)|Retorna uma lista de objetos do painel que estão em um estado destacável.|  
|[CFrameWndEx::GetToolbarButtonToolTipText](#gettoolbarbuttontooltiptext)|Chamado pelo framework quando o aplicativo exibe a dica de ferramenta para um botão de barra de ferramentas.|  
|[CFrameWndEx::InsertPane](#insertpane)|Registra um painel com o Gerenciador de encaixe.|  
|[CFrameWndEx::IsFullScreen](#isfullscreen)|Determina se a janela do quadro está no modo de tela inteira.|  
|[CFrameWndEx::IsMenuBarAvailable](#ismenubaravailable)|Determina se o ponteiro para o objeto de barra de menu é válido.|  
|[CFrameWndEx::IsPointNearDockSite](#ispointneardocksite)|Indica se o ponto está localizado em uma zona de alinhamento.|  
|[CFrameWndEx::IsPrintPreview](#isprintpreview)|Indica se a janela do quadro está no modo de visualização de impressão.|  
|[CFrameWndEx::LoadFrame](#loadframe)|Este método é chamado após a construção para criar a janela do quadro e carregar seus recursos.|  
|[CFrameWndEx::NegotiateBorderSpace](#negotiateborderspace)|Negociação de borda do cliente do OLE implementa.|  
|[CFrameWndEx::OnActivate](#onactivate)|O framework chama esse método quando a entrada do usuário é alternada para ou do quadro.|  
|[CFrameWndEx::OnActivateApp](#onactivateapp)|Chamado pelo framework quando o aplicativo é marcado ou desmarcado.|  
|[CFrameWndEx::OnChangeVisualManager](#onchangevisualmanager)|Chamado pelo framework quando uma alteração ao quadro requer uma alteração para o Gerenciador de visual.|  
|[CFrameWndEx::OnClose](#onclose)|O framework chama esse método para fechar o quadro.|  
|[CFrameWndEx::OnCloseDockingPane](#onclosedockingpane)|Chamado pelo framework quando o usuário clica o **fechar** botão em um painel.|  
|[CFrameWndEx::OnCloseMiniFrame](#oncloseminiframe)|Chamado pelo framework quando o usuário clica o **fechar** botão em uma janela do quadro mini flutuante.|  
|[CFrameWndEx::OnClosePopupMenu](#onclosepopupmenu)|Chamado pelo framework quando um menu pop-up ativo processa uma mensagem WM_DESTROY.|  
|[CFrameWndEx::OnCmdMsg](#oncmdmsg)|O comando expede mensagens.|  
|[CFrameWndEx::OnContextHelp](#oncontexthelp)|Chamado pelo framework exibir o contexto de Ajuda relacionados.|  
|[CFrameWndEx::OnCreate](#oncreate)|Chamado pelo framework depois que o quadro for criado.|  
|[CFrameWndEx::OnDestroy](#ondestroy)|Chamado pelo framework quando o quadro é destruído.|  
|[CFrameWndEx::OnDrawMenuImage](#ondrawmenuimage)|Chamado pelo framework quando o aplicativo desenha a imagem associada a um item de menu.|  
|[CFrameWndEx::OnDrawMenuLogo](#ondrawmenulogo)|Chamado pelo framework quando um `CMFCPopupMenu` objeto processos um [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) mensagem.|  
|[CFrameWndEx::OnDWMCompositionChanged](#ondwmcompositionchanged)|Chamado pelo framework quando a composição do Desktop Window Manager (DWM) foi habilitada ou desabilitada.|  
|[CFrameWndEx::OnExitSizeMove](#onexitsizemove)|Chamado pelo framework quando o quadro para mover ou redimensionar.|  
|[CFrameWndEx::OnGetMinMaxInfo](#ongetminmaxinfo)|Chamado pelo framework quando o quadro é redimensionado para definir limites de dimensão da janela.|  
|[CFrameWndEx::OnIdleUpdateCmdUI](#onidleupdatecmdui)|Chamado pelo framework para atualizar a exibição de quadro quando o processamento do comando está ocioso.|  
|[CFrameWndEx::OnLButtonDown](#onlbuttondown)|O framework chama esse método quando o usuário pressiona o botão esquerdo do mouse.|  
|[CFrameWndEx::OnLButtonUp](#onlbuttonup)|O framework chama esse método quando o usuário libera o botão esquerdo do mouse.|  
|[CFrameWndEx::OnMenuButtonToolHitTest](#onmenubuttontoolhittest)|Chamado pelo framework quando um `CMFCToolBarButton` objeto processos um `WM_NCHITTEST` mensagem.|  
|[CFrameWndEx::OnMenuChar](#onmenuchar)|Chamado pelo framework quando um menu é exibido e o usuário pressiona uma tecla que não corresponde a um comando.|  
|[CFrameWndEx::OnMouseMove](#onmousemove)|O framework chama este método quando o ponteiro se move.|  
|[CFrameWndEx::OnMoveMiniFrame](#onmoveminiframe)|Chamado pelo framework quando um painel de janela é movida.|  
|[CFrameWndEx::OnNcActivate](#onncactivate)|Chamado pelo framework quando a área não cliente do quadro deve ser redesenhada para indicar uma alteração no estado ativo.|  
|[CFrameWndEx::OnNcCalcSize](#onnccalcsize)|Chamado pelo framework quando o tamanho e a posição da área do cliente devem ser calculadas.|  
|[CFrameWndEx::OnNcHitTest](#onnchittest)|Chamado pelo framework quando o ponteiro se move ou quando um botão do mouse é pressionado ou liberado.|  
|[CFrameWndEx::OnNcMouseMove](#onncmousemove)|Chamado pelo framework quando o ponteiro se move em uma área não cliente.|  
|[CFrameWndEx::OnNcPaint](#onncpaint)|Chamado pelo framework quando a área do cliente não deve ser pintada.|  
|[CFrameWndEx::OnPaneCheck](#onpanecheck)|Chamado pelo framework para controlar a visibilidade de um painel.|  
|[CFrameWndEx::OnPostPreviewFrame](#onpostpreviewframe)|Chamado pelo framework quando o usuário alterou o modo de visualização de impressão.|  
|[CFrameWndEx::OnPowerBroadcast](#onpowerbroadcast)|Chamado pelo framework quando ocorre um evento de gerenciamento de energia.|  
|[CFrameWndEx::OnSetMenu](#onsetmenu)|Chamado pelo framework para substituir o menu de janela do quadro.|  
|[CFrameWndEx::OnSetPreviewMode](#onsetpreviewmode)|Chamado pelo framework para definir o modo de visualização de impressão para o quadro.|  
|[CFrameWndEx::OnSetText](#onsettext)|Chamado pelo framework para definir o texto de uma janela.|  
|[CFrameWndEx::OnShowCustomizePane](#onshowcustomizepane)|Chamado pelo framework quando uma rápida Personalizar painel está habilitado.|  
|[CFrameWndEx::OnShowPanes](#onshowpanes)|Chamado pelo framework para mostrar ou ocultar painéis.|  
|[CFrameWndEx::OnShowPopupMenu](#onshowpopupmenu)|Chamado pelo framework quando um menu pop-up está habilitado.|  
|[CFrameWndEx::OnSize](#onsize)|O framework chama esse método após as alterações de tamanho do quadro.|  
|[CFrameWndEx::OnSizing](#onsizing)|O framework chama este método quando o usuário o redimensiona o quadro.|  
|[CFrameWndEx::OnSysColorChange](#onsyscolorchange)|Chamado pelo framework quando alterar as cores do sistema.|  
|[CFrameWndEx::OnTearOffMenu](#ontearoffmenu)|Chamado pelo framework quando um menu que tem uma barra destacável está habilitado.|  
|[CFrameWndEx::OnToolbarContextMenu](#ontoolbarcontextmenu)|Chamado pelo framework para criar um menu de contexto da barra de ferramentas.|  
|[CFrameWndEx::OnToolbarCreateNew](#ontoolbarcreatenew)|O framework chama esse método para criar uma nova barra de ferramentas.|  
|[CFrameWndEx::OnToolbarDelete](#ontoolbardelete)|Chamado pelo framework quando uma barra de ferramentas é excluída.|  
|[CFrameWndEx::OnUpdateFrameMenu](#onupdateframemenu)|Chamado pelo framework para definir o menu do quadro.|  
|[CFrameWndEx::OnUpdateFrameTitle](#onupdateframetitle)|O framework chama esse método para atualizar a barra de título da janela do quadro.|  
|[CFrameWndEx::OnUpdatePaneMenu](#onupdatepanemenu)|Chamado pelo framework para atualizar o menu do painel.|  
|[CFrameWndEx::OnWindowPosChanged](#onwindowposchanged)|Chamado pelo framework quando o tamanho do quadro, a posição ou a ordem z é alterado devido a uma chamada para um método de gerenciamento de janela.|  
|[CFrameWndEx::PaneFromPoint](#panefrompoint)|Retorna o painel de encaixe que contém o ponto especificado.|  
|[CFrameWndEx::PreTranslateMessage](#pretranslatemessage)|Trata mensagens de janela específico antes de serem distribuídos.|  
|[CFrameWndEx::RecalcLayout](#recalclayout)|Ajusta o layout do quadro e janelas filho.|  
|[CFrameWndEx::RemovePaneFromDockManager](#removepanefromdockmanager)|Cancela o registro de um painel e remove da lista interna no Gerenciador de encaixe.|  
|[CFrameWndEx::SetDockState](#setdockstate)|Restaura o layout de encaixe para o estado de encaixe armazenado no registro.|  
|[CFrameWndEx::SetPrintPreviewFrame](#setprintpreviewframe)|Define a janela do quadro de visualização de impressão.|  
|[CFrameWndEx::SetupToolbarMenu](#setuptoolbarmenu)|Inserções de comandos definidos pelo usuário em um menu da barra de ferramentas.|  
|[CFrameWndEx::ShowFullScreen](#showfullscreen)|Alterna o quadro principal entre os modos regulares e a tela inteira.|  
|[CFrameWndEx::ShowPane](#showpane)|Mostra ou oculta o painel especificado.|  
|[CFrameWndEx::UpdateCaption](#updatecaption)|Chamado pelo framework para atualizar a legenda do quadro de janela.|  
|[CFrameWndEx::WinHelp](#winhelp)|Invoca o o `WinHelp` relacionados a aplicativos ou contexto de Ajuda.|  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir demonstra como herdar de uma classe a partir de `CFrameWndEx` classe. O exemplo ilustra as assinaturas de método na subclasse e como substituir o `OnShowPopupMenu` método. Este trecho de código é parte do [exemplo Word Pad](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#3](../../mfc/reference/codesnippet/cpp/cframewndex-class_1.h)]  
[!code-cpp[NVC_MFC_WordPad#4](../../mfc/reference/codesnippet/cpp/cframewndex-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hierarquia de herança  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CWinAppEx é](../../mfc/reference/cframewndex-class.md)  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** afxframewndex.h  
  
##  <a name="activeitemrecalclayout"></a>CFrameWndEx::ActiveItemRecalcLayout  
 Ajusta o layout do item de cliente OLE e área do cliente do quadro.  
  
```  
void ActiveItemRecalcLayout();
```  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="addpane"></a>CFrameWndEx::AddPane  
 Registra uma barra de controle com o Gerenciador de encaixe.  
  
```  
BOOL AddPane(
    CBasePane* pControlBar,  
    BOOL bTail=TRUE);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pControlBar`  
 Um painel da barra de controle para registrar.  
  
 [in] `bTail`  
 `TRUE`Se você deseja adicionar o painel da barra de controle para o final da lista; `FALSE` caso contrário.  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se a barra de controle foi registrada com êxito; `FALSE` caso contrário.  
  
##  <a name="adjustdockinglayout"></a>CFrameWndEx::AdjustDockingLayout  
 Recalcula o layout de todos os painéis que está encaixada na janela do quadro.  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp=NULL);
```  
  
### <a name="parameters"></a>Parâmetros  
 `hdwp`  
 Um identificador para uma estrutura que contém as posições de várias janelas. .  
  
### <a name="remarks"></a>Comentários  
 A estrutura hdwp é inicializada, o [BeginDeferWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms632672) método.  
  
##  <a name="delayupdateframemenu"></a>CFrameWndEx::DelayUpdateFrameMenu  
 Define o menu do quadro e, em seguida, atualiza-la quando o processamento do comando estiver ocioso.  
  
```  
virtual void DelayUpdateFrameMenu(HMENU hMenuAlt);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `hMenuAlt`  
 Identificador para um menu alternativo.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="dockpane"></a>CFrameWndEx::DockPane  
 Encaixa painel especificado para a janela do quadro.  
  
```  
void DockPane(
    CBasePane* pBar,  
    UINT nDockBarID=0,  
    LPCRECT lpRect=NULL);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pBar`  
 Um ponteiro para a barra de controle encaixado.  
  
 [in] `nDockBarID`  
 A ID do lado da janela do quadro para encaixar.  
  
 [in] `lpRect`  
 Um ponteiro para uma estrutura Rect constante que especifica a posição da tela e o tamanho da janela.  
  
### <a name="remarks"></a>Comentários  
 O `nDockBarID` parâmetro pode ter um dos seguintes valores:  
  
-   AFX_IDW_DOCKBAR_TOP  
  
-   AFX_IDW_DOCKBAR_BOTTOM  
  
-   AFX_IDW_DOCKBAR_LEFT  
  
-   AFX_IDW_DOCKBAR_RIGHT  
  
##  <a name="dockpaneleftof"></a>CFrameWndEx::DockPaneLeftOf  
 Encaixa painel especificado à esquerda do outro painel.  
  
```  
BOOL DockPaneLeftOf(
    CPane* pBar,  
    CPane* pLeftOf);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pBar`  
 Um ponteiro para o objeto de painel encaixado.  
  
 [in] `pLeftOf`  
 Um ponteiro para o painel à esquerda do que encaixar o painel especificado pelo `pBar`.  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se `pBar` está encaixado com êxito. `FALSE`Caso contrário.  
  
### <a name="remarks"></a>Comentários  
 O método usa a barra de ferramentas especificada pelo `pBar` parâmetro e módulos de ancoragem especificado por ele no lado esquerdo da barra de ferramentas por `pLeftOf` parâmetro.  
  
##  <a name="enableautohidepanes"></a>CFrameWndEx::EnableAutoHidePanes  
 Permite oculta automaticamente modo para o painel quando ela estiver encaixada para o lado especificado da janela do quadro principal.  
  
```  
BOOL EnableAutoHidePanes(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `dwDockStyle`  
 Especifica o lado da janela do quadro principal ao qual se encaixar o painel.  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se uma barra de painel está encaixado com êxito ao lado de janela do quadro especificado por `dwDockStyle`, `FALSE` caso contrário.  
  
### <a name="remarks"></a>Comentários  
 `dwDockStyle`pode ter um dos seguintes valores:  
  
-   CBRS_ALIGN_TOP: permite que a barra de controle para ser encaixado à parte superior da área cliente de uma janela do quadro.  
  
-   CBRS_ALIGN_BOTTOM: permite que a barra de controle para ser encaixado na parte inferior da área cliente de uma janela do quadro.  
  
-   CBRS_ALIGN_LEFT: permite que a barra de controle encaixado à esquerda da área cliente de uma janela do quadro.  
  
-   CBRS_ALIGN_RIGHT: permite que a barra de controle encaixado à direita da área cliente de uma janela do quadro.  
  
##  <a name="enabledocking"></a>CFrameWndEx::EnableDocking  
 Habilita o encaixe dos painéis da janela do quadro.  
  
```  
BOOL EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `dwDockStyle`  
 Especifica o lado da janela do quadro principal onde encaixa a barra do painel.  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se uma barra de painel pode ser encaixado com êxito no lado especificado. `FALSE`Caso contrário.  
  
### <a name="remarks"></a>Comentários  
 O `dwDockStyle` parâmetro pode ter um dos seguintes valores:  
  
-   CBRS_ALIGN_TOP  
  
-   CBRS_ALIGN_BOTTOM  
  
-   CBRS_ALIGN_LEFT  
  
-   CBRS_ALIGN_RIGHT  
  
##  <a name="enablefullscreenmainmenu"></a>CFrameWndEx::EnableFullScreenMainMenu  
 Mostra ou oculta o menu principal em um modo de tela inteira.  
  
```  
void EnableFullScreenMainMenu(BOOL bEnableMenu);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `bEnableMenu`  
 `TRUE`para mostrar o menu principal em um modo de tela inteira, `FALSE` caso contrário.  
  
##  <a name="enablefullscreenmode"></a>CFrameWndEx::EnableFullScreenMode  
 Habilita o modo de tela inteira para a janela do quadro.  
  
```  
void EnableFullScreenMode(UINT uiFullScreenCmd);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `uiFullScreenCmd`  
 A ID de um comando que habilita e desabilita o modo de tela inteira.  
  
### <a name="remarks"></a>Comentários  
 No modo de tela inteira, todas as barras de controle de encaixe, barras de ferramentas e menus estão ocultos e o modo de exibição ativo é redimensionado para ocupar a tela inteira.  
  
 Quando você habilita o modo de tela inteira, você deve especificar uma ID do comando que habilita ou desabilita o modo de tela inteira. Você pode chamar `EnableFullScreenMode` do quadro principal `OnCreate` função. Quando uma janela do quadro está sendo alternada para um modo de tela cheia, o framework cria uma barra de ferramentas flutuante com um botão que possui a ID de comando especificado.  
  
 Se você quiser manter o menu principal na tela, chame [CFrameWndEx::EnableFullScreenMainMenu](#enablefullscreenmainmenu).  
  
##  <a name="enableloaddockstate"></a>CFrameWndEx::EnableLoadDockState  
 Habilita ou desabilita o carregamento do estado de encaixe.  
  
```  
void EnableLoadDockState(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `bEnable`  
 `TRUE`Para habilitar o carregamento do estado do encaixe, `FALSE` para desabilitar o carregamento do estado de encaixe.  
  
##  <a name="enablepanemenu"></a>CFrameWndEx::EnablePaneMenu  
 Habilita ou desabilita a manipulação automática de menu do painel.  
  
```  
void EnablePaneMenu(
    BOOL bEnable,  
    UINT uiCustomizeCmd,  
    const CString& strCustomizeLabel,  
    UINT uiViewToolbarsMenuEntryID,  
    BOOL bContextMenuShowsToolbarsOnly=FALSE,  
    BOOL bViewMenuShowsToolbarsOnly=FALSE);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `bEnable`  
 `TRUE`Para habilitar a manipulação automática de controle barra de menus pop-up; `FALSE` para desabilitar a manipulação automática de controle barra de menus pop-up.  
  
 [in] `uiCustomizeCmd`  
 A ID de comando do **personalizar** item de menu.  
  
 [in] `strCustomizeLabel`  
 O rótulo a ser exibido para o **personalizar** item de menu  
  
 [in] `uiViewToolbarsMenuEntryID`  
 A ID de um item de menu da barra de ferramentas que abre o menu pop-up na barra de controle.  
  
 [in] `bContextMenuShowsToolbarsOnly`  
 Se `TRUE`, o controle de barra de menu de contexto exibe a lista de apenas barras de ferramentas. Se `FALSE`, o menu exibe a lista de barras de ferramentas e barras de encaixe.  
  
 [in] `bViewMenuShowsToolbarsOnly`  
 Se `TRUE`, no menu da barra de controle exibe a lista de apenas as barras de ferramentas. Se `FALSE`, o menu exibe a lista de barras de ferramentas e barras de encaixe.  
  
##  <a name="getactivepopup"></a>CFrameWndEx::GetActivePopup  
 Retorna um ponteiro para o menu pop-up exibido no momento.  
  
```  
CMFCPopupMenu* GetActivePopup() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 Um ponteiro para o menu pop-up exibido no momento; Caso contrário, `NULL`.  
  
##  <a name="getdefaultresid"></a>CFrameWndEx::GetDefaultResId  
 Retorna a ID de recurso que você especificou quando a estrutura carregado a janela do quadro.  
  
```  
UINT GetDefaultResId() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 O valor de ID de recurso que o usuário especificado quando o framework carregada a janela do quadro. Zero se a janela do quadro não tem uma barra de menus.  
  
##  <a name="getdockingmanager"></a>CFrameWndEx::GetDockingManager  
 Recupera o [CDockingManager classe](../../mfc/reference/cdockingmanager-class.md) objeto para a janela do quadro.  
  
```  
CDockingManager* GetDockingManager();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Um ponteiro para o [CDockingManager classe](../../mfc/reference/cdockingmanager-class.md).  
  
### <a name="remarks"></a>Comentários  
 A janela do quadro cria e usa um [CDockingManager classe](../../mfc/reference/cdockingmanager-class.md) objeto para gerenciar o encaixe de janela filho.  
  
##  <a name="getmenubar"></a>CFrameWndEx::GetMenuBar  
 Retorna um ponteiro para o objeto de barra de menu anexado para a janela do quadro.  
  
```  
const CMFCMenuBar* GetMenuBar() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 Um ponteiro para o objeto de barra de menu anexado para a janela do quadro.  
  
##  <a name="getpane"></a>CFrameWndEx::GetPane  
 Retorna um ponteiro para o painel que tem a ID especificada.  
  
```  
CBasePane* GetPane(UINT nID);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `nID`  
 A ID do controle.  
  
### <a name="return-value"></a>Valor de retorno  
 Um ponteiro para o painel que tem a ID especificada. `NULL`Se esse painel não existe.  
  
##  <a name="getribbonbar"></a>CFrameWndEx::GetRibbonBar  
 Recupera o controle de barra de faixa de opções para o quadro.  
  
```  
CMFCRibbonBar* GetRibbonBar();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Ponteiro para o [classe CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md) para o quadro.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="gettearoffbars"></a>CFrameWndEx::GetTearOffBars  
 Retorna uma lista de objetos do painel que estão em um estado destacável.  
  
```  
const CObList& GetTearOffBars() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 Uma referência a `CObList` objeto que contém uma coleção de ponteiros para os objetos do painel que estão em um estado destacável.  
  
##  <a name="gettoolbarbuttontooltiptext"></a>CFrameWndEx::GetToolbarButtonToolTipText  
 Chamado pelo framework quando o aplicativo exibe a dica de ferramenta para um botão de barra de ferramentas.  
  
```  
virtual BOOL GetToolbarButtonToolTipText(
    CMFCToolBarButton* pButton,  
    CString& strTTText);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pButton`  
 Um ponteiro para um botão de barra de ferramentas.  
  
 [in] `strTTText`  
 O texto de dica de ferramenta a ser exibida para o botão.  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se a dica de ferramenta foi exibida. `FALSE`Caso contrário.  
  
### <a name="remarks"></a>Comentários  
 Por padrão, esse método não fará nada. Substitua este método se você deseja exibir a dica de ferramenta do botão de barra de ferramentas.  
  
##  <a name="insertpane"></a>CFrameWndEx::InsertPane  
 Insere um painel em uma lista de barras de controle e a registra com o Gerenciador de encaixe.  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter=TRUE);
```  
  
### <a name="parameters"></a>Parâmetros  
 `pControlBar`  
 Um ponteiro para uma barra de controle a ser inserido na lista de barras de controle e registrado com o Gerenciador de encaixe.  
  
 `pTarget`  
 Um ponteiro para uma barra antes ou após o qual o painel de controle.  
  
 `bAfter`  
 `TRUE`Se você desejar inserir `pControlBar` depois `pTarget`, `FALSE` caso contrário.  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se a barra de controle com êxito foi inserida e registrada, `FALSE` caso contrário.  
  
### <a name="remarks"></a>Comentários  
 Você deve registrar cada barra de controle usando o [CDockingManager classe](../../mfc/reference/cdockingmanager-class.md) para ajudar no layout de encaixe.  
  
##  <a name="isfullscreen"></a>CFrameWndEx::IsFullScreen  
 Determina se a janela do quadro está no modo de tela inteira.  
  
```  
BOOL IsFullScreen() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se a janela do quadro está no modo de tela inteira. Caso contrário, `FALSE`.  
  
### <a name="remarks"></a>Comentários  
 Você pode definir o modo de tela inteira, chamando o [CFrameWndEx::EnableFullScreenMode](#enablefullscreenmode) método.  
  
##  <a name="ismenubaravailable"></a>CFrameWndEx::IsMenuBarAvailable  
 Determina se o ponteiro para o objeto de barra de menu é válido.  
  
```  
BOOL IsMenuBarAvailable() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se a janela do quadro tem uma barra de menus; Caso contrário, `FALSE`.  
  
##  <a name="ispointneardocksite"></a>CFrameWndEx::IsPointNearDockSite  
 Determina se o ponto está localizado em uma zona de alinhamento.  
  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `point`  
 A posição do ponto.  
  
 [out] `dwBarAlignment`  
 Em que o ponto seja alinhado. Consulte a tabela na seção comentários para os valores possíveis.  
  
 [out] `bOuterEdge`  
 `TRUE`Se o ponto está localizado próximo da borda do quadro; `FALSE` se o ponto está localizado em uma área do cliente.  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se o ponto está localizado em uma zona de alinhamento. Caso contrário, `FALSE`.  
  
### <a name="remarks"></a>Comentários  
 A tabela a seguir lista os possíveis valores para o `dwBarAlignment` parâmetro.  
  
 `CBRS_ALIGN_TOP`  
 Alinhado à parte superior.  
  
 `CBRS_ALIGN_RIGHT`  
 Alinhado à direita.  
  
 `CBRS_ALIGN_BOTTOM`  
 Alinhado à parte inferior.  
  
 `CBRS_ALIGN_LEFT`  
 Alinhado à esquerda.  
  
##  <a name="isprintpreview"></a>CFrameWndEx::IsPrintPreview  
 Determina se a janela do quadro está no modo de visualização de impressão.  
  
```  
BOOL IsPrintPreview();
```  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se a janela do quadro está no modo de visualização de impressão; Caso contrário, `FALSE`.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="loadframe"></a>CFrameWndEx::LoadFrame  
 Este método é chamado após a construção para criar a janela do quadro e carregar seus recursos.  
  
```  
virtual BOOL LoadFrame(
    UINT nIDResource,  
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,  
    CWnd* pParentWnd = NULL,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `nIDResource`  
 A ID de recurso que é usada para carregar todos os recursos do quadro.  
  
 [in] `dwDefaultStyle`  
 O estilo de janela do quadro do padrão.  
  
 [in] `pParentWnd`  
 Ponteiro para a janela pai do quadro.  
  
 [in] `pContext`  
 Ponteiro para um [CCreateContext estrutura](../../mfc/reference/ccreatecontext-structure.md) classe que é usada pelo framework durante a criação do aplicativo.  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE` caso o método tenha sido bem-sucedido; do contrário, `FALSE`.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="negotiateborderspace"></a>CFrameWndEx::NegotiateBorderSpace  
 Negociação de borda do cliente do OLE implementa.  
  
```  
virtual BOOL NegotiateBorderSpace(
    UINT nBorderCmd,  
    LPRECT lpRectBorder);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `nBorderCmd`  
 O comando de negociação de borda. Consulte a seção comentários para os valores possíveis.  
  
 [in, out] `lpRectBorder`  
 Dimensões da borda.  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se o layout deve ser recalculado; Caso contrário, `FALSE`.  
  
### <a name="remarks"></a>Comentários  
 A tabela a seguir lista os possíveis valores para o `nBorderCmd` parâmetro.  
  
 `borderGet`  
 Obter o espaço disponível de cliente OLE.  
  
 `borderRequest`  
 Solicitação do espaço do cliente OLE.  
  
 `borderSet`  
 Defina o espaço de cliente OLE.  
  
##  <a name="onactivate"></a>CFrameWndEx::OnActivate  
 O framework chama esse método quando a entrada do usuário é alternada para ou do quadro.  
  
```  
afx_msg void OnActivate(
    UINT nState,  
    CWnd* pWndOther,  
    BOOL bMinimized);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `nState`  
 Se o quadro está ativo ou inativo. Consulte a tabela na seção comentários para os valores possíveis.  
  
 [in] `pWndOther`  
 Ponteiro para uma outra janela que está alternando a entrada do usuário atual.  
  
 [in] `bMinimized`  
 O estado minimizado do quadro. `TRUE`Se o quadro é minimizado. Caso contrário, `FALSE`.  
  
### <a name="remarks"></a>Comentários  
 A tabela a seguir lista os possíveis valores para o `nState` parâmetro.  
  
 `WA_ACTIVE`  
 O quadro é selecionado por um método diferente de um clique do mouse.  
  
 `WA_CLICKACTIVE`  
 O quadro é selecionado por um clique do mouse.  
  
 `WA_INACTIVE`  
 O quadro não está selecionado.  
  
##  <a name="onactivateapp"></a>CFrameWndEx::OnActivateApp  
 Chamado pelo framework quando o aplicativo é marcado ou desmarcado.  
  
```  
afx_msg void OnActivateApp(
    BOOL bActive,  
    DWORD dwThreadID);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `bActive`  
 `TRUE`Se o aplicativo está selecionado. `FALSE` se o aplicativo não estiver selecionado.  
  
 [in] `dwThreadID`  
 Este parâmetro não é usado.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="onchangevisualmanager"></a>CFrameWndEx::OnChangeVisualManager  
 Chamado pelo framework quando uma alteração ao quadro requer uma alteração para o Gerenciador de visual.  
  
```  
afx_msg LRESULT OnChangeVisualManager(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `wParam`  
 Este parâmetro não é usado.  
  
 [in] `lParam`  
 Este parâmetro não é usado.  
  
### <a name="return-value"></a>Valor de retorno  
 Sempre retorna 0.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="onclose"></a>CFrameWndEx::OnClose  
 O framework chama esse método para fechar o quadro.  
  
```  
afx_msg void OnClose();
```  
  
### <a name="remarks"></a>Comentários  
 Se o quadro estiver no modo de visualização de impressão, ele envia uma mensagem do Windows para fechar a visualização da impressão. Caso contrário, se o quadro hospeda um cliente OLE, o cliente está desativado.  
  
##  <a name="onclosedockingpane"></a>CFrameWndEx::OnCloseDockingPane  
 Chamado pelo framework quando o usuário clica o **fechar** botão em um painel.  
  
```  
virtual BOOL OnCloseDockingPane(CDockablePane* pPane);
```  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se a barra de encaixe pode ser fechada. `FALSE`Caso contrário  
  
### <a name="remarks"></a>Comentários  
 Implementar o padrão não fará nada. Substitua este método se você desejar tratar ocultação da barra de encaixe.  
  
##  <a name="oncloseminiframe"></a>CFrameWndEx::OnCloseMiniFrame  
 Chamado pelo framework quando o usuário clica o **fechar** botão em uma janela do quadro mini flutuante.  
  
```  
virtual BOOL OnCloseMiniFrame(CPaneFrameWnd* pWnd);
```  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se uma janela do quadro mini flutuante pode ser fechada. `FALSE`Caso contrário.  
  
### <a name="remarks"></a>Comentários  
 A implementação padrão não fará nada. Substitua este método se você quiser processar ocultação de uma janela do quadro mini flutuante.  
  
##  <a name="onclosepopupmenu"></a>CFrameWndEx::OnClosePopupMenu  
 Chamado pelo framework quando um menu pop-up ativo processa uma mensagem WM_DESTROY.  
  
```  
virtual void OnClosePopupMenu(CMFCPopupMenu* pMenuPopup);
```  
  
### <a name="parameters"></a>Parâmetros  
 `pMenuPopup`  
 Um ponteiro para um menu pop-up.  
  
### <a name="remarks"></a>Comentários  
 A estrutura envia uma mensagem WM_DESTROY quando ele está prestes a fechar a janela. Substitua este método se você desejar tratar notificações de `CMFCPopupMenu` objetos que pertencem à janela do quadro quando um `CMFCPopupMenu` objeto está processando uma `WM_DESTROY` mensagem enviada pelo framework quando a janela está sendo fechada.  
  
##  <a name="oncmdmsg"></a>CFrameWndEx::OnCmdMsg  
 O comando expede mensagens.  
  
```  
virtual BOOL OnCmdMsg(
    UINT nID,  
    int nCode,  
    void* pExtra,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `nID`  
 A ID de comando.  
  
 [in] `nCode`  
 Categoria de mensagem de comando.  
  
 [in, out] `pExtra`  
 Ponteiro para um objeto de comando.  
  
 [in, out] `pHandlerInfo`  
 Ponteiro para uma estrutura do manipulador de comando.  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se a mensagem de comando foi tratada; Caso contrário, `FALSE`.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="oncontexthelp"></a>CFrameWndEx::OnContextHelp  
 Chamado pelo framework para exibir a Ajuda relacionados ao contexto.  
  
```  
afx_msg void OnContextHelp();
```  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="oncreate"></a>CFrameWndEx::OnCreate  
 Chamado pelo framework depois que o quadro for criado.  
  
```  
afx_msg int OnCreate(LPCREATESTRUCT lpCreateStruct);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `lpCreateStruct`  
 Um ponteiro para o [estrutura CREATESTRUCT](../../mfc/reference/createstruct-structure.md) para o novo quadro.  
  
### <a name="return-value"></a>Valor de retorno  
 0 para continuar com a criação de quadro; -1 para destruir o quadro.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="ondestroy"></a>CFrameWndEx::OnDestroy  
 Chamado pelo framework quando o quadro é destruído.  
  
```  
afx_msg void OnDestroy();
```  
  
### <a name="remarks"></a>Comentários  
 A tabela de Aceleradores e todas as janelas são destruídas.  
  
##  <a name="ondrawmenuimage"></a>CFrameWndEx::OnDrawMenuImage  
 Chamado pelo framework quando o aplicativo desenha a imagem associada a um item de menu.  
  
```  
virtual BOOL OnDrawMenuImage(
    CDC* pDC,  
    const CMFCToolBarMenuButton* pMenuButton,  
    const CRect& rectImage);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pDC`  
 Um ponteiro para um contexto de dispositivo.  
  
 [in] `pMenuButton`  
 Um ponteiro para um botão de menu cuja imagem está sendo processada.  
  
 [in] `rectImage`  
 Um ponteiro para um `Rect` estrutura que especifica a posição da tela e o tamanho da imagem.  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se a estrutura processa com êxito a imagem; `FALSE` caso contrário.  
  
### <a name="remarks"></a>Comentários  
 Substitua este método se você quiser personalizar a renderização de imagem para os itens de menu que pertencem a barra de menus pertencente a `CFrameWndEx` objeto derivado.  
  
##  <a name="ondrawmenulogo"></a>CFrameWndEx::OnDrawMenuLogo  
 Chamado pelo framework quando um `CMFCPopupMenu` objeto processa uma mensagem WM_PAINT.  
  
```  
virtual void OnDrawMenuLogo(
    CDC* pDC,  
    CMFCPopupMenu* pMenu,  
    const CRect& rectLogo);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pDC`  
 Um ponteiro para um contexto de dispositivo.  
  
 [in] `pMenu`  
 Um ponteiro para o item de menu.  
  
 [in] `rectLogo`  
 Uma referência a uma constante `CRect` estrutura que especifica a posição da tela e o tamanho do logotipo do menu.  
  
### <a name="remarks"></a>Comentários  
 Substituir essa função se desejar exibir um logotipo no menu pop-up que pertence à barra de menus pertencente a `CFrameWndEx` objeto derivado.  
  
##  <a name="ondwmcompositionchanged"></a>CFrameWndEx::OnDWMCompositionChanged  
 Chamado pelo framework quando a composição do Desktop Window Manager (DWM) foi habilitada ou desabilitada.  
  
```  
afx_msg LRESULT OnDWMCompositionChanged(
    WPARAM wp,  
    LPARAM lp);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `wp`  
 Este parâmetro não é usado.  
  
 [in] `lp`  
 Este parâmetro não é usado.  
  
### <a name="return-value"></a>Valor de retorno  
 Sempre retorna 0.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="onexitsizemove"></a>CFrameWndEx::OnExitSizeMove  
 Chamado pelo framework quando o quadro para mover ou redimensionar.  
  
```  
LRESULT OnExitSizeMove(
    WPARAM wp,  
    LPARAM lp);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `wp`  
 Este parâmetro não é usado.  
  
 [in] `lp`  
 Este parâmetro não é usado.  
  
### <a name="return-value"></a>Valor de retorno  
 Sempre retorna 0.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="ongetminmaxinfo"></a>CFrameWndEx::OnGetMinMaxInfo  
 Chamado pelo framework quando o quadro é redimensionado para definir limites de dimensão da janela.  
  
```  
afx_msg void OnGetMinMaxInfo(MINMAXINFO FAR* lpMMI);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `lpMMI`  
 Ponteiro para um [MINMAXINFO](http://msdn.microsoft.com/library/windows/desktop/ms632605) estrutura.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="onidleupdatecmdui"></a>CFrameWndEx::OnIdleUpdateCmdUI  
 Chamado pelo framework para atualizar a exibição de quadro quando o processamento do comando está ocioso.  
  
```  
afx_msg LRESULT OnIdleUpdateCmdUI(
    WPARAM wParam = 0,  
    LPARAM lParam = 0);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `wParam`  
 Este parâmetro não é usado.  
  
 [in] `lParam`  
 Este parâmetro não é usado.  
  
### <a name="return-value"></a>Valor de retorno  
 Sempre retorna 0.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="onlbuttondown"></a>CFrameWndEx::OnLButtonDown  
 O framework chama esse método quando o usuário pressiona o botão esquerdo do mouse.  
  
```  
afx_msg void OnLButtonDown(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `nFlags`  
 Indica se o usuário pressionou teclas modificadoras. Para os valores possíveis, consulte o parâmetro `wParam` na [WM_LBUTTONDOWN notificação](http://msdn.microsoft.com/library/windows/desktop/ms645607).  
  
 [in] `point`  
 Especifica a x e y coordenadas do ponteiro, em relação ao canto superior esquerdo da janela.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="onlbuttonup"></a>CFrameWndEx::OnLButtonUp  
 O framework chama esse método quando o usuário libera o botão esquerdo do mouse.  
  
```  
afx_msg void OnLButtonUp(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `nFlags`  
 Indica se o usuário pressionou teclas modificadoras. Para os valores possíveis, consulte o parâmetro `wParam` na [WM_LBUTTONUP notificação](http://msdn.microsoft.com/library/windows/desktop/ms645608).  
  
 [in] `point`  
 Especifica a x e y coordenadas do ponteiro, em relação ao canto superior esquerdo da janela.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="onmenubuttontoolhittest"></a>CFrameWndEx::OnMenuButtonToolHitTest  
 Chamado pelo framework quando um `CMFCToolBarButton` objeto processos um `WM_NCHITTEST` mensagem.  
  
```  
virtual BOOL OnMenuButtonToolHitTest(
    CMFCToolBarButton* pButton,  
    TOOLINFO* pTI);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pButton`  
 Um ponteiro para o botão de barra de ferramenta.  
  
 [out] `pTI`  
 Um ponteiro para uma estrutura de informações da ferramenta.  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se o aplicativo preenche o `pTI` parâmetro. `FALSE`Caso contrário.  
  
### <a name="remarks"></a>Comentários  
 Substitua este método se desejar fornecer um informações de dica de ferramenta sobre um item de menu específico.  
  
##  <a name="onmenuchar"></a>CFrameWndEx::OnMenuChar  
 Chamado pelo framework quando um menu é exibido e o usuário pressiona uma tecla que não corresponde a um comando.  
  
```  
afx_msg LRESULT OnMenuChar(
    UINT nChar,  
    UINT nFlags,  
    CMenu* pMenu);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `nChar`  
 Código de caractere da tecla pressionada.  
  
 [in] `nFlags`  
 Contém o `MF_POPUP` sinalizador se o menu exibido for um submenu; contém o `MF_SYSMENU` sinalizador se o menu exibido um menu de controle.  
  
 [in] `pMenu`  
 Ponteiro para um menu.  
  
### <a name="return-value"></a>Valor de retorno  
 A palavra de ordem superior deve ser um dos valores a seguir.  
  
 `0`  
 A estrutura deve ignorar o pressionamento de tecla.  
  
 `1`  
 A estrutura deve fechar o menu.  
  
 `2`  
 A estrutura deve selecionar um dos itens exibidos no menu. A palavra de ordem inferior contém a ID do comando Selecionar.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="onmousemove"></a>CFrameWndEx::OnMouseMove  
 O framework chama este método quando o ponteiro se move.  
  
```  
afx_msg void OnMouseMove(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `nFlags`  
 Indica se um usuário pressionou teclas modificadoras. Para os valores possíveis, consulte o parâmetro `wParam` na [WM_MOUSEMOVE notificação](http://msdn.microsoft.com/library/windows/desktop/ms645616).  
  
 [in] `point`  
 Especifica a x e y coordenadas do ponteiro em relação ao canto superior esquerdo da janela.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="onmoveminiframe"></a>CFrameWndEx::OnMoveMiniFrame  
 Chamado pelo framework quando um painel de janela é movida.  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pFrame`  
 Ponteiro para o [CPaneFrameWnd classe](../../mfc/reference/cpaneframewnd-class.md) janela do painel.  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se a janela do painel não foi encaixada; `FALSE` se a janela do painel foi encaixada.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="onncactivate"></a>CFrameWndEx::OnNcActivate  
 Chamado pelo framework quando a área não cliente do quadro deve ser redesenhada para indicar uma alteração no estado ativo.  
  
```  
afx_msg BOOL OnNcActivate(BOOL bActive);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `bActive`  
 `TRUE`Para desenhar o quadro ativo; `FALSE` para desenhar o quadro inativo.  
  
### <a name="return-value"></a>Valor de retorno  
 Diferente de zero para continuar com o processamento padrão; 0 para impedir que a área do cliente não está sendo desativado.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="onnccalcsize"></a>CFrameWndEx::OnNcCalcSize  
 Chamado pelo framework quando o tamanho e a posição da área do cliente devem ser calculadas.  
  
```  
afx_msg void OnNcCalcSize(
    BOOL bCalcValidRects,  
    NCCALCSIZE_PARAMS FAR* lpncsp);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `bCalcValidRects`  
 `TRUE`Quando o aplicativo deve especificar uma área de cliente válido; Caso contrário, `FALSE`.  
  
 [in] `lpncsp`  
 Ponteiro para um `NCCALCSIZE_PARAMS` estrutura que contém as alterações de dimensão do quadro.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="onnchittest"></a>CFrameWndEx::OnNcHitTest  
 Chamado pelo framework quando o ponteiro se move ou quando um botão do mouse é pressionado ou liberado.  
  
```  
afx_msg LRESULT OnNcHitTest(CPoint point);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `point`  
 O local do ponteiro em coordenadas da tela.  
  
### <a name="return-value"></a>Valor de retorno  
 Um ponteiro de ocorrências valor enumerado. Para obter uma lista de valores possíveis, consulte [WM_NCHITTEST notificação](http://msdn.microsoft.com/library/windows/desktop/ms645618).  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="onncmousemove"></a>CFrameWndEx::OnNcMouseMove  
 Chamado pelo framework quando o ponteiro se move em uma área não cliente.  
  
```  
afx_msg void OnNcMouseMove(
    UINT nHitTest,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `nHitTest`  
 Um ponteiro de ocorrências valor enumerado. Para obter uma lista de valores possíveis, consulte [WM_NCHITTEST notificação](http://msdn.microsoft.com/library/windows/desktop/ms645618).  
  
 [in] `point`  
 O local do ponteiro em coordenadas da tela.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="onncpaint"></a>CFrameWndEx::OnNcPaint  
 Chamado pelo framework quando a área do cliente não deve ser pintada.  
  
```  
afx_msg void OnNcPaint();
```  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="onpanecheck"></a>CFrameWndEx::OnPaneCheck  
 Chamado pelo framework para controlar a visibilidade de um painel.  
  
```  
afx_msg BOOL OnPaneCheck(UINT nID);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `nID`  
 ID de controle de um painel.  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se o comando foi tratado; `FALSE` para continuar com o processamento do comando.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="onpostpreviewframe"></a>CFrameWndEx::OnPostPreviewFrame  
 Chamado pelo framework quando o usuário altera o modo de visualização de impressão.  
  
```  
afx_msg LRESULT OnPostPreviewFrame(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `wParam`  
 Este parâmetro não é usado.  
  
 [in] `lParam`  
 `TRUE`Quando o quadro estiver no modo de visualização de impressão; `FALSE` quando o modo de visualização de impressão está desativado.  
  
### <a name="return-value"></a>Valor de retorno  
 Sempre retorna 0.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="onpowerbroadcast"></a>CFrameWndEx::OnPowerBroadcast  
 Chamado pelo framework quando ocorre um evento de gerenciamento de energia.  
  
```  
afx_msg LRESULT OnPowerBroadcast(
    WPARAM wp,  
    LPARAM lp);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `wp`  
 O evento de gerenciamento de energia. Para obter uma lista de valores possíveis, consulte [mensagem WM_POWERBROADCAST](http://msdn.microsoft.com/library/windows/desktop/aa373247).  
  
 [in] `lp`  
 Este parâmetro não é usado.  
  
### <a name="return-value"></a>Valor de retorno  
 O resultado de chamar o procedimento de janela padrão.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="onsetmenu"></a>CFrameWndEx::OnSetMenu  
 Chamado pelo framework para substituir o menu de janela do quadro.  
  
```  
afx_msg LRESULT OnSetMenu(
    WPARAM wp,  
    LPARAM lp);  
  
BOOL OnSetMenu(HMENU hmenu);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `wp`  
 Identificador para o novo menu de janela do quadro.  
  
 [in] `lp`  
 Identificador para o novo menu janela.  
  
 [in] `hmenu`  
 Identificador para o novo menu de janela do quadro.  
  
### <a name="return-value"></a>Valor de retorno  
 `LRESULT`é o resultado de chamar o procedimento de janela padrão.  
  
 `BOOL`é `TRUE` se o evento foi tratada; caso contrário, `FALSE`.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="onsetpreviewmode"></a>CFrameWndEx::OnSetPreviewMode  
 Chamado pelo framework para definir o modo de visualização de impressão para o quadro.  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `bPreview`  
 `TRUE`Para habilitar a visualização da impressão. `FALSE` para desabilitar a visualização de impressão.  
  
 [in] `pState`  
 Ponteiro para um `CPrintPreviewState` estrutura de estado do quadro.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="onsettext"></a>CFrameWndEx::OnSetText  
 Chamado pelo framework para definir o texto de uma janela.  
  
```  
afx_msg LRESULT OnSetText(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `wParam`  
 Este parâmetro não é usado.  
  
 [in] `lParam`  
 Ponteiro para o texto da janela.  
  
### <a name="return-value"></a>Valor de retorno  
 Valor de retorno de uma chamada para [DefWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633572).  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="onshowcustomizepane"></a>CFrameWndEx::OnShowCustomizePane  
 Chamado pelo framework quando ele for exibido um `QuickCustomizePane`.  
  
```  
virtual BOOL OnShowCustomizePane(
    CMFCPopupMenu* pMenuPane,  
    UINT uiToolbarID);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pMenuPane`  
 Um ponteiro para a rápida personalizar o painel.  
  
 [in] `uiToolbarID`  
 A ID de controle da barra de ferramentas para personalizar.  
  
### <a name="return-value"></a>Valor de retorno  
 Esse método sempre retornam `TRUE`.  
  
### <a name="remarks"></a>Comentários  
 Personalizar o rápido menu é um menu pop-up que aparece quando você clica em botão de personalizar a barra de ferramentas  
  
##  <a name="onshowpanes"></a>CFrameWndEx::OnShowPanes  
 Chamado pelo framework para mostrar ou ocultar painéis.  
  
```  
virtual BOOL OnShowPanes(BOOL bShow);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `bShow`  
 `TRUE`Se o aplicativo mostra os painéis; `FALSE` caso contrário.  
  
### <a name="return-value"></a>Valor de retorno  
 Esse método sempre retornam `FALSE`.  
  
### <a name="remarks"></a>Comentários  
 A implementação padrão mostra os painéis se `bShow` é `TRUE` e os painéis são ocultados ou quando `bShow` é `FALSE` e os painéis são visíveis.  
  
 A implementação padrão oculta os painéis se `bShow` é `TRUE` e os painéis são visíveis ou quando `bShow` é `FALSE` e os painéis são ocultados.  
  
 Substitua este método em uma classe derivada para executar código personalizado quando o framework mostra ou oculta os painéis.  
  
##  <a name="onshowpopupmenu"></a>CFrameWndEx::OnShowPopupMenu  
 Chamado pelo framework quando ele for exibido um menu pop-up.  
  
```  
virtual BOOL OnShowPopupMenu(CMFCPopupMenu* pMenu);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pMenu`  
 Um ponteiro para um menu pop-up.  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se o menu pop-up estiver visível; Caso contrário, `FALSE`.  
  
### <a name="remarks"></a>Comentários  
 Substitua este método em uma classe derivada para executar código personalizado quando o framework exibe um menu pop-up. Por exemplo, substitua este método para alterar a cor de plano de fundo dos comandos em um menu pop-up.  
  
##  <a name="onsize"></a>CFrameWndEx::OnSize  
 Chamado pelo framework depois das alterações de tamanho do quadro.  
  
```  
afx_msg void OnSize(
    UINT nType,  
    int cx,  
    int cy);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `nType`  
 O tipo de redimensionamento. Para os valores possíveis, consulte o parâmetro `wParam` na [WM_SIZE notificação](http://msdn.microsoft.com/library/windows/desktop/ms632646).  
  
 [in] `cx`  
 Nova largura do quadro em pixels.  
  
 [in] `cy`  
 Nova altura do quadro em pixels.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="onsizing"></a>CFrameWndEx::OnSizing  
 Chamado pelo framework quando o usuário o redimensiona o quadro.  
  
```  
afx_msg void OnSizing(
    UINT fwSide,  
    LPRECT pRect);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `fwSide`  
 A borda do quadro que é movido. Consulte o parâmetro `wParam` na [WM_SIZING notificação](http://msdn.microsoft.com/library/windows/desktop/ms632647).  
  
 [in, out] `pRect`  
 Ponteiro para um [CRect](../../atl-mfc-shared/reference/crect-class.md) ou [RECT](../../mfc/reference/rect-structure1.md) estrutura que contém as coordenadas do quadro.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="onsyscolorchange"></a>CFrameWndEx::OnSysColorChange  
 Chamado pelo framework quando alterar as cores do sistema.  
  
```  
void OnSysColorChange();
```  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="ontearoffmenu"></a>CFrameWndEx::OnTearOffMenu  
 Chamado pelo framework quando o aplicativo exibe um menu que tem uma barra destacável.  
  
```  
virtual BOOL OnTearOffMenu(
    CMFCPopupMenu* pMenuPopup,  
    CPane* pBar);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pMenuPopup`  
 Um ponteiro para um menu pop-up.  
  
 [in] `pBar`  
 Um ponteiro para uma barra destacável.  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se o menu pop-up com barra destacável está ativado. Caso contrário, `FALSE`.  
  
### <a name="remarks"></a>Comentários  
 Substitua este método em uma classe derivada para executar código personalizado quando o framework exibe uma barra de controle.  
  
 A implementação padrão não faz nada e retorna `TRUE`.  
  
##  <a name="ontoolbarcontextmenu"></a>CFrameWndEx::OnToolbarContextMenu  
 Chamado pelo framework para criar um menu pop-up da barra de ferramentas.  
  
```  
afx_msg LRESULT OnToolbarContextMenu(
    WPARAM wp,  
    LPARAM lp);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `wp`  
 Este parâmetro não é usado.  
  
 [in] `lp`  
 Este parâmetro não é usado.  
  
### <a name="return-value"></a>Valor de retorno  
 Sempre retorna 1.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="ontoolbarcreatenew"></a>CFrameWndEx::OnToolbarCreateNew  
 O framework chama esse método para criar uma nova barra de ferramentas.  
  
```  
afx_msg LRESULT OnToolbarCreateNew(
    WPARAM wp,  
    LPARAM lp);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `wp`  
 Este parâmetro não é usado.  
  
 [in] `lp`  
 Ponteiro para o texto da barra de título da barra de ferramentas.  
  
### <a name="return-value"></a>Valor de retorno  
 Ponteiro para a barra de ferramentas. ou `NULL` se uma barra de ferramentas não foi criada.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="ontoolbardelete"></a>CFrameWndEx::OnToolbarDelete  
 Chamado pelo framework quando uma barra de ferramentas é excluída.  
  
```  
afx_msg LRESULT OnToolbarDelete(
    WPARAM, 
    LPARAM lp);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in]  
 Este parâmetro não é usado.  
  
 [in] `lp`  
 Ponteiro para uma barra de ferramentas.  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se a barra de ferramentas foi excluída; Caso contrário, `FALSE`.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="onupdateframemenu"></a>CFrameWndEx::OnUpdateFrameMenu  
 Chamado pelo framework para definir o menu do quadro.  
  
```  
virtual void OnUpdateFrameMenu(HMENU hMenuAlt);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `hMenuAlt`  
 Identificador para o menu alternativo.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="onupdateframetitle"></a>CFrameWndEx::OnUpdateFrameTitle  
 O framework chama esse método para atualizar a barra de título da janela do quadro.  
  
```  
virtual void OnUpdateFrameTitle(BOOL bAddToTitle);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `bAddToTitle`  
 `TRUE`Para adicionar o título do documento ativo para a barra de título da janela de quadro; Caso contrário`FALSE.`  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="onupdatepanemenu"></a>CFrameWndEx::OnUpdatePaneMenu  
 Chamado pelo framework para atualizar o menu do painel.  
  
```  
afx_msg void OnUpdatePaneMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pCmdUI`  
 Ponteiro para o objeto de interface de usuário do painel.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="onwindowposchanged"></a>CFrameWndEx::OnWindowPosChanged  
 Chamado pelo framework quando o tamanho do quadro, a posição ou a ordem z é alterado devido a uma chamada para um método de gerenciamento de janela.  
  
```  
afx_msg void OnWindowPosChanged(WINDOWPOS FAR* lpwndpos);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `lpwndpos`  
 Ponteiro para um [WINDOWPOS](../../mfc/reference/windowpos-structure1.md) estrutura que contém o novo tamanho e posição.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="panefrompoint"></a>CFrameWndEx::PaneFromPoint  
 Pesquisa cada painel para o ponto.  
  
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
 As coordenadas de tela do ponto para verificar.  
  
 [in] `nSensitivity`  
 Expanda o retângulo delimitador de cada barra de controle por esse valor durante a pesquisa de ponto.  
  
 [in] `bExactBar`  
 `TRUE`para ignorar o `nSensitivity` parâmetro; caso contrário, `FALSE`.  
  
 [in] `pRTCBarType`  
 Se não for `NULL`, o método procura somente as barras de controle do tipo especificado.  
  
 [out] `dwAlignment`  
 Se for bem-sucedido, este parâmetro contém o lado da barra de controle mais próximo para o ponto especificado. Caso contrário, esse parâmetro não foi inicializado.  
  
### <a name="return-value"></a>Valor de retorno  
 Um ponteiro para uma barra de controle que contém o `point`; `NULL` se o controle não foi encontrado.  
  
### <a name="remarks"></a>Comentários  
 Este método pesquisa todas as barras de controle em seu aplicativo para um `point`.  
  
 Use `nSensitivity` para aumentar o tamanho da área de pesquisa. Use `pRTCBarType` para restringir os tipos de barras de controle que o método de pesquisa.  
  
##  <a name="pretranslatemessage"></a>CFrameWndEx::PreTranslateMessage  
 Trata mensagens de janela específico antes de serem distribuídos.  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pMsg`  
 Um ponteiro para um [MSG](../../mfc/reference/msg-structure1.md) estrutura que contém a mensagem para processar.  
  
### <a name="return-value"></a>Valor de retorno  
 Diferente de zero se a mensagem foi manipulada e não deve ser distribuída; 0 se a mensagem não foi tratada e deve ser enviada.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="recalclayout"></a>CFrameWndEx::RecalcLayout  
 Ajusta o layout do quadro e janelas filho.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `bNotify`  
 Especifica se deve notificar o item de cliente OLE sobre a alteração de layout.  
  
### <a name="remarks"></a>Comentários  
 Este método é chamado quando o tamanho da janela do quadro foi alterado ou quando as barras de controle são exibidas ou ocultas.  
  
##  <a name="removepanefromdockmanager"></a>CFrameWndEx::RemovePaneFromDockManager  
 Cancela o registro de um painel e a remove do Gerenciador de encaixe.  
  
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
 Um ponteiro para o painel da barra de controle para remover.  
  
 [in] `bDestroy`  
 `TRUE`destruir a barra de controle depois de remover. `FALSE` caso contrário.  
  
 [in] `bAdjustLayout`  
 `TRUE`Para ajustar o layout de encaixe; `FALSE` caso contrário.  
  
 [in] `bAutoHide`  
 `TRUE`Se a barra de controle está no modo de ocultar automaticamente; `FALSE` caso contrário.  
  
 [in] `pBarReplacement`  
 Um ponteiro para um painel que substitui o painel removido.  
  
### <a name="remarks"></a>Comentários  
 Use esse método para remover uma barra de controle do encaixe layout da janela do quadro.  
  
 O [CDockingManager classe](../../mfc/reference/cdockingmanager-class.md) manipula o layout das barras de controle. Você deve registrar cada barra de controle com o Gerenciador de encaixe usando o [CFrameWndEx::AddPane](#addpane) método ou o [CFrameWndEx::InsertPane](#insertpane) método.  
  
##  <a name="setdockstate"></a>CFrameWndEx::SetDockState  
 Restaura o layout de encaixe para o estado de encaixe armazenado no registro.  
  
```  
void SetDockState(const CDockState& state);
```  
  
### <a name="parameters"></a>Parâmetros  
 `state`  
 O estado de encaixe. Este parâmetro é ignorado.  
  
##  <a name="setprintpreviewframe"></a>CFrameWndEx::SetPrintPreviewFrame  
 Define a janela do quadro de visualização de impressão.  
  
```  
void SetPrintPreviewFrame(CFrameWnd* pWnd);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pWnd`  
 Ponteiro para uma janela do quadro de visualização de impressão.  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="setuptoolbarmenu"></a>CFrameWndEx::SetupToolbarMenu  
 Inserções de comandos definidos pelo usuário em um menu da barra de ferramentas.  
  
```  
void SetupToolbarMenu(
    CMenu& menu,  
    const UINT uiViewUserToolbarCmdFirst,  
    const UINT uiViewUserToolbarCmdLast);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `menu`  
 Um `CMenu` objeto a ser modificado.  
  
 [in] `uiViewUserToolbarCmdFirst`  
 O primeiro comando definido pelo usuário.  
  
 [in] `uiViewUserToolbarCmdLast`  
 O último comando definido pelo usuário.  
  
### <a name="remarks"></a>Comentários  
 O framework armazena comandos definidos pelo usuário em uma lista. Use `uiViewUserToolbarCmdFirst` e `uiViewUserToolbarCmdList` para especificar os índices de comandos para inserir.  
  
##  <a name="showfullscreen"></a>CFrameWndEx::ShowFullScreen  
 Alterna o quadro principal entre o modo de tela inteira e o modo normal.  
  
```  
void ShowFullScreen();
```  
  
##  <a name="showpane"></a>CFrameWndEx::ShowPane  
 Mostra ou oculta o painel especificado.  
  
```  
void ShowPane(
    CBasePane* pBar,  
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pBar`  
 Um ponteiro para mostrar ou ocultar a barra de controle.  
  
 [in] `bShow`  
 Se `TRUE`, o aplicativo mostra a barra de controle. Caso contrário, o aplicativo oculta a barra de controle.  
  
 [in] `bDelay`  
 Se `TRUE`, adiar o ajuste do layout do encaixe até o framework chama [CFrameWndEx::AdjustDockingLayout](#adjustdockinglayout). Caso contrário, recalcula o layout de encaixe imediatamente.  
  
 [in] `bActivate`  
 Se `TRUE`, ativar a barra de controle. Caso contrário, exibe a barra de controle em um estado inativo.  
  
##  <a name="updatecaption"></a>CFrameWndEx::UpdateCaption  
 Chamado pelo framework para atualizar a legenda do quadro de janela.  
  
```  
void UpdateCaption();
```  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="winhelp"></a>CFrameWndEx::WinHelp  
 Invoca o aplicativo WinHelp ou contexto relacionadas a Ajuda.  
  
```  
virtual void WinHelp(
    DWORD dwData,  
    UINT nCmd = HELP_CONTEXT);
```  
  
### <a name="parameters"></a>Parâmetros  
 `dwData`  
 Dados que dependem de `nCmd` parâmetro. Para obter uma lista de valores possíveis, consulte [WinHelp](http://msdn.microsoft.com/library/windows/desktop/bb762267).  
  
 `nCmd`  
 O comando Ajuda. Para obter uma lista de valores possíveis, consulte [WinHelp](http://msdn.microsoft.com/library/windows/desktop/bb762267).  
  
### <a name="remarks"></a>Comentários  
  
## <a name="see-also"></a>Consulte também  
 [Gráfico de hierarquia](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)