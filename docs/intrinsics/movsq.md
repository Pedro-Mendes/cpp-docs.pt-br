---
title: __movsq | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __movsq
dev_langs:
- C++
helpviewer_keywords:
- __movsq intrinsic
- rep movsq instruction
- movsq instruction
ms.assetid: be116a6e-2176-4ca4-93b1-9ccf3e7e7835
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9386a35d7cfab67d0a981bd75d889f27e0ef4631
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46443810"
---
# <a name="movsq"></a>__movsq

**Seção específica da Microsoft**

Gera uma cadeia de caracteres repetida mover (`rep movsq`) instrução.

## <a name="syntax"></a>Sintaxe

```
void __movsq( 
   unsigned char* Dest, 
   unsigned char* Source, 
   size_t Count 
);
```

#### <a name="parameters"></a>Parâmetros

*dest*<br/>
[out] O destino da operação.

*Source*<br/>
[in] A origem da operação.

*Contagem*<br/>
[in] O número de palavras quádruplas para copiar.

## <a name="requirements"></a>Requisitos

|Intrínseco|Arquitetura|
|---------------|------------------|
|`__movsq`|X64|

**Arquivo de cabeçalho** \<intrin. h >

## <a name="remarks"></a>Comentários

O resultado é que a primeira `Count` palavras quádruplas apontado por `Source` são copiados para o `Dest` cadeia de caracteres.

Essa rotina só está disponível como função intrínseca.

## <a name="example"></a>Exemplo

```
// movsq.cpp
// processor: x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__movsq)

int main()
{
    unsigned __int64 a1[10];
    unsigned __int64 a2[10] = {950, 850, 750, 650, 550, 450, 350, 250,
                               150, 50};
    __movsq(a1, a2, 10);

    for (int i = 0; i < 10; i++)
       printf_s("%d ", a1[i]);
    printf_s("\n");
}
```

```Output
950 850 750 650 550 450 350 250 150 50
```

**Fim da seção específica da Microsoft**

## <a name="see-also"></a>Consulte também

[Intrínsecos do compilador](../intrinsics/compiler-intrinsics.md)