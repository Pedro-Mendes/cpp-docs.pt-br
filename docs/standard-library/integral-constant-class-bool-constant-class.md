---
title: Classe integral_constant, Classe bool_constant | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- integral_constant
- std::integral_constant
- type_traits/std::integral_constant
- XTR1COMMON/std::integral_constant
- bool_constant
- std::bool_constant
- type_traits/std::bool_constant
- XTR1COMMON/std::bool_constant
dev_langs:
- C++
helpviewer_keywords:
- integral_constant class
- integral_constant
- bool_constant
ms.assetid: 11c002c6-4d31-4042-9341-f2543f43e108
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 8630a5c0b97b85e0dc75e8b470974bb7d223a511
ms.openlocfilehash: 6c71c3571e19c57b13c827bbb84e347e3ff26b01
ms.lasthandoff: 02/25/2017

---
# <a name="integralconstant-class-boolconstant-class"></a>Classe integral_constant, classe bool_constant
Cria uma constante integral de um tipo e um valor.  
  
## <a name="syntax"></a>Sintaxe  
  
```
template<class T, T v>
struct integral_constant {  
   static constexpr T value = v;  
   typedef T value_type;  
   typedef integral_constant<T, v> type;  
   constexpr operator value_type() const noexcept;  
   constexpr value_type operator()() const noexcept;  
   };  
```
  
### <a name="parameters"></a>Parâmetros  
*T*  
O tipo da constante.  
  
*v*  
O valor da constante.  
  
## <a name="remarks"></a>Comentários  
A classe de modelo `integral_constant`, quando especializada com um tipo integral *T* e um valor *v* desse tipo, representa um objeto que contém uma constante desse tipo integral com o valor especificado. O membro denominado `type` é um alias para o tipo da especialização de modelo gerada e o membro `value` contém o valor *v* usado para criar a especialização.  
  
A classe de modelo `bool_constant` é uma especialização parcial explícita de `integral_constant`, que usa `bool` como o argumento *T*.  
  
## <a name="example"></a>Exemplo  
  
```cpp  
// std__type_traits__integral_constant.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::cout << "integral_constant<int, 5> == "   
        << std::integral_constant<int, 5>::value << std::endl;   
    std::cout << "integral_constant<bool, false> == " << std::boolalpha   
        << std::integral_constant<bool, false>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
integral_constant<int, 5> == 5  
integral_constant<bool, false> == false  
```  
  
## <a name="requirements"></a>Requisitos  

**Cabeçalho:** \<type_traits>
  
**Namespace:** std  
  
## <a name="see-also"></a>Consulte também  
 [<type_traits>](../standard-library/type-traits.md)   
 [Typedef false_type](../standard-library/type-traits-typedefs.md#false_type_typedef)   
 [Typedef true_type](../standard-library/type-traits-typedefs.md#true_type_typedef)

