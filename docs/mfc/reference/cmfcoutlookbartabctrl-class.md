---
title: Classe CMFCOutlookBarTabCtrl | Documentos do Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCOutlookBarTabCtrl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::AddControl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::CanShowFewerPageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::CanShowMorePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::Create
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableAnimation
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableInPlaceEdit
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableScrollButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::GetBorderSize
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::GetVisiblePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::IsAnimation
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::IsMode2003
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowFewerPageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowMorePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowOptions
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetActiveTab
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetBorderSize
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetPageButtonTextAlign
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetToolbarImageList
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetVisiblePageButtons
dev_langs:
- C++
helpviewer_keywords:
- CMFCOutlookBarTabCtrl class
ms.assetid: b1f2b3f7-cc59-49a3-99d8-7ff9b37c044b
caps.latest.revision: 26
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 16de4287a2b3a6352fb4fc560b9c8eec2ba766d1
ms.lasthandoff: 02/25/2017

---
# <a name="cmfcoutlookbartabctrl-class"></a>Classe CMFCOutlookBarTabCtrl
Um que tenha a aparência visual do controle de guia de **painel de navegação** no Microsoft Outlook.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
class CMFCOutlookBarTabCtrl : public CMFCBaseTabCtrl  
```  
  
## <a name="members"></a>Membros  
  
### <a name="public-constructors"></a>Construtores públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|`CMFCOutlookBarTabCtrl::CMFCOutlookBarTabCtrl`|Construtor padrão.|  
|`CMFCOutlookBarTabCtrl::~CMFCOutlookBarTabCtrl`|Destruidor.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CMFCOutlookBarTabCtrl::AddControl](#addcontrol)|Adiciona um controle do Windows como uma nova guia na barra do Outlook.|  
|`CMFCOutlookBarTabCtrl::CalcRectEdit`|Chamado pela estrutura determinar as dimensões da caixa de edição é exibida quando um usuário renomeia uma guia. (Substitui `CMFCBaseTabCtrl::CalcRectEdit`.)|  
|[CMFCOutlookBarTabCtrl::CanShowFewerPageButtons](#canshowfewerpagebuttons)|Chamado pela estrutura durante operações de redimensionamento para determinar se podem ser exibidas menos Outlook guia página botões da barra de que estão visíveis no momento.|  
|[CMFCOutlookBarTabCtrl::CanShowMorePageButtons](#canshowmorepagebuttons)|Chamado pela estrutura durante operações de redimensionamento para determinar se podem ser exibido mais Outlook guia página botões da barra de que estão visíveis no momento.|  
|[CMFCOutlookBarTabCtrl::Create](#create)|Cria o controle de guia de barra do Outlook.|  
|`CMFCOutlookBarTabCtrl::CreateObject`|Usado pelo framework para criar uma instância desse tipo de classe dinâmica.|  
|[CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation)|Especifica se a animação que ocorre durante a alternância entre guias ativos está habilitada.|  
|[CMFCOutlookBarTabCtrl::EnableInPlaceEdit](#enableinplaceedit)|Especifica se um usuário pode modificar os rótulos de texto em botões da guia da barra do Outlook. (Substitui [CMFCBaseTabCtrl::EnableInPlaceEdit](../../mfc/reference/cmfcbasetabctrl-class.md#enableinplaceedit).)|  
|[CMFCOutlookBarTabCtrl::EnableScrollButtons](#enablescrollbuttons)|Chamado pela estrutura para habilitar os botões que permitem que o usuário role por meio de botões no painel da barra do Outlook.|  
|`CMFCOutlookBarTabCtrl::FindTargetWnd`|Identifica o painel que contém um ponto especificado. (Substitui [CMFCBaseTabCtrl::FindTargetWnd](../../mfc/reference/cmfcbasetabctrl-class.md#findtargetwnd).)|  
|[CMFCOutlookBarTabCtrl::GetBorderSize](#getbordersize)|Retorna o tamanho da borda do controle guia Outlook.|  
|`CMFCOutlookBarTabCtrl::GetTabArea`|Recupera o tamanho e a posição da área de guias do controle guia. (Substitui [CMFCBaseTabCtrl::GetTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#gettabarea).)|  
|`CMFCOutlookBarTabCtrl::GetThisClass`|Usado pelo framework para obter um ponteiro para o [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) objeto associado esse tipo de classe.|  
|[CMFCOutlookBarTabCtrl::GetVisiblePageButtons](#getvisiblepagebuttons)||  
|[CMFCOutlookBarTabCtrl::IsAnimation](#isanimation)|Determina se a animação que ocorre durante a alternância entre guias ativos está habilitada.|  
|[CMFCOutlookBarTabCtrl::IsMode2003](#ismode2003)|Determina se o controle de guia de barra do Outlook está em um modo que emula o Microsoft Outlook 2003.|  
|`CMFCOutlookBarTabCtrl::IsPtInTabArea`|Determina se um ponto está dentro da área de guia. (Substitui [CMFCBaseTabCtrl::IsPtInTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#isptintabarea).)|  
|`CMFCOutlookBarTabCtrl::IsTabDetachable`|Determina se uma guia é removível. (Substitui [CMFCBaseTabCtrl::IsTabDetachable](../../mfc/reference/cmfcbasetabctrl-class.md#istabdetachable).)|  
|`CMFCOutlookBarTabCtrl::OnChangeTabs`|Chamado pela estrutura quando uma guia é inserida ou removida. (Substitui `CMFCBaseTabCtrl::OnChangeTabs`.)|  
|[CMFCOutlookBarTabCtrl::OnShowFewerPageButtons](#onshowfewerpagebuttons)|Chamado pela estrutura para diminuir o número de botões de página de guia que são visíveis.|  
|[CMFCOutlookBarTabCtrl::OnShowMorePageButtons](#onshowmorepagebuttons)|Chamado pela estrutura para aumentar o número de botões de página de guia que são visíveis.|  
|[CMFCOutlookBarTabCtrl::OnShowOptions](#onshowoptions)|Exibe o **opções do painel de navegação** caixa de diálogo.|  
|`CMFCOutlookBarTabCtrl::RecalcLayout`|Recalcula o layout interno do controle guia. (Substitui [CMFCBaseTabCtrl::RecalcLayout](../../mfc/reference/cmfcbasetabctrl-class.md#recalclayout).)|  
|[CMFCOutlookBarTabCtrl::SetActiveTab](#setactivetab)|Define a guia ativa. (Substitui [CMFCBaseTabCtrl::SetActiveTab](../../mfc/reference/cmfcbasetabctrl-class.md#setactivetab).)|  
|[CMFCOutlookBarTabCtrl::SetBorderSize](#setbordersize)|Define o tamanho da borda do controle guia Outlook.|  
|[CMFCOutlookBarTabCtrl::SetPageButtonTextAlign](#setpagebuttontextalign)|Define o alinhamento dos rótulos de texto em botões da guia da barra do Outlook.|  
|[CMFCOutlookBarTabCtrl::SetToolbarImageList](#settoolbarimagelist)|Define o bitmap que contém os ícones são exibidos na parte inferior da barra do Outlook no modo do Outlook 2003 (consulte [CMFCOutlookBar classe](../../mfc/reference/cmfcoutlookbar-class.md)).|  
|[CMFCOutlookBarTabCtrl::SetVisiblePageButtons](#setvisiblepagebuttons)||  
  
## <a name="remarks"></a>Comentários  
 Para criar uma barra do Outlook que tem suporte de encaixe, use uma `CMFCOutlookBar` objeto para hospedar o controle de guia da barra do Outlook. Para obter mais informações, consulte [CMFCOutlookBar classe](../../mfc/reference/cmfcoutlookbar-class.md).  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir demonstra como inicializar um `CMFCOutlookBarTabCtrl` de objeto e usar vários métodos no `CMFCOutlookBarTabCtrl` classe. O exemplo mostra como habilitar a edição in-loco do rótulo do texto dos botões da página de guia da barra do Outlook, habilitar a animação, habilitar identificadores de rolagem que permitem que o usuário role por meio de botões no painel da barra do Outlook, defina o tamanho da borda do controle guia Outlook e definir o alinhamento dos rótulos de texto em botões da guia da barra do Outlook. Este trecho de código é parte do [exemplo Outlook demonstração](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_OutlookDemo n º&1;](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_1.cpp)]  
[!code-cpp[NVC_MFC_OutlookDemo n º&2;](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hierarquia de herança  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)  
  
 [CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md)  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** afxoutlookbartabctrl.h  
  
##  <a name="addcontrol"></a>CMFCOutlookBarTabCtrl::AddControl  
 Adiciona um controle do Windows como uma nova guia na barra do Outlook.  
  
```  
void AddControl(
    CWnd* pWndCtrl,  
    LPCTSTR lpszName,  
    int nImageID=-1,  
    BOOL bDetachable=TRUE,  
    DWORD dwControlBarStyle=AFX_CBRS_FLOAT |  AFX_CBRS_CLOSE | AFX_CBRS_RESIZE |  CBRS_AFX_AUTOHIDE);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pWndCtrl`  
 Um ponteiro para um controle a ser adicionado.  
  
 [in] `lpszName`  
 Especifica o nome da guia.  
  
 [in] `bDetachable`  
 Se `TRUE`, a página será criada como removível.  
  
 [in] `nImageID`  
 Índice de imagem na lista de imagens interno para a imagem a ser exibida em uma nova guia.  
  
 [in] `dwControlBarStyle`  
 Especifica o AFX_ `CBRS_`* estilo de painéis de encaixe encapsulados.  
  
### <a name="remarks"></a>Comentários  
 Use esta função para adicionar um controle como uma nova página de uma barra do outlook.  
  
 Essa função chama internamente em [CMFCBaseTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab).  
  
 Se você definir `bDetachable` para `TRUE`, `AddControl` cria internamente uma `CDockablePaneAdapter` de objeto e encapsula o controle adicionado. Define automaticamente a classe de tempo de execução da janela com guias para a classe de tempo de execução de `CMFCOutlookBar` e a classe de tempo de execução do quadro flutuante para `CMultiPaneFrameWnd`.  
  
### <a name="example"></a>Exemplo  
 O exemplo a seguir demonstra como usar o `AddControl` método o `CMFCOutlookBarTabCtrl` classe. Este trecho de código é parte do [exemplo Outlook demonstração](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_OutlookDemo n º&3;](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_3.cpp)]  
  
##  <a name="canshowfewerpagebuttons"></a>CMFCOutlookBarTabCtrl::CanShowFewerPageButtons  
 Chamado pela estrutura durante o redimensionamento de operações para determinar se menos botões da página Outlook barra guia podem ser exibidos de estão visíveis no momento.  
  
```  
virtual BOOL CanShowFewerPageButtons() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se houver mais de um botão. Caso contrário, `FALSE`.  
  
### <a name="remarks"></a>Comentários  
 O controle da guia barra Outlook dinamicamente adiciona ou remove o guias da exibição dependendo de quanto espaço está disponível. Esse método é usado pelo framework para auxiliar nesse processo.  
  
##  <a name="canshowmorepagebuttons"></a>CMFCOutlookBarTabCtrl::CanShowMorePageButtons  
 Chamado pela estrutura durante o redimensionamento de operações para determinar se mais botões da página Outlook barra guia podem ser exibidos de estão visíveis no momento.  
  
```  
virtual BOOL CanShowMorePageButtons() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se houver botões que não são visíveis no momento; Caso contrário, `FALSE`.  
  
### <a name="remarks"></a>Comentários  
 O controle da guia barra Outlook dinamicamente adiciona ou remove o guias da exibição, dependendo de quanto espaço está disponível. Esse método é usado pelo framework para auxiliar nesse processo.  
  
##  <a name="create"></a>CMFCOutlookBarTabCtrl::Create  
 Cria o controle de guia de barra do Outlook.  
  
```  
virtual BOOL Create(
    const CRect& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `rect`  
 Especifica o tamanho inicial e a posição, em pixels.  
  
 [in] `pParentWnd`  
 Aponta para a janela pai. Não deve ser `NULL`.  
  
 [in] `nID`  
 A ID do controle.  
  
### <a name="return-value"></a>Valor de retorno  
 Diferente de zero se o controle foi criado com êxito; Caso contrário, 0.  
  
### <a name="remarks"></a>Comentários  
 Geralmente, controles de guia de barra do outlook são criados quando [CMFCOutlookBar classe](../../mfc/reference/cmfcoutlookbar-class.md) controles a `WM_CREATE` mensagem do processo.  
  
##  <a name="enableanimation"></a>CMFCOutlookBarTabCtrl::EnableAnimation  
 Especifica se a animação que ocorre durante a alternância entre guias ativos está habilitada.  
  
```  
static void EnableAnimation(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `bEnable`  
 Especifica se a animação deve ser habilitada ou desabilitada.  
  
### <a name="remarks"></a>Comentários  
 Chame essa função para ativar e desativar a animação. Quando o usuário abre uma página da guia, legenda da página desliza para cima ou para baixo se a animação está habilitada. Se a animação é desabilitada, a página se torna ativa imediatamente.  
  
 Por padrão, a animação está habilitada.  
  
##  <a name="enableinplaceedit"></a>CMFCOutlookBarTabCtrl::EnableInPlaceEdit  
 Especifica se um usuário pode modificar os rótulos de texto em botões da página da guia da barra do Outlook.  
  
```  
virtual void EnableInPlaceEdit(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parâmetros  
 `bEnable`  
 Se `TRUE`, habilitar a edição in-loco do rótulo do texto. Se `FALSE`, desabilite a edição in-loco.  
  
### <a name="remarks"></a>Comentários  
 Chame essa função para ativar ou desativar a edição in-loco dos rótulos de texto em botões da página de guia. A edição in-loco é desabilitado por padrão.  
  
##  <a name="enablescrollbuttons"></a>CMFCOutlookBarTabCtrl::EnableScrollButtons  
 Chamado pela estrutura para habilitar identificadores de rolagem que permitem que o usuário role por meio de botões no painel da barra do Outlook.  
  
```  
void EnableScrollButtons(
    BOOL bEnable = TRUE,  
    BOOL bIsUp = TRUE,  
    BOOL bIsDown = TRUE);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `bEnable`  
 Determina se os botões de rolagem são exibidos.  
  
 [in] `bIsUp`  
 Determina se a barra de rolagem superior é exibida.  
  
 [in] `bIsDown`  
 Determina se a barra de rolagem inferior é exibida.  
  
### <a name="remarks"></a>Comentários  
 Permite a exibição dos botões de rolagem. Esse método é chamado pela estrutura quando altera a guia ativa para restaurar os botões de rolagem.  
  
##  <a name="getbordersize"></a>CMFCOutlookBarTabCtrl::GetBorderSize  
 Retorna o tamanho da borda do controle guia Outlook.  
  
```  
int GetBorderSize() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 O tamanho da borda, em pixels.  
  
##  <a name="getvisiblepagebuttons"></a>CMFCOutlookBarTabCtrl::GetVisiblePageButtons  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetVisiblePageButtons() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="isanimation"></a>CMFCOutlookBarTabCtrl::IsAnimation  
 Especifica se a animação que ocorre durante a alternância entre guias ativos está habilitada.  
  
```  
static BOOL IsAnimation();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Diferente de zero se a animação estiver habilitada; Caso contrário, 0.  
  
### <a name="remarks"></a>Comentários  
 Chamar o [CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation) função para habilitar ou desabilitar a animação.  
  
##  <a name="ismode2003"></a>CMFCOutlookBarTabCtrl::IsMode2003  
 Determina se o controle de guia de barra do Outlook está em um modo que emula o Microsoft Outlook 2003.  
  
```  
BOOL IsMode2003() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se a barra de controle guia do Outlook estiver no modo do Outlook 2003; Caso contrário, `FALSE`;  
  
### <a name="remarks"></a>Comentários  
 Esse valor é definido [CMFCOutlookBar::SetMode2003](../../mfc/reference/cmfcoutlookbar-class.md#setmode2003).  
  
##  <a name="onshowfewerpagebuttons"></a>CMFCOutlookBarTabCtrl::OnShowFewerPageButtons  
 Chamado pela estrutura para diminuir o número de botões de página de guia que são visíveis.  
  
```  
virtual void OnShowFewerPageButtons();
```  
  
### <a name="remarks"></a>Comentários  
 Esse método ajusta o número de botões da guia de página visível quando o controle é redimensionado.  
  
##  <a name="onshowmorepagebuttons"></a>CMFCOutlookBarTabCtrl::OnShowMorePageButtons  
 Chamado pela estrutura para aumentar o número de botões de página de guia que são visíveis.  
  
```  
virtual void OnShowMorePageButtons();
```  
  
### <a name="remarks"></a>Comentários  
 Esse método ajustar o número de botões de página de guia que são visíveis quando o controle é redimensionado.  
  
##  <a name="onshowoptions"></a>CMFCOutlookBarTabCtrl::OnShowOptions  
 Exibe o **opções do painel de navegação** caixa de diálogo.  
  
```  
virtual void OnShowOptions();
```  
  
### <a name="remarks"></a>Comentários  
 O **opções do painel de navegação** caixa de diálogo permite que o usuário selecione os botões de página de guia devem ser exibidas e a ordem na qual elas são exibidas.  
  
 Este método é chamado pela estrutura quando o usuário seleciona o **opções do painel de navegação** item de menu no menu de personalização do controle.  
  
##  <a name="setactivetab"></a>CMFCOutlookBarTabCtrl::SetActiveTab  
 Define a guia ativa. A guia ativa é aquela que é aberta, com o conteúdo visível.  
  
```  
virtual BOOL SetActiveTab(int iTab);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `iTab`  
 O índice com base em zero de uma guia a ser aberto.  
  
### <a name="return-value"></a>Valor de retorno  
 Diferente de zero se a guia especificada foi aberta com êxito; Caso contrário, 0.  
  
### <a name="remarks"></a>Comentários  
 O efeito visual da configuração na guia active depende de você ter habilitado a animação. Para obter mais informações, consulte [CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation).  
  
##  <a name="setbordersize"></a>CMFCOutlookBarTabCtrl::SetBorderSize  
 Define o tamanho da borda do controle guia Outlook.  
  
```  
void SetBorderSize(int nBorderSize);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `nBorderSize`  
 Especifica o novo tamanho da borda em pixels.  
  
### <a name="remarks"></a>Comentários  
 Define o novo tamanho da borda e recalcula o layout de janela do outlook.  
  
##  <a name="setpagebuttontextalign"></a>CMFCOutlookBarTabCtrl::SetPageButtonTextAlign  
 Define o alinhamento dos rótulos de texto em botões da guia da barra do Outlook.  
  
```  
void SetPageButtonTextAlign(
    UINT uiAlign,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `uiAlign`  
 Especifica o alinhamento de texto.  
  
 [in] `bRedraw`  
 Se `TRUE`, a janela do outlook será redesenhada.  
  
### <a name="remarks"></a>Comentários  
 Use esta função para alterar o alinhamento de texto para botões da página.  
  
 `uiAlign`pode ser um dos seguintes valores:  
  
|Constante|Significado|  
|--------------|-------------|  
|TA_LEFT|Alinhamento à esquerda|  
|TA_CENTER|Alinhamento centralizado|  
|TA_RIGHT|Alinhamento à direita|  
  
 O valor padrão é TA_CENTER.  
  
##  <a name="settoolbarimagelist"></a>CMFCOutlookBarTabCtrl::SetToolbarImageList  
 Define o bitmap que contém os ícones são exibidos na parte inferior da barra do Outlook no modo do Outlook 2003.  
  
```  
BOOL SetToolbarImageList(
    UINT uiID,  
    int cx,  
    COLORREF clrTransp=RGB(255, 0, 255));
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `uiID`  
 Especifica a ID de recurso da imagem para carregar.  
  
 [in] `cx`  
 Especifica a largura de uma imagem na lista de imagens, em pixels.  
  
 [in] `clrTransp`  
 Um valor RGB que especifica a cor transparente.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna `TRUE` se for bem-sucedido; caso contrário, retornará `FALSE`.  
  
### <a name="remarks"></a>Comentários  
 Use esta função para anexar uma lista de imagens cujas imagens serão exibidas nos botões da barra de ferramentas no modo do Microsoft Office 2003. Índices de imagem devem corresponder a índices de página.  
  
 Esse método não deve ser chamado se não estiver no modo do Microsoft Office 2003. Para obter mais informações, consulte [CMFCOutlookBar classe](../../mfc/reference/cmfcoutlookbar-class.md).  
  
##  <a name="setvisiblepagebuttons"></a>CMFCOutlookBarTabCtrl::SetVisiblePageButtons  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetVisiblePageButtons(int nVisiblePageButtons);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `nVisiblePageButtons`  
  
### <a name="remarks"></a>Comentários  
  
## <a name="see-also"></a>Consulte também  
 [Gráfico de hierarquia](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [Classe CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)   
 [Classe CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)   
 [Classe CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md)
