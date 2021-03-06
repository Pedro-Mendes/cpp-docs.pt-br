---
title: Implementando CComObjectRootEx | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- CComObjectRootEx
dev_langs:
- C++
helpviewer_keywords:
- CComObjectRoot class, implementing
- CComObjectRootEx class
ms.assetid: 79630c44-f2df-4e9e-b730-400a0ebfbd2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f91346febbb84ab7c1978740e0cbc6f0c43cbb4b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46052628"
---
# <a name="implementing-ccomobjectrootex"></a>Implementando CComObjectRootEx

[CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) é essencial; todos os objetos ATL devem ter uma instância do `CComObjectRootEx` ou [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) em sua herança. `CComObjectRootEx` fornece o mecanismo padrão `QueryInterface` com base em entradas de mapa COM.

Por meio de seu mapa COM, interfaces de um objeto são expostas a um cliente quando o cliente consulta uma interface. A consulta é realizada pelo `CComObjectRootEx::InternalQueryInterface`. `InternalQueryInterface` somente lida com interfaces na tabela de mapa COM.

Você pode inserir interfaces na tabela de mapa COM o [COM_INTERFACE_ENTRY](reference/com-interface-entry-macros.md#com_interface_entry) macro ou uma de suas variantes. Por exemplo, o código a seguir insere as interfaces `IDispatch`, `IBeeper` e `ISupportErrorInfo` na tabela de mapa COM:

[!code-cpp[NVC_ATL_COM#1](../atl/codesnippet/cpp/implementing-ccomobjectrootex_1.h)]

## <a name="see-also"></a>Consulte também

[Princípios básicos de objetos COM da ATL](../atl/fundamentals-of-atl-com-objects.md)<br/>
[Macros de mapa COM](../atl/reference/com-map-macros.md)

