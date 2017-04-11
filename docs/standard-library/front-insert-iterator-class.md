---
title: Construtor front_insert_iterator | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iterator/std::front_insert_iterator
- std::front_insert_iterator
- std.front_insert_iterator
- front_insert_iterator
dev_langs:
- C++
helpviewer_keywords:
- front_insert_iterator class
ms.assetid: a9a9c075-136a-4419-928b-c4871afa033c
caps.latest.revision: 17
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
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 6468f372324cb6f62b5b09524cfbf5386b1502c6
ms.lasthandoff: 02/25/2017

---
# <a name="frontinsertiterator-class"></a>Classe front_insert_iterator
Descreve um adaptador de iterador que atende aos requisitos de um iterador de saída. Insere, em vez de substituições, elementos na frente de uma sequência e, dessa forma, fornece semânticas que são diferentes da semântica de substituição fornecida pelos iteradores dos contêineres de sequência do C++. A classe `front_insert_iterator` é modelada no tipo do contêiner.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
template <class Container>  
class front_insert_iterator;  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `Container`  
 O tipo de contêiner na parte da frente dos elementos a serem inseridos por um `front_insert_iterator`.  
  
## <a name="remarks"></a>Comentários  
 O contêiner deve atender aos requisitos de uma sequência de inserção anterior em que é possível inserir elementos no início da sequência em tempo constante amortizado. Os contêineres de sequência da Biblioteca Padrão C++ definidos pela [classe deque](../standard-library/deque-class.md) e pela [classe list](../standard-library/list-class.md) fornecem a função membro `push_front` necessária e atendem a esses requisitos. Por outro lado, contêineres de sequência definidos pela [classe vector](../standard-library/vector-class.md) não atendem a esses requisitos e não podem ser adaptados para uso com `front_insert_iterator`s. Um `front_insert_iterator` sempre deve ser inicializado com seu contêiner.  
  
### <a name="constructors"></a>Construtores  
  
|||  
|-|-|  
|[front_insert_iterator](#front_insert_iterator__front_insert_iterator)|Cria um iterador que pode inserir elementos na frente de um objeto de contêiner especificado.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[container_type](#front_insert_iterator__container_type)|Um tipo que representa o contêiner no qual uma inserção anterior deve ser feita.|  
|[reference](#front_insert_iterator__reference)|Um tipo que fornece uma referência a um elemento em uma sequência controlada pelo contêiner associado.|  
  
### <a name="operators"></a>Operadores  
  
|||  
|-|-|  
|[operator*](#front_insert_iterator__operator_star)|Operador de cancelamento de referência usado para implementar a expressão do iterador de saída * `i` = `x` para uma inserção anterior.|  
|[operator++](#front_insert_iterator__operator_add_add)|Incrementa o `front_insert_iterator` para o próximo local no qual um valor pode ser armazenado.|  
|[operator=](#front_insert_iterator__operator_eq)|Operador de atribuição usado para implementar a expressão do iterador de saída * `i` = `x` para uma inserção anterior.|  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho**: \<iterator>  
  
 **Namespace:** std  
  
##  <a name="front_insert_iterator__container_type"></a>  front_insert_iterator::container_type  
 Um tipo que representa o contêiner no qual uma inserção anterior deve ser feita.  
  
```  
typedef Container container_type;  
```  
  
### <a name="remarks"></a>Comentários  
 O tipo é um sinônimo do parâmetro de modelo **Container**.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// front_insert_iterator_container_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   list<int> L1;  
   front_insert_iterator<list<int> >::container_type L2 = L1;  
   front_inserter ( L2 ) = 20;  
   front_inserter ( L2 ) = 10;  
   front_inserter ( L2 ) = 40;  
  
   list <int>::iterator vIter;  
   cout << "The list L2 is: ( ";  
   for ( vIter = L2.begin ( ) ; vIter != L2.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L2 is: ( 40 10 20 ).  
*\  
```  
  
##  <a name="front_insert_iterator__front_insert_iterator"></a>  front_insert_iterator::front_insert_iterator  
 Cria um iterador que pode inserir elementos na frente de um objeto de contêiner especificado.  
  
```  
explicit front_insert_iterator(Container& _Cont);
```  
  
### <a name="parameters"></a>Parâmetros  
 `_Cont`  
 O objeto de contêiner no qual o `front_insert_iterator` deve inserir elementos.  
  
### <a name="return-value"></a>Valor de retorno  
 Um `front_insert_iterator` para o objeto de contêiner do parâmetro.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// front_insert_iterator_front_insert_iterator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
   list <int>::iterator L_Iter;  
  
   list<int> L;  
   for (i = -1 ; i < 9 ; ++i )    
   {  
      L.push_back ( 2 * i );  
   }  
  
   cout << "The list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
  
   // Using the member function to insert an element  
   front_inserter ( L ) = 20;  
  
   // Alternatively, one may use the template function  
   front_insert_iterator< list < int> > Iter(L);  
 *Iter = 30;  
  
   cout << "After the front insertions, the list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L is:  
 ( -2 0 2 4 6 8 10 12 14 16 ).  
After the front insertions, the list L is:  
 ( 30 20 -2 0 2 4 6 8 10 12 14 16 ).  
*\  
```  
  
##  <a name="front_insert_iterator__operator_star"></a>  front_insert_iterator::operator*  
 Cancela a referência do iterador de inserção, retornando o elemento que é seu alvo.  
  
```  
front_insert_iterator<Container>& operator*();
```  
  
### <a name="return-value"></a>Valor de retorno  
 A função membro retorna o valor do elemento de destino.  
  
### <a name="remarks"></a>Comentários  
 Usado para implementar a expressão do iterador de saída **\*Iter** = **value**. Se **Iter** for um iterador que trata de um elemento em uma sequência, **\*Iter** = **value** substituirá esse elemento pelo valor e não alterará o número total de elementos na sequência.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// front_insert_iterator_deref.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
   list <int>::iterator L_Iter;  
  
   list<int> L;  
   for ( i = -1 ; i < 9 ; ++i )   
   {  
      L.push_back ( 2 * i );  
   }  
  
   cout << "The list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
  
   front_insert_iterator< list < int> > Iter(L);  
 *Iter = 20;  
  
   // Alternatively, you may use  
   front_inserter ( L ) = 30;  
  
   cout << "After the front insertions, the list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L is:  
 ( -2 0 2 4 6 8 10 12 14 16 ).  
After the front insertions, the list L is:  
 ( 30 20 -2 0 2 4 6 8 10 12 14 16 ).  
*\  
```  
  
##  <a name="front_insert_iterator__operator_add_add"></a>  front_insert_iterator::operator++  
 Incrementa o `back_insert_iterator` para o próximo local no qual um valor pode ser armazenado.  
  
```  
front_insert_iterator<Container>& operator++();

front_insert_iterator<Container> operator++(int);
```  
  
### <a name="return-value"></a>Valor de retorno  
 Um `front_insert_iterator` que trata do próximo local no qual um valor pode ser armazenado.  
  
### <a name="remarks"></a>Comentários  
 Os operadores pré-incremento e pós-incremento retornam o mesmo resultado.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// front_insert_iterator_op_incre.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   list<int> L1;  
   front_insert_iterator<list<int> > iter ( L1 );  
 *iter = 10;  
   iter++;  
 *iter = 20;  
   iter++;  
 *iter = 30;  
   iter++;  
  
   list <int>::iterator vIter;  
   cout << "The list L1 is: ( ";  
   for ( vIter = L1.begin ( ) ; vIter != L1.end ( ); vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L1 is: ( 30 20 10 ).  
*\  
```  
  
##  <a name="front_insert_iterator__operator_eq"></a>  front_insert_iterator::operator=  
 Acrescenta (envia por push) um valor à frente do contêiner.  
  
```  
front_insert_iterator<Container>& operator=(typename Container::const_reference val);

front_insert_iterator<Container>& operator=(typename Container::value_type&& val);
```  
  
### <a name="parameters"></a>Parâmetros  
 `val`  
 O valor a ser atribuído ao contêiner.  
  
### <a name="return-value"></a>Valor de retorno  
 Uma referência ao último elemento inserido na frente do contêiner.  
  
### <a name="remarks"></a>Comentários  
 O primeiro operador membro avalia `container.push_front( val)` e retorna `*this`.  
  
 O segundo operador membro avalia  
  
 `container->push_front((typename Container::value_type&&) val)`,  
  
 em seguida, retorna `*this`.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// front_insert_iterator_op_assign.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   list<int> L1;  
   front_insert_iterator<list<int> > iter ( L1 );  
 *iter = 10;  
   iter++;  
 *iter = 20;  
   iter++;  
 *iter = 30;  
   iter++;  
  
   list <int>::iterator vIter;  
   cout << "The list L1 is: ( ";  
   for ( vIter = L1.begin ( ) ; vIter != L1.end ( ); vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L1 is: ( 30 20 10 ).  
*\  
```  
  
##  <a name="front_insert_iterator__reference"></a>  front_insert_iterator::reference  
 Um tipo que fornece uma referência a um elemento em uma sequência controlada pelo contêiner associado.  
  
```  
typedef typename Container::reference reference;  
```  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// front_insert_iterator_reference.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   list<int> L;  
   front_insert_iterator<list<int> > fiivIter( L );  
 *fiivIter = 10;  
 *fiivIter = 20;  
 *fiivIter = 30;  
  
   list<int>::iterator LIter;  
   cout << "The list L is: ( ";  
   for ( LIter = L.begin ( ) ; LIter != L.end ( ); LIter++)  
      cout << *LIter << " ";  
   cout << ")." << endl;  
  
   front_insert_iterator<list<int> >::reference   
        RefFirst = *(L.begin ( ));  
   cout << "The first element in the list L is: "   
        << RefFirst << "." << endl;  
}  
\* Output:   
The list L is: ( 30 20 10 ).  
The first element in the list L is: 30.  
*\  
```  
  
## <a name="see-also"></a>Consulte também  
 [\<iterator>](../standard-library/iterator.md)   
 [Acesso Thread-Safe na Biblioteca Padrão C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Referência da biblioteca padrão C++](../standard-library/cpp-standard-library-reference.md)

