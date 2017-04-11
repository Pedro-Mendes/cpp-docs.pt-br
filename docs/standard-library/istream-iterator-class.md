---
title: Classe istream_iterator | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iterator/std::istream_iterator
- std.istream_iterator
- std::istream_iterator
- istream_iterator
dev_langs:
- C++
helpviewer_keywords:
- istream_iterator class
ms.assetid: fb52a8cd-7f71-48d1-b73e-4b064e2a8d16
caps.latest.revision: 18
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
ms.sourcegitcommit: 2d05749ba2837a3879c91886b9266de47dd2ece6
ms.openlocfilehash: e5f214501712bd8d6212f465fe82d835ccaf9028
ms.lasthandoff: 02/25/2017

---
# <a name="istreamiterator-class"></a>Classe istream_iterator
Descreve um objeto de iterador de entrada. Extrai objetos da classe `Type` de um fluxo de entrada, que acessa por meio de um objeto que armazena, do tipo `pointer` para `basic_istream`< `CharType`, `Traits`>.  
  
## <a name="syntax"></a>Sintaxe  
  
```
template <class Type, class CharType = char, class Traits = char_traits<CharType>, class Distance = ptrdiff_t,>  
class istream_iterator
 : public iterator<
    input_iterator_tag, Type, Distance,
    const Type *,
    const Type&>;
```  
  
#### <a name="parameters"></a>Parâmetros  
 `Type`  
 O tipo de objeto a ser extraído do fluxo de entrada.  
  
 `CharType`  
 O tipo que representa o tipo de caractere para `istream_iterator`. Esse argumento é opcional e o valor padrão é `char`.  
  
 `Traits`  
 O tipo que representa o tipo de caractere para `istream_iterator`. Esse argumento é opcional e o valor padrão é `char_traits`< `CharType`>.  
  
 `Distance`  
 Um tipo integral com sinal que representa o tipo de diferença para `istream_iterator`. Esse argumento é opcional e o valor padrão é `ptrdiff_t`.  
  
 Depois de construir ou incrementar um objeto da classe istream_iterator com um ponteiro armazenado não nulo, o objeto tenta extrair e armazenar um objeto do tipo `Type` do fluxo de entrada associado. Se a extração falhar, o objeto substitui eficientemente o ponteiro armazenado por um ponteiro nulo, criando um indicador de fim de sequência.  
  
### <a name="constructors"></a>Construtores  
  
|||  
|-|-|  
|[istream_iterator](#istream_iterator__istream_iterator)|Constrói um iterador de fim de fluxo como o `istream_iterator` padrão ou um `istream_iterator` inicializado para o tipo de fluxo do iterador do qual ele lê.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#istream_iterator__char_type)|Um tipo que é fornecido para o tipo de caractere do `istream_iterator`.|  
|[istream_type](#istream_iterator__istream_type)|Um tipo que é fornecido para o tipo de fluxo da `istream_iterator`.|  
|[traits_type](#istream_iterator__traits_type)|Um tipo que fornece o tipo de característica do caractere da `istream_iterator`.|  
  
### <a name="operators"></a>Operadores  
  
|||  
|-|-|  
|[operator*](#istream_iterator__operator_star)|O operador de desreferenciamento retorna o objeto armazenado do tipo `Type` tratado por `istream_iterator`.|  
|[operator->](#istream_iterator__operator-_gt_)|Retorna o valor de um membro, se houver.|  
|[operator++](#istream_iterator__operator_add_add)|Ou extrai um objeto incrementado do fluxo de entrada, ou copia o objeto antes de incrementá-lo e retorna a cópia.|  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** \<iterator>  
  
 **Namespace:** std  
  
##  <a name="a-nameistreamiteratorchartypea--istreamiteratorchartype"></a><a name="istream_iterator__char_type"></a>  istream_iterator::char_type  
 Um tipo que é fornecido para o tipo de caractere do `istream_iterator`.  
  
```
typedef CharType char_type;
```  
  
### <a name="remarks"></a>Comentários  
 O tipo é um sinônimo do parâmetro de modelo **Chartype**.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// istream_iterator_char_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   typedef istream_iterator<int>::char_type CHT1;  
   typedef istream_iterator<int>::traits_type CHTR1;  
  
   // Standard iterator interface for reading  
   // elements from the input stream:  
   cout << "Enter integers separated by spaces & then\n"  
        << " any character ( try example: '2 4 f' ): ";  
  
   // istream_iterator for reading int stream  
   istream_iterator<int, CHT1, CHTR1> intRead ( cin );  
  
   // End-of-stream iterator  
   istream_iterator<int, CHT1, CHTR1> EOFintRead;  
  
   while ( intRead != EOFintRead )  
   {  
      cout << "Reading:  " << *intRead << endl;  
      ++intRead;  
   }  
   cout << endl;  
}  
```  
  
##  <a name="a-nameistreamiteratoristreamiteratora--istreamiteratoristreamiterator"></a><a name="istream_iterator__istream_iterator"></a>  istream_iterator::istream_iterator  
 Constrói um iterador de fim de fluxo como o `istream_iterator` padrão ou um `istream_iterator` inicializado para o tipo de fluxo do iterador do qual ele lê.  
  
```
istream_iterator();

istream_iterator(istream_type& _Istr);
```  
  
### <a name="parameters"></a>Parâmetros  
 `_Istr`  
 O fluxo de entrada a ser lido usado para inicializar o `istream_iterator`.  
  
### <a name="remarks"></a>Comentários  
 O primeiro construtor inicializa o ponteiro de fluxo de entrada com um ponteiro nulo e cria um iterador de fim do fluxo. O segundo construtor inicializa o ponteiro de fluxo de entrada com *&_Istr* e tenta extrair e armazenar um objeto do tipo **Type**.  
  
 O iterador de fim do fluxo pode ser usado para testar se um `istream_iterator` atingiu o final de um fluxo.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// istream_iterator_istream_iterator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <algorithm>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Used in conjunction with copy algorithm  
   // to put elements into a vector read from cin  
   vector<int> vec ( 4 );  
   vector <int>::iterator Iter;  
  
   cout << "Enter 4 integers separated by spaces & then\n"  
        << " a character ( try example: '2 4 6 8 a' ): ";  
   istream_iterator<int> intvecRead ( cin );  
  
   // Default constructor will test equal to end of stream  
   // for delimiting source range of vecor  
   copy ( intvecRead , istream_iterator<int>( ) , vec.begin ( ) );  
   cin.clear ( );  
  
   cout << "vec = ";  
   for ( Iter = vec.begin( ) ; Iter != vec.end( ) ; Iter++ )  
      cout << *Iter << " "; cout << endl;  
}  
```  
  
##  <a name="a-nameistreamiteratoristreamtypea--istreamiteratoristreamtype"></a><a name="istream_iterator__istream_type"></a>  istream_iterator::istream_type  
 Um tipo que é fornecido para o tipo de fluxo da `istream_iterator`.  
  
```
typedef basic_istream<CharType, Traits> istream_type;
```  
  
### <a name="remarks"></a>Comentários  
 O tipo é um sinônimo de `basic_istream`\< **CharType**, **Traits**>.  
  
### <a name="example"></a>Exemplo  
  Consulte [istream_iterator](#istream_iterator__istream_iterator) para obter um exemplo de como declarar e usar `istream_type`.  
  
##  <a name="a-nameistreamiteratoroperatorstara--istreamiteratoroperator"></a><a name="istream_iterator__operator_star"></a>  istream_iterator::operator*  
 O operador de desreferenciamento retorna o objeto armazenado do tipo **Type** tratado por `istream_iterator`.  
  
```
const Type& operator*() const;
```  
  
### <a name="return-value"></a>Valor de retorno  
 O objeto armazenado do tipo **Type**.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// istream_iterator_operator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <algorithm>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   cout << "Enter integers separated by spaces & then\n"  
        << " a character ( try example: '2 4 6 8 a' ): ";  
  
   // istream_iterator from stream cin  
   istream_iterator<int> intRead ( cin );  
  
   // End-of-stream iterator  
   istream_iterator<int> EOFintRead;  
  
   while ( intRead != EOFintRead )  
   {  
      cout << "Reading:  " << *intRead << endl;  
      ++intRead;  
   }  
   cout << endl;  
}  
```  
  
##  <a name="a-nameistreamiteratoroperator-gta--istreamiteratoroperator-gt"></a><a name="istream_iterator__operator-_gt_"></a>  istream_iterator::operator-&gt;  
 Retorna o valor de um membro, se houver.  
  
```
const Type* operator->() const;
```  
  
### <a name="return-value"></a>Valor de retorno  
 O valor de um membro, se houver.  
  
### <a name="remarks"></a>Comentários  
 *i* -> é equivalente a (\* *i*). *m*  
  
 O operador retorna **&\*\*this**.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// istream_iterator_operator_vm.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <iostream>  
#include <complex>  
  
using namespace std;  
  
int main( )  
{  
   cout << "Enter complex numbers separated by spaces & then\n"  
        << " a character pair ( try example: '(1,2) (3,4) (a,b)' ): ";  
  
   // istream_iterator from stream cin  
   istream_iterator< complex<double> > intRead ( cin );  
  
   // End-of-stream iterator  
   istream_iterator<complex<double> > EOFintRead;  
  
   while ( intRead != EOFintRead )  
   {  
      cout << "Reading the real part: " << intRead ->real( ) << endl;  
      cout << "Reading the imaginary part: " << intRead ->imag( ) << endl;  
      ++intRead;  
   }  
   cout << endl;  
}  
```  
  
##  <a name="a-nameistreamiteratoroperatoraddadda--istreamiteratoroperator"></a><a name="istream_iterator__operator_add_add"></a>  istream_iterator::operator++  
 Ou extrai um objeto incrementado do fluxo de entrada, ou copia o objeto antes de incrementá-lo e retorna a cópia.  
  
```
istream_iterator<Type, CharType, Traits, Distance>& operator++();

istream_iterator<Type, CharType, Traits, Distance> operator++(int);
```  
  
### <a name="return-value"></a>Valor de retorno  
 O primeiro operador membro retorna uma referência ao objeto incrementado do tipo **Type** extraído do fluxo de entrada e a segunda função membro retorna uma cópia do objeto.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// istream_iterator_operator_incr.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <algorithm>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   cout << "Enter integers separated by spaces & then\n"  
        << " a character ( try example: '2 4 6 8 a' ): ";  
  
   // istream_iterator from stream cin  
   istream_iterator<int> intRead ( cin );  
  
   // End-of-stream iterator  
   istream_iterator<int> EOFintRead;  
  
   while ( intRead != EOFintRead )  
   {  
      cout << "Reading:  " << *intRead << endl;  
      ++intRead;  
   }  
   cout << endl;  
}  
```  
  
##  <a name="a-nameistreamiteratortraitstypea--istreamiteratortraitstype"></a><a name="istream_iterator__traits_type"></a>  istream_iterator::traits_type  
 Um tipo que fornece o tipo de característica do caractere da `istream_iterator`.  
  
```
typedef Traits traits_type;
```  
  
### <a name="remarks"></a>Comentários  
 O tipo é um sinônimo do parâmetro de modelo **Traits**.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// istream_iterator_traits_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   typedef istream_iterator<int>::char_type CHT1;  
   typedef istream_iterator<int>::traits_type CHTR1;  
  
   // Standard iterator interface for reading  
   // elements from the input stream:  
   cout << "Enter integers separated by spaces & then\n"  
        << " any character ( try example: '10 20 a' ): ";  
  
   // istream_iterator for reading int stream  
   istream_iterator<int, CHT1, CHTR1> intRead ( cin );  
  
   // End-of-stream iterator  
   istream_iterator<int, CHT1, CHTR1> EOFintRead;  
  
   while ( intRead != EOFintRead )  
   {  
      cout << "Reading:  " << *intRead << endl;  
      ++intRead;  
   }  
   cout << endl;  
}  
```  
  
## <a name="see-also"></a>Consulte também  
 [Struct input_iterator_tag](../standard-library/input-iterator-tag-struct.md)   
 [Struct iterator](../standard-library/iterator-struct.md)   
 [\<iterator>](../standard-library/iterator.md)   
 [Acesso Thread-Safe na Biblioteca Padrão C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Referência da biblioteca padrão C++](../standard-library/cpp-standard-library-reference.md)



