---
title: Se (OpenMP) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- if
dev_langs:
- C++
helpviewer_keywords:
- if OpenMP clause
ms.assetid: db5940b6-2414-4bf8-934d-3edd8393c0f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e4aaad878040534fd198bcdf4a93d7820fd89adc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404807"
---
# <a name="if-openmp"></a>if (OpenMP)

Especifica se deve ser executado um loop em paralelo ou em série.

## <a name="syntax"></a>Sintaxe

```
if(expression)
```

### <a name="parameters"></a>Parâmetros

*Expressão*<br/>
Uma expressão integral que, se ele for avaliado como true (diferente de zero), faz com que o código na região paralela para executar em paralelo. Se a expressão for avaliada como false (zero), a região paralela é executado em série (por um único thread).

## <a name="remarks"></a>Comentários

`if` aplica-se para as seguintes diretivas:

- [parallel](../../../parallel/openmp/reference/parallel.md)

- [for](../../../parallel/openmp/reference/for-openmp.md)

- [Seções](../../../parallel/openmp/reference/sections-openmp.md)

Para obter mais informações, consulte [2.3 construto parallel](../../../parallel/openmp/2-3-parallel-construct.md).

## <a name="example"></a>Exemplo

```
// omp_if.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

void test(int val)
{
    #pragma omp parallel if (val)
    if (omp_in_parallel())
    {
        #pragma omp single
        printf_s("val = %d, parallelized with %d threads\n",
                 val, omp_get_num_threads());
    }
    else
    {
        printf_s("val = %d, serialized\n", val);
    }
}

int main( )
{
    omp_set_num_threads(2);
    test(0);
    test(2);
}
```

```Output
val = 0, serialized
val = 2, parallelized with 2 threads
```

## <a name="see-also"></a>Consulte também

[Cláusulas](../../../parallel/openmp/reference/openmp-clauses.md)