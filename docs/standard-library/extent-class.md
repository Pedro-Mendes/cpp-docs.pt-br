---
title: Classe extent | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::extent
dev_langs:
- C++
helpviewer_keywords:
- extent class
- extent
ms.assetid: 6d16263d-90b2-4330-9ec7-b59ed898792d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 156ae11bcc63e5d19b816580bfce7bb24cfbc3d4
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44106672"
---
# <a name="extent-class"></a>Classe extent

Obtém uma dimensão de matriz.

## <a name="syntax"></a>Sintaxe

```cpp
template <class Ty, unsigned I = 0>
struct extent;
```

### <a name="parameters"></a>Parâmetros

*Ty*<br/>
O tipo a ser consultado.

*I*<br/>
A matriz associada à consulta.

## <a name="remarks"></a>Comentários

Se *Ty* é um tipo de matriz que tem pelo menos *eu* dimensões, a consulta de tipo contém o número de elementos na dimensão especificada pelo *eu*. Se *Ty* não é um tipo de matriz ou sua classificação for menor que *eu*, ou se *eu* é zero e *Ty* é do tipo "matriz desconhecida associada de `U` ", a consulta de tipo mantém o valor 0.

## <a name="example"></a>Exemplo

```cpp
// std__type_traits__extent.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

int main()
    {
    std::cout << "extent 0 == "
        << std::extent<int[5][10]>::value << std::endl;
    std::cout << "extent 1 == "
        << std::extent<int[5][10], 1>::value << std::endl;

    return (0);
    }

```

```Output
extent 0 == 5
extent 1 == 10
```

## <a name="requirements"></a>Requisitos

**Cabeçalho:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Consulte também

[<type_traits>](../standard-library/type-traits.md)<br/>
[Classe remove_all_extents](../standard-library/remove-all-extents-class.md)<br/>
[Classe remove_extent](../standard-library/remove-extent-class.md)<br/>
