---
title: Atributo Platform::Metadata::DefaultMemberAttribute | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Metadata::DefaultMemberAttribute
dev_langs:
- C++
helpviewer_keywords:
- Platform::Metadata::DefaultMemberAttribute Attribute
ms.assetid: d8abda01-c257-4371-aec4-541d4825e0af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 54959b293752ac0453ba383f86ab225e0b45e471
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44106984"
---
# <a name="platformmetadatadefaultmemberattribute-attribute"></a>Atributo Platform::Metadata::DefaultMemberAttribute

Indica a função preferencial a ser invocada dentre várias funções sobrecarregadas possíveis.

## <a name="syntax"></a>Sintaxe

```cpp
public ref class DefaultMember abstract : Attribute
```

## <a name="inheritance"></a>Herança

[Platform::Object](../cppcx/platform-object-class.md)

[Platform::Metadata::Attribute](../cppcx/platform-metadata-attribute-attribute.md)

### <a name="remarks"></a>Comentários

Aplique o atributo DefaultMember a um método que será consumido por um aplicativo JavaScript.

### <a name="requirements"></a>Requisitos

**Mínimo de cliente com suporte:** Windows 8

**Mínimo de servidor com suporte:** Windows Server 2012

**Namespace:** Platform::Metadata

**Metadados:** platform.winmd

## <a name="see-also"></a>Consulte também

[Namespace Platform::Metadata](../cppcx/platform-metadata-namespace.md)