---
title: Funções &lt;memory&gt; | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- memory/std::addressof
- memory/std::align
- memory/std::allocate_shared
- memory/std::const_pointer_cast
- memory/std::declare_no_pointers
- memory/std::declare_reachable
- memory/std::default_delete
- memory/std::dynamic_pointer_cast
- memory/std::get_deleter
- memory/std::get_pointer_safety
- xmemory/std::get_temporary_buffer
- memory/std::make_shared
- memory/std::make_unique
- memory/std::owner_less
- xmemory/std::return_temporary_buffer
- memory/std::static_pointer_cast
- memory/std::swap
- memory/std::undeclare_no_pointers
- memory/std::undeclare_reachable
- memory/std::uninitialized_copy
- memory/std::uninitialized_copy_n
- memory/std::uninitialized_fill
- memory/std::uninitialized_fill_n
- memory/std::get_temporary_buffer
- memory/std::return_temporary_buffer
dev_langs:
- C++
ms.assetid: 3e1898c2-44b7-4626-87ce-84962e4c6f1a
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::addressof [C++]
- std::align [C++]
- std::allocate_shared [C++]
- std::const_pointer_cast [C++]
- std::declare_no_pointers [C++]
- std::declare_reachable [C++]
- std::default_delete [C++]
- std::dynamic_pointer_cast [C++]
- std::get_deleter [C++]
- std::get_pointer_safety [C++]
- std::get_temporary_buffer [C++]
- std::make_shared [C++]
- std::make_unique [C++]
- std::owner_less [C++]
- std::return_temporary_buffer [C++]
- std::static_pointer_cast [C++]
- std::swap [C++]
- std::undeclare_no_pointers [C++]
- std::undeclare_reachable [C++]
- std::uninitialized_copy [C++]
- std::uninitialized_copy_n [C++]
- std::uninitialized_fill [C++]
- std::uninitialized_fill_n [C++]
- std::addressof [C++]
- std::align [C++]
- std::allocate_shared [C++]
- std::const_pointer_cast [C++]
- std::declare_no_pointers [C++]
- std::declare_reachable [C++]
- std::default_delete [C++]
- std::dynamic_pointer_cast [C++]
- std::get_deleter [C++]
- std::get_pointer_safety [C++]
- std::get_temporary_buffer [C++]
- std::make_shared [C++]
- std::make_unique [C++]
- std::owner_less [C++]
- std::return_temporary_buffer [C++]
- std::static_pointer_cast [C++]
- std::undeclare_no_pointers [C++]
- std::undeclare_reachable [C++]
- std::uninitialized_copy [C++]
- std::uninitialized_copy_n [C++]
- std::uninitialized_fill [C++]
- std::uninitialized_fill_n [C++]
ms.workload:
- cplusplus
ms.openlocfilehash: b740613666c7e4e1b5cc2c1b14c5cbf04b0fe6ef
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702865"
---
# <a name="ltmemorygt-functions"></a>Funções &lt;memory&gt;

||||
|-|-|-|
|[addressof](#addressof)|[align](#align)|[allocate_shared](#allocate_shared)|
|[const_pointer_cast](#const_pointer_cast)|[declare_no_pointers](#declare_no_pointers)|[declare_reachable](#declare_reachable)|
|[default_delete](#default_delete)|[dynamic_pointer_cast](#dynamic_pointer_cast)|[get_deleter](#get_deleter)|
|[get_pointer_safety](#get_pointer_safety)|[get_temporary_buffer](#get_temporary_buffer)|[make_shared](#make_shared)|
|[make_unique](#make_unique)|[owner_less](#owner_less)|[return_temporary_buffer](#return_temporary_buffer)|
|[static_pointer_cast](#static_pointer_cast)|[swap (Biblioteca Padrão C++)](#swap)|[undeclare_no_pointers](#undeclare_no_pointers)|
|[undeclare_reachable](#undeclare_reachable)|[uninitialized_copy](#uninitialized_copy)|[uninitialized_copy_n](#uninitialized_copy_n)|
|[uninitialized_fill](#uninitialized_fill)|[uninitialized_fill_n](#uninitialized_fill_n)|

## <a name="addressof"></a>  addressof

Obtém o endereço verdadeiro de um objeto.

```cpp
template <class T>
T* addressof(T& Val);
```

### <a name="parameters"></a>Parâmetros

*Val*<br/>
O objeto ou a função para o qual obter o endereço verdadeiro.

### <a name="return-value"></a>Valor de retorno

O endereço real do objeto ou da função referenciado por *Val*, mesmo se houver um sobrecarregado `operator&()` existe.

### <a name="remarks"></a>Comentários

## <a name="align"></a>  align

Ajusta o armazenamento do tamanho fornecido (alinhado pela especificação de alinhamento fornecido) no primeiro endereço possível do armazenamento fornecido.

```cpp
void* align(
    size_t Alignment, // input
    size_t Size,      // input
    void*& Ptr,        // input/output
    size_t& Space     // input/output
);
```

### <a name="parameters"></a>Parâmetros

*Alinhamento*<br/>
O limite de alinhamento ser tentado.

*Size*<br/>
O tamanho em bytes para o armazenamento alinhado.

*PTR*<br/>
O endereço inicial do pool de armazenamento contíguo disponível a ser usado. Esse parâmetro também é um parâmetro de saída e é definido para conter o novo endereço inicial se o alinhamento for bem-sucedido. Se `align()` for malsucedido, esse parâmetro não será modificado.

*Espaço*<br/>
O espaço total disponível para `align()` a ser usado ao criar o armazenamento alinhado. Esse parâmetro também é um parâmetro de saída e contém o espaço ajustado deixado no buffer de armazenamento após o armazenamento alinhado e qualquer sobrecarga associada é subtraída.

Se `align()` for malsucedido, esse parâmetro não será modificado.

### <a name="return-value"></a>Valor de retorno

Um ponteiro nulo se o buffer alinhado solicitado não se ajusta ao espaço disponível. Caso contrário, o novo valor de *Ptr*.

### <a name="remarks"></a>Comentários

Modificado *Ptr* e *espaço* parâmetros permitem que você chame `align()` repetidamente no mesmo buffer, possivelmente com valores diferentes para *alinhamento* e  *Tamanho*. O snippet de código a seguir mostra um uso de `align()`.

```cpp
#include <type_traits> // std::alignment_of()
#include <memory>
//...
char buffer[256]; // for simplicity
size_t alignment = std::alignment_of<int>::value;
void * ptr = buffer;
std::size_t space = sizeof(buffer); // Be sure this results in the true size of your buffer

while (std::align(alignment, sizeof(MyObj), ptr, space)) {
    // You now have storage the size of MyObj, starting at ptr, aligned on
    // int boundary. Use it here if you like, or save off the starting address
    // contained in ptr for later use.
    // ...
    // Last, move starting pointer and decrease available space before
    // the while loop restarts.
    ptr = reinterpret_cast<char*>(ptr) + sizeof(MyObj);
    space -= sizeof(MyObj);
}
// At this point, align() has returned a null pointer, signaling it is not
// possible to allow more aligned storage in this buffer.
```

## <a name="allocate_shared"></a>  allocate_shared

Cria um `shared_ptr` para objetos alocados e construídos para um determinado tipo usando um alocador especificado. Retorna o `shared_ptr`.

```cpp
template <class Type, class Allocator, class... Types>
shared_ptr<Type>
allocate_shared(Allocator Alloc, Types&&... Args);
```

### <a name="parameters"></a>Parâmetros

*ALLOC*<br/>
O alocador usado para criar objetos.

*Args*<br/>
O zero ou mais argumentos que se tornam os objetos.

### <a name="remarks"></a>Comentários

A função cria o objeto `shared_ptr<Type>`, um ponteiro para `Type(Args...)` conforme alocado e construído por *Alloc*.

## <a name="const_pointer_cast"></a>  const_pointer_cast

Conversão constante para shared_ptr.

```cpp
template <class Ty, class Other>
shared_ptr<Ty>
const_pointer_cast(const shared_ptr<Other>& sp);
```

### <a name="parameters"></a>Parâmetros

*Ty*<br/>
O tipo controlado pelo ponteiro compartilhado retornado.

*Outros*<br/>
O tipo controlado pelo ponteiro compartilhado de argumento.

*Outros*<br/>
O ponteiro compartilhado de argumento.

### <a name="remarks"></a>Comentários

A função de modelo retorna um objeto shared_ptr vazio se `const_cast<Ty*>(sp.get())` retorna um ponteiro nulo; caso contrário, retornará um [classe shared_ptr](../standard-library/shared-ptr-class.md)\<Ty > objeto que possui o recurso que pertence a `sp`. A expressão `const_cast<Ty*>(sp.get())` deve ser válida.

### <a name="example"></a>Exemplo

```cpp
// std__memory__const_pointer_cast.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0(new int);
    std::shared_ptr<const int> sp1 =
        std::const_pointer_cast<const int>(sp0);

*sp0 = 3;
    std::cout << "sp1 == " << *sp1 << std::endl;

    return (0);
}
```

```Output
sp1 == 3
```

## <a name="declare_no_pointers"></a> declare_no_pointers

Informa um coletor de lixo que os caracteres no bloco de memória definido por um ponteiro de endereço básico e o tamanho de bloco não contêm ponteiros rastreáveis.

```cpp
void declare_no_pointers(
    char* ptr,
    size_t _Size);
```

### <a name="parameters"></a>Parâmetros

|Parâmetro|Descrição|
|---------------|-----------------|
|*ptr*|O endereço do primeiro caractere que não contém mais ponteiros rastreáveis.|
|*Tamanho*|Tamanho de bloco que começa em *ptr* que não contêm ponteiros rastreáveis.|

### <a name="remarks"></a>Comentários

A função informa qualquer coletor de lixo que o intervalo de endereços `[ ptr, ptr + _Size)` não contêm mais ponteiros rastreáveis. (Todos os ponteiros para o armazenamento alocado não devem ser desreferenciados a menos que tornando-se atingível.)

## <a name="declare_reachable"></a>  declare_reachable

Informa a coleta de lixo que o endereço indicado é para armazenamento alocado e é alcançável.

```cpp
void declare_reachable(void* ptr);
```

### <a name="parameters"></a>Parâmetros

*ptr*<br/>
Um ponteiro para uma área de armazenamento acessível, alocada e válida.

### <a name="remarks"></a>Comentários

Se *ptr* não for nulo, a função informa qualquer coletor de lixo que *ptr* daqui em diante é acessível (aponta para o armazenamento alocado válido).

## <a name="default_delete"></a>  default_delete

Exclui objetos alocados com **operador new**. Adequado para uso com `unique_ptr`.

```cpp
struct default_delete {
   constexpr default_delete() noexcept = default;
   template <class Other, class = typename enable_if<is_convertible<Other*, T*>::value, void>::type>>
   default_delete(const default_delete<Other>&) noexcept;
   void operator()(T* Ptr) const noexcept;
};
```

### <a name="parameters"></a>Parâmetros

*PTR*<br/>
Ponteiro para o objeto a ser excluído.

*Outros*<br/>
O tipo dos elementos na matriz a ser excluída.

### <a name="remarks"></a>Comentários

A classe de modelo descreve uma `deleter` que exclui objetos escalares alocados com **operador new**, adequado para uso com a classe de modelo `unique_ptr`. Ela também tem a especialização explícita `default_delete<Type[]>`.

## <a name="dynamic_pointer_cast"></a>  dynamic_pointer_cast

Conversão dinâmica para shared_ptr.

```cpp
template <class Ty, class Other>
shared_ptr<Ty>
dynamic_pointer_cast(const shared_ptr<Other>& sp);
```

### <a name="parameters"></a>Parâmetros

*Ty*<br/>
O tipo controlado pelo ponteiro compartilhado retornado.

*Outros*<br/>
O tipo controlado pelo ponteiro compartilhado de argumento.

*SP*<br/>
O ponteiro compartilhado de argumento.

### <a name="remarks"></a>Comentários

A função de modelo retorna um objeto shared_ptr vazio se `dynamic_cast<Ty*>(sp.get())` retorna um ponteiro nulo; caso contrário, retornará um [classe shared_ptr](../standard-library/shared-ptr-class.md)\<Ty > objeto que possui o recurso que pertence a *sp* . A expressão `dynamic_cast<Ty*>(sp.get())` deve ser válida.

### <a name="example"></a>Exemplo

```cpp
// std__memory__dynamic_pointer_cast.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct base
{
    virtual ~base() {}
    int val;
};

struct derived
    : public base
{
};

int main()
{
    std::shared_ptr<base> sp0(new derived);
    std::shared_ptr<derived> sp1 =
        std::dynamic_pointer_cast<derived>(sp0);

    sp0->val = 3;
    std::cout << "sp1->val == " << sp1->val << std::endl;

    return (0);
}
```

```Output
sp1->val == 3
```

## <a name="get_deleter"></a>  get_deleter

Obtenha o agente de exclusão de shared_ptr.

```cpp
template <class D, class Ty>
D* get_deleter(const shared_ptr<Ty>& sp);
```

### <a name="parameters"></a>Parâmetros

*D*<br/>
O tipo do agente de exclusão.

*Ty*<br/>
O tipo controlado pelo ponteiro compartilhado.

*SP*<br/>
O ponteiro compartilhado.

### <a name="remarks"></a>Comentários

A função de modelo retorna um ponteiro para o agente de exclusão do tipo *1!d* que pertence a [classe shared_ptr](../standard-library/shared-ptr-class.md) objeto *sp*. Se *sp* não tem nenhum agente de exclusão ou se o agente de exclusão não é do tipo *1!d* a função retornará 0.

### <a name="example"></a>Exemplo

```cpp
// std__memory__get_deleter.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct base
{
    int val;
};

struct deleter
{
    void operator()(base *p)
    {
        delete p;
    }
};

int main()
{
    std::shared_ptr<base> sp0(new base);

    sp0->val = 3;
    std::cout << "get_deleter(sp0) != 0 == " << std::boolalpha
        << (std::get_deleter<deleter>(sp0) != 0) << std::endl;

    std::shared_ptr<base> sp1(new base, deleter());

    sp0->val = 3;
    std::cout << "get_deleter(sp1) != 0 == " << std::boolalpha
        << (std::get_deleter<deleter>(sp1) != 0) << std::endl;

    return (0);
}

```

```Output
get_deleter(sp0) != 0 == false
get_deleter(sp1) != 0 == true
```

## <a name="get_pointer_safety"></a>  get_pointer_safety

Retorna o tipo de segurança do ponteiro pressuposto por qualquer coletor de lixo.

```cpp
pointer_safety get_pointer_safety();
```

### <a name="remarks"></a>Comentários

A função retorna o tipo de segurança do ponteiro pressuposto por qualquer coletor de lixo automática.

## <a name="get_temporary_buffer"></a>  get_temporary_buffer

Atribui o armazenamento temporário para uma sequência de elementos que não excede um número especificado de elementos.

```cpp
template <class Type>
pair<Type *, ptrdiff_t> get_temporary_buffer(ptrdiff_t count);
```

### <a name="parameters"></a>Parâmetros

*count*<br/>
O número máximo de elementos solicitados para o qual a memória deve ser alocada.

### <a name="return-value"></a>Valor de retorno

Um `pair` cujo primeiro componente é um ponteiro para a memória que foi alocada e cujo segundo componente retorna o tamanho do buffer, indicando o maior número de elementos que ele pode armazenar.

### <a name="remarks"></a>Comentários

A função faz uma solicitação de memória e ela pode não ser bem-sucedida. Se nenhum é for alocado, a função retornará um par, com o segundo componente igual a zero e o primeiro componente igual ao ponteiro nulo.

Essa função deve ser usada apenas para a memória que é temporária.

### <a name="example"></a>Exemplo

```cpp
// memory_get_temp_buf.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

using namespace std;

int main( )
{
   // Create an array of ints
   int intArray [ ] = { 10, 20, 30, 40, 100, 200, 300, 1000, 2000 };
   int count = sizeof ( intArray ) / sizeof ( int );
   cout << "The number of integers in the array is: "
      << count << "." << endl;

   pair<int *, ptrdiff_t> resultPair;
   resultPair = get_temporary_buffer<int>( count );

   cout << "The number of elements that the allocated memory\n"
        << "could store is given by: resultPair.second = "
        << resultPair.second << "." << endl;
}
```

```Output
The number of integers in the array is: 9.
The number of elements that the allocated memory
could store is given by: resultPair.second = 9.
```

## <a name="make_shared"></a>  make_shared

Cria e retorna um `shared_ptr` que aponta para os objetos alocados construídos de zero ou mais argumentos usando o alocador padrão. Aloca e constrói um objeto do tipo especificado e um `shared_ptr` para gerenciar a propriedade compartilhada do objeto e retorna o `shared_ptr`.

```cpp
template <class Type, class... Types>
shared_ptr<Type>
make_shared(Types&&... _Args);
```

### <a name="parameters"></a>Parâmetros

|Parâmetro|Descrição|
|---------------|-----------------|
|*_Args*|Zero ou mais argumentos de construtor. A função infere qual sobrecarga de construtor deve ser invocada com base nos argumentos fornecidos.|

### <a name="remarks"></a>Comentários

Use `make_shared` como uma forma simples e mais eficiente de criar um objeto e um `shared_ptr` para gerenciar o acesso compartilhado para o objeto ao mesmo tempo. Semanticamente, essas duas instruções são equivalentes:

```cpp
auto sp = std::shared_ptr<Example>(new Example(argument));
auto msp = std::make_shared<Example>(argument);
```

No entanto, a primeira instrução faz duas alocações e se a alocação do `shared_ptr` falhar após a alocação do objeto `Example` ter sido bem sucedida, o objeto `Example` sem nome será vazado. A instrução que usa `make_shared` é mais simples porque há apenas uma chamada de função envolvida. Ela é mais eficiente porque a biblioteca pode fazer uma única alocação do objeto e do ponteiro inteligente. Isso é mais rápido e resulta em menos fragmentação da memória e não há nenhuma chance de uma exceção em uma alocação, mas não na outra. O desempenho é melhorado pela melhor localidade para o código que faz referência ao objeto e atualiza as contagens de referência no ponteiro inteligente.

Considere o uso de [make_unique](../standard-library/memory-functions.md#make_unique) se não precisar de acesso compartilhado ao objeto. Use [allocate_shared](../standard-library/memory-functions.md#allocate_shared) se você precisar especificar um alocador personalizado para o objeto. Não será possível usar `make_shared` se o objeto exigir um agente de exclusão personalizado, pois não há como passar o agente de exclusão como um argumento.

O exemplo a seguir mostra como criar ponteiros compartilhados para um tipo invocando as sobrecargas do construtor específicas.

### <a name="example"></a>Exemplo

```cpp
// stl_make_shared.cpp
// Compile by using: cl /W4 /EHsc stl_make_shared.cpp
#include <iostream>
#include <string>
#include <memory>
#include <vector>

class Song {
public:
   std::wstring title_;
   std::wstring artist_;

   Song(std::wstring title, std::wstring artist) : title_(title), artist_(artist) {}
   Song(std::wstring title) : title_(title), artist_(L"Unknown") {}
};

void CreateSharedPointers() {
   // Okay, but less efficient to have separate allocations for
   // Song object and shared_ptr control block.
   auto song = new Song(L"Ode to Joy", L"Beethoven");
   std::shared_ptr<Song> sp0(song);

   // Use make_shared function when possible. Memory for control block
   // and Song object are allocated in the same call:
   auto sp1 = std::make_shared<Song>(L"Yesterday", L"The Beatles");
   auto sp2 = std::make_shared<Song>(L"Blackbird", L"The Beatles");

   // make_shared infers which constructor to use based on the arguments.
   auto sp3 = std::make_shared<Song>(L"Greensleeves");

   // The playlist vector makes copies of the shared_ptr pointers.
   std::vector<std::shared_ptr<Song>> playlist;
   playlist.push_back(sp0);
   playlist.push_back(sp1);
   playlist.push_back(sp2);
   playlist.push_back(sp3);
   playlist.push_back(sp1);
   playlist.push_back(sp2);
   for (auto&& sp : playlist) {
      std::wcout << L"Playing " << sp->title_ <<
         L" by " << sp->artist_ << L", use count: " <<
         sp.use_count() << std::endl;
   }
}

int main() {
   CreateSharedPointers();
}
```

O exemplo produz essa saída:

```Output
Playing Ode to Joy by Beethoven, use count: 2
Playing Yesterday by The Beatles, use count: 3
Playing Blackbird by The Beatles, use count: 3
Playing Greensleeves by Unknown, use count: 2
Playing Yesterday by The Beatles, use count: 3
Playing Blackbird by The Beatles, use count: 3
```

## <a name="make_unique"></a>  make_unique

Cria e retorna um [unique_ptr](../standard-library/unique-ptr-class.md) para um objeto do tipo especificado, que é construído usando os argumentos especificados.

```cpp
// make_unique<T>
template <class T, class... Types>
unique_ptr<T>
make_unique(Types&&... Args)
{
    return (unique_ptr<T>(new T(forward<Types>(Args)...)));
}

// make_unique<T[]>
template <class T>
make_unique(size_t Size)
{
    return (unique_ptr<T>(new Elem[Size]()));
}

// make_unique<T[N]> disallowed
template <class T, class... Types>
typename enable_if<extent<T>::value != 0, void>::type
make_unique(Types&&...) = delete;
```

### <a name="parameters"></a>Parâmetros

*T*<br/>
O tipo do objeto para o qual o `unique_ptr` apontará.

*Tipos*<br/>
Os tipos dos argumentos do construtor especificados por *Args*.

*Args*<br/>
Os argumentos a serem passados para o construtor do objeto do tipo *T*.

*Elem*<br/>
Uma matriz de elementos do tipo *T*.

*Size*<br/>
O número de elementos para os quais alocar espaço na nova matriz.

### <a name="remarks"></a>Comentários

A primeira sobrecarga é usada para objetos únicos, a segunda sobrecarga é invocada para matrizes e a terceira sobrecarga impede que você especifique um tamanho de matriz no argumento de tipo (make_unique\<T[N]>), não há suporte para essa construção no padrão atual. Quando você usa `make_unique` para criar um `unique_ptr` para uma matriz, é necessário inicializar os elementos da matriz separadamente. Se você estiver considerando essa sobrecarga, talvez a melhor opção seja usar um [std::vector](../standard-library/vector-class.md).

Como `make_unique` é cuidadosamente implementado para a segurança de exceção, é recomendável usar `make_unique` em vez de chamar diretamente os construtores `unique_ptr`.

### <a name="example"></a>Exemplo

O exemplo a seguir mostra como usar `make_unique`. Para mais exemplos, consulte [Como criar e usar instâncias unique_ptr](../cpp/how-to-create-and-use-unique-ptr-instances.md).

[!code-cpp[stl_smart_pointers#214](../cpp/codesnippet/CPP/memory-functions_1.cpp)]

Quando você vir o erro C2280 em conexão com um `unique_ptr`, provavelmente é porque você está tentando invocar o construtor de cópia, o que é uma função excluída.

## <a name="owner_less"></a>  owner_less

Permite comparações mistas baseadas em propriedade de ponteiros compartilhados e fracos. Retorna **verdadeira** se o parâmetro esquerdo for ordenado antes do parâmetro direito pela função de membro `owner_before`.

```cpp
template <class Type>
struct owner_less; // not defined

template <class Type>
struct owner_less<shared_ptr<Type>> {
    bool operator()(
    const shared_ptr<Type>& left,
    const shared_ptr<Type>& right);

    bool operator()(
    const shared_ptr<Type>& left,
    const weak_ptr<Type>& right);

    bool operator()(
    const weak_ptr<Type>& left,
    const shared_ptr<Type>& right);
};

template <class Type>
struct owner_less<weak_ptr<Type>>
    bool operator()(
    const weak_ptr<Type>& left,
    const weak_ptr<Type>& right);

    bool operator()(
    const weak_ptr<Type>& left,
    const shared_ptr<Ty>& right);

    bool operator()(
    const shared_ptr<Type>& left,
    const weak_ptr<Type>& right);
};
```

### <a name="parameters"></a>Parâmetros

*à esquerda*<br/>
Um ponteiro compartilhado ou fraco.

*right*<br/>
Um ponteiro compartilhado ou fraco.

### <a name="remarks"></a>Comentários

As classes de modelo definem todos os operadores membro como `left.owner_before(right)` de retorno.

## <a name="return_temporary_buffer"></a>  return_temporary_buffer

Desaloca a memória temporária que foi alocada usando a função de modelo `get_temporary_buffer`.

```cpp
template <class Type>
void return_temporary_buffer(Type* _Pbuf);
```

### <a name="parameters"></a>Parâmetros

*_Pbuf*<br/>
Um ponteiro para a memória a ser desalocada.

### <a name="remarks"></a>Comentários

Essa função deve ser usada apenas para a memória que é temporária.

### <a name="example"></a>Exemplo

```cpp
// memory_ret_temp_buf.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

using namespace std;

int main( )
{
   // Create an array of ints
   int intArray [ ] = { 10, 20, 30, 40, 100, 200, 300 };
   int count = sizeof ( intArray ) / sizeof ( int );
   cout << "The number of integers in the array is: "
         << count << "." << endl;

   pair<int *, ptrdiff_t> resultPair;
   resultPair = get_temporary_buffer<int>( count );

   cout << "The number of elements that the allocated memory\n"
         << " could store is given by: resultPair.second = "
         << resultPair.second << "." << endl;

   int* tempBuffer = resultPair.first;

   // Deallocates memory allocated with get_temporary_buffer
   return_temporary_buffer ( tempBuffer );
}
```

```Output
The number of integers in the array is: 7.
The number of elements that the allocated memory
could store is given by: resultPair.second = 7.
```

## <a name="static_pointer_cast"></a>  static_pointer_cast

Conversão estática para shared_ptr.

```cpp
template <class Ty, class Other>
shared_ptr<Ty>
static_pointer_cast(const shared_ptr<Other>& sp);
```

### <a name="parameters"></a>Parâmetros

*Ty*<br/>
O tipo controlado pelo ponteiro compartilhado retornado.

*Outros*<br/>
O tipo controlado pelo ponteiro compartilhado de argumento.

*Outros*<br/>
O ponteiro compartilhado de argumento.

### <a name="remarks"></a>Comentários

A função de modelo retorna um objeto shared_ptr vazio se `sp` está vazio `shared_ptr` objeto; caso contrário, retornará uma [classe shared_ptr](../standard-library/shared-ptr-class.md)\<Ty > objeto que possui o recurso que pertence a `sp`. A expressão `static_cast<Ty*>(sp.get())` deve ser válida.

### <a name="example"></a>Exemplo

```cpp
// std__memory__static_pointer_cast.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct base
{
    int val;
};

struct derived
    : public base
{
};

int main()
{
    std::shared_ptr<base> sp0(new derived);
    std::shared_ptr<derived> sp1 =
        std::static_pointer_cast<derived>(sp0);

    sp0->val = 3;
    std::cout << "sp1->val == " << sp1->val << std::endl;

    return (0);
}
```

```Output
sp1->val == 3
```

## <a name="swap"></a> swap (Biblioteca Padrão C++)

Troque dois objetos shared_ptr ou weak_ptr.

```cpp
template <class Ty, class Other>
void swap(shared_ptr<Ty>& left, shared_ptr<Other>& right);

template <class Ty, class Other>
void swap(weak_ptr<Ty>& left, weak_ptr<Other>& right);
```

### <a name="parameters"></a>Parâmetros

*Ty*<br/>
O tipo controlado pelo ponteiro compartilhado/fraco esquerdo.

*Outros*<br/>
O tipo controlado pelo ponteiro compartilhado/fraco direito.

*left*<br/>
O ponteiro compartilhado/fraco esquerdo.

*right*<br/>
O ponteiro compartilhado/fraco direito.

### <a name="remarks"></a>Comentários

As funções de modelo chamam `left.swap(right)`.

### <a name="example"></a>Exemplo

```cpp
// std__memory__swap.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct deleter
{
    void operator()(int *p)
    {
        delete p;
    }
};

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::shared_ptr<int> sp2(new int(10));
    std::cout << "*sp1 == " << *sp1 << std::endl;

    sp1.swap(sp2);
    std::cout << "*sp1 == " << *sp1 << std::endl;

    swap(sp1, sp2);
    std::cout << "*sp1 == " << *sp1 << std::endl;
    std::cout << std::endl;

    std::weak_ptr<int> wp1(sp1);
    std::weak_ptr<int> wp2(sp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    wp1.swap(wp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    swap(wp1, wp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    return (0);
}
```

```Output
*sp1 == 5
*sp1 == 10
*sp1 == 5

*wp1 == 5
*wp1 == 10
*wp1 == 5
```

## <a name="undeclare_no_pointers"></a>  undeclare_no_pointers

Informa um coletor de lixo que os caracteres no bloco de memória definido por um ponteiro de endereço básico e o tamanho de bloco agora podem conter ponteiros rastreáveis.

```cpp
void undeclare_no_pointers(
    char* ptr,
    size_t _Size);
```

### <a name="remarks"></a>Comentários

A função informa qualquer coletor de lixo que o intervalo de endereços `[ptr, ptr + _Size)` agora podem conter ponteiros rastreáveis.

## <a name="undeclare_reachable"></a>  undeclare_reachable

Revoga uma declaração de acessibilidade para um local de memória especificado.

```cpp
template <class Type>
Type *undeclare_reachable(Type* ptr);
```

### <a name="parameters"></a>Parâmetros

|Parâmetro|Descrição|
|---------------|-----------------|
|*ptr*|Um ponteiro para o endereço de memória a ser declarado como inacessível.|

### <a name="remarks"></a>Comentários

Se *ptr* não está **nullptr**, a função informa qualquer coletor de lixo que *ptr* não está mais acessível. Ele retorna um ponteiro de derivados de forma segura que compara igual a *ptr*.

## <a name="uninitialized_copy"></a>  uninitialized_copy

Copia objetos de um intervalo de origem especificado em um intervalo de destino não inicializado.

```cpp
template <class InputIterator, class ForwardIterator>
ForwardIterator uninitialized_copy(InputIterator first, InputIterator last, ForwardIterator dest);
```

### <a name="parameters"></a>Parâmetros

*first*<br/>
Um iterador de entrada que trata o primeiro elemento no intervalo de origem.

*last*<br/>
Um iterador de entrada que trata o último elemento no intervalo de origem.

*dest*<br/>
Um iterador de avanço que trata o primeiro elemento no intervalo de destino.

### <a name="return-value"></a>Valor de retorno

Um iterador de avanço que trata a primeira posição além do intervalo de destino, a menos que o intervalo de origem estava vazio.

### <a name="remarks"></a>Comentários

Esse algoritmo permite dissociar a alocação da memória da construção do objeto.

A função de modelo é executada efetivamente:

```cpp
while (first != last) {
    new (static_cast<void*>(&* dest++))
        typename iterator_traits<InputIterator>::value_type(*first++);
}
return dest;
```

a menos que o código lance uma exceção. Nesse caso, todos os objetos construídos são destruídos e a exceção é relançada.

### <a name="example"></a>Exemplo

```cpp
// memory_uninit_copy.cpp
// compile with: /EHsc /W3
#include <memory>
#include <iostream>

using namespace std;

class Integer
{
public:
    Integer(int x) : val(x) {}
    int get() { return val; }
private:
    int val;
};

int main()
{
    int Array[] = { 10, 20, 30, 40 };
    const int N = sizeof(Array) / sizeof(int);

    int i;
    cout << "The initialized Array contains " << N << " elements: ";
    for (i = 0; i < N; i++)
    {
        cout << " " << Array[i];
    }
    cout << endl;

    Integer* ArrayPtr = (Integer*)malloc(N * sizeof(int));
    Integer* LArrayPtr = uninitialized_copy(
        Array, Array + N, ArrayPtr);  // C4996

    cout << "Address of position after the last element in the array is: "
        << &Array[0] + N << endl;
    cout << "The iterator returned by uninitialized_copy addresses: "
        << (void*)LArrayPtr << endl;
    cout << "The address just beyond the last copied element is: "
        << (void*)(ArrayPtr + N) << endl;

    if ((&Array[0] + N) == (void*)LArrayPtr)
        cout << "The return value is an iterator "
        << "pointing just beyond the original array." << endl;
    else
        cout << "The return value is an iterator "
        << "not pointing just beyond the original array." << endl;

    if ((void*)LArrayPtr == (void*)(ArrayPtr + N))
        cout << "The return value is an iterator "
        << "pointing just beyond the copied array." << endl;
    else
        cout << "The return value is an iterator "
        << "not pointing just beyond the copied array." << endl;

    free(ArrayPtr);

    cout << "Note that the exact addresses returned will vary\n"
        << "with the memory allocation in individual computers."
        << endl;
}
```

## <a name="uninitialized_copy_n"></a>  uninitialized_copy_n

Cria uma cópia de um número especificado de elementos de um iterador de entrada. As cópias são colocadas em um iterador de avanço.

```cpp
template <class InputIterator, class Size, class ForwardIterator>
ForwardIterator uninitialized_copy_n(
    InputIterator first,
    Size count,
    ForwardIterator dest);
```

### <a name="parameters"></a>Parâmetros

*first*<br/>
Um iterador de entrada que faz referência ao objeto a ser copiado.

*count*<br/>
Um tipo de inteiro com sinal e sem sinal que especifica o número de vezes que o objeto deve ser copiado.

*dest*<br/>
Um iterador de avanço que faz referência ao local das novas cópias.

### <a name="return-value"></a>Valor de retorno

Um iterador de avanço que atende à primeira posição além do destino. Se o intervalo de origem estiver vazio, o iterador abordará *primeiro*.

### <a name="remarks"></a>Comentários

A função de modelo executa eficazmente o seguinte:

```cpp
    for (; 0 < count; --count)
        new (static_cast<void*>(&* dest++))
            typename iterator_traits<InputIterator>::value_type(*first++);
    return dest;
```

a menos que o código lance uma exceção. Nesse caso, todos os objetos construídos são destruídos e a exceção é relançada.

## <a name="uninitialized_fill"></a>  uninitialized_fill

Copia objetos de um valor especificado em um intervalo de destino não inicializado.

```cpp
template <class ForwardIterator, class Type>
void uninitialized_fill(ForwardIterator first, ForwardIterator last, const Type& val);
```

### <a name="parameters"></a>Parâmetros

*first*<br/>
Um iterador de avanço que trata o primeiro elemento no intervalo de destino a ser iniciado.

*last*<br/>
Um iterador de avanço que trata o último elemento no intervalo de destino a ser iniciado.

*Val*<br/>
O valor a ser usado para inicializar o intervalo de destino.

### <a name="remarks"></a>Comentários

Esse algoritmo permite dissociar a alocação da memória da construção do objeto.

A função de modelo é executada efetivamente:

```cpp
while (first != last)
    new (static_cast<void*>(&* first ++))
        typename iterator_traits<ForwardIterator>::value_type (val);
```

a menos que o código lance uma exceção. Nesse caso, todos os objetos construídos são destruídos e a exceção é relançada.

### <a name="example"></a>Exemplo

```cpp
// memory_uninit_fill.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

using namespace std;

class Integer {         // No default constructor
   public:
      Integer( int x ) : val( x ) {}
      int get( ) { return val; }
   private:
      int val;
};

int main( )
{
   const int N = 10;
   Integer val ( 25 );
   Integer* Array = ( Integer* ) malloc( N * sizeof( int ) );
   uninitialized_fill( Array, Array + N, val );
   int i;
   cout << "The initialized Array contains: ";
      for ( i = 0 ; i < N; i++ )
      {
         cout << Array [ i ].get( ) << " ";
      }
   cout << endl;
}
```

```Output
The initialized Array contains: 25 25 25 25 25 25 25 25 25 25
```

## <a name="uninitialized_fill_n"></a>  uninitialized_fill_n

Copia objetos de um valor especificado em um número especificado de elementos em um intervalo de destino não inicializado.

```cpp
template <class FwdIt, class Size, class Type>
void uninitialized_fill_n(ForwardIterator first, Size count, const Type& val);
```

### <a name="parameters"></a>Parâmetros

*first*<br/>
Um iterador de avanço que trata o primeiro elemento no intervalo de destino a ser iniciado.

*count*<br/>
O número de elementos a ser inicializado.

*Val*<br/>
O valor a ser usado para inicializar o intervalo de destino.

### <a name="remarks"></a>Comentários

Esse algoritmo permite dissociar a alocação da memória da construção do objeto.

A função de modelo é executada efetivamente:

```cpp
while (0 < count--)
    new (static_cast<void*>(&* first++))
        typename iterator_traits<ForwardIterator>::value_type(val);
```

a menos que o código lance uma exceção. Nesse caso, todos os objetos construídos são destruídos e a exceção é relançada.

### <a name="example"></a>Exemplo

```cpp
// memory_uninit_fill_n.cpp
// compile with: /EHsc /W3
#include <memory>
#include <iostream>

using namespace std;

class Integer {   // No default constructor
public:
   Integer( int x ) : val( x ) {}
   int get( ) { return val; }
private:
   int val;
};

int main() {
   const int N = 10;
   Integer val ( 60 );
   Integer* Array = ( Integer* ) malloc( N * sizeof( int ) );
   uninitialized_fill_n( Array, N, val );  // C4996
   int i;
   cout << "The uninitialized Array contains: ";
   for ( i = 0 ; i < N; i++ )
      cout << Array [ i ].get( ) <<  " ";
}
```

## <a name="see-also"></a>Consulte também

[\<memory>](../standard-library/memory.md)<br/>
