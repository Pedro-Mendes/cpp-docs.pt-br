---
title: Classe regex_iterator | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- regex_iterator
- std::regex_iterator
- regex/std::regex_iterator
- std::regex_iterator::operator==
- regex/std::regex_iterator::operator==
- std::regex_iterator::operator!=
- regex/std::regex_iterator::operator!=
- std::regex_iterator::operator*
- regex/std::regex_iterator::operator*
- std::regex_iterator::operator->
- regex/std::regex_iterator::operator->
- std::regex_iterator::operator++
- regex/std::regex_iterator::operator++
dev_langs:
- C++
helpviewer_keywords:
- regex_iterator class
ms.assetid: 0cfd8fd0-5a95-4f3c-bf8e-6ef028c423d3
caps.latest.revision: 16
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
ms.sourcegitcommit: 248e9ba676b906af62f6804f4939e04158a8e2ef
ms.openlocfilehash: 8bfed3b74020bce20f18700d30573f01cdfd2adc
ms.lasthandoff: 02/25/2017

---
# <a name="regexiterator-class"></a>Classe regex_iterator
Classe de iterador para correspondências.  
  
## <a name="syntax"></a>Sintaxe  
```
template<class BidIt,
   class Elem = typename std::iterator_traits<BidIt>::value_type,
   class RxTraits = regex_traits<Elem> >
class regex_iterator {  
public:  
   typedef basic_regex<Elem, RXtraits> regex_type;  
   typedef match_results<BidIt> value_type;  
   typedef std::forward_iterator_tag iterator_category;  
   typedef std::ptrdiff_t difference_type;  
   typedef const match_results<BidIt>* pointer;  
   typedef const match_results<BidIt>& reference;  

   regex_iterator();
   regex_iterator(
      BidIt first, BidIt last, const regex_type& re,  
      regex_constants::match_flag_type f = regex_constants::match_default);

   bool operator==(const regex_iterator& right);
   bool operator!=(const regex_iterator& right);
   const match_results<BidIt>& operator*();
   const match_results<BidIt> * operator->();
   regex_iterator& operator++();
   regex_iterator& operator++(int);

private:
   BidIt begin; // exposition only  
   BidIt end; // exposition only  
   regex_type *pregex;     // exposition only  
   regex_constants::match_flag_type flags; // exposition only  
   match_results<BidIt> match; // exposition only  
   };  
```  
  
### <a name="parameters"></a>Parâmetros  
 `BidIt`  
 O tipo de iterador para subcorrespondências.  
  
 `Elem`  
 O tipo de elemento a ser correspondido.  
  
 `RXtraits`  
 Classe de características para elementos.  
  
## <a name="remarks"></a>Comentários  
 A classe de modelo descreve um objeto de iterador de avanço constante. Ele extrai objetos do tipo `match_results<BidIt>` aplicando repetidamente seu objeto de expressão regular `*pregex` à sequência de caracteres definida pelo intervalo do iterador `[begin, end)`.  
  
## <a name="examples"></a>Exemplos  
 Consulte os tópicos a seguir para ver exemplos de expressões regulares:  
  
- [Função regex_match](../standard-library/regex-functions.md#regex_match_function)  
  
- [Função regex_replace](../standard-library/regex-functions.md#regex_replace_function)  
  
- [Função regex_search](../standard-library/regex-functions.md#regex_search_function)  
  
- [Função swap](../standard-library/regex-functions.md#swap_function)  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** \<regex>  
  
 **Namespace:** std  
  
##  <a name="a-nameregexiteratordifferencetypea--regexiteratordifferencetype"></a><a name="regex_iterator__difference_type"></a>  regex_iterator::difference_type  
 O tipo de uma diferença de iterador.  
  
```  
typedef std::ptrdiff_t difference_type;  
```  
  
### <a name="remarks"></a>Comentários  
 O tipo é um sinônimo de `std::ptrdiff_t`.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// std__regex__regex_iterator_difference_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratoriteratorcategorya--regexiteratoriteratorcategory"></a><a name="regex_iterator__iterator_category"></a>  regex_iterator::iterator_category  
 O tipo da categoria do iterador.  
  
```  
typedef std::forward_iterator_tag iterator_category;  
```  
  
### <a name="remarks"></a>Comentários  
 O tipo é um sinônimo de `std::forward_iterator_tag`.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// std__regex__regex_iterator_iterator_category.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratoroperatorneqa--regexiteratoroperator"></a><a name="regex_iterator__operator_neq"></a>  regex_iterator::operator!=  
 Compara a desigualdade dos iteradores.  
  
```  
bool operator!=(const regex_iterator& right);
```  
  
### <a name="parameters"></a>Parâmetros  
 `right`  
 O iterador a ser comparado.  
  
### <a name="remarks"></a>Comentários  
 A função membro retorna `!(*this == right)`.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// std__regex__regex_iterator_operator_ne.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratoroperatorstara--regexiteratoroperator"></a><a name="regex_iterator__operator_star"></a>  regex_iterator::operator*  
 Acessa a correspondência designada.  
  
```  
const match_results<BidIt>& operator*();
```  
  
### <a name="remarks"></a>Comentários  
 A função do membro retorna o valor armazenado `match`.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// std__regex__regex_iterator_operator_star.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratoroperatoraddadda--regexiteratoroperator"></a><a name="regex_iterator__operator_add_add"></a>  regex_iterator::operator++  
 Incrementa o iterador.  
  
```  
regex_iterator& operator++();
regex_iterator& operator++(int);
```  
  
### <a name="remarks"></a>Comentários  
 Se a correspondência atual não tiver nenhum caractere, o primeiro operador chama `regex_search(begin, end, match, *pregex, flags | regex_constants::match_prev_avail | regex_constants::match_not_null)`; caso contrário, ele avança o valor armazenado `begin` para apontar para o primeiro caractere após a correspondência atual e chama `regex_search(begin, end, match, *pregex, flags | regex_constants::match_prev_avail)`. Em ambos os casos, se a pesquisa falhar, o operador define o objeto como um iterador de fim de sequência. O operador retorna o objeto.  
  
 O segundo operador faz uma cópia do objeto, incrementa o objeto e retorna a cópia.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// std__regex__regex_iterator_operator_inc.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratoroperatoreqa--regexiteratoroperator"></a><a name="regex_iterator__operator_eq"></a>  regex_iterator::operator=  
 Compara a igualdade dos iteradores.  
  
```  
bool operator==(const regex_iterator& right);
```  
  
### <a name="parameters"></a>Parâmetros  
 `right`  
 O iterador a ser comparado.  
  
### <a name="remarks"></a>Comentários  
 A função de membro retorna true se `*this` e `right` forem iteradores de fim de sequência ou se nenhum deles for um iterador de fim-de-sequência e `begin == right.begin`, `end == right.end`, `pregex == right.pregex` e `flags == right.flags`. Caso contrário, retorna false.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// std__regex__regex_iterator_operator_as.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratoroperator-gta--regexiteratoroperator-gt"></a><a name="regex_iterator__operator-_gt_"></a>  regex_iterator::operator-&gt;  
 Acessa a correspondência designada.  
  
```  
const match_results<BidIt> * operator->();
```  
  
### <a name="remarks"></a>Comentários  
 A função membro retorna o endereço do valor armazenado `match`.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// std__regex__regex_iterator_operator_arrow.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratorpointera--regexiteratorpointer"></a><a name="regex_iterator__pointer"></a>  regex_iterator::pointer  
 O tipo de um ponteiro para uma correspondência.  
  
```  
typedef match_results<BidIt> *pointer;  
```  
  
### <a name="remarks"></a>Comentários  
 O tipo é um sinônimo de `match_results<BidIt>*`, em que `BidIt` é o parâmetro de modelo.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// std__regex__regex_iterator_pointer.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratorreferencea--regexiteratorreference"></a><a name="regex_iterator__reference"></a>  regex_iterator::reference  
 O tipo de uma referência de uma correspondência.  
  
```  
typedef match_results<BidIt>& reference;  
```  
  
### <a name="remarks"></a>Comentários  
 O tipo é um sinônimo de `match_results<BidIt>&`, em que `BidIt` é o parâmetro de modelo.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// std__regex__regex_iterator_reference.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratorregexiteratora--regexiteratorregexiterator"></a><a name="regex_iterator__regex_iterator"></a>  regex_iterator::regex_iterator  
 Constrói o iterador.  
  
```  
regex_iterator();

regex_iterator(BidIt first,
    BidIt last,  
    const regex_type& re,
    regex_constants::match_flag_type f = regex_constants::match_default);
```  
  
### <a name="parameters"></a>Parâmetros  
 `first`  
 Início da sequência de correspondência.  
  
 `last`  
 Fim da sequência de correspondência.  
  
 `re`  
 Expressão regular para correspondências.  
  
 `f`  
 Sinalizadores de correspondências.  
  
### <a name="remarks"></a>Comentários  
 O primeiro construtor cria um iterador de fim de sequência. O segundo construtor inicializa o valor armazenado `begin` com `first`, o valor armazenado `end` com `last`, o valor armazenado `pregex` com `&re` e o valor armazenado `flags` com `f`. Depois, chama `regex_search(begin, end, match, *pregex, flags)`. Se a pesquisa falhar, o construtor define o objeto como um iterador de fim de sequência.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// std__regex__regex_iterator_construct.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratorregextypea--regexiteratorregextype"></a><a name="regex_iterator__regex_type"></a>  regex_iterator::regex_type  
 O tipo da expressão regular de correspondência.  
  
```  
typedef basic_regex<Elem, RXtraits> regex_type;  
```  
  
### <a name="remarks"></a>Comentários  
 O typedef é um sinônimo de `basic_regex<Elem, RXtraits>`.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// std__regex__regex_iterator_regex_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
##  <a name="a-nameregexiteratorvaluetypea--regexiteratorvaluetype"></a><a name="regex_iterator__value_type"></a>  regex_iterator::value_type  
 O tipo de uma correspondência.  
  
```  
typedef match_results<BidIt> value_type;  
```  
  
### <a name="remarks"></a>Comentários  
 O tipo é um sinônimo de `match_results<BidIt>`, em que `BidIt` é o parâmetro de modelo.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// std__regex__regex_iterator_value_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
typedef std::regex_iterator<const char *> Myiter;   
int main()   
    {   
    const char *pat = "axayaz";   
    Myiter::regex_type rx("a");   
    Myiter next(pat, pat + strlen(pat), rx);   
    Myiter end;   
  
    for (; next != end; ++next)   
        std::cout << "match == " << next->str() << std::endl;   
  
// other members   
    Myiter it1(pat, pat + strlen(pat), rx);   
    Myiter it2(it1);   
    next = it1;   
  
    Myiter::iterator_category cat = std::forward_iterator_tag();   
    Myiter::difference_type dif = -3;   
    Myiter::value_type mr = *it1;   
    Myiter::reference ref = mr;   
    Myiter::pointer ptr = &ref;   
  
    dif = dif; // to quiet "unused" warnings   
    ptr = ptr;   
  
    return (0);   
    }  
  
```  
  
```Output  
match == a  
match == a  
match == a  
```  
  
## <a name="see-also"></a>Consulte também  
[\<regex>](../standard-library/regex.md)  
[Classe regex_constants](../standard-library/regex-constants-class.md)  
[Classe regex_error](../standard-library/regex-error-class.md)  
[\<Funções regex>](../standard-library/regex-functions.md)  
[Classe regex_iterator](../standard-library/regex-iterator-class.md)  
[\<Operadores regex>](../standard-library/regex-operators.md)  
[Classe regex_token_iterator](../standard-library/regex-token-iterator-class.md)  
[Classe regex_traits](../standard-library/regex-traits-class.md)  
[\<Typedef regex>](../standard-library/regex-typedefs.md)  

  
