---
title: Classe de valor sizet | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/PlatformSizeT::SizeT constructor
dev_langs:
- C++
helpviewer_keywords:
- Platform::SizeT Struct
ms.assetid: 0803612c-8ba1-430c-9b7b-1bebae88608d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b78d205956f026fe730848afa4c0d6fe7b52b52c
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44101996"
---
# <a name="platformsizet-value-class"></a>Platform::classe de valor SizeT

Representa o tamanho de um objeto. SizeT é um tipo de dados sem sinal.

## <a name="syntax"></a>Sintaxe

```cpp
public ref class SizeT sealed : ValueType
```

### <a name="members"></a>Membros

|Membro|Descrição|
|------------|-----------------|
|[Construtor SizeT::SizeT](#ctor)|Inicializa uma nova instância da classe com o valor especificado.|

### <a name="requirements"></a>Requisitos

**Mínimo de cliente com suporte:** Windows 8

**Mínimo de servidor com suporte:** Windows Server 2012

**Namespace:** Platform

**Metadados:** platform.winmd

## <a name="ctor"></a>  Construtor sizet:: Sizet

Inicializa uma nova instância de SizeT com o valor especificado.

### <a name="syntax"></a>Sintaxe

```cpp
SizeT( uint32 value1 );   SizeT( void* value2 );
```

### <a name="parameters"></a>Parâmetros

*Valor1*<br/>
Um valor de 32 bits sem sinal.

*Value2*<br/>
Ponteiro para um valor de 32 bits sem sinal.

## <a name="see-also"></a>Consulte também

[Namespace Platform](../cppcx/platform-namespace-c-cx.md)