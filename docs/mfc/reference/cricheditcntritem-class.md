---
title: Classe CRichEditCntrItem | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CRichEditCntrItem
- AFXRICH/CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::SyncToRichEditObject
dev_langs:
- C++
helpviewer_keywords:
- CRichEditCntrItem [MFC], CRichEditCntrItem
- CRichEditCntrItem [MFC], SyncToRichEditObject
ms.assetid: 6c0b4efe-0fb8-4621-b5e1-fdcb8ec48c3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: af8d2a2d8fd5bf54e117b3cdb44628f167d67cb9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46403510"
---
# <a name="cricheditcntritem-class"></a>Classe CRichEditCntrItem

Com o [CRichEditView](../../mfc/reference/cricheditview-class.md) e [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), fornece a funcionalidade do controle de edição rica dentro do contexto da arquitetura de exibição de documento do MFC.

## <a name="syntax"></a>Sintaxe

```
class CRichEditCntrItem : public COleClientItem
```

## <a name="members"></a>Membros

### <a name="public-constructors"></a>Construtores Públicos

|Nome|Descrição|
|----------|-----------------|
|[CRichEditCntrItem::CRichEditCntrItem](#cricheditcntritem)|Constrói um objeto `CRichEditCntrItem`.|

### <a name="public-methods"></a>Métodos Públicos

|Nome|Descrição|
|----------|-----------------|
|[CRichEditCntrItem::SyncToRichEditObject](#synctoricheditobject)|Ativa o item como outro tipo.|

## <a name="remarks"></a>Comentários

Um "controle de edição rica" é uma janela na qual o usuário pode inserir e editar o texto. O texto pode ser atribuído caracteres e formatação de parágrafo e pode incluir objetos OLE incorporados. Controles de edição avançada fornecem uma interface de programação de formatação de texto. No entanto, um aplicativo deve implementar quaisquer componentes de interface do usuário necessários para tornar as operações de formatação disponíveis para o usuário.

`CRichEditView` mantém o texto e as características de formatação de texto. `CRichEditDoc` mantém a lista de itens de cliente OLE que estão no modo de exibição. `CRichEditCntrItem` fornece acesso de lado do contêiner para o item de cliente OLE.

Esse controle comum do Windows (e, portanto, o [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) e as classes relacionadas) está disponível somente para programas executados no Windows 95/98 e Windows NT versões 3.51 e posterior.

Para obter um exemplo de como usar itens de contêiner de edição rica em um aplicativo MFC, consulte o [WORDPAD](../../visual-cpp-samples.md) aplicativo de exemplo.

## <a name="inheritance-hierarchy"></a>Hierarquia de herança

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

[COleClientItem](../../mfc/reference/coleclientitem-class.md)

`CRichEditCntrItem`

## <a name="requirements"></a>Requisitos

**Cabeçalho:** afxrich.h

##  <a name="cricheditcntritem"></a>  CRichEditCntrItem::CRichEditCntrItem

Chame essa função para criar um `CRichEditCntrItem` do objeto e adicioná-lo no documento contêiner.

```
CRichEditCntrItem(
    REOBJECT* preo = NULL,
    CRichEditDoc* pContainer = NULL);
```

### <a name="parameters"></a>Parâmetros

*preo*<br/>
Ponteiro para um [REOBJECT](/windows/desktop/api/richole/ns-richole-_reobject) estrutura que descreve um item OLE. O novo `CRichEditCntrItem` objeto é construído ao redor deste item OLE. Se *preo* for NULL, o item do cliente está vazio.

*pContainer*<br/>
Ponteiro para o documento de contêiner que contém esse item. Se *pContainer* for NULL, você deve chamar explicitamente [COleDocument::AddItem](../../mfc/reference/coledocument-class.md#additem) para adicionar este item de cliente a um documento.

### <a name="remarks"></a>Comentários

Essa função não executa qualquer inicialização OLE.

Para obter mais informações, consulte o [REOBJECT](/windows/desktop/api/richole/ns-richole-_reobject) estrutura no SDK do Windows.

##  <a name="synctoricheditobject"></a>  CRichEditCntrItem::SyncToRichEditObject

Chame essa função para sincronizar o aspecto de dispositivo [DVASPECT](/windows/desktop/api/wtypes/ne-wtypes-tagdvaspect), isso `CRichEditCntrltem` especificado por *reo*.

```
void SyncToRichEditObject(REOBJECT& reo);
```

### <a name="parameters"></a>Parâmetros

*REO*<br/>
Referência a um [REOBJECT](/windows/desktop/api/richole/ns-richole-_reobject) estrutura que descreve um item OLE.

### <a name="remarks"></a>Comentários

Para obter mais informações, consulte [DVASPECT](/windows/desktop/api/wtypes/ne-wtypes-tagdvaspect) no SDK do Windows.

## <a name="see-also"></a>Consulte também

[Exemplo MFC WORDPAD](../../visual-cpp-samples.md)<br/>
[Classe COleClientItem](../../mfc/reference/coleclientitem-class.md)<br/>
[Gráfico da hierarquia](../../mfc/hierarchy-chart.md)<br/>
[Classe CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)<br/>
[Classe CRichEditView](../../mfc/reference/cricheditview-class.md)
