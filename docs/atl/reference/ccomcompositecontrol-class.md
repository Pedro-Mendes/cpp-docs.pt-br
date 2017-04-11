---
title: Classe CComCompositeControl | Documentos do Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComCompositeControl
- ATLCTL/ATL::CComCompositeControl
- ATLCTL/ATL::CComCompositeControl::CComCompositeControl
- ATLCTL/ATL::CComCompositeControl::AdviseSinkMap
- ATLCTL/ATL::CComCompositeControl::CalcExtent
- ATLCTL/ATL::CComCompositeControl::Create
- ATLCTL/ATL::CComCompositeControl::CreateControlWindow
- ATLCTL/ATL::CComCompositeControl::SetBackgroundColorFromAmbient
- ATLCTL/ATL::CComCompositeControl::m_hbrBackground
- ATLCTL/ATL::CComCompositeControl::m_hWndFocus
dev_langs:
- C++
helpviewer_keywords:
- CComCompositeControl class
- composite controls, CComCompositeControl class
ms.assetid: 1304b931-27e8-4fbc-be8e-bb226ad887fb
caps.latest.revision: 21
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
ms.openlocfilehash: ab99b8682e8b529cc124fbda1e6facaac48d0927
ms.lasthandoff: 02/25/2017

---
# <a name="ccomcompositecontrol-class"></a>Classe CComCompositeControl
Essa classe fornece os métodos necessários para implementar um controle composto.  
  
> [!IMPORTANT]
>  Essa classe e seus membros não podem ser usados em aplicativos executados no tempo de execução do Windows.  
  
## <a name="syntax"></a>Sintaxe  
  
```
template <class T>  
class CComCompositeControl : public CComControl<T,CAxDialogImpl<T>>
```  
  
#### <a name="parameters"></a>Parâmetros  
 `T`  
 Sua classe derivada de [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) ou [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), bem como de outras interfaces que você deseja oferecer suporte para o controle composto.  
  
## <a name="members"></a>Membros  
  
### <a name="public-constructors"></a>Construtores públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CComCompositeControl::CComCompositeControl](#ccomcompositecontrol)|O construtor.|  
|[CComCompositeControl:: ~ CComCompositeControl](#dtor)|O destruidor.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CComCompositeControl::AdviseSinkMap](#advisesinkmap)|Chame esse método para recomendar ou não recomendar a todos os controles hospedados pelo controle composto.|  
|[CComCompositeControl::CalcExtent](#calcextent)|Chame esse método para calcular o tamanho em **HIMETRIC** unidades do recurso da caixa de diálogo usada para hospedar o controle composto.|  
|[CComCompositeControl::Create](#create)|Este método é chamado para criar a janela de controle para o controle composto.|  
|[CComCompositeControl::CreateControlWindow](#createcontrolwindow)|Chame esse método para criar a janela de controle e aconselha qualquer controle hospedado.|  
|[CComCompositeControl::SetBackgroundColorFromAmbient](#setbackgroundcolorfromambient)|Chame esse método para definir a cor de plano de fundo do controle composto usando a cor de plano de fundo do contêiner.|  
  
### <a name="public-data-members"></a>Membros de Dados Públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CComCompositeControl::m_hbrBackground](#m_hbrbackground)|O pincel do plano de fundo.|  
|[CComCompositeControl::m_hWndFocus](#m_hwndfocus)|O identificador da janela que tem o foco no momento.|  
  
## <a name="remarks"></a>Comentários  
 Classes derivadas da classe `CComCompositeControl` herdar a funcionalidade de um controle composto do ActiveX. Controles ActiveX derivados de `CComCompositeControl` são hospedados por uma caixa de diálogo padrão. Esses tipos de controles são chamados controles compostos porque eles são capazes de hospedar outros controles (controles nativos do Windows e controles ActiveX).  
  
 `CComCompositeControl`identifica o recurso da caixa de diálogo para usar na criação do controle composto procurando um membro de dados enumerados na classe filha. O membro IDD dessa classe filho é definido como a ID de recurso do recurso da caixa de diálogo que será usado como a janela do controle. A seguir está um exemplo do membro de dados que a classe derivada de `CComCompositeControl` deve conter para identificar o recurso a ser usado para a janela do controle de caixa de diálogo:  
  
 [!code-cpp[NVC_ATL_COM&13;](../../atl/codesnippet/cpp/ccomcompositecontrol-class_1.h)]  
  
> [!NOTE]
>  Controles compostos são sempre controles em janelas, embora possam conter controles sem janelas.  
  
 Um controle implementado por um `CComCompositeControl`-classe derivada tem padrão tabulações comportamento interno. Quando o controle recebe o foco está sendo com guias para um aplicativo que contém, sucessivamente pressionando a tecla TAB fará com que o foco a ser alternado em todos os controles do controle composto independente, em seguida, fora do controle composto e para o próximo item na ordem de tabulação do contêiner. A ordem de tabulação dos controles hospedados é determinada pelo recurso de caixa de diálogo e determina a ordem na qual a tabulação ocorrerá.  
  
> [!NOTE]
>  Para que funcione corretamente com os aceleradores um `CComCompositeControl`, é necessário carregar uma tabela de aceleradores, como o controle é criado, passar o identificador e o número de aceleradores no [IOleControlImpl::GetControlInfo](../../atl/reference/iolecontrolimpl-class.md#getcontrolinfo)e finalmente destruir a tabela quando o controle for lançado.  
  
## <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_COM&#14;](../../atl/codesnippet/cpp/ccomcompositecontrol-class_2.h)]  
  
## <a name="inheritance-hierarchy"></a>Hierarquia de herança  
 `WinBase`  
  
 [CComControlBase](../../atl/reference/ccomcontrolbase-class.md)  
  
 [CComControl](../../atl/reference/ccomcontrol-class.md)  
  
 `CComCompositeControl`  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** atlctl.h  
  
##  <a name="advisesinkmap"></a>CComCompositeControl::AdviseSinkMap  
 Chame esse método para recomendar ou não recomendar a todos os controles hospedados pelo controle composto.  
  
```
HRESULT AdviseSinkMap(bool bAdvise);
```  
  
### <a name="parameters"></a>Parâmetros  
 `bAdvise`  
 True se todos os controles estão ser notificado; Caso contrário, false.  
  
### <a name="return-value"></a>Valor de retorno  
 `S_OK`  
 Todos os controles no evento mapa coletor foram conectado ou desconectado da fonte de evento com êxito.  
  
 **E_FAIL**  
 Nem todos os controles no evento mapa coletor pode ser conectado ou desconectado da fonte de evento com êxito.  
  
 `E_POINTER`  
 Esse erro geralmente indica um problema com uma entrada no mapa de coletor de eventos do controle ou um problema com um argumento de modelo usado em uma `IDispEventImpl` ou `IDispEventSimpleImpl` classe base.  
  
 **CONNECT_E_ADVISELIMIT**  
 O ponto de conexão já atingiu o limite de conexões e não pode aceitar mais.  
  
 **CONNECT_E_CANNOTCONNECT**  
 O coletor não suporta a interface necessária por esse ponto de conexão.  
  
 **CONNECT_E_NOCONNECTION**  
 O valor do cookie não representa uma conexão válida. Esse erro geralmente indica um problema com uma entrada no mapa de coletor de eventos do controle ou um problema com um argumento de modelo usado em uma `IDispEventImpl` ou `IDispEventSimpleImpl` classe base.  
  
### <a name="remarks"></a>Comentários  
 A implementação base desse método pesquisa as entradas de eventos mapa coletor. Em seguida, ele avisa ou unadvises os pontos de conexão para os objetos descritos pelas entradas de coletor do mapa de coletor de evento. Esse método de membro também se baseia no fato de que a classe derivada herda de uma instância de `IDispEventImpl` para cada controle no mapa coletor a ser aconselhável ou unadvised.  
  
##  <a name="calcextent"></a>CComCompositeControl::CalcExtent  
 Chame esse método para calcular o tamanho em **HIMETRIC** unidades do recurso da caixa de diálogo usada para hospedar o controle composto.  
  
```
BOOL CalcExtent(SIZE& size);
```  
  
### <a name="parameters"></a>Parâmetros  
 `size`  
 Uma referência a um **tamanho** estrutura a ser preenchido por esse método.  
  
### <a name="return-value"></a>Valor de retorno  
 TRUE se o controle é hospedado por uma caixa de diálogo. Caso contrário, FALSE.  
  
### <a name="remarks"></a>Comentários  
 O tamanho é retornado no `size` parâmetro.  
  
##  <a name="create"></a>CComCompositeControl::Create  
 Este método é chamado para criar a janela de controle para o controle composto.  
  
```
HWND Create(
    HWND hWndParent,
    RECT& /* rcPos */,
    LPARAM dwInitParam = NULL);
```  
  
### <a name="parameters"></a>Parâmetros  
 `hWndParent`  
 Um identificador para a janela pai do controle.  
  
 `rcPos`  
 Reservado.  
  
 `dwInitParam`  
 Dados a serem passados para o controle durante a criação do controle. Os dados passados como `dwInitParam` será exibido como o **LPARAM** parâmetro o [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) mensagem, que será enviada para o controle composto quando ele é criado.  
  
### <a name="return-value"></a>Valor de retorno  
 Um identificador para a caixa de diálogo controle composto criado recentemente.  
  
### <a name="remarks"></a>Comentários  
 Geralmente, esse método é chamado durante a ativação no local do controle.  
  
##  <a name="ccomcompositecontrol"></a>CComCompositeControl::CComCompositeControl  
 O construtor.  
  
```
CComCompositeControl();
```  
  
### <a name="remarks"></a>Comentários  
 Inicializa o [CComCompositeControl::m_hbrBackground](#m_hbrbackground) e [CComCompositeControl::m_hWndFocus](#m_hwndfocus) membros de dados como NULL.  
  
##  <a name="dtor"></a>CComCompositeControl:: ~ CComCompositeControl  
 O destruidor.  
  
```
~CComCompositeControl();
```  
  
### <a name="remarks"></a>Comentários  
 Exclui o objeto de plano de fundo, se ele existir.  
  
##  <a name="createcontrolwindow"></a>CComCompositeControl::CreateControlWindow  
 Chame esse método para criar a janela de controle e informar a todos os controles hospedados.  
  
```
virtual HWND CreateControlWindow(
    HWND hWndParent,
    RECT& rcPos);
```  
  
### <a name="parameters"></a>Parâmetros  
 `hWndParent`  
 Um identificador para a janela pai do controle.  
  
 `rcPos`  
 O retângulo da posição do controle composto no cliente coordena relativo a `hWndParent`.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna um identificador para a caixa de diálogo controle composto criado recentemente.  
  
### <a name="remarks"></a>Comentários  
 Esse método chama [CComCompositeControl::Create](#create) e [CComCompositeControl::AdviseSinkMap](#advisesinkmap).  
  
##  <a name="m_hbrbackground"></a>CComCompositeControl::m_hbrBackground  
 O pincel do plano de fundo.  
  
```
HBRUSH m_hbrBackground;
```  
  
##  <a name="m_hwndfocus"></a>CComCompositeControl::m_hWndFocus  
 O identificador da janela que tem o foco no momento.  
  
```
HWND m_hWndFocus;
```  
  
##  <a name="setbackgroundcolorfromambient"></a>CComCompositeControl::SetBackgroundColorFromAmbient  
 Chame esse método para definir a cor de plano de fundo do controle composto usando a cor de plano de fundo do contêiner.  
  
```
HRESULT SetBackgroundColorFromAmbient();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna S_OK com êxito, ou um erro HRESULT em caso de falha.  
  
## <a name="see-also"></a>Consulte também  
 [Classe CComControl](../../atl/reference/ccomcontrol-class.md)   
 [Fundamentos do controle composto](../../atl/atl-composite-control-fundamentals.md)   
 [Visão geral da classe](../../atl/atl-class-overview.md)
