---
title: Suporte ao iterador de depuração | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- Safe Libraries
- Safe Libraries, C++ Standard Library
- Safe C++ Standard Library
- C++ Standard Library, debug iterator support
- iterators, debug iterator support
- iterators, incompatible
- incompatible iterators
- debug iterator support
ms.assetid: f3f5bd15-4be8-4d64-a4d0-8bc0761c68b6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ffcd69475d13277884deaf9ee114f3cd8d86516f
ms.sourcegitcommit: 87d317ac62620c606464d860aaa9e375a91f4c99
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2018
ms.locfileid: "45601464"
---
# <a name="debug-iterator-support"></a>Suporte a Iterador de Depuração

A biblioteca em tempo de execução Visual C++ detecta o uso incorreto do iterador e declara e exibe uma caixa de diálogo em tempo de execução. Para habilitar o suporte do iterador de depuração, é necessário usar versões de depuração da Biblioteca Padrão C++ e da Biblioteca em Tempo de Execução C para compilar seu programa. Para obter mais informações, consulte [Recursos da biblioteca CRT](../c-runtime-library/crt-library-features.md). Para obter informações sobre como usar iteradores verificados, consulte [Iteradores verificados](../standard-library/checked-iterators.md).

O padrão C++ descreve como funções de membro podem fazer com que iteradores em um contêiner se tornem inválidos. Dois exemplos são:

- Apagar um elemento de um contêiner faz com que os iteradores no elemento se tornem inválidos.

- Aumentar o tamanho de um [vector](../standard-library/vector.md) por meio de envio por push ou inserção faz com que os iteradores no `vector` se tornem inválidos.

## <a name="invalid-iterators"></a>Iteradores inválidos

Se você compilar esse programa de amostra no modo de depuração, ele será declarado e encerrado em tempo de execução.

```cpp
// iterator_debugging_0.cpp
// compile by using /EHsc /MDd
#include <vector>
#include <iostream>

int main() {
   std::vector<int> v {10, 15, 20};
   std::vector<int>::iterator i = v.begin();
   ++i;

   std::vector<int>::iterator j = v.end();
   --j;

   std::cout << *j << '\n';

   v.insert(i,25);

   std::cout << *j << '\n'; // Using an old iterator after an insert
}
```

## <a name="using-iteratordebuglevel"></a>Usando iterator_debug_level

É possível usar a macro do pré-processador [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) para desligar o recurso do iterador de depuração em um build de depuração. Esse programa não é declarado, mas ainda dispara um comportamento indefinido.

```cpp
// iterator_debugging_1.cpp
// compile by using: /EHsc /MDd
#define _ITERATOR_DEBUG_LEVEL 0
#include <vector>
#include <iostream>

int main() {
    std::vector<int> v {10, 15, 20};

   std::vector<int>::iterator i = v.begin();
   ++i;

   std::vector<int>::iterator j = v.end();
   --j;

   std::cout << *j << '\n';

   v.insert(i,25);

   std::cout << *j << '\n'; // Using an old iterator after an insert
}
```

```Output
20
-572662307
```

## <a name="unitialized-iterators"></a>Iteradores não inicializados

Uma declaração também ocorrerá se você tentar usar um iterador antes de ele ser inicializado, conforme mostrado aqui:

```cpp
// iterator_debugging_2.cpp
// compile by using: /EHsc /MDd
#include <string>
using namespace std;

int main() {
   string::iterator i1, i2;
   if (i1 == i2)
      ;
}
```

## <a name="incompatible-iterators"></a>Iteradores incompatíveis

O exemplo de código a seguir causa uma declaração, pois os dois iteradores do algoritmo [for_each](../standard-library/algorithm-functions.md#for_each) são incompatíveis. Os algoritmos verificam para determinar se os iteradores fornecidos para eles referenciam o mesmo contêiner.

```cpp
// iterator_debugging_3.cpp
// compile by using /EHsc /MDd
#include <algorithm>
#include <vector>
using namespace std;

int main()
{
    vector<int> v1 {10, 20};
    vector<int> v2 {10, 20};

    // The next line asserts because v1 and v2 are
    // incompatible.
    for_each(v1.begin(), v2.end(), [] (int& elem) { elem *= 2; } );
}
```

Observe que esse exemplo usa a expressão lambda `[] (int& elem) { elem *= 2; }` em vez de um functor. Embora essa escolha não tenha efeito sobre a falha de declaração – um functor semelhante causaria a mesma falha –, lambdas são uma maneira muito útil de realizar tarefas compactas de objeto de função. Para obter mais informações sobre expressões lambda, consulte [Expressões lambda](../cpp/lambda-expressions-in-cpp.md).

## <a name="iterators-going-out-of-scope"></a>Iteradores indo fora do escopo

Verificações do iterador de depuração também fazem com que uma variável do iterador declarada em um **para** loop fique fora do escopo quando o **para** término do escopo de loop.

```cpp
// iterator_debugging_4.cpp
// compile by using: /EHsc /MDd
#include <vector>
#include <iostream>
int main() {
   std::vector<int> v {10, 15, 20};

   for (std::vector<int>::iterator i = v.begin(); i != v.end(); ++i)
      ;   // do nothing
   --i;   // C2065
}
```

## <a name="destructors-for-debug-iterators"></a>Destruidores para iteradores de depuração

Iteradores de depuração têm destruidores não triviais. Se um destruidor não é executado, mas a memória do objeto é liberada, pode ocorrer corrupção de dados e violações de acesso. Considere este exemplo:

```cpp
// iterator_debugging_5.cpp
// compile by using: /EHsc /MDd
#include <vector>
struct base {
   // TO FIX: uncomment the next line
   // virtual ~base() {}
};

struct derived : base {
   std::vector<int>::iterator m_iter;
   derived( std::vector<int>::iterator iter ) : m_iter( iter ) {}
   ~derived() {}
};

int main() {
  auto vect = std::vector<int>(10);
  auto sink = new auto(std::begin(vect));
  ::operator delete(sink); // frees the memory without calling ~iterator()
} // access violation
```

## <a name="see-also"></a>Consulte também

[Visão geral da biblioteca padrão C++](../standard-library/cpp-standard-library-overview.md)<br/>
