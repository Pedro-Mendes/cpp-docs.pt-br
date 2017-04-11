---
title: "Funções &lt;tuple&gt; | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- tuple/std::get
- tuple/std::make_tuple
- tuple/std::tie
ms.assetid: bc6be38f-5258-4c14-b81b-63caa335fd44
caps.latest.revision: 13
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 41b445ceeeb1f37ee9873cb55f62d30d480d8718
ms.openlocfilehash: 4726f9457aa20889362f1058abedd0ac521c775c
ms.lasthandoff: 02/25/2017

---
# <a name="lttuplegt-functions"></a>Funções &lt;tuple&gt;
||||  
|-|-|-|  
|[Função get](#get_function)|[Função make_tuple](#make_tuple_function)|[Função tie](#tie_function)|  
  
##  <a name="a-namegetfunctiona--get-function"></a><a name="get_function"></a> Função get  
 Obtém um elemento de um objeto `tuple`, por índice ou (em C++14) por tipo.  
  
```  
// by index:
// get reference to Index element of tuple
template <size_t Index, class... Types>  
   constexpr tuple_element_t<Index, tuple<Types...>>& get(tuple<Types...>& Tuple) noexcept;

// get const reference to Index element of tuple
template <size_t Index, class... Types>  
   constexpr const tuple_element_t<Index, tuple<Types...>>& get(const tuple<Types...>& Tuple) noexcept;

// get rvalue reference to Index element of tuple
template <size_t Index, class... Types>  
   constexpr tuple_element_t<Index, tuple<Types...>>&& get(tuple<Types...>&& Tuple) noexcept;

// (C++14) by type:
// get reference to T element of tuple
template <class T, class... Types>  
   constexpr T& get(tuple<Types...>& Tuple) noexcept;

// get const reference to T element of tuple
template <class T, class... Types>  
   constexpr const T& get(const tuple<Types...>& Tuple) noexcept;

// get rvalue reference to T element of tuple
template <class T, class... Types>  
   constexpr T&& get(tuple<Types...>&& Tuple) noexcept;  
```  
  
### <a name="parameters"></a>Parâmetros  
 `Index`  
 O índice do elemento a ser obtido.  
  
 `Types`  
 A sequência de tipos declarados na tupla, em ordem de declaração.  
  
 `T`  
 O tipo do elemento a ser obtido.  
  
 `Tuple`  
 Um std::tuple que contém qualquer número de elementos.  
  
### <a name="remarks"></a>Comentários  
 As funções de modelo retornam uma referência ao valor no índice `Index` ou de tipo `T` no objeto `tuple`.  
  
 Chamar `get<T>(Tuple)` produzirá um erro do compilador se a Tupla contiver mais ou menos de um elemento do tipo T.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
#include <tuple>   
#include <iostream>   
#include <string>  
  
using namespace std;  
  
int main() {  
    tuple<int, double, string> tup(0, 1.42, "Call me Tuple");  
  
    // get elements by index  
    cout << " " << get<0>(tup);  
    cout << " " << get<1>(tup);  
    cout << " " << get<2>(tup) << endl;  
  
    // get elements by type  
    cout << " " << get<int>(tup);  
    cout << " " << get<double>(tup);  
    cout << " " << get<string>(tup) << endl;    
}  
```  
  
```Output  
0 1.42 Call me Tuple  
0 1.42 Call me Tuple  
```  
  
##  <a name="a-namemaketuplefunctiona--maketuple-function"></a><a name="make_tuple_function"></a> Função make_tuple  
 Constitui uma `tuple` dos valores de elemento.  
  
```  
template <class T1, class T2, ..., class TN>  
   tuple<V1, V2, ..., VN> make_tuple(const T1& t1, const T2& t2, ..., const TN& tN);
```  
  
### <a name="parameters"></a>Parâmetros  
 `TN`  
 O tipo do enésimo parâmetro de função.  
  
 `tN`  
 O valor do enésimo parâmetro de função.  
  
### <a name="remarks"></a>Comentários  
 A função do modelo retorna `tuple<V1, V2, ..., VN>(t1, t2, ..., tN)`, em que cada tipo `Vi` é `X&` quando o tipo correspondente `Ti` é `cv` `reference_wrapper<X>`; caso contrário, `Ti`.  
  
 Uma vantagem de `make_tuple` é que os tipos de objetos que estão sendo armazenados são determinados automaticamente pelo compilador e não precisam ser explicitamente especificados. Não use argumentos de modelo explícitos, como `make_tuple<int, int>(1, 2)`, ao usar `make_tuple`, pois ele é desnecessariamente detalhado e adiciona problemas complexos de referência rvalue que podem causar falha de compilação.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// std__tuple__make_tuple.cpp   
// compile by using: /EHsc   
#include <tuple>   
#include <iostream>   
  
typedef std::tuple<int, double, int, double> Mytuple;   
int main() {   
    Mytuple c0(0, 1, 2, 3);   
  
// display contents " 0 1 2 3"   
    std::cout << " " << std::get<0>(c0);   
    std::cout << " " << std::get<1>(c0);   
    std::cout << " " << std::get<2>(c0);   
    std::cout << " " << std::get<3>(c0);   
    std::cout << std::endl;   
  
    c0 = std::make_tuple(4, 5, 6, 7);   
  
// display contents " 4 5 6 7"   
    std::cout << " " << std::get<0>(c0);   
    std::cout << " " << std::get<1>(c0);   
    std::cout << " " << std::get<2>(c0);   
    std::cout << " " << std::get<3>(c0);   
    std::cout << std::endl;   
  
    return (0);   
}  
```  
  
```  
 0 1 2 3
 4 5 6 7  
```  
  
##  <a name="a-nametiefunctiona--tie-function"></a><a name="tie_function"></a> Função tie  
 Constitui um `tuple` das referências do elemento.  
  
```  
template <class T1, class T2, ..., class TN>  
tuple<T1&, T2&, ..., TN&> tie(T1& t1, T2& t2, ..., TN& tN);
```  
  
### <a name="parameters"></a>Parâmetros  
 `TN`  
 O tipo de base do enésimo elemento de tupla.  
  
### <a name="remarks"></a>Comentários  
 A função do modelo retorna `tuple<T1&, T2&, ..., TN&>(t1, t2, ..., tN)`.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// std__tuple__tie.cpp   
// compile with: /EHsc   
#include <tuple>   
#include <iostream>   
  
typedef std::tuple<int, double, int, double> Mytuple;   
int main() {   
    Mytuple c0(0, 1, 2, 3);   
  
// display contents " 0 1 2 3"   
    std::cout << " " << std::get<0>(c0);   
    std::cout << " " << std::get<1>(c0);   
    std::cout << " " << std::get<2>(c0);   
    std::cout << " " << std::get<3>(c0);   
    std::cout << std::endl;   
  
    int v4 = 4;   
    double v5 = 5;   
    int v6 = 6;   
    double v7 = 7;   
    std::tie(v4, v5, v6, v7) = c0;   
  
// display contents " 0 1 2 3"   
    std::cout << " " << v4;   
    std::cout << " " << v5;   
    std::cout << " " << v6;   
    std::cout << " " << v7;   
    std::cout << std::endl;   
  
    return (0);   
}    
```  
  
```Output  
0 1 2 3  
0 1 2 3  
```  
  
## <a name="see-also"></a>Consulte também  
 [\<tuple>](../standard-library/tuple.md)

