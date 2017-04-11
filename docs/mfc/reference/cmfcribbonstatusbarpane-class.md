---
title: Classe CMFCRibbonStatusBarPane | Documentos do Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsExtended
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnDrawBorder
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFillBackground
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAnimationList
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StartAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StopAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFinishAnimation
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonStatusBarPane class
ms.assetid: 5d034c3c-ecca-4267-b88c-0f55a2884dd0
caps.latest.revision: 31
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
ms.openlocfilehash: a101e50f55efab44e4cb66d314b2426228dbc5c0
ms.lasthandoff: 02/25/2017

---
# <a name="cmfcribbonstatusbarpane-class"></a>Classe CMFCRibbonStatusBarPane
O `CMFCRibbonStatusBarPane` classe implementa um elemento de faixa de opções que você pode adicionar a uma barra de status da faixa de opções.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
class CMFCRibbonStatusBarPane : public CMFCRibbonButton  
```  
  
## <a name="members"></a>Membros  
  
### <a name="public-constructors"></a>Construtores públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane](#cmfcribbonstatusbarpane)|Constrói e inicializa um objeto `CMFCRibbonStatusBarPane`.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::GetAlmostLargeText](#getalmostlargetext)|Retorna a cadeia de caracteres que define a cadeia de caracteres de texto mais longa que pode ser exibida no painel sem truncamento.|  
|[CMFCRibbonStatusBarPane::GetTextAlign](#gettextalign)|Retorna a configuração atual do alinhamento de texto.|  
|[CMFCRibbonStatusBarPane::IsAnimation](#isanimation)|Determina se a animação está em andamento.|  
|[CMFCRibbonStatusBarPane::IsExtended](#isextended)|Determina se o painel está localizado na área estendida da barra de status da faixa de opções.|  
|[CMFCRibbonStatusBarPane::OnDrawBorder](#ondrawborder)|(Substitui [CMFCRibbonButton::OnDrawBorder](../../mfc/reference/cmfcribbonbutton-class.md#ondrawborder).)|  
|[CMFCRibbonStatusBarPane::OnFillBackground](#onfillbackground)|(Substitui [CMFCRibbonButton::OnFillBackground](../../mfc/reference/cmfcribbonbutton-class.md#onfillbackground).)|  
|[CMFCRibbonStatusBarPane::SetAlmostLargeText](#setalmostlargetext)|Define a cadeia de caracteres de texto mais longa que pode ser exibida no painel sem truncamento.|  
|[CMFCRibbonStatusBarPane::SetAnimationList](#setanimationlist)|Atribui uma lista de imagens que pode ser usada para animação ao painel.|  
|[CMFCRibbonStatusBarPane::SetTextAlign](#settextalign)|Define o alinhamento do texto.|  
|[CMFCRibbonStatusBarPane::StartAnimation](#startanimation)|Inicia a animação que é atribuída ao painel.|  
|[CMFCRibbonStatusBarPane::StopAnimation](#stopanimation)|Interrompe a animação que é atribuída ao painel. .|  
  
### <a name="protected-methods"></a>Métodos Protegidos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CMFCRibbonStatusBarPane::OnFinishAnimation](#onfinishanimation)|Chamado pela estrutura quando parar a animação que é atribuída ao painel.|  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir demonstra como usar os vários métodos na `CMFCRibbonStatusBarPane` classe. O exemplo mostra como construir um `CMFCRibbonStatusBarPane` de objeto, definir o alinhamento do texto do rótulo do painel da barra de status, defina o texto mais longo que pode ser exibida no painel da barra de status sem truncamento, anexar uma lista de imagens que pode ser usada para animação e iniciar a animação no painel de barra de status.  
  
 [!code-cpp[NVC_MFC_RibbonApp n º&2;](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbarpane-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hierarquia de herança  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonStatusBarPane](../../mfc/reference/cmfcribbonstatusbarpane-class.md)  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** afxribbonstatusbarpane.h  
  
##  <a name="cmfcribbonstatusbarpane"></a>CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane  
 Construa um objeto de painel na barra de status.  
  
```  
CMFCRibbonStatusBarPane(
    UINT nCmdID,  
    LPCTSTR lpszText,  
    BOOL bIsStatic=FALSE,  
    HICON hIcon=NULL,  
    LPCTSTR lpszAlmostLargeText=NULL);

CMFCRibbonStatusBarPane(
    UINT nCmdID,  
    LPCTSTR lpszText,  
    HBITMAP hBmpAnimationList,  
    int cxAnimation=16,  
    COLORREF clrTrnsp=RGB(192,192 1,192) 1,  
    HICON hIcon=NULL,  
    BOOL bIsStatic=FALSE);

CMFCRibbonStatusBarPane(
    UINT nCmdID,  
    LPCTSTR lpszText,  
    UINT uiAnimationListResID,  
    int cxAnimation=16,  
    COLORREF clrTrnsp=RGB(192, 192 1, 192) 1,  
    HICON hIcon=NULL,  
    BOOL bIsStatic=FALSE);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `nCmdID`  
 Especifica a ID de comando do painel.  
  
 [in] `lpszText`  
 Especifica a cadeia de caracteres de texto a ser exibido no painel.  
  
 [in] `bIsStatic`  
 Se `TRUE`, o painel de status não pode ser realçado ou selecionado clicando nele.  
  
 [in] `hIcon`  
 Especifica um identificador para um ícone a ser exibido no painel.  
  
 [in] `lpszAlmostLargeText`  
 Especifica a cadeia de caracteres de texto mais longa que pode ser exibida pelo painel.  
  
 [in] `hBmpAnimationList`  
 Especifica um identificador para uma lista de imagens é usado para animação.  
  
 [in] `cxAnimation`  
 Especifica a largura, em pixels, do ícone na lista de imagens é usado para animação.  
  
 [in] `clrTrnsp`  
 Especifica a cor transparente da imagens na lista de imagens que são usadas para animação.  
  
 [in] `uiAnimationListResID`  
 Especifica uma ID de recurso de uma lista de imagens é usada para animação.  
  
##  <a name="getalmostlargetext"></a>CMFCRibbonStatusBarPane::GetAlmostLargeText  
 Obtém a cadeia de caracteres de texto mais longa que pode exibir o painel da barra de status.  
  
```  
LPCTSTR GetAlmostLargeText() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 A cadeia de texto mais longa que pode exibir o painel da barra de status.  
  
##  <a name="gettextalign"></a>CMFCRibbonStatusBarPane::GetTextAlign  
 Obtém a configuração atual do alinhamento do texto do rótulo do painel da barra de status.  
  
```  
int GetTextAlign() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 O alinhamento de texto atual que pode ser um dos seguintes:  
  
-   TA_LEFT  
  
-   TA_CENTER  
  
-   TA_RIGHT.  
  
##  <a name="isanimation"></a>CMFCRibbonStatusBarPane::IsAnimation  
 Determina se a animação está em andamento.  
  
```  
BOOL IsAnimation() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se a animação está em andamento. `FALSE` caso contrário.  
  
##  <a name="isextended"></a>CMFCRibbonStatusBarPane::IsExtended  
 Determine se o painel está localizado na área estendida da barra de status da faixa de opções.  
  
```  
BOOL IsExtended() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se o painel está na área estendida da barra de status. `FALSE`Caso contrário.  
  
##  <a name="ondrawborder"></a>CMFCRibbonStatusBarPane::OnDrawBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawBorder(CDC*);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `CDC*`  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="onfillbackground"></a>CMFCRibbonStatusBarPane::OnFillBackground  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF OnFillBackground(CDC* pDC);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pDC`  
  
### <a name="return-value"></a>Valor de retorno  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="onfinishanimation"></a>CMFCRibbonStatusBarPane::OnFinishAnimation  
 Framework chama esse método quando termina a animação que é atribuída ao painel.  
  
```  
virtual void OnFinishAnimation();
```  
  
### <a name="remarks"></a>Comentários  
 `StopAnimation`chamadas de método de `OnFinishAnimation` método, que você pode usar para limpar os dados quando a animação termina.  
  
##  <a name="setalmostlargetext"></a>CMFCRibbonStatusBarPane::SetAlmostLargeText  
 Defina o texto mais longo que pode ser exibido no painel de barra de status sem truncamento.  
  
```  
void SetAlmostLargeText(LPCTSTR lpszAlmostLargeText);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `lpszAlmostLargeText`  
 Especifica a cadeia de caracteres mais longa que pode ser exibida no painel de barra de status sem truncamento.  
  
### <a name="remarks"></a>Comentários  
 A biblioteca calcula o tamanho do texto que `lpszAlmostLargeText` Especifica e redimensiona o painel de acordo. O texto será truncado se ele ainda não couber no painel.  
  
##  <a name="setanimationlist"></a>CMFCRibbonStatusBarPane::SetAnimationList  
 Anexa uma lista de imagens que pode ser usada para animação para o painel da barra de status.  
  
```  
void SetAnimationList(
    HBITMAP hBmpAnimationList,  
    int cxAnimation=16,  
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);

BOOL SetAnimationList(
    UINT uiAnimationListResID,  
    int cxAnimation=16,  
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `hBmpAnimationList`  
 Especifica um identificador para uma lista de imagens.  
  
 [in] `cxAnimation`  
 Especifica a largura, em pixels, do quadro na lista de imagens.  
  
 [in] `clrTransp`  
 Especifica a cor transparente da lista de imagens.  
  
 [in] `uiAnimationListResID`  
 Especifica a ID de recurso da lista de imagens.  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se a lista de imagens foi anexada com êxito para o painel da barra de status; `FALSE` caso contrário.  
  
##  <a name="settextalign"></a>CMFCRibbonStatusBarPane::SetTextAlign  
 Define o alinhamento do texto do rótulo do painel da barra de status.  
  
```  
void SetTextAlign(int nAlign);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `nAlign`  
 Especifica o alinhamento de texto.  
  
### <a name="remarks"></a>Comentários  
 `nAlign`pode ter um dos seguintes valores:  
  
- `TA_LEFT`: à esquerda  
  
- `TA_CENTER:`alinhamento centralizado  
  
- `TA_RIGHT:`alinhamento à direita  
  
##  <a name="startanimation"></a>CMFCRibbonStatusBarPane::StartAnimation  
 Inicia a animação que você atribui ao painel.  
  
```  
void StartAnimation(
    UINT nFrameDelay=500,  
    UINT nDuration=-1);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `nFrameDelay`  
 Especifica a taxa de quadros de animação, em milissegundos.  
  
 [in] `nDuration`  
 Especifica quanto tempo para reproduzir a animação, em milissegundos. Use -1 para um loop infinito.  
  
### <a name="remarks"></a>Comentários  
 Você deve especificar um identificador para uma lista de imagens antes de chamar `StartAnimation` usando `SetAnimationList`.  
  
##  <a name="stopanimation"></a>CMFCRibbonStatusBarPane::StopAnimation  
 Interrompe a animação que você atribuiu ao painel da barra de status.  
  
```  
void StopAnimation();
```  
  
## <a name="see-also"></a>Consulte também  
 [Gráfico de hierarquia](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [Classe CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)   
 [Classe CMFCRibbonStatusBar](../../mfc/reference/cmfcribbonstatusbar-class.md)
