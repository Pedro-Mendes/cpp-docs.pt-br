---
title: 'Método activationfactory:: QueryInterface | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory::QueryInterface
dev_langs:
- C++
helpviewer_keywords:
- QueryInterface method
ms.assetid: 2a9b71aa-61c0-43f7-aa35-00f0ee0af031
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b4fa728039010ec30748773a51579ad8aabfac0f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398775"
---
# <a name="activationfactoryqueryinterface-method"></a>Método ActivationFactory::QueryInterface

Recupera um ponteiro para a interface especificada.

## <a name="syntax"></a>Sintaxe

```cpp
STDMETHOD(
   QueryInterface
)(REFIID riid, _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>Parâmetros

*riid*<br/>
Uma ID de interface.

*ppvObject*<br/>
Quando essa operação for concluída, um ponteiro para a interface especificada pelo parâmetro *riid*.

## <a name="return-value"></a>Valor de retorno

S_OK se bem-sucedido; Caso contrário, um HRESULT que descreve a falha.

## <a name="requirements"></a>Requisitos

**Cabeçalho:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Consulte também

[Classe ActivationFactory](../windows/activationfactory-class.md)