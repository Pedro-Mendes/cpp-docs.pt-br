---
title: Função TerminateMap | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::TerminateMap
dev_langs:
- C++
helpviewer_keywords:
- TerminateMap function
ms.assetid: 1c314a61-da5d-49bb-ac44-c34ee3c23b66
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f844d63bc04deb4294203f04aef30db48f195fd9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438061"
---
# <a name="terminatemap-function"></a>Função TerminateMap

Oferece suporte a infraestrutura do WRL e não se destina a ser usado diretamente do seu código.

## <a name="syntax"></a>Sintaxe

```cpp
inline bool TerminateMap(
   _In_ ModuleBase *module,
   _In_opt_z_ const wchar_t *serverName,
    bool forceTerminate) throw()  
```

### <a name="parameters"></a>Parâmetros

*módulo*<br/>
Um [módulo](../windows/module-class.md).

*ServerName*<br/>
O nome de um subconjunto de fábricas de classe no módulo especificado pelo parâmetro *módulo*.

*forceTerminate*<br/>
**True** para encerrar a classe fábricas, independentemente de eles estão ativos; **falsos** não encerrar as fábricas de classes se qualquer fábrica estiver ativa.

## <a name="return-value"></a>Valor de retorno

**Verdadeiro** se todas as fábricas de classes foram encerradas; caso contrário, **falso**.

## <a name="remarks"></a>Comentários

Desliga as fábricas de classes no módulo especificado.

## <a name="requirements"></a>Requisitos

**Cabeçalho:** module.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Consulte também

[Namespace Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)