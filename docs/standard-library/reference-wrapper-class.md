---
title: Classe reference_wrapper | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- reference_wrapper
- std::reference_wrapper
- functional/std::reference_wrapper
- type_traits/std::reference_wrapper
- xrefwrap/std::reference_wrapper
- type_traits/std::reference_wrapper::get
- type_traits/std::reference_wrapper::operator()
dev_langs:
- C++
helpviewer_keywords:
- reference_wrapper class
- reference_wrapper
ms.assetid: 90b8ed62-e6f1-44ed-acc7-9619bd58865a
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.sourcegitcommit: f0e7b22e4fbd6f54d390adfe70f7bfb99e4bc5df
ms.openlocfilehash: 1b6968f2300e5214575cc5385c136d6f27bab10a
ms.lasthandoff: 02/25/2017

---
# <a name="referencewrapper-class"></a>Classe reference_wrapper
Encapsula uma referência.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
template <class Ty>  
class reference_wrapper  
{  
public:  
    typedef Ty type;  
 
    reference_wrapper(Ty&) noexcept;
    operator Ty&() const noexcept;
    Ty& get() const noexcept;

    template <class... Types> 
    auto operator()(Types&&... args) const ->
        decltype(std::invoke(get(), std::forward<Types>(args)...));
 
private:  
    Ty *ptr; // exposition only  
};  
```  
  
## <a name="remarks"></a>Comentários  
Um `reference_wrapper<Ty>` é uma cópia construível e copia um wrapper atribuível em uma referência a um objeto ou uma função de tipo `Ty`, além de conter um ponteiro que aponta para um objeto desse tipo. Um `reference_wrapper` pode ser usado para armazenar referências em contêineres padrão e para passar objetos por referência a `std::bind`.  
  
O tipo `Ty` deve ser um tipo de objeto ou um tipo de função ou uma falha de declaração estática no tempo de compilação.  
  
As funções auxiliares [std::ref](functional-functions.md#ref_function) e [std::cref](functional-functions.md#cref_function) podem ser usadas para criar objetos `reference_wrapper`.  
  
### <a name="constructors"></a>Construtores  
  
|||  
|-|-|  
|[reference_wrapper::reference_wrapper](#reference_wrapper)|Constrói um `reference_wrapper`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[reference_wrapper::result_type](#result_type)|O tipo de resultado fraco da referência encapsulada.|  
|[reference_wrapper::type](#type)|O tipo da referência encapsulada.|  
  
### <a name="member-functions"></a>Funções membro  
  
|||  
|-|-|  
|[reference_wrapper::get](#get)|Obtém a referência encapsulada.|  
  
### <a name="operators"></a>Operadores  
  
|||  
|-|-|  
|[reference_wrapper::operator Ty&amp;](#operator_ty_amp_)|Obtém um ponteiro para a referência encapsulada.|  
|[reference_wrapper::operator()](#operator_call)|Chama a referência encapsulada.|  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** \<functional>  
  
 **Namespace:** std  
  
##  <a name="a-namegeta--referencewrapperget"></a><a name="get"></a>  reference_wrapper::get  
 Obtém a referência encapsulada.  
  
```  
Ty& get() const noexcept;
```  
  
### <a name="remarks"></a>Comentários  
A função membro retorna a referência encapsulada.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// std__functional__reference_wrapper_get.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int main() {   
    int i = 1;   
    std::reference_wrapper<int> rwi(i);   
  
    std::cout << "i = " << i << std::endl;   
    std::cout << "rwi = " << rwi << std::endl;   
    rwi.get() = -1;   
    std::cout << "i = " << i << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
i = 1  
rwi = 1  
i = -1  
```  
  
##  <a name="a-nameoperatortyampa--referencewrapperoperator-tyamp"></a><a name="operator_ty_amp_"></a>  reference_wrapper::operator Ty&amp;  
 Obtém a referência encapsulada.  
  
```  
operator Ty&() const noexcept;
```  
  
### <a name="remarks"></a>Comentários  
 O operador de membro retorna `*ptr`.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// std__functional__reference_wrapper_operator_cast.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int main() {   
    int i = 1;   
    std::reference_wrapper<int> rwi(i);   
  
    std::cout << "i = " << i << std::endl;   
    std::cout << "(int)rwi = " << (int)rwi << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
i = 1  
(int)rwi = 1  
```  
  
##  <a name="a-nameoperatorcalla--referencewrapperoperator"></a><a name="operator_call"></a>  reference_wrapper::operator()  
 Chama a referência encapsulada.  
  
```  
template <class... Types>  
auto operator()(Types&&... args);
```  
  
### <a name="parameters"></a>Parâmetros  
 `Types`  
 Os tipos da lista de argumentos.  
  
 `args`  
 A lista de argumentos.  
  
### <a name="remarks"></a>Comentários  
 O membro de modelo `operator()` retorna `std::invoke(get(), std::forward<Types>(args)...)`.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// std__functional__reference_wrapper_operator_call.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int neg(int val) {   
    return (-val);   
}   
  
int main() {   
    std::reference_wrapper<int (int)> rwi(neg);   
  
    std::cout << "rwi(3) = " << rwi(3) << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
rwi(3) = -3  
```  
  
##  <a name="a-namereferencewrappera--referencewrapperreferencewrapper"></a><a name="reference_wrapper"></a>  reference_wrapper::reference_wrapper  
 Constrói um `reference_wrapper`.  
  
```  
reference_wrapper(Ty& val) noexcept;
```  
  
### <a name="parameters"></a>Parâmetros  
 `Ty`  
 O tipo a ser encapsulado.  
  
 `val`  
 O valor a ser encapsulado.  
  
### <a name="remarks"></a>Comentários  
 O construtor define o valor armazenado `ptr` para `&val`.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// std__functional__reference_wrapper_reference_wrapper.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int neg(int val) {   
    return (-val);   
}   
  
int main() {   
    int i = 1;   
    std::reference_wrapper<int> rwi(i);   
  
    std::cout << "i = " << i << std::endl;   
    std::cout << "rwi = " << rwi << std::endl;   
    rwi.get() = -1;   
    std::cout << "i = " << i << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
i = 1  
rwi = 1  
i = -1  
```  
  
##  <a name="a-nameresulttypea--referencewrapperresulttype"></a><a name="result_type"></a>  reference_wrapper::result_type  
 O tipo de resultado fraco da referência encapsulada.  
  
```  
typedef R result_type;  
```  
  
### <a name="remarks"></a>Comentários  
 O typedef `result_type` é um sinônimo do tipo de resultado fraco de uma função encapsulada. Este typedef só é significativo para tipos de função.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// std__functional__reference_wrapper_result_type.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int neg(int val) {   
    return (-val);   
}   
  
int main() {   
    typedef std::reference_wrapper<int (int)> Mywrapper;   
    Mywrapper rwi(neg);   
    Mywrapper::result_type val = rwi(3);   
  
    std::cout << "val = " << val << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
val = -3  
```  
  
##  <a name="a-nametypea--referencewrappertype"></a><a name="type"></a>  reference_wrapper::type  
 O tipo da referência encapsulada.  
  
```  
typedef Ty type;  
```  
  
### <a name="remarks"></a>Comentários  
 O typedef é um sinônimo do argumento de modelo `Ty`.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// std__functional__reference_wrapper_type.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int neg(int val) {   
    return (-val);   
}   
  
int main() {   
    int i = 1;   
    typedef std::reference_wrapper<int> Mywrapper;   
    Mywrapper rwi(i);   
    Mywrapper::type val = rwi.get();   
  
    std::cout << "i = " << i << std::endl;   
    std::cout << "rwi = " << val << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
i = 1  
rwi = 1  
```  
  
## <a name="see-also"></a>Consulte também  
 [Função cref](../standard-library/functional-functions.md#cref_function)   
 [Função ref](../standard-library/functional-functions.md#ref_function)

