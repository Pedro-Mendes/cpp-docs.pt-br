---
title: Classe COleDBRecordView | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDBRecordView
- AFXOLEDB/COleDBRecordView
- AFXOLEDB/COleDBRecordView::COleDBRecordView
- AFXOLEDB/COleDBRecordView::OnGetRowset
- AFXOLEDB/COleDBRecordView::OnMove
dev_langs:
- C++
helpviewer_keywords:
- MFC, OLE DB
- COleDBRecordView class
ms.assetid: 98612427-c4c9-4760-b7e1-85b17448add9
caps.latest.revision: 20
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 6129ad49f58cecb099927fe3d422fe215d143b67
ms.lasthandoff: 04/01/2017

---
# <a name="coledbrecordview-class"></a>Classe COleDBRecordView
Uma exibição que mostra os registros do banco de dados em controles.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
class COleDBRecordView : public CFormView  
```  
  
## <a name="members"></a>Membros  
  
### <a name="protected-constructors"></a>Construtores Protegidos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[COleDBRecordView::COleDBRecordView](#coledbrecordview)|Constrói um objeto `COleDBRecordView`.|  
  
### <a name="public-methods"></a>Métodos Públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[COleDBRecordView::OnGetRowset](#ongetrowset)|Retorna um padrão `HRESULT` valor.|  
|[COleDBRecordView::OnMove](#onmove)|Atualiza o registro atual (se estiver sujo) na fonte de dados e, em seguida, move para o registro especificado (próximo, anterior, primeiro ou último).|  
  
## <a name="remarks"></a>Comentários  
 A exibição é um modo de exibição de formulário conectado diretamente a um `CRowset` objeto. A exibição é criada a partir de um recurso de modelo de caixa de diálogo e exibe os campos do `CRowset` objeto nos controles do modelo de caixa de diálogo. O `COleDBRecordView` objeto usa a troca de dados de caixa de diálogo (DDX) e a funcionalidade de navegação incorporados `CRowset`, para automatizar a movimentação de dados entre os controles no formulário e os campos do conjunto de linhas. `COleDBRecordView`também fornece uma implementação padrão para mover para a primeira, próximo, anterior ou o último registro e uma interface para atualizar o registro no momento no modo de exibição.  
  
 Você pode usar funções DDX com **COleDbRecordView** obter dados diretamente do conjunto de registros do banco de dados e exibi-lo em um controle de caixa de diálogo. Você deve usar o **DDX_\*** métodos (como `DDX_Text`), não o **DDX_Field\* ** funções (como `DDX_FieldText`) com **COleDbRecordView**. `DDX_FieldText`não funcionarão com **COleDbRecordView** porque `DDX_FieldText` usa um argumento adicional do tipo **CRecordset\*** (para `CRecordView`) ou **CDaoRecordset\* ** (para `CDaoRecordView`).  
  
> [!NOTE]
>  Se você estiver trabalhando com as classes de objetos de acesso de dados (DAO) em vez das OLE DB consumidor classes de modelo, use a classe [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) em vez disso. Para obter mais informações, consulte o artigo [visão geral: programação do banco de dados](../../data/data-access-programming-mfc-atl.md).  
  
 `COleDBRecordView`Controla de posição do usuário no conjunto de linhas para que a exibição de registro possa atualizar a interface do usuário. Quando o usuário move para o fim do conjunto de linhas, o modo de exibição de registro desabilita os objetos de interface do usuário — como itens de menu ou botões da barra de ferramentas — para mover adicional na mesma direção.  
  
 Para obter mais informações sobre classes de conjunto de linhas, consulte o [usando OLE DB modelos de consumidor](../../data/oledb/ole-db-consumer-templates-cpp.md) artigo.  
  
## <a name="inheritance-hierarchy"></a>Hierarquia de herança  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `COleDBRecordView`  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** afxoledb.h  
  
##  <a name="coledbrecordview"></a>COleDBRecordView::COleDBRecordView  
 Constrói um objeto `COleDBRecordView`.  
  
```  
COleDBRecordView(LPCTSTR lpszTemplateName);  
COleDBRecordView(UINT nIDTemplate);
```  
  
### <a name="parameters"></a>Parâmetros  
 `lpszTemplateName`  
 Contém uma cadeia de caracteres terminada em nulo que é o nome de um recurso de modelo de caixa de diálogo.  
  
 `nIDTemplate`  
 Contém o número de identificação de um recurso de modelo de caixa de diálogo.  
  
### <a name="remarks"></a>Comentários  
 Quando você cria um objeto de um tipo derivado de `COleDBRecordView`, chamar um dos construtores para criar o objeto de exibição e identificar o recurso de caixa de diálogo na qual a exibição é baseada. Você pode identificar os recursos por nome (passar uma cadeia de caracteres como o argumento para o construtor) ou por sua ID (um inteiro sem sinal, como o argumento de passagem).  
  
> [!NOTE]
>  A classe derivada *deve* fornecer seu próprio construtor. No construtor, chamar o construtor, `COleDBRecordView::COleDBRecordView`, com o nome do recurso ou a ID como um argumento.  
  
##  <a name="ongetrowset"></a>COleDBRecordView::OnGetRowset  
 Retorna um identificador para o **CRowset<> </>** objeto associado à exibição de registro.  
  
```  
virtual CRowset<>* OnGetRowset() = 0;  
 
```  
  
### <a name="return-value"></a>Valor de retorno  
 Um padrão `HRESULT` valor.  
  
### <a name="remarks"></a>Comentários  
 Você deve substituir esta função de membro para criar ou obter um objeto de conjunto de linhas e retornar um identificador a ele. Se você declarar a classe de exibição de registro com ClassWizard, o assistente grava uma substituição padrão para você. Implementação do padrão do ClassWizard retorna o identificador do conjunto de linhas armazenado na exibição de registro se houver um. Se não, ele constrói um objeto de conjunto de linhas do tipo especificado com ClassWizard e chama seu **abrir** membro de função para abrir a tabela ou executar a consulta e, em seguida, retorna um identificador para o objeto.  
  
> [!NOTE]
>  Antes do MFC 7.0, `OnGetRowset` retornou um ponteiro para `CRowset`. Se você tiver um código que chama `OnGetRowset`, você precisa alterar o tipo de retorno para a classe de modelo **CRowset<>**.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_MFCDatabase 38](../../mfc/codesnippet/cpp/coledbrecordview-class_1.cpp)]  
  
 Para obter mais informações e exemplos, consulte o artigo [exibições de registro: usando uma exibição de registro](../../data/using-a-record-view-mfc-data-access.md).  
  
##  <a name="onmove"></a>COleDBRecordView::OnMove  
 Move para um registro diferente no conjunto de linhas e exibir seus campos nos controles do registro exibir.  
  
```  
virtual BOOL OnMove(UINT nIDMoveCommand);
```  
  
### <a name="parameters"></a>Parâmetros  
 `nIDMoveCommand`  
 Um dos seguintes valores de ID de comando padrão:  
  
- `ID_RECORD_FIRST`– Mover para o primeiro registro no conjunto de registros.  
  
- `ID_RECORD_LAST`– Mova para o último no conjunto de registros registro.  
  
- `ID_RECORD_NEXT`– Mover para o próximo registro no conjunto de registros.  
  
- `ID_RECORD_PREV`– Mover para o registro anterior no conjunto de registros.  
  
### <a name="return-value"></a>Valor de retorno  
 Diferente de zero se a movimentação foi bem-sucedida; Caso contrário, 0 se a solicitação de movimentação foi negada.  
  
### <a name="remarks"></a>Comentários  
 A implementação padrão chama apropriada **mover** função de membro de `CRowset` objeto associado à exibição de registro.  
  
 Por padrão, `OnMove` atualiza o registro atual na fonte de dados se o usuário alterou na exibição do registro.  
  
 O Assistente de aplicativo cria um recurso de menu com itens de menu do primeiro registro, último registro, próximo registro e registro anterior. Se você selecionar a opção de barra de ferramentas acopláveis, o Assistente de aplicativo também cria uma barra de ferramentas com botões correspondentes a esses comandos.  
  
 Se você mover além do último registro no conjunto de registros, o modo de exibição de registro continua a exibir o último registro. Se você retroceder após o primeiro registro, o modo de exibição de registro continua a exibir o primeiro registro.  
  
## <a name="see-also"></a>Consulte também  
 [Gráfico da hierarquia](../../mfc/hierarchy-chart.md)



