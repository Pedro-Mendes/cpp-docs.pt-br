---
title: Classe CComControl | Documentos do Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComControl
- ATLCTL/ATL::CComControl
- ATLCTL/ATL::CComControl::CComControl
- ATLCTL/ATL::CComControl::ControlQueryInterface
- ATLCTL/ATL::CComControl::CreateControlWindow
- ATLCTL/ATL::CComControl::FireOnChanged
- ATLCTL/ATL::CComControl::FireOnRequestEdit
- ATLCTL/ATL::CComControl::MessageBox
dev_langs:
- C++
helpviewer_keywords:
- control flags
- CComControlBase class, CComControl class
- stock properties, ATL
- CComControl class
- controls [ATL], control helper functions
- ambient properties
- controls [ATL], properties
ms.assetid: 55368c27-bd16-45a7-b701-edb36157c8e8
caps.latest.revision: 22
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
ms.openlocfilehash: 387d38f89e8d783c7ae85c2ab960d5e59c1c4009
ms.lasthandoff: 02/25/2017

---
# <a name="ccomcontrol-class"></a>Classe CComControl
Essa classe fornece métodos para criar e gerenciar controles da ATL.  
  
> [!IMPORTANT]
>  Essa classe e seus membros não podem ser usados em aplicativos executados no tempo de execução do Windows.  
  
## <a name="syntax"></a>Sintaxe  
  
```
template <class T, class WinBase = CWindowImpl<T>>  
class ATL_NO_VTABLE CComControl : public CComControlBase,
    public WinBase;
```  
  
#### <a name="parameters"></a>Parâmetros  
 `T`  
 A classe de implementação do controle.  
  
 *WinBase*  
 A classe base que implementa funções em janela. O padrão é [CWindowImpl](../../atl/reference/cwindowimpl-class.md).  
  
## <a name="members"></a>Membros  
  
### <a name="public-constructors"></a>Construtores públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CComControl::CComControl](#ccomcontrol)|Construtor.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CComControl::ControlQueryInterface](#controlqueryinterface)|Recupera um ponteiro para a interface solicitada.|  
|[CComControl::CreateControlWindow](#createcontrolwindow)|Cria uma janela para o controle.|  
|[CComControl::FireOnChanged](#fireonchanged)|Notifica o coletor do contêiner que uma propriedade de controle mudou.|  
|[CComControl::FireOnRequestEdit](#fireonrequestedit)|Notifica o coletor do contêiner que uma propriedade de controle está prestes a ser alterada e que o objeto está solicitando o coletor como proceder.|  
|[CComControl::MessageBox](#messagebox)|Chame esse método para criar, exibir e operar uma caixa de mensagem.|  
  
## <a name="remarks"></a>Comentários  
 `CComControl`é um conjunto de funções de auxiliar de controle útil e membros de dados essenciais para controles da ATL. Quando você cria um controle padrão ou um controle DHTML usando o Assistente de controle ATL, o assistente automaticamente irá derivar a classe de `CComControl`. `CComControl`deriva a maioria de seus métodos de [CComControlBase](../../atl/reference/ccomcontrolbase-class.md).  
  
 Para obter mais informações sobre como criar um controle, consulte o [Tutorial da ATL](../../atl/active-template-library-atl-tutorial.md). Para obter mais informações sobre os ATL Project Wizard, consulte o artigo [criando um projeto ATL](../../atl/reference/creating-an-atl-project.md).  
  
 Para uma demonstração de `CComControl` métodos e membros de dados, consulte o [c](../../visual-cpp-samples.md) exemplo.  
  
## <a name="inheritance-hierarchy"></a>Hierarquia de herança  
 `WinBase`  
  
 [CComControlBase](../../atl/reference/ccomcontrolbase-class.md)  
  
 `CComControl`  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** atlctl.h  
  
##  <a name="ccomcontrol"></a>CComControl::CComControl  
 O construtor.  
  
```
CComControl();
```  
  
### <a name="remarks"></a>Comentários  
 Chamadas de [CComControlBase](ccomcontrolbase-class.md#ccomcontrolbase) construtor, passando o `m_hWnd` herdado do membro de dados [CWindowImpl](../../atl/reference/cwindowimpl-class.md).  
  
##  <a name="controlqueryinterface"></a>CComControl::ControlQueryInterface  
 Recupera um ponteiro para a interface solicitada.  
  
```
virtual HRESULT ControlQueryInterface(const IID& iid, void** ppv);
```  
  
### <a name="parameters"></a>Parâmetros  
 `iid`  
 [in] O GUID da interface que está sendo solicitado.  
  
 `ppv`  
 [out] Um ponteiro para o ponteiro de interface identificado pelo `iid`, ou **nulo** se a interface não for encontrada.  
  
### <a name="remarks"></a>Comentários  
 Apenas lida com interfaces na tabela de mapa COM.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_COM&15;](../../atl/codesnippet/cpp/ccomcontrol-class_1.cpp)]  
  
##  <a name="createcontrolwindow"></a>CComControl::CreateControlWindow  
 Por padrão, cria uma janela para o controle chamando `CWindowImpl::Create`.  
  
```
virtual HWND CreateControlWindow(HWND hWndParent, RECT& rcPos);
```  
  
### <a name="parameters"></a>Parâmetros  
 `hWndParent`  
 [in] Identificador para a janela pai ou proprietário. Um identificador de janela válido deve ser fornecido. A janela de controle é restrito para a área da sua janela pai.  
  
 `rcPos`  
 [in] O tamanho inicial e a posição da janela a ser criado.  
  
### <a name="remarks"></a>Comentários  
 Substituir esse método se você deseja fazer algo diferente de criar uma única janela, por exemplo, para criar duas janelas, uma das quais se torna uma barra de ferramentas para o seu controle.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_COM N º&16;](../../atl/codesnippet/cpp/ccomcontrol-class_2.cpp)]  
  
##  <a name="fireonchanged"></a>CComControl::FireOnChanged  
 Notifica o coletor do contêiner que uma propriedade de controle mudou.  
  
```
HRESULT FireOnChanged(DISPID dispID);
```  
  
### <a name="parameters"></a>Parâmetros  
 *dispID*  
 [in] Identificador da propriedade que foi alterada.  
  
### <a name="return-value"></a>Valor de retorno  
 Um dos valores HRESULT padrão.  
  
### <a name="remarks"></a>Comentários  
 Se sua classe de controle deriva de [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638), esse método chama [CFirePropNotifyEvent::FireOnChanged](cfirepropnotifyevent-class.md#fireonchanged) notificar todos conectados `IPropertyNotifySink` interfaces que alterou a propriedade do controle especificado. Se sua classe de controle deriva de `IPropertyNotifySink`, esse método retornará `S_OK`. 
  
 Esse método é seguro chamar o mesmo que o controle não oferece suporte a pontos de conexão.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_COM&17;](../../atl/codesnippet/cpp/ccomcontrol-class_3.cpp)]  
  
##  <a name="fireonrequestedit"></a>CComControl::FireOnRequestEdit  
 Notifica o coletor do contêiner que uma propriedade de controle está prestes a ser alterada e que o objeto está solicitando o coletor como proceder.  
  
```
HRESULT FireOnRequestEdit(DISPID dispID);
```  
  
### <a name="parameters"></a>Parâmetros  
 *dispID*  
 [in] Identificador da propriedade prestes a ser alterada.  
  
### <a name="return-value"></a>Valor de retorno  
 Um dos valores HRESULT padrão.  
  
### <a name="remarks"></a>Comentários  
 Se sua classe de controle deriva de [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638), esse método chama [CFirePropNotifyEvent::FireOnRequestEdit](cfirepropnotifyevent-class.md#fireonrequestedit) notificar todos conectados `IPropertyNotifySink` interfaces que a propriedade do controle especificado está prestes a alterar. Se sua classe de controle deriva de `IPropertyNotifySink`, esse método retornará `S_OK`.  

  
 Esse método é seguro chamar o mesmo que o controle não oferece suporte a pontos de conexão.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_COM N º&18;](../../atl/codesnippet/cpp/ccomcontrol-class_4.cpp)]  
  
##  <a name="messagebox"></a>CComControl::MessageBox  
 Chame esse método para criar, exibir e operar uma caixa de mensagem.  
  
```
int MessageBox(
    LPCTSTR lpszText,
    LPCTSTR lpszCaption = _T(""),
    UINT nType = MB_OK);
```  
  
### <a name="parameters"></a>Parâmetros  
 `lpszText`  
 O texto a ser exibido na caixa de mensagem.  
  
 `lpszCaption`  
 Título da caixa de diálogo. Se NULL (padrão), o título "Error" é usado.  
  
 `nType`  
 Especifica o conteúdo e o comportamento da caixa de diálogo. Consulte o [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) entrada do [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] documentação para obter uma lista de caixas de mensagem diferentes disponíveis. O padrão fornece uma simples **Okey** botão.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna um valor inteiro especificando um dos valores de item de menu listados em [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) no [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] documentação.  
  
### <a name="remarks"></a>Comentários  
 `MessageBox`é útil durante o desenvolvimento e como uma maneira fácil de exibir uma mensagem de erro ou aviso para o usuário.  
  
## <a name="see-also"></a>Consulte também  
 [Classe CWindowImpl](../../atl/reference/cwindowimpl-class.md)   
 [Visão geral da classe](../../atl/atl-class-overview.md)   
 [Classe CComControlBase](../../atl/reference/ccomcontrolbase-class.md)   
 [Classe CComCompositeControl](../../atl/reference/ccomcompositecontrol-class.md)
