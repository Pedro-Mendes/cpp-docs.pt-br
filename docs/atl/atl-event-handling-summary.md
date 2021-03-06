---
title: Resumo de manipulação de eventos ATL | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- event handling, implementing
ms.assetid: e8b47ef0-0bdc-47ff-9dd6-34df11dde9a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bf676dfdc197d756a8a8e46b9a68ce4de2136284
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026148"
---
# <a name="atl-event-handling-summary"></a>Resumo de manipulação de eventos do ATL

Em geral, a manipulação de eventos COM é um processo relativamente simples. Há três etapas principais:

- Implemente a interface de eventos em seu objeto.

- A origem do evento de aviso que seu objeto deseja receber eventos.

- Não recomendar a origem do evento quando seu objeto não precisa mais receber eventos.

## <a name="implementing-the-interface"></a>Implementando a Interface

Há quatro maneiras principais de implementação de uma interface usando ATL.

|Derivar de|Adequado para o tipo de Interface|Exige que você implementar todos os métodos *|Requer uma biblioteca de tipos em tempo de execução|
|-----------------|---------------------------------|---------------------------------------------|-----------------------------------------|
|A interface|Vtable|Sim|Não|
|[IDispatchImpl](../atl/reference/idispatchimpl-class.md)|Duplo|Sim|Sim|
|[IDispEventImpl](../atl/reference/idispeventimpl-class.md)|Dispinterface|Não|Sim|
|[IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|Dispinterface|Não|Não|

\* Ao usar classes de suporte ATL, você nunca é necessários para implementar o `IUnknown` ou `IDispatch` métodos manualmente.

## <a name="advising-and-unadvising-the-event-source"></a>Conselho administrativo e Unadvising a origem do evento

Há três maneiras principais de consultoria e unadvising uma origem de evento usando ATL.

|Função de aviso|Não recomendar a função|Mais adequado para uso com|Exige que você mantenha o controle de um cookie|Comentários|
|---------------------|-----------------------|--------------------------------|---------------------------------------------|--------------|
|[AtlAdvise](reference/connection-point-global-functions.md#atladvise), [CComPtrBase::Advise](../atl/reference/ccomptrbase-class.md#advise)|[AtlUnadvise](reference/connection-point-global-functions.md#atlunadvise)|Vtable ou interfaces duplas|Sim|`AtlAdvise` é uma função global do ATL. `CComPtrBase::Advise` é usado pelo [CComPtr](../atl/reference/ccomptr-class.md) e [CComQIPtr](../atl/reference/ccomqiptr-class.md).|
|[IDispEventSimpleImpl::DispEventAdvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventadvise)|[IDispEventSimpleImpl::DispEventUnadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventunadvise)|[IDispEventImpl](../atl/reference/idispeventimpl-class.md) ou [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|Não|Menos parâmetros que `AtlAdvise` , pois a classe base faz mais trabalho.|
|[CComCompositeControl::AdviseSinkMap(TRUE)](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)|[CComCompositeControl::AdviseSinkMap(FALSE)](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)|Controles ActiveX em controles de composição|Não|`CComCompositeControl::AdviseSinkMap` recomenda que todas as entradas de mapa do coletor de eventos. A mesma função unadvises as entradas. Esse método é chamado automaticamente pelo `CComCompositeControl` classe.|
|[CAxDialogImpl::AdviseSinkMap(TRUE)](../atl/reference/caxdialogimpl-class.md#advisesinkmap)|[CAxDialogImpl::AdviseSinkMap(FALSE)](../atl/reference/caxdialogimpl-class.md#advisesinkmap)|Controles ActiveX em uma caixa de diálogo|Não|`CAxDialogImpl::AdviseSinkMap` avisa e unadvises todos os controles ActiveX no recurso da caixa de diálogo. Isso é feito automaticamente para você.|

## <a name="see-also"></a>Consulte também

[Manipulação de eventos](../atl/event-handling-and-atl.md)<br/>
[Suporte a IDispEventImpl](../atl/supporting-idispeventimpl.md)

