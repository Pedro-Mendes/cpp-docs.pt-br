---
title: Função CreateActivationFactory | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreateActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- CreateActivationFactory function
ms.assetid: a1a53e04-6757-4faf-a4c8-ecf06e43b959
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: aed52e5ba209a826130b1a85aa866fe024174818
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424632"
---
# <a name="createactivationfactory-function"></a>Função CreateActivationFactory

Cria uma fábrica que produz instâncias da classe especificada que pode ser ativado pelo tempo de execução do Windows.

## <a name="syntax"></a>Sintaxe

```cpp
template<typename Factory>
   inline HRESULT STDMETHODCALLTYPE CreateActivationFactory(
      _In_ unsigned int *flags,        _In_ const CreatorMap* entry,
      REFIID riid,
   _Outptr_ IUnknown **ppFactory) throw();
```

### <a name="parameters"></a>Parâmetros

*flags*<br/>
Uma combinação de um ou mais [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) valores de enumeração.

*entry*<br/>
Ponteiro para um [CreatorMap](../windows/creatormap-structure.md) que contém informações de registro e inicialização sobre o parâmetro *riid*.

*riid*<br/>
Referência a uma ID de interface.

*ppFactory*<br/>
Se essa operação for concluída com êxito, um ponteiro para um alocador de ativação.

## <a name="return-value"></a>Valor de retorno

S_OK se bem-sucedido; Caso contrário, um HRESULT que indica o erro.

## <a name="remarks"></a>Comentários

Um erro de asserção será emitido se o parâmetro de modelo *fábrica* não deriva da interface `IActivationFactory`.

## <a name="requirements"></a>Requisitos

**Cabeçalho:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Consulte também

[Namespace Microsoft::WRL::Wrappers::Details](../windows/microsoft-wrl-wrappers-details-namespace.md)