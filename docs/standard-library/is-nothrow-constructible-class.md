---
title: Classe is_nothrow_constructible | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_nothrow_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_constructible
ms.assetid: 8be3f927-283e-4d67-95a5-8bf5dc4e7a3d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0726839baadf5265d604f231615f1add069ccfcb
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44106516"
---
# <a name="isnothrowconstructible-class"></a>Classe is_nothrow_constructible

Testa se um tipo pode ser construído e não efetua lançamentos quando os tipos de argumento especificados são usados.

## <a name="syntax"></a>Sintaxe

```cpp
template <class T, class... Args>
struct is_nothrow_constructible;
```

### <a name="parameters"></a>Parâmetros

*T*<br/>
O tipo a ser consultado.

*Args*<br/>
Os tipos de argumento para corresponder a um construtor *T*.

## <a name="remarks"></a>Comentários

Uma instância do predicado de tipo será verdadeira se o tipo *T* é construível usando os tipos de argumento na *Args*e o construtor pelo compilador não efetua lançamentos; caso contrário, será falsa. Tipo de *T* pode ser construído se a definição da variável `T t(std::declval<Args>()...);` está bem formado. Ambos *T* e todos os tipos *Args* devem ser tipos completos, **void**, ou matrizes de limite desconhecido.

## <a name="requirements"></a>Requisitos

**Cabeçalho:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Consulte também

[<type_traits>](../standard-library/type-traits.md)<br/>
