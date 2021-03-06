---
title: Classe is_integral | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_integral
dev_langs:
- C++
helpviewer_keywords:
- is_integral class
- is_integral
ms.assetid: fe9279d0-4495-4e88-bf23-153cc6602397
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c44288c990f773984492f7c05b80423b17c1a37c
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44110572"
---
# <a name="isintegral-class"></a>Classe is_integral

Testa se o tipo é integral.

## <a name="syntax"></a>Sintaxe

```cpp
template <class Ty>
struct is_integral;
```

### <a name="parameters"></a>Parâmetros

*Ty*<br/>
O tipo a ser consultado.

## <a name="remarks"></a>Comentários

Uma instância do predicado de tipo será verdadeira se o tipo *Ty* é um dos tipos integrais, ou um `cv-qualified` forma de um dos tipos integrais, caso contrário, será falsa.

Um tipo integral é um dos **bool**, **char**, **unsigned char**, **assinado char**, **wchar_t**, **curto**, **unsigned short**, **int**, **int sem sinal**, **longo**e **unsigned long**. Além disso, com os compiladores que fornecem a eles, um tipo integral pode ser uma das **long long**, **longo longo sem sinal**, **__int64**, e **unsigned __int64**.

## <a name="example"></a>Exemplo

```cpp
// std__type_traits__is_integral.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_integral<trivial> == " << std::boolalpha
        << std::is_integral<trivial>::value << std::endl;
    std::cout << "is_integral<int> == " << std::boolalpha
        << std::is_integral<int>::value << std::endl;
    std::cout << "is_integral<float> == " << std::boolalpha
        << std::is_integral<float>::value << std::endl;

    return (0);
    }

```

```Output
is_integral<trivial> == false
is_integral<int> == true
is_integral<float> == false
```

## <a name="requirements"></a>Requisitos

**Cabeçalho:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Consulte também

[<type_traits>](../standard-library/type-traits.md)<br/>
[Classe is_enum](../standard-library/is-enum-class.md)<br/>
[Classe is_floating_point](../standard-library/is-floating-point-class.md)<br/>
