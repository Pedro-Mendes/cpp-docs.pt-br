---
title: Estrutura FactoryCache | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::FactoryCache
dev_langs:
- C++
helpviewer_keywords:
- FactoryCache structure
ms.assetid: 624544e6-0989-47f6-a3e9-edb60e1ee6d4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: df2335a49d2d5daf862db7cea7eb413c01164bee
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609022"
---
# <a name="factorycache-structure"></a>Estrutura FactoryCache

Oferece suporte a infraestrutura de biblioteca de modelos de C++ de tempo de execução do Windows e não se destina a ser usado diretamente do seu código.

## <a name="syntax"></a>Sintaxe

```cpp
struct FactoryCache;
```

## <a name="remarks"></a>Comentários

Contém o local de uma fábrica de classes e um valor que identifica um registrado wrt ou objeto de classe COM.

## <a name="members"></a>Membros

### <a name="public-data-members"></a>Membros de Dados Públicos

|Nome|Descrição|
|----------|-----------------|
|[Membro de dados FactoryCache::cookie](../windows/factorycache-cookie-data-member.md)|Contém um valor que identifica um objeto de classe de tempo de execução do Windows ou COM registrado e é usado posteriormente para cancelar o registro do objeto.|
|[Membro de dados FactoryCache::factory](../windows/factorycache-factory-data-member.md)|Aponta para uma fábrica de classes de tempo de execução do Windows ou COM.|

## <a name="inheritance-hierarchy"></a>Hierarquia de herança

`FactoryCache`

## <a name="requirements"></a>Requisitos

**Cabeçalho:** module.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Consulte também

[Namespace Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)