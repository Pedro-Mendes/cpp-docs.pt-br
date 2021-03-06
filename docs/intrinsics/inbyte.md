---
title: __inbyte | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __inbyte
- __inbyte_cpp
dev_langs:
- C++
helpviewer_keywords:
- in instruction
- __inbyte intrinsic
ms.assetid: 03b61799-2a08-474d-adc4-2cbf7c81a4d5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7e9b4950c16cdab8dd282f772e84f7f222246328
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46414453"
---
# <a name="inbyte"></a>__inbyte

**Seção específica da Microsoft**

Gera o `in` instrução de retorno de um byte ler da porta especificada pelo `Port`.

## <a name="syntax"></a>Sintaxe

```
unsigned char __inbyte(
   unsigned short Port
);
```

#### <a name="parameters"></a>Parâmetros

*Porta*<br/>
[in] A porta leiam.

## <a name="return-value"></a>Valor de retorno

O byte lido da porta especificada.

## <a name="requirements"></a>Requisitos

|Intrínseco|Arquitetura|
|---------------|------------------|
|`__inbyte`|x86, x64|

**Arquivo de cabeçalho** \<intrin. h >

**Fim da seção específica da Microsoft**

## <a name="remarks"></a>Comentários

Essa rotina só está disponível como função intrínseca.

## <a name="see-also"></a>Consulte também

[Intrínsecos do compilador](../intrinsics/compiler-intrinsics.md)