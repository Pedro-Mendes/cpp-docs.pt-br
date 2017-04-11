---
title: Classe hash_map | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- stdext::hash_map
- hash_map/stdext::hash_map
- std.hash_map
- stdext.hash_map
- std::hash_map
- hash_map
dev_langs:
- C++
helpviewer_keywords:
- hash_map class
ms.assetid: 40879dfc-51ba-4a59-9f9e-26208de568a8
caps.latest.revision: 25
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
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: 21f5925e6b5e7ac3dcaa32262ad2c39eac4d6827
ms.lasthandoff: 02/25/2017

---
# <a name="hashmap-class"></a>Classe hash_map
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Armazena e recupera dados rapidamente de uma coleção em que cada elemento é um par que tem uma chave de classificação cujo valor é exclusivo, bem como um valor de dados associado.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
template <class Key,   
    class Type,   
    class Traits=hash_compare<Key, less<Key>>,   
    class Allocator=allocator<pair <const Key, Type>>>  
class hash_map  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `Key`  
 O tipo de dados da chave a ser armazenado no hash_map.  
  
 `Type`  
 O tipo de dados do elemento a ser armazenado no hash_map.  
  
 `Traits`  
 O tipo que inclui dois objetos de função: um da classe compare, para comparar dois valores de elemento como chaves de classificação para determinar sua ordem relativa e uma função de hash, que é um predicado unário que mapeia valores chave dos elementos para inteiros sem sinal do tipo `size_t`. Esse argumento é opcional e hash_compare< `Key`, less< `Key`> > é o valor padrão.  
  
 `Allocator`  
 O tipo que representa o objeto alocador armazenado que encapsula detalhes sobre a alocação e a desalocação de memória do hash_map. Esse argumento é opcional e o valor padrão é allocator<pair <const `Key`, `Type`>>.  
  
## <a name="remarks"></a>Comentários  
 O hash_map é:  
  
-   Um contêiner associativo, que é um contêiner de tamanho variável que oferece suporte à recuperação eficiente dos valores de elemento com base em um valor de chave associado.  
  
-   Reversível, pois fornece um iterador bidirecional para acessar seus elementos.  
  
-   Com hash, pois seus elementos são agrupados em buckets com base no valor de uma função de hash aplicada aos valores chave dos elementos.  
  
-   Exclusivo no sentido de que cada um de seus elementos deve ter uma chave exclusiva.  
  
-   Um contêiner de par associativo, pois seus valores de dados de elemento são distintos de seus valores de chave.  
  
-   Uma classe de modelo, pois a funcionalidade fornecida por ela é genérica e, portanto, independente do tipo de dados específico contido como elementos ou chaves. Os tipos de dados a serem usados para elementos e chaves são especificados como parâmetros no modelo de classe juntamente com o alocador e a função de comparação.  
  
 A principal vantagem do uso de hash em vez da classificação é a maior eficiência: um hash bem-sucedido executa inserções, exclusões e localizações em tempos médios constantes, em comparação com um tempo proporcional ao logaritmo do número de elementos no contêiner para técnicas de classificação. O valor de um elemento em um hash_map, mas não seu valor de chave associado, pode ser alterado diretamente. Em vez disso, os valores de chave associados aos elementos antigos devem ser excluídos e os novos valores de chave associados aos novos elementos inseridos.  
  
 A escolha do tipo de contêiner deve se basear, de modo geral, no tipo de pesquisa e inserção exigido pelo aplicativo. Contêineres associativos com hash são otimizados para as operações de pesquisa, inserção e remoção. As funções membro que dão suporte explicitamente a essas operações são eficientes quando usadas com uma função de hash bem elaborada, executando-as em um tempo que é, em média, constante e não dependente do número de elementos no contêiner. Uma função de hash bem elaborada produz uma distribuição uniforme de valores em hash e minimiza o número de colisões, em que uma colisão deve ocorrer quando valores de chave distintos são mapeados para o mesmo valor em hash. No pior caso, com a pior função de hash possível, o número de operações será proporcional ao número de elementos na sequência (tempo linear).  
  
 O hash_map deve ser o contêiner associativo escolhido quando as condições que associam os valores às respectivas chaves forem atendidas pelo aplicativo. Um modelo para esse tipo de estrutura é uma lista ordenada de palavras-chave que ocorrem uma única vez e com valores de cadeia de caracteres associados que forneçam definições. Se as palavras tiverem mais de uma definição correta, as chave não seriam exclusivas, de modo que um hash_multimap seria o contêiner ideal. Se, por outro lado, apenas as listas de palavras estavam sendo armazenadas, um hash_set seria o contêiner correto. Se forem permitidas várias ocorrências das palavras, um hash_multiset seria a estrutura de contêiner apropriada.  
  
 O hash_map ordena a sequência que controla chamando um objeto de hash `Traits` armazenado da classe [value_compare](../standard-library/value-compare-class.md). Esse objeto armazenado pode ser acessado chamando a função membro [key_comp](#hash_map__key_comp). Um objeto de função deve se comportar da mesma forma que um objeto da classe [hash_compare](../standard-library/hash-compare-class.md)<Key, less\<Key>>. Especificamente, para todos os valores de `Key` do tipo `Key`, a chamada `Traits`( `Key` ) produz uma distribuição de valores do tipo `size_t`.  
  
 De modo geral, os elementos precisam ser simplesmente menores que os comparáveis para estabelecer essa ordem: desse modo, considerando dois elementos, pode ser determinado que, ou eles são equivalentes (no sentido de que nenhum deles é menor que o outro), ou que um é menor que o outro. Isso resulta em uma ordenação entre os elementos não equivalentes. Fazendo uma observação mais técnica, a função de comparação é um predicado binário que induz a uma ordenação fraca restrita no sentido matemático padrão. Um predicado binário f(x,y) é um objeto de função que tem dois objetos de argumento `x` e `y` e um valor retornado de `true` ou `false`. Uma ordenação imposta a um hash_map será uma ordenação fraca restrita se o predicado binário for irreflexivo, antissimétrico e transitivo, e se a equivalência for transitiva, em que dois objetos x e y são definidos para serem equivalentes quando f( x, y) e f( y, x) forem falsos. Se a condição mais forte de igualdade entre as chaves substituir essa equivalência, a ordenação será total (no sentido de que todos os elementos serão ordenados um em relação ao outro) e as chaves correspondentes não poderão ser diferenciadas uma da outra.  
  
 A ordem real dos elementos na sequência controlada depende da função de hash, da função de ordenação e do tamanho atual da tabela de hash armazenada no objeto de contêiner. Não é possível determinar o tamanho atual da tabela de hash, portanto, de modo geral, não é possível prever a ordem dos elementos na sequência controlada. A inserção de elementos não invalida iteradores e a remoção de elementos invalida apenas os iteradores que apontavam especificamente os elementos removidos.  
  
 O iterador fornecido pela classe hash_map é um iterador bidirecional, mas as funções membro da classe [insert](#hash_map__insert) e [hash_map](#hash_map__hash_map) têm versões que usam como parâmetros de modelo um iterador de entrada mais fraco, cujos requisitos de funcionalidade são mais reduzidos do que os garantidos pela classe de iteradores bidirecionais. Os conceitos de iterador diferente formam uma família relacionada por refinamentos em sua funcionalidade. Cada conceito de iterador tem seu próprio conjunto de requisitos e os algoritmos que funcionam com eles devem limitar suas suposições para os requisitos fornecidos por esse tipo de iterador. Pode ser pressuposto que um iterador de entrada possa ser desreferenciado para fazer referência a algum objeto e que possa ser incrementado para o próximo iterador na sequência. Esse é um conjunto mínimo de funcionalidade, mas é suficiente para poder expressar de forma significativa um intervalo de iteradores `[First, Last)` no contexto de funções membro da classe.  
  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="constructors"></a>Construtores  
  
|||  
|-|-|  
|[hash_map](#hash_map__hash_map)|Constrói um `hash_map` que está vazio ou que é uma cópia de todo ou parte de algum outro `hash_map`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[allocator_type](#hash_map__allocator_type)|Um tipo que representa a classe `allocator` para o objeto `hash_map`.|  
|[const_iterator](#hash_map__const_iterator)|Um tipo que fornece um iterador bidirecional que pode ler um elemento `const` no `hash_map`.|  
|[const_pointer](#hash_map__const_pointer)|Um tipo que fornece um ponteiro para um elemento `const` em um `hash_map`.|  
|[const_reference](#hash_map__const_reference)|Um tipo que fornece uma referência para um elemento `const` armazenado em um `hash_map` para leitura e execução de operações `const`.|  
|[const_reverse_iterator](#hash_map__const_reverse_iterator)|Um tipo que fornece um iterador bidirecional que pode ler qualquer elemento `const` no `hash_map`.|  
|[difference_type](#hash_map__difference_type)|Um tipo de inteiro com sinal que pode ser usado para representar o número de elementos de um `hash_map` em um intervalo entre os elementos apontado pelos iteradores.|  
|[iterator](#hash_map__iterator)|Um tipo que fornece um iterador bidirecional que pode ler ou modificar qualquer elemento em um `hash_map`.|  
|[key_compare](#hash_map__key_compare)|Um tipo que fornece um objeto de função que pode comparar duas chaves de classificação para determinar a ordem relativa de dois elementos no `hash_map`.|  
|[key_type](#hash_map__key_type)|Um tipo que descreve o objeto de chave de classificação que constitui cada elemento do `hash_map`.|  
|[mapped_type](#hash_map__mapped_type)|Um tipo que representa o tipo de dados armazenado em um `hash_map`.|  
|[pointer](#hash_map__pointer)|Um tipo que fornece um ponteiro para um elemento em um `hash_map`.|  
|[reference](#hash_map__reference)|Um tipo que fornece uma referência a um elemento armazenado em um `hash_map`.|  
|[reverse_iterator](#hash_map__reverse_iterator)|Um tipo que fornece um iterador bidirecional que pode ler ou modificar um elemento em um `hash_map` invertido.|  
|[size_type](#hash_map__size_type)|Um tipo de inteiro sem sinal que pode representar o número de elementos em um `hash_map`.|  
|[value_type](#hash_map__value_type)|Um tipo que fornece um objeto de função que pode comparar dois elementos como chaves de classificação para determinar sua ordem relativa no `hash_map`.|  
  
### <a name="member-functions"></a>Funções membro  
  
|||  
|-|-|  
|[hash_map::at](#hash_map__at)|Localiza um elemento em um `hash_map` com um valor de chave especificado.|  
|[begin](#hash_map__begin)|Retorna um iterador que trata o primeiro elemento no `hash_map`.|  
|[hash_map::cbegin](#hash_map__cbegin)|Retorna um iterador const que trata o primeiro elemento no `hash_map`.|  
|[hash_map::cend](#hash_map__cend)|Retorna um iterador const que trata o local após o último elemento em um `hash_map`.|  
|[clear](#hash_map__clear)|Apaga todos os elementos de um `hash_map`.|  
|[count](#hash_map__count)|Retorna o número de elementos em um `hash_map` cuja chave corresponde a uma chave especificada pelo parâmetro.|  
|[hash_map::crbegin](#hash_map__crbegin)|Retorna um iterador const que trata o primeiro elemento em um `hash_map` invertido.|  
|[hash_map::crend](#hash_map__crend)|Retorna um iterador const que trata o local após o último elemento em um `hash_map` invertido.|  
|[hash_map::emplace](#hash_map__emplace)|Insere um elemento construído adequadamente em um `hash_map`.|  
|[hash_map::emplace_hint](#hash_map__emplace_hint)|Insere um elemento construído adequadamente em um `hash_map`, com uma dica de posicionamento.|  
|[empty](#hash_map__empty)|Testa se `hash_map` está vazio.|  
|[end](#hash_map__end)|Retorna um iterador que trata o local após o último elemento em um `hash_map`.|  
|[equal_range](#hash_map__equal_range)|Retorna um par de iteradores, respectivamente, para o primeiro elemento em um `hash_map` com uma chave que é maior do que uma chave especificada e para o primeiro elemento no `hash_map` com uma chave igual ou maior que a chave.|  
|[erase](#hash_map__erase)|Remove um elemento ou um intervalo de elementos em um `hash_map` das posições especificadas|  
|[find](#hash_map__find)|Retorna um iterador que trata do local de um elemento em um `hash_map` que tem uma chave equivalente a uma chave especificada.|  
|[get_allocator](#hash_map__get_allocator)|Retorna uma cópia do objeto `allocator` usada para construir o `hash_map`.|  
|[insert](#hash_map__insert)|Insere um elemento ou um intervalo de elementos em um `hash_map`.|  
|[key_comp](#hash_map__key_comp)|Retorna um iterador para o primeiro elemento em um `hash_map` com um valor de chave que é igual ou maior que uma chave especificada.|  
|[lower_bound](#hash_map__lower_bound)|Retorna um iterador para o primeiro elemento em um `hash_map` com um valor de chave que é igual ou maior que uma chave especificada.|  
|[max_size](#hash_map__max_size)|Retorna o comprimento máximo do `hash_map`.|  
|[rbegin](#hash_map__rbegin)|Retorna um iterador que trata o primeiro elemento em um `hash_map` invertido.|  
|[rend](#hash_map__rend)|Retorna um iterador que trata o local após o último elemento em um `hash_map` invertido.|  
|[size](#hash_map__size)|Retorna o número de elementos no `hash_map`.|  
|[swap](#hash_map__swap)|Troca os elementos de dois `hash_map`s.|  
|[upper_bound](#hash_map__upper_bound)|Retorna um iterador para o primeiro elemento em um `hash_map` que tem um valor de chave que é maior que uma chave especificada.|  
|[value_comp](#hash_map__value_comp)|Recupera uma cópia do objeto de comparação usado para ordenar valores de elemento em um `hash_map`.|  
  
### <a name="operators"></a>Operadores  
  
|||  
|-|-|  
|[operator&#91;&#93;](#hash_map__operator_at)|Insere um elemento em um `hash_map` com um valor de chave especificado.|  
|[hash_map::operator=](#hash_map__operator_eq)|Substitui os elementos de um `hash_map` por uma cópia de outro `hash_map`.|  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** \<hash_map>  
  
 **Namespace:** stdext  
  
##  <a name="a-namehashmapallocatortypea--hashmapallocatortype"></a><a name="hash_map__allocator_type"></a>  hash_map::allocator_type  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Um tipo que representa a classe allocator do objeto hash_map.  
  
```  
typedef list<typename Traits::value_type, typename Traits::allocator_type>::allocator_type allocator_type;  
```  
  
### <a name="example"></a>Exemplo  
  Consulte o exemplo para [get_allocator](#hash_map__get_allocator) para obter um exemplo do uso de `allocator_type`.  
  
##  <a name="a-namehashmapata--hashmapat"></a><a name="hash_map__at"></a>  hash_map::at  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Localiza um elemento em um hash_map com um valor de chave especificado.  
  
```  
Type& at(const Key& key);

const Type& at(const Key& key) const;
```  
  
### <a name="parameters"></a>Parâmetros  
  
|||  
|-|-|  
|Parâmetro|Descrição|  
|` key`|O valor de chave do elemento que deve ser encontrado.|  
  
### <a name="return-value"></a>Valor de retorno  
 Uma referência ao valor de dados do elemento encontrado.  
  
### <a name="remarks"></a>Comentários  
 Se o valor de chave do argumento não for encontrado, a função gerará um objeto da [Classe out_of_range](../standard-library/out-of-range-class.md).  
  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// hash_map_at.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   typedef pair <const int, int> cInt2Int;  
   hash_map <int, int> hm1;  
  
   // Insert data values  
   hm1.insert ( cInt2Int ( 1, 10 ) );  
   hm1.insert ( cInt2Int ( 2, 20 ) );  
   hm1.insert ( cInt2Int ( 3, 30 ) );  
  
   cout  << "The values of the mapped elements are:";  
   for ( int i = 1 ; i <= hm1.size() ; i++ )  
      cout << " " << hm1.at(i);  
   cout << "." << endl;  
}  
```  
  
##  <a name="a-namehashmapbegina--hashmapbegin"></a><a name="hash_map__begin"></a>  hash_map::begin  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Retorna um iterador que trata do primeiro elemento no hash_map.  
  
```  
const_iterator begin() const;

iterator begin();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Um iterador bidirecional que trata do primeiro elemento no hash_map ou no local que sucede um hash_map vazio.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// hash_map_begin.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_map <int, int> hm1;  
  
   hash_map <int, int> :: iterator hm1_Iter;  
   hash_map <int, int> :: const_iterator hm1_cIter;  
   typedef pair <int, int> Int_Pair;  
  
   hm1.insert ( Int_Pair ( 0, 0 ) );  
   hm1.insert ( Int_Pair ( 1, 1 ) );  
   hm1.insert ( Int_Pair ( 2, 4 ) );  
  
   hm1_cIter = hm1.begin ( );  
   cout << "The first element of hm1 is "   
        << hm1_cIter -> first << "." << endl;  
  
   hm1_Iter = hm1.begin ( );  
   hm1.erase ( hm1_Iter );  
  
   // The following 2 lines would err because the iterator is const  
   // hm1_cIter = hm1.begin ( );  
   // hm1.erase ( hm1_cIter );  
  
   hm1_cIter = hm1.begin( );  
   cout << "The first element of hm1 is now "   
        << hm1_cIter -> first << "." << endl;  
}  
```  
  
```Output  
The first element of hm1 is 0.  
The first element of hm1 is now 1.  
```  
  
##  <a name="a-namehashmapcbegina--hashmapcbegin"></a><a name="hash_map__cbegin"></a>  hash_map::cbegin  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Retorna um iterador const que trata do primeiro elemento no hash_map.  
  
```  
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Valor de retorno  
 Um iterador bidirecional const que trata do primeiro elemento no [hash_map](../standard-library/hash-map-class.md) ou do local que sucede um `hash_map` vazio.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// hash_map_cbegin.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_map <int, int> hm1;  
  
   hash_map <int, int> :: const_iterator hm1_cIter;  
   typedef pair <int, int> Int_Pair;  
  
   hm1.insert ( Int_Pair ( 2, 4 ) );  
  
   hm1_cIter = hm1.cbegin ( );  
   cout << "The first element of hm1 is "   
        << hm1_cIter -> first << "." << endl;  
   }  
```  
  
```Output  
The first element of hm1 is 2.  
```  
  
##  <a name="a-namehashmapcenda--hashmapcend"></a><a name="hash_map__cend"></a>  hash_map::cend  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Retorna um iterador const que trata do local após o último elemento em um hash_map.  
  
```  
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Valor de retorno  
 Um iterador bidirecional const que trata do local após o último elemento em um [hash_map](../standard-library/hash-map-class.md). Se o `hash_map` estiver vazio, então `hash_map::cend == hash_map::begin`.  
  
### <a name="remarks"></a>Comentários  
 `cend` é usado para testar se um iterador atingiu o fim de seu `hash_map`.  
  
 O valor retornado por `cend` não deve ser desreferenciado.  
  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// hash_map_cend.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   using namespace stdext;  
   hash_map <int, int> hm1;  
  
   hash_map <int, int> :: const_iterator hm1_cIter;  
   typedef pair <int, int> Int_Pair;  
  
   hm1.insert ( Int_Pair ( 3, 30 ) );  
  
   hm1_cIter = hm1.cend( );  
   hm1_cIter--;  
   cout << "The value of last element of hm1 is "   
        << hm1_cIter -> second << "." << endl;  
   }  
```  
  
```Output  
The value of last element of hm1 is 30.  
```  
  
##  <a name="a-namehashmapcleara--hashmapclear"></a><a name="hash_map__clear"></a>  hash_map::clear  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Apaga todos os elementos de um hash_map.  
  
```  
void clear();
```  
  
### <a name="remarks"></a>Comentários  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  O exemplo a seguir demonstra o uso da função membro hash_map::clear.  
  
```  
// hash_map_clear.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
    using namespace std;  
    using namespace stdext;  
    hash_map<int, int> hm1;  
    hash_map<int, int>::size_type i;  
    typedef pair<int, int> Int_Pair;  
  
    hm1.insert(Int_Pair(1, 1));  
    hm1.insert(Int_Pair(2, 4));  
  
    i = hm1.size();  
    cout << "The size of the hash_map is initially "  
         << i << "." << endl;  
  
    hm1.clear();  
    i = hm1.size();  
    cout << "The size of the hash_map after clearing is "  
         << i << "." << endl;  
}  
```  
  
```Output  
The size of the hash_map is initially 2.  
The size of the hash_map after clearing is 0.  
```  
  
##  <a name="a-namehashmapconstiteratora--hashmapconstiterator"></a><a name="hash_map__const_iterator"></a>  hash_map::const_iterator  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Um tipo que fornece um iterador bidirecional que pode ler um elemento **const** no hash_map.  
  
```  
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_iterator const_iterator;  
```  
  
### <a name="remarks"></a>Comentários  
 Um tipo de `const_iterator` não pode ser usado para modificar o valor de um elemento.  
  
 O `const_iterator` definido pelo hash_map aponta para elementos que são objetos de [value_type](#hash_map__value_type), que é do tipo `pair`*\<***const Key, Type***>*, cujo primeiro membro é a chave do elemento e cujo segundo membro é a referência mapeada mantida pelo elemento.  
  
 Para desreferenciar um `const_iterator``cIter` que aponta para um elemento em um hash_map, use o operador **->**.  
  
 Para acessar o valor de chave do elemento, use `cIter` **-> first**, que é equivalente a (\* `cIter`) **.first**. Para acessar o valor da referência mapeada do elemento, use `cIter` **-> second**, que é equivalente a (\* `cIter`) **.second**.  
  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  Consulte o exemplo para [begin](#hash_map__begin) para obter um exemplo que usa `const_iterator`.  
  
##  <a name="a-namehashmapconstpointera--hashmapconstpointer"></a><a name="hash_map__const_pointer"></a>  hash_map::const_pointer  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Um tipo que fornece um ponteiro para um elemento **const** em um hash_map.  
  
```  
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::const_pointer const_pointer;  
```  
  
### <a name="remarks"></a>Comentários  
 Um tipo de `const_pointer` não pode ser usado para modificar o valor de um elemento.  
  
 Na maioria dos casos, um [iterador](#hash_map__iterator) deve ser usado para acessar os elementos em um objeto hash_map.  
  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
##  <a name="a-namehashmapconstreferencea--hashmapconstreference"></a><a name="hash_map__const_reference"></a>  hash_map::const_reference  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Um tipo que fornece uma referência a um elemento **const** armazenado em um hash_map para leitura e execução de operações **const**.  
  
```  
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::const_reference const_reference;  
```  
  
### <a name="remarks"></a>Comentários  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// hash_map_const_ref.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_map<int, int> hm1;  
   typedef pair <int, int> Int_Pair;  
  
   hm1.insert ( Int_Pair ( 1, 10 ) );  
   hm1.insert ( Int_Pair ( 2, 20 ) );  
  
   // Declare and initialize a const_reference &Ref1   
   // to the key of the first element  
   const int &Ref1 = ( hm1.begin( ) -> first );  
  
   // The following line would cause an error because the   
   // non-const_reference cannot be used to access the key  
   // int &Ref1 = ( hm1.begin( ) -> first );  
  
   cout << "The key of the first element in the hash_map is "  
        << Ref1 << "." << endl;  
  
   // Declare and initialize a reference &Ref2   
   // to the data value of the first element  
   int &Ref2 = ( hm1.begin( ) -> second );  
  
   cout << "The data value of the first element in the hash_map is "  
        << Ref2 << "." << endl;  
}  
```  
  
```Output  
The key of the first element in the hash_map is 1.  
The data value of the first element in the hash_map is 10.  
```  
  
##  <a name="a-namehashmapconstreverseiteratora--hashmapconstreverseiterator"></a><a name="hash_map__const_reverse_iterator"></a>  hash_map::const_reverse_iterator  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Um tipo que fornece um iterador bidirecional que pode ler qualquer elemento **const** no hash_map.  
  
```  
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_reverse)iterator const_reverse_iterator;  
```  
  
### <a name="remarks"></a>Comentários  
 Um tipo `const_reverse_iterator` não pode modificar o valor de um elemento e é usado para iterar no hash_map em ordem inversa.  
  
 O `const_reverse_iterator` definido por hash_map aponta para elementos que são objetos de [value_type](#hash_map__value_type), que é do tipo `pair`\< **const Key, Type**>, cujo primeiro membro é a chave do elemento e cujo segundo membro é a referência mapeada mantida pelo elemento.  
  
 Para desreferenciar um `const_reverse_iterator``crIter` que aponta para um elemento em um hash_map, use o operador **->**.  
  
 Para acessar o valor da chave do elemento, use `crIter` -> **first**, que é equivalente a (\* `crIter`) **.first**. Para acessar o valor dos dados mapeados do elemento, use `crIter` -> **second**, que é equivalente a (\* `crIter`). **first**.  
  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  Veja o exemplo de [rend](#hash_map__rend) para obter um exemplo de como declarar e usar o `const_reverse_iterator`.  
  
##  <a name="a-namehashmapcounta--hashmapcount"></a><a name="hash_map__count"></a>  hash_map::count  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Retorna o número de elementos em um hash_map cuja chave corresponde a uma chave especificada pelo parâmetro.  
  
```  
size_type count(const Key& key) const;
```  
  
### <a name="parameters"></a>Parâmetros  
 ` key`  
 O valor de chave dos elementos a serem correspondidos do hash_map.  
  
### <a name="return-value"></a>Valor de retorno  
 1 se o hash_map tiver um elemento cuja chave de classificação corresponde à chave de parâmetro; 0 se o hash_map não tiver um elemento com uma chave correspondente.  
  
### <a name="remarks"></a>Comentários  
 A função membro retorna o número de elementos *x* no intervalo  
  
 [ `lower_bound` (_ *Key* ), `upper_bound` (\_ *Key* ) )  
  
 que será 0 ou 1, no caso do hash_map, que é um contêiner associativo exclusivo.  
  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  O exemplo a seguir demonstra o uso da função membro hash_map::count.  
  
```  
// hash_map_count.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    using namespace stdext;  
    hash_map<int, int> hm1;  
    hash_map<int, int>::size_type i;  
    typedef pair<int, int> Int_Pair;  
  
    hm1.insert(Int_Pair (1, 1));  
    hm1.insert(Int_Pair (2, 1));  
    hm1.insert(Int_Pair (1, 4));  
    hm1.insert(Int_Pair (2, 1));  
  
    // Keys must be unique in hash_map, so duplicates are ignored  
    i = hm1.count(1);  
    cout << "The number of elements in hm1 with a sort key of 1 is: "  
         << i << "." << endl;  
  
    i = hm1.count(2);  
    cout << "The number of elements in hm1 with a sort key of 2 is: "  
         << i << "." << endl;  
  
    i = hm1.count(3);  
    cout << "The number of elements in hm1 with a sort key of 3 is: "  
         << i << "." << endl;  
}  
```  
  
```Output  
The number of elements in hm1 with a sort key of 1 is: 1.  
The number of elements in hm1 with a sort key of 2 is: 1.  
The number of elements in hm1 with a sort key of 3 is: 0.  
```  
  
##  <a name="a-namehashmapcrbegina--hashmapcrbegin"></a><a name="hash_map__crbegin"></a>  hash_map::crbegin  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Retorna um iterador const que trata do primeiro elemento em um hash_map invertido.  
  
```  
const_reverse_iterator crbegin() const;
```  
  
### <a name="return-value"></a>Valor de retorno  
 Um iterador bidirecional invertido const que trata do primeiro elemento em um [hash_map](../standard-library/hash-map-class.md) invertido ou que trata do que foi o último elemento do `hash_map` não invertido.  
  
### <a name="remarks"></a>Comentários  
 `crbegin` é usado com um hash_map invertido, assim como [begin](#hash_map__begin) é usado com um `hash_map`.  
  
 Com o valor de retorno `crbegin`, o objeto `hash_map` não pode ser modificado.  
  
 `crbegin` pode ser usado para iterar em um `hash_map` no sentido inverso.  
  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// hash_map_crbegin.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_map <int, int> hm1;  
  
   hash_map <int, int> :: const_reverse_iterator hm1_crIter;  
   typedef pair <int, int> Int_Pair;  
  
   hm1.insert ( Int_Pair ( 3, 30 ) );  
  
   hm1_crIter = hm1.crbegin( );  
   cout << "The first element of the reversed hash_map hm1 is "  
        << hm1_crIter -> first << "." << endl;  
}  
```  
  
```Output  
The first element of the reversed hash_map hm1 is 3.  
```  
  
##  <a name="a-namehashmapcrenda--hashmapcrend"></a><a name="hash_map__crend"></a>  hash_map::crend  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Retorna um iterador const que trata do local após o último elemento em um hash_map invertido.  
  
```  
const_reverse_iterator crend() const;
```  
  
### <a name="return-value"></a>Valor de retorno  
 Um iterador bidirecional inverso const que trata da localização que vem após o último elemento em um [hash_map](../standard-library/hash-map-class.md) invertido (o local que precedeu o primeiro elemento no `hash_map` não invertido).  
  
### <a name="remarks"></a>Comentários  
 `crend` é usado com um `hash_map` invertido, assim como [hash_map::end](#hash_map__end) é usado com um `hash_map`.  
  
 Com o valor de retorno `crend`, o objeto `hash_map` não pode ser modificado.  
  
 `crend` pode ser usado para testar se um iterador inverso alcançou o final de sua `hash_map`.  
  
 O valor retornado por `crend` não deve ser desreferenciado.  
  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// hash_map_crend.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_map <int, int> hm1;  
  
   hash_map <int, int> :: const_reverse_iterator hm1_crIter;  
   typedef pair <int, int> Int_Pair;  
  
   hm1.insert ( Int_Pair ( 3, 30 ) );  
  
   hm1_crIter = hm1.crend( );  
   hm1_crIter--;  
   cout << "The last element of the reversed hash_map hm1 is "  
        << hm1_crIter -> first << "." << endl;  
}  
```  
  
```Output  
The last element of the reversed hash_map hm1 is 3.  
```  
  
##  <a name="a-namehashmapdifferencetypea--hashmapdifferencetype"></a><a name="hash_map__difference_type"></a>  hash_map::difference_type  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Um tipo de inteiro com sinal que pode ser usado para representar o número de elementos de um hash_map em um intervalo entre os elementos apontado pelos iteradores.  
  
```  
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::difference_type difference_type;  
```  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// hash_map_diff_type.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <hash_map>  
#include <algorithm>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_map <int, int> hm1;  
   typedef pair <int, int> Int_Pair;  
  
   hm1.insert ( Int_Pair ( 2, 20 ) );  
   hm1.insert ( Int_Pair ( 1, 10 ) );  
   hm1.insert ( Int_Pair ( 3, 20 ) );  
  
   // The following won't insert, because map keys are unique  
   hm1.insert ( Int_Pair ( 2, 30 ) );     
  
   hash_map <int, int>::iterator hm1_Iter, hm1_bIter, hm1_eIter;     
   hm1_bIter = hm1.begin( );  
   hm1_eIter = hm1.end( );  
  
   // Count the number of elements in a hash_map   
   hash_map <int, int>::difference_type  df_count = 0;  
   hm1_Iter = hm1.begin( );  
   while ( hm1_Iter != hm1_eIter)     
   {  
      df_count++;  
      hm1_Iter++;  
   }  
  
   cout << "The number of elements in the hash_map hm1 is: "   
        << df_count << "." << endl;  
  
   cout  << "The keys of the mapped elements are:";  
   for ( hm1_Iter= hm1.begin( ) ; hm1_Iter!= hm1.end( ) ;  
         hm1_Iter++)  
      cout << " " << hm1_Iter-> first;  
   cout << "." << endl;  
  
   cout  << "The values of the mapped elements are:";  
   for ( hm1_Iter= hm1.begin( ) ; hm1_Iter!= hm1.end( ) ;  
         hm1_Iter++)  
      cout << " " << hm1_Iter-> second;  
   cout << "." << endl;  
}  
```  
  
```Output  
The number of elements in the hash_map hm1 is: 3.  
The keys of the mapped elements are: 1 2 3.  
The values of the mapped elements are: 10 20 20.  
```  
  
##  <a name="a-namehashmapemplacea--hashmapemplace"></a><a name="hash_map__emplace"></a>  hash_map::emplace  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Insere um elemento construído em um hash_map.  
  
```  
template <class ValTy>  
pair <iterator, bool>  
emplace(
    ValTy&& val);
```  
  
### <a name="parameters"></a>Parâmetros  
  
|||  
|-|-|  
|Parâmetro|Descrição|  
|` val`|O valor usado para construir um elemento a ser inserido no [hash_map](../standard-library/hash-map-class.md), a menos que o `hash_map` já contenha o elemento (ou, de modo geral, um elemento cuja chave seja ordenada de maneira equivalente).|  
  
### <a name="return-value"></a>Valor de retorno  
 A função membro `emplace` retorna um par cujo componente booliano retorna verdadeiro se uma inserção tiver sido feita e falso se o `hash_map` já contivesse um elemento cuja chave tinha um valor equivalente na ordenação e cujo componente do iterador retorna o endereço em que um novo elemento foi inserido ou onde o elemento já estava localizado.  
  
 Para acessar o componente do iterador de um par `pr` retornado por essa função membro, use `pr.first` e, para desreferenciar, use `*(pr.first)`. Para acessar o componente `bool` de um par `pr` retornado por essa função membro, use `pr.second` e, para desreferenciar, use `*(pr.second)`.  
  
### <a name="remarks"></a>Comentários  
 O [hash_map::value_type](#hash_map__value_type) de um elemento é um par, de forma que o valor de um elemento será um par ordenado com o primeiro componente igual ao valor de chave e o segundo componente igual ao valor dos dados do elemento.  
  
 A partir do Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// hash_map_emplace.cpp  
// compile with: /EHsc  
#include<hash_map>  
#include<iostream>  
#include <string>  
  
int main()  
{  
    using namespace std;  
    using namespace stdext;  
    hash_map<int, string> hm1;  
    typedef pair<int, string> is1(1, "a");  
  
    hm1.emplace(move(is1));  
    cout << "After the emplace insertion, hm1 contains:" << endl  
      << " " << hm1.begin()->first  
      << " => " << hm1.begin()->second  
      << endl;  
}  
```  
  
```Output  
After the emplace insertion, hm1 contains:  
 1 => a  
```  
  
##  <a name="a-namehashmapemplacehinta--hashmapemplacehint"></a><a name="hash_map__emplace_hint"></a>  hash_map::emplace_hint  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Insere um elemento construído no hash_map, com uma dica de posicionamento.  
  
```  
template <class ValTy>  
iterator emplace_hint(
    const_iterator _Where,  
    ValTy&& val);
```  
  
### <a name="parameters"></a>Parâmetros  
  
|||  
|-|-|  
|Parâmetro|Descrição|  
|` val`|O valor usado para construir um elemento a ser inserido no [hash_map](../standard-library/hash-map-class.md), a menos que o `hash_map` já contenha o elemento (ou, de modo geral, um elemento cuja chave seja ordenada de maneira equivalente).|  
|`_Where`|Uma dica relacionada ao local do qual se começa a procurar pelo ponto de inserção correto.|  
  
### <a name="return-value"></a>Valor de retorno  
 A função membro [hash_multimap::emplace](../standard-library/hash-multimap-class.md#hash_multimap__emplace) retorna um iterador que aponta para a posição em que o novo elemento foi inserido no `hash_map` ou em que o elemento existente com uma ordenação equivalente está localizado.  
  
### <a name="remarks"></a>Comentários  
 O [hash_map::value_type](#hash_map__value_type) de um elemento é um par, de forma que o valor de um elemento será um par ordenado com o primeiro componente igual ao valor de chave e o segundo componente igual ao valor dos dados do elemento.  
  
 A inserção poderá ocorrer em um tempo constante amortizado, em vez de no tempo logarítmico, se o ponto de inserção seguir `_Where` imediatamente.  
  
 A partir do Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// hash_map_emplace_hint.cpp  
// compile with: /EHsc  
#include<hash_map>  
#include<iostream>  
#include <string>  
  
int main()  
{  
    using namespace std;  
    using namespace stdext;  
    hash_map<int, string> hm1;  
    typedef pair<int, string> is1(1, "a");  
  
    hm1.emplace(hm1.begin(), move(is1));  
    cout << "After the emplace, hm1 contains:" << endl  
      << " " << hm1.begin()->first  
      << " => " << hm1.begin()->second  
      << endl;  
}  
```  
  
```Output  
After the emplace insertion, hm1 contains:  
 1 => a  
```  
  
##  <a name="a-namehashmapemptya--hashmapempty"></a><a name="hash_map__empty"></a>  hash_map::empty  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Testa se um hash_map está vazio.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>Valor de retorno  
 **true** se o hash_map estiver vazio; **false** se o hash_map não estiver vazio.  
  
### <a name="remarks"></a>Comentários  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// hash_map_empty.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_map <int, int> hm1, hm2;  
  
   typedef pair <int, int> Int_Pair;  
   hm1.insert ( Int_Pair ( 1, 1 ) );  
  
   if ( hm1.empty( ) )  
      cout << "The hash_map hm1 is empty." << endl;  
   else  
      cout << "The hash_map hm1 is not empty." << endl;  
  
   if ( hm2.empty( ) )  
      cout << "The hash_map hm2 is empty." << endl;  
   else  
      cout << "The hash_map hm2 is not empty." << endl;  
}  
```  
  
```Output  
The hash_map hm1 is not empty.  
The hash_map hm2 is empty.  
```  
  
##  <a name="a-namehashmapenda--hashmapend"></a><a name="hash_map__end"></a>  hash_map::end  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Retorna um iterador que trata do local após o último elemento em um hash_map.  
  
```  
const_iterator end() const;

iterator end();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Um iterador bidirecional que trata do local após o último elemento em um hash_map. Se o hash_map estiver vazio, então hash_map::end == hash_map::begin.  
  
### <a name="remarks"></a>Comentários  
 **end** é usado para testar se um iterador atingiu o fim de seu hash_map.  
  
 O valor retornado por **end** não deve ser desreferenciado.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// hash_map_end.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   using namespace stdext;  
   hash_map <int, int> hm1;  
  
   hash_map <int, int> :: iterator hm1_Iter;  
   hash_map <int, int> :: const_iterator hm1_cIter;  
   typedef pair <int, int> Int_Pair;  
  
   hm1.insert ( Int_Pair ( 1, 10 ) );  
   hm1.insert ( Int_Pair ( 2, 20 ) );  
   hm1.insert ( Int_Pair ( 3, 30 ) );  
  
   hm1_cIter = hm1.end( );  
   hm1_cIter--;  
   cout << "The value of last element of hm1 is "   
        << hm1_cIter -> second << "." << endl;  
  
   hm1_Iter = hm1.end( );  
   hm1_Iter--;  
   hm1.erase ( hm1_Iter );  
  
   // The following 2 lines would err because the iterator is const  
   // hm1_cIter = hm1.end ( );  
   // hm1_cIter--;  
   // hm1.erase ( hm1_cIter );  
  
   hm1_cIter = hm1.end( );  
   hm1_cIter--;  
   cout << "The value of last element of hm1 is now "  
        << hm1_cIter -> second << "." << endl;  
}  
```  
  
```Output  
The value of last element of hm1 is 30.  
The value of last element of hm1 is now 20.  
```  
  
##  <a name="a-namehashmapequalrangea--hashmapequalrange"></a><a name="hash_map__equal_range"></a>  hash_map::equal_range  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Retorna um par de iteradores respectivamente para o primeiro elemento em um hash_map com uma chave que é maior do que uma chave especificada e para o primeiro elemento no hash_map com uma chave igual ou maior que a chave.  
  
```  
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```  
  
### <a name="parameters"></a>Parâmetros  
 ` key`  
 O valor de chave do argumento a ser comparado com a chave de classificação de um elemento do hash_map que está sendo pesquisado.  
  
### <a name="return-value"></a>Valor de retorno  
 Um par de iteradores em que o primeiro é o [lower_bound](#hash_map__lower_bound) da chave e o segundo é o [upper_bound](#hash_map__upper_bound) da chave.  
  
 Para acessar o primeiro iterador de um par `pr` retornado pela função membro, use `pr`. **first** e para desreferenciar o iterador de limite inferior, use \*( `pr`. **first**). Para acessar o segundo iterador de um par `pr` retornado pela função membro, use `pr`. **second** e para desreferenciar o iterador de limite superior, use \*( `pr`. **second**).  
  
### <a name="remarks"></a>Comentários  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// hash_map_equal_range.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   typedef hash_map <int, int> IntMap;  
   IntMap hm1;  
   hash_map <int, int> :: const_iterator hm1_RcIter;  
   typedef pair <int, int> Int_Pair;  
  
   hm1.insert ( Int_Pair ( 1, 10 ) );  
   hm1.insert ( Int_Pair ( 2, 20 ) );  
   hm1.insert ( Int_Pair ( 3, 30 ) );  
  
   pair <IntMap::const_iterator, IntMap::const_iterator> p1, p2;  
   p1 = hm1.equal_range( 2 );  
  
   cout << "The lower bound of the element with "  
        << "a key of 2 in the hash_map hm1 is: "  
        << p1.first -> second << "." << endl;  
  
   cout << "The upper bound of the element with "  
        << "a key of 2 in the hash_map hm1 is: "  
        << p1.second -> second << "." << endl;  
  
   // Compare the upper_bound called directly   
   hm1_RcIter = hm1.upper_bound( 2 );  
  
   cout << "A direct call of upper_bound( 2 ) gives "  
        << hm1_RcIter -> second << "," << endl  
        << " matching the 2nd element of the pair"  
        << " returned by equal_range( 2 )." << endl;  
  
   p2 = hm1.equal_range( 4 );  
  
   // If no match is found for the key,  
   // both elements of the pair return end( )  
   if ( ( p2.first == hm1.end( ) ) && ( p2.second == hm1.end( ) ) )  
      cout << "The hash_map hm1 doesn't have an element "  
             << "with a key less than 40." << endl;  
   else  
      cout << "The element of hash_map hm1 with a key >= 40 is: "  
           << p1.first -> first << "." << endl;  
}  
```  
  
```Output  
The lower bound of the element with a key of 2 in the hash_map hm1 is: 20.  
The upper bound of the element with a key of 2 in the hash_map hm1 is: 30.  
A direct call of upper_bound( 2 ) gives 30,  
 matching the 2nd element of the pair returned by equal_range( 2 ).  
The hash_map hm1 doesn't have an element with a key less than 40.  
```  
  
##  <a name="a-namehashmaperasea--hashmaperase"></a><a name="hash_map__erase"></a>  hash_map::erase  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Remove um elemento ou um intervalo de elementos em um hash_map das posições especificadas ou remove elementos que correspondem a uma chave especificada.  
  
```  
iterator erase(iterator _Where);

iterator erase(iterator first, iterator last);

size_type erase(const key_type& key);
```  
  
### <a name="parameters"></a>Parâmetros  
 `_Where`  
 Posição do elemento a ser removido do hash_map.  
  
 ` first`  
 Posição do primeiro elemento removido do hash_map.  
  
 ` last`  
 Posição logo após o último elemento removido do hash_map.  
  
 ` key`  
 O valor de chave dos elementos a serem removidos do hash_map.  
  
### <a name="return-value"></a>Valor de retorno  
 Para as duas primeiras funções membro, um iterador bidirecional que designa o primeiro elemento restante além de qualquer elemento removido ou um ponteiro para o final do hash_map, se não houver tal elemento.  
  
 Para a terceira função membro, ele retorna o número de elementos que foram removidos do hash_map.  
  
### <a name="remarks"></a>Comentários  
 As funções membro nunca geram uma exceção.  
  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  O exemplo a seguir demonstra o uso da função membro hash_map::erase.  
  
```  
// hash_map_erase.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    using namespace stdext;  
    hash_map<int, int> hm1, hm2, hm3;  
    hash_map<int, int> :: iterator pIter, Iter1, Iter2;  
    int i;  
    hash_map<int, int>::size_type n;  
    typedef pair<int, int> Int_Pair;  
  
    for (i = 1; i < 5; i++)  
    {  
        hm1.insert(Int_Pair (i, i));  
        hm2.insert(Int_Pair (i, i*i));  
        hm3.insert(Int_Pair (i, i-1));  
    }  
  
    // The 1st member function removes an element at a given position  
    Iter1 = ++hm1.begin();  
    hm1.erase(Iter1);  
  
    cout << "After the 2nd element is deleted, the hash_map hm1 is:";  
    for (pIter = hm1.begin(); pIter != hm1.end(); pIter++)  
        cout << " " << pIter -> second;  
    cout << "." << endl;  
  
    // The 2nd member function removes elements  
    // in the range [ first,  last)  
    Iter1 = ++hm2.begin();  
    Iter2 = --hm2.end();  
    hm2.erase(Iter1, Iter2);  
  
    cout << "After the middle two elements are deleted, "  
         << "the hash_map hm2 is:";  
    for (pIter = hm2.begin(); pIter != hm2.end(); pIter++)  
        cout << " " << pIter -> second;  
    cout << "." << endl;  
  
    // The 3rd member function removes elements with a given  key  
    n = hm3.erase(2);  
  
    cout << "After the element with a key of 2 is deleted,\n"  
         << "the hash_map hm3 is:";  
    for (pIter = hm3.begin(); pIter != hm3.end(); pIter++)  
        cout << " " << pIter -> second;  
    cout << "." << endl;  
  
    // The 3rd member function returns the number of elements removed  
    cout << "The number of elements removed from hm3 is: "  
         << n << "." << endl;  
  
    // The dereferenced iterator can also be used to specify a key  
    Iter1 = ++hm3.begin();  
    hm3.erase(Iter1);  
  
    cout << "After another element with a key equal to that"  
         << endl;  
    cout  << "of the 2nd element is deleted, "  
          << "the hash_map hm3 is:";  
    for (pIter = hm3.begin(); pIter != hm3.end(); pIter++)  
        cout << " " << pIter -> second;  
    cout << "." << endl;  
}  
```  
  
```Output  
After the 2nd element is deleted, the hash_map hm1 is: 1 3 4.  
After the middle two elements are deleted, the hash_map hm2 is: 1 16.  
After the element with a key of 2 is deleted,  
the hash_map hm3 is: 0 2 3.  
The number of elements removed from hm3 is: 1.  
After another element with a key equal to that  
of the 2nd element is deleted, the hash_map hm3 is: 0 3.  
```  
  
##  <a name="a-namehashmapfinda--hashmapfind"></a><a name="hash_map__find"></a>  hash_map::find  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Retorna um iterador que trata do local de um elemento em um hash_map que tem uma chave equivalente a uma chave especificada.  
  
```  
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```  
  
### <a name="parameters"></a>Parâmetros  
 ` key`  
 O valor da chave a ser correspondido pela chave de classificação de um elemento do hash_map que está sendo pesquisado.  
  
### <a name="return-value"></a>Valor de retorno  
 Um iterador que trata do local de um elemento com uma chave especificada ou do local que sucede o último elemento no hash_map se nenhuma correspondência for encontrada para a chave.  
  
### <a name="remarks"></a>Comentários  
 **find** retorna um iterador que trata de um elemento no hash_map, cuja chave de classificação é equivalente à chave de argumento em um predicado binário que induz uma ordenação com base em uma relação de comparação do tipo "menor que".  
  
 Se o valor retornado de **find** for atribuído a um [const_iterator](#hash_map__const_iterator), o objeto hash_map não poderá ser modificado. Se o valor retornado de **find** for atribuído a um [iterador](#hash_map__iterator), o objeto hash_map poderá ser modificado  
  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// hash_map_find.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_map <int, int> hm1;  
   hash_map <int, int> :: const_iterator hm1_AcIter, hm1_RcIter;  
   typedef pair <int, int> Int_Pair;  
  
   hm1.insert ( Int_Pair ( 1, 10 ) );  
   hm1.insert ( Int_Pair ( 2, 20 ) );  
   hm1.insert ( Int_Pair ( 3, 30 ) );  
  
   hm1_RcIter = hm1.find( 2 );  
   cout << "The element of hash_map hm1 with a key of 2 is: "  
        << hm1_RcIter -> second << "." << endl;  
  
   // If no match is found for the key, end( ) is returned  
   hm1_RcIter = hm1.find( 4 );  
  
   if ( hm1_RcIter == hm1.end( ) )  
      cout << "The hash_map hm1 doesn't have an element "  
           << "with a key of 4." << endl;  
   else  
      cout << "The element of hash_map hm1 with a key of 4 is: "  
           << hm1_RcIter -> second << "." << endl;  
  
   // The element at a specific location in the hash_map can be found   
   // using a dereferenced iterator addressing the location  
   hm1_AcIter = hm1.end( );  
   hm1_AcIter--;  
   hm1_RcIter = hm1.find( hm1_AcIter -> first );  
   cout << "The element of hm1 with a key matching "  
        << "that of the last element is: "  
        << hm1_RcIter -> second << "." << endl;  
}  
```  
  
```Output  
The element of hash_map hm1 with a key of 2 is: 20.  
The hash_map hm1 doesn't have an element with a key of 4.  
The element of hm1 with a key matching that of the last element is: 30.  
```  
  
##  <a name="a-namehashmapgetallocatora--hashmapgetallocator"></a><a name="hash_map__get_allocator"></a>  hash_map::get_allocator  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Retorna uma cópia do objeto alocador usado para construir o hash_map.  
  
```  
Allocator get_allocator() const;
```  
  
### <a name="return-value"></a>Valor de retorno  
 O alocador usado pelo hash_map.  
  
### <a name="remarks"></a>Comentários  
 Alocadores para a classe hash_map especificam como a classe gerencia o armazenamento. Os alocadores padrão fornecidos com as classes de contêiner da Biblioteca Padrão C++ são suficientes para a maioria das necessidades de programação. Gravando e usando sua própria classe de alocador é um tópico avançado do C++.  
  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// hash_map_get_allocator.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_map <int, int>::allocator_type hm1_Alloc;  
   hash_map <int, int>::allocator_type hm2_Alloc;  
   hash_map <int, double>::allocator_type hm3_Alloc;  
   hash_map <int, int>::allocator_type hm4_Alloc;  
  
   // The following lines declare objects  
   // that use the default allocator.  
   hash_map <int, int> hm1;  
   hash_map <int, int> hm2;  
   hash_map <int, double> hm3;  
  
   hm1_Alloc = hm1.get_allocator( );  
   hm2_Alloc = hm2.get_allocator( );  
   hm3_Alloc = hm3.get_allocator( );  
  
   cout << "The number of integers that can be allocated"  
        << endl << "before free memory is exhausted: "  
        << hm2.max_size( ) << "." << endl;  
  
   cout << "The number of doubles that can be allocated"  
        << endl << "before free memory is exhausted: "  
        << hm3.max_size( ) <<  "." << endl;  
  
   // The following line creates a hash_map hm4  
   // with the allocator of hash_map hm1.  
   hash_map <int, int> hm4( less<int>( ), hm1_Alloc );  
  
   hm4_Alloc = hm4.get_allocator( );  
  
   // Two allocators are interchangeable if  
   // storage allocated from each can be  
   // deallocated with the other  
   if( hm1_Alloc == hm4_Alloc )  
   {  
      cout << "The allocators are interchangeable."  
           << endl;     
   }  
   else     
   {  
      cout << "The allocators are not interchangeable."  
           << endl;     
   }  
}  
```  
  
##  <a name="a-namehashmaphashmapa--hashmaphashmap"></a><a name="hash_map__hash_map"></a>  hash_map::hash_map  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Cria um hash_map que está vazio ou que é uma cópia de todo ou de parte de algum outro hash_map.  
  
```  
hash_map();

explicit hash_map(
    const Traits& Comp);

hash_map(
    const Traits& Comp,  
    const Allocator& Al);

hash_map(
    const hash_map& Right);

hash_map(
    hash_map&& Right);

hash_map(
    initializer_list<Type> IList);hash_map(initializer_list<Type> IList,  
    const key_compare& Comp);

hash_map(
    initializer_list<Type> IList,  
    const key_compare& Comp,   
    const allocator_type& Al);

template <class InputIterator>  
hash_map(
 InputIterator First,  
    InputIterator Last);

template <class InputIterator>  
hash_map(
 InputIterator First,  
    InputIterator Last,  
    const Traits& Comp);

template <class InputIterator>  
hash_map(
 InputIterator First,  
    InputIterator Last,  
    const Traits& Comp,  
    const Allocator& Al  
```  
  
### <a name="parameters"></a>Parâmetros  
  
|||  
|-|-|  
|Parâmetro|Descrição|  
|`Al`|A classe do alocador de armazenamento a ser usado neste objeto hash_map, cujo padrão é **Allocator**.|  
|`Comp`|A função de comparação do tipo const `Traits` usada para ordenar os elementos no hash_map, cujo padrão é `hash_compare`.|  
|`Right`|O hash_map do qual o mapa construído deve ser uma cópia.|  
|`First`|A posição do primeiro elemento no intervalo de elementos a serem copiados.|  
|`Last`|A posição do primeiro elemento além do intervalo de elementos a serem copiados.|  
|`IList`|A initializer_list|  
  
### <a name="remarks"></a>Comentários  
 Todos os construtores armazenam um tipo de objeto alocador que gerencia o armazenamento de memória para o hash_map e que, posteriormente, pode ser retornado ao chamar [get_allocator](#hash_map__get_allocator). O parâmetro do alocador muitas vezes é omitido nas declarações de classe e nas macros de pré-processamento usadas para substituir os alocadores alternativos.  
  
 Todos os construtores inicializam seu hash_map.  
  
 Todos os construtores armazenam um objeto de função do tipo `Traits`, que é usado para estabelecer uma ordem entre as chaves do hash_map e que posteriormente pode ser retornado ao chamar [key_comp](#hash_map__key_comp).  
  
 Os primeiros três construtores especificam um hash_map inicial vazio, o segundo especifica o tipo de função de comparação (`Comp`) a ser usada para estabelecer a ordem dos elementos e o terceiro especifica explicitamente o tipo de alocador (`Al`) a ser usado. A palavra-chave `explicit` suprime determinados tipos de conversão de tipo automática.  
  
 O quarto construtor especifica uma cópia do hash_map `Right`.  
  
 Os próximos três construtores copiam o intervalo `[First, Last)` de um hash_map com clareza crescente para especificar o tipo de função de comparação da classe `Traits` e do alocador.  
  
 O último construtor move o hash_map `Right`.  
  
##  <a name="a-namehashmapinserta--hashmapinsert"></a><a name="hash_map__insert"></a>  hash_map::insert  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Insere um elemento ou um intervalo de elementos em um hash_map.  
  
```  
pair <iterator, bool> insert(
    const value_type& val);

iterator insert(
    const_iterator _Where,  
    const value_type& val);

template <class InputIterator>  
void insert(
    InputIterator first,  
    InputIterator last);

template <class ValTy>  
pair <iterator, bool>  
insert(
    ValTy&& val);

template <class ValTy>  
iterator insert(
    const_iterator _Where,  
    ValTy&& val);
```  
  
### <a name="parameters"></a>Parâmetros  
  
|||  
|-|-|  
|Parâmetro|Descrição|  
|` val`|O valor de um elemento a ser inserido no hash_map, a menos que o hash_map já contenha o elemento (ou, de modo geral, um elemento cuja chave seja ordenada de maneira equivalente).|  
|`_Where`|Uma dica relacionada ao local do qual se começa a procurar pelo ponto de inserção correto.|  
|` first`|A posição do primeiro elemento a ser copiado de um hash_map.|  
|` last`|A posição logo após o último elemento a ser copiado de um hash_map.|  
  
### <a name="return-value"></a>Valor de retorno  
 A primeira função membro **insert** retorna um par cujo componente booliano retorna verdadeiro se uma inserção tiver sido feita e falso se o hash_map já contivesse um elemento cuja chave tinha um valor equivalente na ordenação e cujo componente do iterador retorna o endereço em que um novo elemento foi inserido ou onde o elemento já estava localizado.  
  
 Para acessar o componente do iterador de um par `pr` retornado por essa função membro, use `pr`. **first** e, para desreferenciá-lo, use \*( `pr`. **first**). Para acessar o componente `bool` de um par `pr` retornado por essa função membro, use `pr`. **second** e, para desreferenciá-lo, use \*( `pr`. **second**).  
  
 A segunda função membro **insert**, a versão de dica, retorna um iterador que aponta para a posição em que o novo elemento foi inserido no hash_map.  
  
 As duas últimas funções membro **insert** se comportam da mesma forma que as duas primeiras, mas elas constroem o valor inserido.  
  
### <a name="remarks"></a>Comentários  
 O [value_type](../standard-library/map-class.md#map__value_type) de um elemento é um par, de forma que o valor de um elemento será um par ordenado com o primeiro componente igual ao valor de chave e o segundo componente igual ao valor dos dados do elemento.  
  
 A inserção poderá ocorrer em um tempo constante amortizado para a versão de dica da inserção, em vez de no tempo logarítmico, se o ponto de inserção seguir `_Where` imediatamente.  
  
 A terceira função membro insere a sequência de valores de elemento em um hash_map que corresponde a cada elemento tratado por um iterador no intervalo *[primeiro, segundo)* de um conjunto especificado.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// hash_map_insert.cpp  
// compile with: /EHsc  
#include<hash_map>  
#include<iostream>  
#include <string>  
  
int main()  
{  
    using namespace std;  
    using namespace stdext;  
    hash_map<int, int>::iterator hm1_pIter, hm2_pIter;  
  
    hash_map<int, int> hm1, hm2;  
    typedef pair<int, int> Int_Pair;  
  
    hm1.insert(Int_Pair(1, 10));  
    hm1.insert(Int_Pair(2, 20));  
    hm1.insert(Int_Pair(3, 30));  
    hm1.insert(Int_Pair(4, 40));  
  
    cout<< "The original elements (Key => Value) of hm1 are:";  
    for (hm1_pIter = hm1.begin(); hm1_pIter != hm1.end(); hm1_pIter++)  
        cout << endl << " " << hm1_pIter -> first << " => "  
             << hm1_pIter->second;  
    cout << endl;  
  
    pair< hash_map<int,int>::iterator, bool > pr;  
    pr = hm1.insert(Int_Pair(1, 10));  
  
    if (pr.second == true)  
    {  
        cout<< "The element 10 was inserted in hm1 successfully."  
            << endl;  
    }  
    else  
    {  
        cout<< "The element 10 already exists in hm1\n with a key value of"  
            << "((pr.first) -> first)= "<<(pr.first)-> first  
            << "."<< endl;  
    }  
  
    // The hint version of insert  
    hm1.insert(--hm1.end(), Int_Pair(5, 50));  
  
    cout<< "After the insertions, the elements of hm1 are:";  
    for (hm1_pIter = hm1.begin(); hm1_pIter != hm1.end(); hm1_pIter++)  
        cout << endl << " " << hm1_pIter -> first << " => "  
             << hm1_pIter->second;  
    cout << endl;  
  
    hm2.insert(Int_Pair(10, 100));  
  
    // The templatized version inserting a range  
    hm2.insert( ++hm1.begin(), --hm1.end() );  
  
    cout<< "After the insertions, the elements of hm2 are:";  
    for (hm2_pIter = hm2.begin(); hm2_pIter != hm2.end(); hm2_pIter++)  
        cout << endl << " " << hm2_pIter -> first << " => "  
             << hm2_pIter->second;  
    cout << endl;  
  
    // The templatized versions move constructing elements  
    hash_map<int, string> hm3, hm4;  
    pair<int, string> is1(1, "a"), is2(2, "b");  
  
    hm3.insert(move(is1));  
    cout << "After the move insertion, hm3 contains:" << endl  
      << " " << hm3.begin()->first  
      << " => " << hm3.begin()->second  
      << endl;  
  
    hm4.insert(hm4.begin(), move(is2));  
    cout << "After the move insertion, hm4 contains:" << endl  
      << " " << hm4.begin()->first  
      << " => " << hm4.begin()->second  
      << endl;  
}  
```  
  
```Output  
The original elements (Key => Value) of hm1 are:  
 1 => 10  
 2 => 20  
 3 => 30  
 4 => 40  
The element 10 already exists in hm1  
 with a key value of((pr.first) -> first)= 1.  
After the insertions, the elements of hm1 are:  
 1 => 10  
 2 => 20  
 3 => 30  
 4 => 40  
 5 => 50  
After the insertions, the elements of hm2 are:  
 2 => 20  
 10 => 100  
 3 => 30  
 4 => 40  
After the move insertion, hm3 contains:  
 1 => a  
After the move insertion, hm4 contains:  
 2 => b  
```  
  
##  <a name="a-namehashmapiteratora--hashmapiterator"></a><a name="hash_map__iterator"></a>  hash_map::iterator  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Um tipo que fornece um iterador bidirecional que pode ler ou modificar qualquer elemento em um hash_map.  
  
```  
typedef list<typename Traits::value_type, typename Traits::allocator_type>::iterator iterator;  
```  
  
### <a name="remarks"></a>Comentários  
 O **iterador** definido pelo hash_map aponta para elementos que são objetos de [value_type](#hash_map__value_type), que é do tipo **pair\<const Key, Type>,** cujo primeiro membro é a chave do elemento e cujo segundo membro é a referência mapeada mantida pelo elemento.  
  
 Para desreferenciar um **iterador**`Iter` que aponta para um elemento em um multimap, use o operador **->**.  
  
 Para acessar o valor de chave do elemento, use `Iter` -> **first**, que é equivalente a (\* `Iter`). **first**. Para acessar o valor dos dados mapeados do elemento, use `Iter` -> **second**, que é equivalente a (\* `Iter`). **second**.  
  
 Um tipo **iterator** pode ser usado para modificar o valor de um elemento.  
  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  Veja o exemplo de [begin](#hash_map__begin) para obter uma demonstração de como declarar e usar o **iterador**.  
  
##  <a name="a-namehashmapkeycompa--hashmapkeycomp"></a><a name="hash_map__key_comp"></a>  hash_map::key_comp  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Recupera uma cópia do objeto de comparação usada para ordenar chaves em um hash_map.  
  
```  
key_compare key_comp() const;
```  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna o objeto de função que um hash_map usa para ordenar seus elementos.  
  
### <a name="remarks"></a>Comentários  
 O objeto armazenado define a função membro  
  
 **operador booliano**( **const Key&** ` left`**, const Key&** ` right`);  
  
 que retornará **true**, se ` left` preceder e não for igual a ` right` na ordem de classificação.  
  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// hash_map_key_comp.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
  
   hash_map <int, int, hash_compare<int, less<int> > > hm1;  
   hash_map <int, int, hash_compare<int, less<int> > >::key_compare   
      kc1 = hm1.key_comp( ) ;  
  
   // Operator stored in kc1 tests order & returns bool value  
   bool result1 = kc1( 2, 3 ) ;     
   if( result1 == true )     
   {  
      cout << "kc1( 2,3 ) returns value of true,"  
           << "\n where kc1 is the function object of hm1"  
           << " of type key_compare." << endl;  
   }  
   else     
   {  
      cout << "kc1( 2,3 ) returns value of false"  
           << "\n where kc1 is the function object of hm1"  
           << " of type key_compare." << endl;  
   }  
  
   hash_map <int, int, hash_compare<int, greater<int> > > hm2;  
   hash_map <int, int, hash_compare<int, greater<int> > >  
      ::key_compare kc2 = hm2.key_comp( );  
  
   // Operator stored in kc2 tests order & returns bool value  
   bool result2 = kc2( 2, 3 ) ;  
   if( result2 == true )  
   {  
      cout << "kc2( 2,3 ) returns value of true,"  
           << "\n where kc2 is the function object of hm2"  
           << " of type key_compare." << endl;  
   }  
   else     
   {  
      cout << "kc2( 2,3 ) returns value of false,"  
           << "\n where kc2 is the function object of hm2"  
           << " of type key_compare." << endl;  
   }  
}  
```  
  
##  <a name="a-namehashmapkeycomparea--hashmapkeycompare"></a><a name="hash_map__key_compare"></a>  hash_map::key_compare  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Um tipo que fornece um objeto de função que pode comparar duas chaves de classificação para determinar a ordem relativa de dois elementos no mapa.  
  
```  
typedef Traits key_compare;  
```  
  
### <a name="remarks"></a>Comentários  
 `key_compare` é um sinônimo do parâmetro de modelo `Traits`.  
  
 Para obter mais informações sobre `Traits`, consulte o tópico [Classe hash_map](../standard-library/hash-map-class.md).  
  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  Consulte o exemplo de [key_comp](#hash_map__key_comp) para obter um exemplo de como declarar e usar `key_compare`.  
  
##  <a name="a-namehashmapkeytypea--hashmapkeytype"></a><a name="hash_map__key_type"></a>  hash_map::key_type  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Um tipo que descreve o objeto de chave de classificação que constitui cada elemento do hash_map.  
  
```  
typedef Key key_type;  
```  
  
### <a name="remarks"></a>Comentários  
 `key_type` é um sinônimo do parâmetro de modelo `Key`.  
  
 Para obter mais informações sobre `Key`, consulte a seção Comentários do tópico [Classe hash_map](../standard-library/hash-map-class.md).  
  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  Consulte o exemplo para [value_type](#hash_map__value_type) para obter uma amostra de como declarar e usar `key_type`.  
  
##  <a name="a-namehashmaplowerbounda--hashmaplowerbound"></a><a name="hash_map__lower_bound"></a>  hash_map::lower_bound  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Retorna um iterador para o primeiro elemento em um hash_map com um valor de chave que é igual ou maior que uma chave especificada.  
  
```  
iterator lower_bound(const Key& key);

const_iterator lower_bound(const Key& key) const;
```  
  
### <a name="parameters"></a>Parâmetros  
 ` key`  
 O valor de chave do argumento a ser comparado com a chave de classificação de um elemento do hash_map que está sendo pesquisado.  
  
### <a name="return-value"></a>Valor de retorno  
 Um [iterador](#hash_map__iterator) ou [const_iterator](#hash_map__const_iterator) que trata da localização de um elemento em um hash_map com uma chave, que é igual ou maior que a chave de argumento ou que trata do local que sucede o último elemento no hash_map, se nenhuma correspondência for encontrada para a chave.  
  
 Se o valor retornado de `lower_bound` for atribuído a `const_iterator`, o objeto do hash_map não poderá ser modificado. Se o valor retornado de `lower_bound` for atribuído a um **iterador**, o objeto do hash_map poderá ser modificado.  
  
### <a name="remarks"></a>Comentários  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// hash_map_lower_bound.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_map <int, int> hm1;  
   hash_map <int, int> :: const_iterator hm1_AcIter, hm1_RcIter;  
   typedef pair <int, int> Int_Pair;  
  
   hm1.insert ( Int_Pair ( 1, 10 ) );  
   hm1.insert ( Int_Pair ( 2, 20 ) );  
   hm1.insert ( Int_Pair ( 3, 30 ) );  
  
   hm1_RcIter = hm1.lower_bound( 2 );  
   cout << "The first element of hash_map hm1 with a key of 2 is: "  
        << hm1_RcIter -> second << "." << endl;  
  
   // If no match is found for the key, end( ) is returned  
   hm1_RcIter = hm1. lower_bound ( 4 );  
  
   if ( hm1_RcIter == hm1.end( ) )  
      cout << "The hash_map hm1 doesn't have an element "  
           << "with a key of 4." << endl;  
   else  
      cout << "The element of hash_map hm1 with a key of 4 is: "  
           << hm1_RcIter -> second << "." << endl;  
  
   // An element at a specific location in the hash_map can be   
   // found using a dereferenced iterator addressing the location  
   hm1_AcIter = hm1.end( );  
   hm1_AcIter--;  
   hm1_RcIter = hm1. lower_bound ( hm1_AcIter -> first );  
   cout << "The element of hm1 with a key matching "  
        << "that of the last element is: "  
        << hm1_RcIter -> second << "." << endl;  
}  
```  
  
```Output  
The first element of hash_map hm1 with a key of 2 is: 20.  
The hash_map hm1 doesn't have an element with a key of 4.  
The element of hm1 with a key matching that of the last element is: 30.  
```  
  
##  <a name="a-namehashmapmappedtypea--hashmapmappedtype"></a><a name="hash_map__mapped_type"></a>  hash_map::mapped_type  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Um tipo que representa o tipo de dados armazenado em um hash_map.  
  
```  
typedef Type mapped_type;  
```  
  
### <a name="remarks"></a>Comentários  
 O tipo `mapped_type` é um sinônimo do parâmetro do modelo `Type`.  
  
 Para obter mais informações sobre `Type`, consulte o tópico [Classe hash_map](../standard-library/hash-map-class.md).  
  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  Consulte o exemplo para [value_type](#hash_map__value_type) para obter uma amostra de como declarar e usar `key_type`.  
  
##  <a name="a-namehashmapmaxsizea--hashmapmaxsize"></a><a name="hash_map__max_size"></a>  hash_map::max_size  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Retorna o tamanho máximo do hash_map.  
  
```  
size_type max_size() const;
```  
  
### <a name="return-value"></a>Valor de retorno  
 O tamanho máximo possível do hash_map.  
  
### <a name="remarks"></a>Comentários  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// hash_map_max_size.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_map <int, int> hm1;  
   hash_map <int, int> :: size_type i;  
  
   i = hm1.max_size( );     
   cout << "The maximum possible length "  
        << "of the hash_map is " << i << "."  
        << endl << "(Magnitude is machine specific.)";  
}  
```  
  
##  <a name="a-namehashmapoperatorata--hashmapoperator"></a><a name="hash_map__operator_at"></a>  hash_map::operator[]  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Insere um elemento em um `hash_map` com um valor de chave especificado.  
  
```  
Type& operator[](const Key& key);

Type& operator[](Key&& key);
```  
  
### <a name="parameters"></a>Parâmetros  
  
|||  
|-|-|  
|Parâmetro|Descrição|  
|` key`|O valor de chave do elemento a ser inserido.|  
  
### <a name="return-value"></a>Valor de retorno  
 Uma referência ao valor de dados do elemento inserido.  
  
### <a name="remarks"></a>Comentários  
 Se o valor de chave do argumento não for encontrado, ele será inserido juntamente com o valor padrão do tipo de dados.  
  
 `operator[]` pode ser usado para inserir elementos em um `hash_map m` usando  
  
 `m[ key] = DataValue`;  
  
 em que DataValue é o valor de `mapped_type` do elemento com um valor de chave de ` key`.  
  
 Ao usar `operator[]` para inserir elementos, a referência retornada não indica se uma inserção está alterando um elemento preexistente ou criando outro. As funções membro [find](../standard-library/map-class.md#map__find) e [insert](../standard-library/map-class.md#map__insert) podem ser usadas para determinar se um elemento com uma chave especificada já está presente antes de uma inserção.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// hash_map_op_ref.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
#include <string>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   typedef pair <const int, int> cInt2Int;  
   hash_map <int, int> hm1;  
   hash_map <int, int> :: iterator pIter;  
  
   // Insert a data value of 10 with a key of 1  
   // into a hash_map using the operator[] member function  
   hm1[ 1 ] = 10;  
  
   // Compare other ways to insert objects into a hash_map  
   hm1.insert ( hash_map <int, int> :: value_type ( 2, 20 ) );  
   hm1.insert ( cInt2Int ( 3, 30 ) );  
  
   cout  << "The keys of the mapped elements are:";  
   for ( pIter = hm1.begin( ) ; pIter != hm1.end( ) ; pIter++ )  
      cout << " " << pIter -> first;  
   cout << "." << endl;  
  
   cout  << "The values of the mapped elements are:";  
   for ( pIter = hm1.begin( ) ; pIter != hm1.end( ) ; pIter++ )  
      cout << " " << pIter -> second;  
   cout << "." << endl;  
  
   // If the key already exists, operator[]  
   // changes the value of the datum in the element  
   hm1[ 2 ] = 40;  
  
   // operator[] will also insert the value of the data  
   // type's default constructor if the value is unspecified  
   hm1[5];  
  
   cout  << "The keys of the mapped elements are now:";  
   for ( pIter = hm1.begin( ) ; pIter != hm1.end( ) ; pIter++ )  
      cout << " " << pIter -> first;  
   cout << "." << endl;  
  
   cout  << "The values of the mapped elements are now:";  
   for ( pIter = hm1.begin( ) ; pIter != hm1.end( ) ; pIter++ )  
      cout << " " << pIter -> second;  
   cout << "." << endl;  
  
   // opperator[] will also insert by moving a key  
   hash_map <string, int> hm2;  
   string str("a");  
   hm2[move(str)] = 1;  
   cout << "The moved key is " << hm2.begin()->first  
      << ", with value " << hm2.begin()->second << endl;  
}  
```  
  
##  <a name="a-namehashmapoperatoreqa--hashmapoperator"></a><a name="hash_map__operator_eq"></a>  hash_map::operator=  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Substitui os elementos do hash_map por uma cópia de outro hash_map.  
  
```  
hash_map& operator=(const hash_map& right);

hash_map& operator=(hash_map&& right);
```  
  
### <a name="parameters"></a>Parâmetros  
  
|||  
|-|-|  
|Parâmetro|Descrição|  
|` right`|A [Classe hash_map](../standard-library/hash-map-class.md) que está sendo copiado para o `hash_map`.|  
  
### <a name="remarks"></a>Comentários  
 Após apagar os elementos existentes em um `hash_map`, `operator=` copiará ou moverá o conteúdo de ` right` para `hash_map`.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// hash_map_operator_as.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_map<int, int> v1, v2, v3;  
   hash_map<int, int>::iterator iter;  
  
   v1.insert(pair<int, int>(1, 10));  
  
   cout << "v1 = " ;  
   for (iter = v1.begin(); iter != v1.end(); iter++)  
      cout << iter->second << " ";  
   cout << endl;  
  
   v2 = v1;  
   cout << "v2 = ";  
   for (iter = v2.begin(); iter != v2.end(); iter++)  
      cout << iter->second << " ";  
   cout << endl;  
  
// move v1 into v2  
   v2.clear();  
   v2 = move(v1);  
   cout << "v2 = ";  
   for (iter = v2.begin(); iter != v2.end(); iter++)  
      cout << iter->second << " ";  
   cout << endl;  
}  
```  
  
##  <a name="a-namehashmappointera--hashmappointer"></a><a name="hash_map__pointer"></a>  hash_map::pointer  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Um tipo que fornece um ponteiro para um elemento em um hash_map.  
  
```  
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::pointer pointer;  
```  
  
### <a name="remarks"></a>Comentários  
 Um tipo **pointer** pode ser usado para modificar o valor de um elemento.  
  
 Na maioria dos casos, um [iterador](#hash_map__iterator) deve ser usado para acessar os elementos em um objeto hash_map.  
  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
##  <a name="a-namehashmaprbegina--hashmaprbegin"></a><a name="hash_map__rbegin"></a>  hash_map::rbegin  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Retorna um iterador que trata do primeiro elemento em um hash_map invertido.  
  
```  
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Um iterador bidirecional invertido que trata do primeiro elemento em um hash_map invertido ou que trata do que foi o último elemento do hash_map não invertido.  
  
### <a name="remarks"></a>Comentários  
 `rbegin` é usado com um hash_map invertido, assim como [begin](#hash_map__begin) é usado com um hash_map.  
  
 Se o valor retornado de `rbegin` for atribuído a um [const_reverse_iterator](#hash_map__const_reverse_iterator), o objeto hash_map não poderá ser modificado. Se o valor retornado de `rbegin` for atribuído a um [reverse_iterator](#hash_map__reverse_iterator), o objeto hash_map poderá ser modificado.  
  
 `rbegin` pode ser usado para iterar em um hash_map no sentido reverso.  
  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// hash_map_rbegin.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_map <int, int> hm1;  
  
   hash_map <int, int> :: iterator hm1_Iter;  
   hash_map <int, int> :: reverse_iterator hm1_rIter;  
   hash_map <int, int> :: const_reverse_iterator hm1_crIter;  
   typedef pair <int, int> Int_Pair;  
  
   hm1.insert ( Int_Pair ( 1, 10 ) );  
   hm1.insert ( Int_Pair ( 2, 20 ) );  
   hm1.insert ( Int_Pair ( 3, 30 ) );  
  
   hm1_rIter = hm1.rbegin( );  
   cout << "The first element of the reversed hash_map hm1 is "  
        << hm1_rIter -> first << "." << endl;  
  
   // begin can be used to start an iteration   
   // through a hash_map in a forward order  
   cout << "The hash_map is: ";  
   for ( hm1_Iter = hm1.begin( ) ; hm1_Iter != hm1.end( ); hm1_Iter++)  
      cout << hm1_Iter -> first << " ";  
      cout << "." << endl;  
  
   // rbegin can be used to start an iteration   
   // through a hash_map in a reverse order  
   cout << "The reversed hash_map is: ";  
   for ( hm1_rIter = hm1.rbegin( ) ; hm1_rIter != hm1.rend( ); hm1_rIter++)  
      cout << hm1_rIter -> first << " ";  
      cout << "." << endl;  
  
   // A hash_map element can be erased by dereferencing to its key   
   hm1_rIter = hm1.rbegin( );  
   hm1.erase ( hm1_rIter -> first );  
  
   hm1_rIter = hm1.rbegin( );  
   cout << "After the erasure, the first element "  
        << "in the reversed hash_map is "  
        << hm1_rIter -> first << "." << endl;  
}  
```  
  
```Output  
The first element of the reversed hash_map hm1 is 3.  
The hash_map is: 1 2 3 .  
The reversed hash_map is: 3 2 1 .  
After the erasure, the first element in the reversed hash_map is 2.  
```  
  
##  <a name="a-namehashmapreferencea--hashmapreference"></a><a name="hash_map__reference"></a>  hash_map::reference  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Um tipo que fornece uma referência a um elemento armazenado em um hash_map.  
  
```  
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::reference reference;  
```  
  
### <a name="remarks"></a>Comentários  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// hash_map_reference.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   using namespace stdext;  
   hash_map <int, int> hm1;  
   typedef pair <int, int> Int_Pair;  
  
   hm1.insert ( Int_Pair ( 1, 10 ) );  
   hm1.insert ( Int_Pair ( 2, 20 ) );  
  
   // Declare and initialize a const_reference &Ref1   
   // to the key of the first element  
   const int &Ref1 = ( hm1.begin( ) -> first );  
  
   // The following line would cause an error as the   
   // non-const_reference cannot be used to access the key  
   // int &Ref1 = ( hm1.begin( ) -> first );  
  
   cout << "The key of first element in the hash_map is "  
        << Ref1 << "." << endl;  
  
   // Declare and initialize a reference &Ref2   
   // to the data value of the first element  
   int &Ref2 = ( hm1.begin( ) -> second );  
  
   cout << "The data value of first element in the hash_map is "  
        << Ref2 << "." << endl;  
  
   // The non-const_reference can be used to modify the   
   // data value of the first element  
   Ref2 = Ref2 + 5;  
   cout << "The modified data value of first element is "  
        << Ref2 << "." << endl;  
}  
```  
  
```Output  
The key of first element in the hash_map is 1.  
The data value of first element in the hash_map is 10.  
The modified data value of first element is 15.  
```  
  
##  <a name="a-namehashmaprenda--hashmaprend"></a><a name="hash_map__rend"></a>  hash_map::rend  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Retorna um iterador que trata do local após o último elemento em um hash_map invertido.  
  
```  
const_reverse_iterator rend() const;

reverse_iterator rend();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Um iterador bidirecional inverso que trata da localização que vem após o último elemento em um hash_map invertido (o local que precedeu o primeiro elemento no hash_map não invertido).  
  
### <a name="remarks"></a>Comentários  
 `rend` é usado com um hash_map invertido, assim como [end](#hash_map__end) é usado com um hash_map.  
  
 Se o valor retornado de `rend` for atribuído a um [const_reverse_iterator](#hash_map__const_reverse_iterator), o objeto hash_map não poderá ser modificado. Se o valor retornado de `rend` for atribuído a um [reverse_iterator](#hash_map__reverse_iterator), o objeto hash_map poderá ser modificado.  
  
 `rend` pode ser usado para testar se um iterador inverso alcançou o final de seu hash_map.  
  
 O valor retornado por `rend` não deve ser desreferenciado.  
  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// hash_map_rend.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_map <int, int> hm1;  
  
   hash_map <int, int> :: iterator hm1_Iter;  
   hash_map <int, int> :: reverse_iterator hm1_rIter;  
   hash_map <int, int> :: const_reverse_iterator hm1_crIter;  
   typedef pair <int, int> Int_Pair;  
  
   hm1.insert ( Int_Pair ( 1, 10 ) );  
   hm1.insert ( Int_Pair ( 2, 20 ) );  
   hm1.insert ( Int_Pair ( 3, 30 ) );  
  
   hm1_rIter = hm1.rend( );  
   hm1_rIter--;  
   cout << "The last element of the reversed hash_map hm1 is "  
        << hm1_rIter -> first << "." << endl;  
  
   // begin can be used to start an iteration   
   // through a hash_map in a forward order  
   cout << "The hash_map is: ";  
   for ( hm1_Iter = hm1.begin( ) ; hm1_Iter != hm1.end( );  
   hm1_Iter++)  
      cout << hm1_Iter -> first << " ";  
      cout << "." << endl;  
  
   // rbegin can be used to start an iteration   
   // through a hash_map in a reverse order  
   cout << "The reversed hash_map is: ";  
   for ( hm1_rIter = hm1.rbegin( ) ; hm1_rIter != hm1.rend( );  
      hm1_rIter++)  
      cout << hm1_rIter -> first << " ";  
      cout << "." << endl;  
  
   // A hash_map element can be erased by dereferencing to its key   
   hm1_rIter = --hm1.rend( );  
   hm1.erase ( hm1_rIter -> first );  
  
   hm1_rIter = hm1.rend( );  
   hm1_rIter--;  
   cout << "After the erasure, the last element "  
        << "in the reversed hash_map is "  
        << hm1_rIter -> first << "." << endl;  
}  
```  
  
```Output  
The last element of the reversed hash_map hm1 is 1.  
The hash_map is: 1 2 3 .  
The reversed hash_map is: 3 2 1 .  
After the erasure, the last element in the reversed hash_map is 2.  
```  
  
##  <a name="a-namehashmapreverseiteratora--hashmapreverseiterator"></a><a name="hash_map__reverse_iterator"></a>  hash_map::reverse_iterator  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Um tipo que fornece um iterador bidirecional que pode ler ou modificar um elemento em um hash_map invertido.  
  
```  
typedef list<typename Traits::value_type, typename Traits::allocator_type>::reverse_iterator reverse_iterator;  
```  
  
### <a name="remarks"></a>Comentários  
 Um tipo `reverse_iterator` não pode modificar o valor de um elemento e é usado para iterar no hash_map em ordem inversa.  
  
 O `reverse_iterator` definido pelo hash_map aponta para elementos que são objetos de [value_type](#hash_map__value_type), que é do tipo **pair\<const Key, Type>**, cujo primeiro membro é a chave do elemento e cujo segundo membro é a referência mapeada mantida pelo elemento.  
  
 Para desreferenciar um `reverse_iterator``rIter` que aponta para um elemento em um hash_map, use o operador ->.  
  
 Para acessar o valor de chave do elemento, use `rIter` -> **first**, que é equivalente a (\* `rIter`). **first**. Para acessar o valor dos dados mapeados do elemento, use `rIter` -> **second**, que é equivalente a (\* `rIter`). **first**.  
  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  Veja o exemplo de [rbegin](#hash_map__rbegin) que demonstra como declarar e usar `reverse_iterator`.  
  
##  <a name="a-namehashmapsizea--hashmapsize"></a><a name="hash_map__size"></a>  hash_map::size  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Retorna o número de elementos no hash_map.  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>Valor de retorno  
 O tamanho atual do hash_map.  
  
### <a name="remarks"></a>Comentários  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  O exemplo a seguir demonstra o uso da função membro hash_map::size.  
  
```  
// hash_map_size.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
    using namespace std;  
    using namespace stdext;  
    hash_map<int, int> hm1, hm2;  
    hash_map<int, int>::size_type i;  
    typedef pair<int, int> Int_Pair;  
  
    hm1.insert(Int_Pair(1, 1));  
    i = hm1.size();  
    cout << "The hash_map length is " << i << "." << endl;  
  
    hm1.insert(Int_Pair(2, 4));  
    i = hm1.size();  
    cout << "The hash_map length is now " << i << "." << endl;  
}  
```  
  
```Output  
The hash_map length is 1.  
The hash_map length is now 2.  
```  
  
##  <a name="a-namehashmapsizetypea--hashmapsizetype"></a><a name="hash_map__size_type"></a>  hash_map::size_type  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Um tipo inteiro sem sinal que pode representar o número de elementos em um hash_map.  
  
```  
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::size_type size_type;  
```  
  
### <a name="remarks"></a>Comentários  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  Veja o exemplo de [size](#hash_map__size) para obter um exemplo de como declarar e usar `size_type`  
  
##  <a name="a-namehashmapswapa--hashmapswap"></a><a name="hash_map__swap"></a>  hash_map::swap  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Troca os elementos de dois hash_maps.  
  
```  
void swap(hash_map& right);
```  
  
### <a name="parameters"></a>Parâmetros  
 ` right`  
 O hash_map do argumento que fornece os elementos a serem trocados com o hash_map de destino.  
  
### <a name="remarks"></a>Comentários  
 A função membro não invalida referências, ponteiros ou iteradores que designam elementos nos dois hash_mapm cujos elementos são trocados.  
  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// hash_map_swap.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_map <int, int> hm1, hm2, hm3;  
   hash_map <int, int>::iterator hm1_Iter;  
   typedef pair <int, int> Int_Pair;  
  
   hm1.insert ( Int_Pair ( 1, 10 ) );  
   hm1.insert ( Int_Pair ( 2, 20 ) );  
   hm1.insert ( Int_Pair ( 3, 30 ) );  
   hm2.insert ( Int_Pair ( 10, 100 ) );  
   hm2.insert ( Int_Pair ( 20, 200 ) );  
   hm3.insert ( Int_Pair ( 30, 300 ) );  
  
   cout << "The original hash_map hm1 is:";  
   for ( hm1_Iter = hm1.begin( ); hm1_Iter != hm1.end( ); hm1_Iter++ )  
      cout << " " << hm1_Iter -> second;  
   cout   << "." << endl;  
  
   // This is the member function version of swap  
   // hm2 is said to be the argument hash_map;   
   // hm1 is said to be the target hash_map  
   hm1.swap( hm2 );  
  
   cout << "After swapping with hm2, hash_map hm1 is:";  
   for ( hm1_Iter = hm1.begin( ); hm1_Iter != hm1.end( ); hm1_Iter++ )  
      cout << " " << hm1_Iter -> second;  
   cout  << "." << endl;  
  
   // This is the specialized template version of swap  
   swap( hm1, hm3 );  
  
   cout << "After swapping with hm3, hash_map hm1 is:";  
   for ( hm1_Iter = hm1.begin( ); hm1_Iter != hm1.end( ); hm1_Iter++ )  
      cout << " " << hm1_Iter -> second;  
   cout   << "." << endl;  
}  
```  
  
```Output  
The original hash_map hm1 is: 10 20 30.  
After swapping with hm2, hash_map hm1 is: 100 200.  
After swapping with hm3, hash_map hm1 is: 300.  
```  
  
##  <a name="a-namehashmapupperbounda--hashmapupperbound"></a><a name="hash_map__upper_bound"></a>  hash_map::upper_bound  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Retorna um iterador para o primeiro elemento em um hash_map com uma chave que é maior que uma chave especificada.  
  
```  
iterator upper_bound(const Key& key);

const_iterator upper_bound(const Key& key) const;
```  
  
### <a name="parameters"></a>Parâmetros  
 ` key`  
 O valor de chave do argumento a ser comparado com o valor da chave de classificação de um elemento do hash_map que está sendo pesquisado.  
  
### <a name="return-value"></a>Valor de retorno  
 Um [iterador](#hash_map__iterator) ou [const_iterator](#hash_map__const_iterator) que trata da localização de um elemento em um hash_map com uma chave que é maior que a chave de argumento ou que trata do local que sucede o último elemento no hash_map, se nenhuma correspondência for encontrada para a chave.  
  
 Se o valor retornado for atribuído a `const_iterator`, o objeto do hash_map não poderá ser modificado. Se o valor retornado for atribuído a um **iterador**, o objeto do hash_map poderá ser modificado.  
  
### <a name="remarks"></a>Comentários  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// hash_map_upper_bound.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_map <int, int> hm1;  
   hash_map <int, int> :: const_iterator hm1_AcIter, hm1_RcIter;  
   typedef pair <int, int> Int_Pair;  
  
   hm1.insert ( Int_Pair ( 1, 10 ) );  
   hm1.insert ( Int_Pair ( 2, 20 ) );  
   hm1.insert ( Int_Pair ( 3, 30 ) );  
  
   hm1_RcIter = hm1.upper_bound( 2 );  
   cout << "The first element of hash_map hm1 with a key "  
        << "greater than 2 is: "  
        << hm1_RcIter -> second << "." << endl;  
  
   // If no match is found for the key, end is returned  
   hm1_RcIter = hm1. upper_bound ( 4 );  
  
   if ( hm1_RcIter == hm1.end( ) )  
      cout << "The hash_map hm1 doesn't have an element "  
           << "with a key greater than 4." << endl;  
   else  
      cout << "The element of hash_map hm1 with a key > 4 is: "  
           << hm1_RcIter -> second << "." << endl;  
  
   // The element at a specific location in the hash_map can be found   
   // using a dereferenced iterator addressing the location  
   hm1_AcIter = hm1.begin( );  
   hm1_RcIter = hm1. upper_bound ( hm1_AcIter -> first );  
   cout << "The 1st element of hm1 with a key greater than "  
        << "that\n of the initial element of hm1 is: "  
        << hm1_RcIter -> second << "." << endl;  
}  
```  
  
```Output  
The first element of hash_map hm1 with a key greater than 2 is: 30.  
The hash_map hm1 doesn't have an element with a key greater than 4.  
The 1st element of hm1 with a key greater than that  
 of the initial element of hm1 is: 20.  
```  
  
##  <a name="a-namehashmapvaluecompa--hashmapvaluecomp"></a><a name="hash_map__value_comp"></a>  hash_map::value_comp  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Retorna um objeto de função que determina a ordem dos elementos em um hash_map comparando os valores de chave.  
  
```  
value_compare value_comp() const;
```  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna o objeto da função de comparação que um hash_map usa para ordenar seus elementos.  
  
### <a name="remarks"></a>Comentários  
 Para um hash_map *m*, se dois elementos *e*1 *(k*1 *, d*1 *)* e *e*2 *(k*2 *, d*2 *)* forem objetos do tipo [value_type](#hash_map__value_type), em que *k*1 e *k*2 são suas chaves do tipo [key_type](#hash_map__key_type) e `d`1 e `d`2 são seus dados do tipo [mapped_type](#hash_map__mapped_type), então *m.*`value_comp`*( )(e*1 *, e*2 *)* é equivalente a *m.*`key_comp`*( ) (k*1 *, k*2 *)*. Um objeto armazenado define a função de membro  
  
 **operador booliano**( **value_type&** ` left`, **value_type&** ` right`) **;**  
  
 que retornará **true** se o valor de chave ` left` preceder e for diferente do valor de chave de ` right` na ordem de classificação.  
  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// hash_map_value_comp.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
  
   hash_map <int, int, hash_compare<int, less<int> > > hm1;  
   hash_map <int, int, hash_compare<int, less<int> > >  
   ::value_compare vc1 = hm1.value_comp( );  
   pair< hash_map<int,int>::iterator, bool > pr1, pr2;  
  
   pr1= hm1.insert ( hash_map <int, int> :: value_type ( 1, 10 ) );  
   pr2= hm1.insert ( hash_map <int, int> :: value_type ( 2, 5 ) );  
  
   if( vc1( *pr1.first, *pr2.first ) == true )     
   {  
      cout << "The element ( 1,10 ) precedes the element ( 2,5 )."  
           << endl;  
   }  
   else     
   {  
      cout << "The element ( 1,10 ) does not precede the element ( 2,5 )."  
           << endl;  
   }  
  
   if( vc1 ( *pr2.first, *pr1.first ) == true )  
   {  
      cout << "The element ( 2,5 ) precedes the element ( 1,10 )."  
           << endl;  
   }  
   else     
   {  
      cout << "The element ( 2,5 ) does not precede the element ( 1,10 )."  
           << endl;  
   }  
}  
```  
  
##  <a name="a-namehashmapvaluetypea--hashmapvaluetype"></a><a name="hash_map__value_type"></a>  hash_map::value_type  
  
> [!NOTE]
>  Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).  
  
 Um tipo que representa o tipo do objeto armazenado em um hash_map.  
  
```  
typedef pair<const Key, Type> value_type;  
```  
  
### <a name="remarks"></a>Comentários  
 `value_type` é declarado como `pair` *\<***const**[key_type](#hash_map__key_type), [mapped_type](#hash_map__mapped_type)*>* e não como `pair`**\<key_type, mapped_type>** porque as chaves de um contêiner associativo não podem ser alteradas usando uma referência ou iterador não constante.  
  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
### <a name="example"></a>Exemplo  
  
```cpp  
// hash_map_value_type.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   using namespace stdext;  
   typedef pair <const int, int> cInt2Int;  
   hash_map <int, int> hm1;  
   hash_map <int, int> :: key_type key1;  
   hash_map <int, int> :: mapped_type mapped1;  
   hash_map <int, int> :: value_type value1;  
   hash_map <int, int> :: iterator pIter;  
  
   // value_type can be used to pass the correct type  
   // explicitely to avoid implicit type conversion  
   hm1.insert ( hash_map <int, int> :: value_type ( 1, 10 ) );  
  
   // Compare other ways to insert objects into a hash_map  
   hm1.insert ( cInt2Int ( 2, 20 ) );  
   hm1[ 3 ] = 30;  
  
   // Initializing key1 and mapped1  
   key1 = ( hm1.begin( ) -> first );  
   mapped1 = ( hm1.begin( ) -> second );  
  
   cout << "The key of first element in the hash_map is "  
        << key1 << "." << endl;  
  
   cout << "The data value of first element in the hash_map is "  
        << mapped1 << "." << endl;  
  
   // The following line would cause an error because  
   // the value_type is not assignable  
   // value1 = cInt2Int ( 4, 40 );  
  
   cout  << "The keys of the mapped elements are:";  
   for ( pIter = hm1.begin( ) ; pIter != hm1.end( ) ; pIter++ )  
      cout << " " << pIter -> first;  
   cout << "." << endl;  
  
   cout  << "The values of the mapped elements are:";  
   for ( pIter = hm1.begin( ) ; pIter != hm1.end( ) ; pIter++ )  
      cout << " " << pIter -> second;  
   cout << "." << endl;  
}  
```  
  
```Output  
The key of first element in the hash_map is 1.  
The data value of first element in the hash_map is 10.  
The keys of the mapped elements are: 1 2 3.  
The values of the mapped elements are: 10 20 30.  
```  
  
## <a name="see-also"></a>Consulte também  
 [Acesso Thread-Safe na Biblioteca Padrão C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Referência da biblioteca padrão C++](../standard-library/cpp-standard-library-reference.md)

