---
title: omp_lock_t | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_lock_t
dev_langs:
- C++
helpviewer_keywords:
- omp_lock_t OpenMP data type
ms.assetid: 51b80629-4ffc-4b8a-95c7-1af048f1f286
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f109ae179c1fcb3393a41d6c0831b0faf69b1d77
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444223"
---
# <a name="omplockt"></a>omp_lock_t

Um tipo que contém o status de um bloqueio, se o bloqueio está disponível ou se um thread possui um bloqueio.

As seguintes funções que usam **omp_lock_t**:

- [omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md)

- [omp_destroy_lock](../../../parallel/openmp/reference/omp-destroy-lock.md)

- [omp_set_lock](../../../parallel/openmp/reference/omp-set-lock.md)

- [omp_unset_lock](../../../parallel/openmp/reference/omp-unset-lock.md)

- [omp_test_lock](../../../parallel/openmp/reference/omp-test-lock.md)

Para obter mais informações, consulte [3.2 funções de bloqueio](../../../parallel/openmp/3-2-lock-functions.md).

## <a name="example"></a>Exemplo

Ver [funções omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md) para obter um exemplo de como usar **omp_lock_t**.

## <a name="see-also"></a>Consulte também

[Tipos de Dados](../../../parallel/openmp/reference/openmp-data-types.md)