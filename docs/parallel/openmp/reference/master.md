---
title: mestre | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- master
dev_langs:
- C++
helpviewer_keywords:
- master OpenMP directive
ms.assetid: 559ed974-e02a-486e-a23f-31556429b2c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9472854e22b1a1f7c4a13316244554b473f48298
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46423722"
---
# <a name="master"></a>master

Especifica que somente o mestre threadshould executar uma seção do programa.

## <a name="syntax"></a>Sintaxe

```
#pragma omp master
{
   code_block
}
```

## <a name="remarks"></a>Comentários

O **mestre** diretiva dá suporte a nenhuma cláusulas OpenMP.

O [único](../../../parallel/openmp/reference/single.md) diretiva permite que você especifique que uma seção de código deve ser executada em um único thread, não necessariamente o thread mestre.

Para obter mais informações, consulte [2.6.1 constructo de mestre](../../../parallel/openmp/2-6-1-master-construct.md).

## <a name="example"></a>Exemplo

```
// omp_master.cpp
// compile with: /openmp
#include <omp.h>
#include <stdio.h>

int main( )
{
    int a[5], i;

    #pragma omp parallel
    {
        // Perform some computation.
        #pragma omp for
        for (i = 0; i < 5; i++)
            a[i] = i * i;

        // Print intermediate results.
        #pragma omp master
            for (i = 0; i < 5; i++)
                printf_s("a[%d] = %d\n", i, a[i]);

        // Wait.
        #pragma omp barrier

        // Continue with the computation.
        #pragma omp for
        for (i = 0; i < 5; i++)
            a[i] += i;
    }
}
```

```Output
a[0] = 0
a[1] = 1
a[2] = 4
a[3] = 9
a[4] = 16
```

## <a name="see-also"></a>Consulte também

[Diretivas](../../../parallel/openmp/reference/openmp-directives.md)