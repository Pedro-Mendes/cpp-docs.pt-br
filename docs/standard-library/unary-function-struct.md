---
title: unary_function Struct | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- functional/std::unary
dev_langs:
- C++
helpviewer_keywords:
- unary_function class
ms.assetid: 04c2fbdc-c1f6-48ed-b6cc-292a6d484627
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff8e486be6e28de313a8e1a20634af4c50c350e8
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44313852"
---
# <a name="unaryfunction-struct"></a>Struct unary_function

Um struct vazio de base que define os tipos que podem ser herdados por classes derivadas que fornece um objeto de função unária.

## <a name="syntax"></a>Sintaxe

```cpp
struct unary_function
{
   typedef Arg argument_type;
   typedef Result result_type;
};
```
## <a name="remarks"></a>Comentários

O struct de modelo serve como base para classes que definem uma função membro no formato **result_type**`operator()`( **constargument_type&**) **const**.

Todas as funções unárias derivadas podem se referir ao tipo único de argumento como **argument_type** e seu tipo de retorno como **result_type**.

## <a name="example"></a>Exemplo

```cpp
// functional_unary_function.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

// Creation of a user-defined function object
// that inherits from the unary_function base class
class greaterthan10: unary_function<int, bool>
{
public:
    result_type operator()(argument_type i)
    {
        return (result_type)(i > 10);
    }
};

int main()
{
    vector<int> v1;
    vector<int>::iterator Iter;

    int i;
    for (i = 0; i <= 5; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( " ;
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    vector<int>::iterator::difference_type result1;
    result1 = count_if(v1.begin(), v1.end(), greaterthan10());
    cout << "The number of elements in v1 greater than 10 is: "
         << result1 << "." << endl;
}
/* Output:
The vector v1 = ( 0 5 10 15 20 25 )
The number of elements in v1 greater than 10 is: 3.
*/
```

## <a name="requirements"></a>Requisitos

**Cabeçalho:** \<functional>

**Namespace:** std

## <a name="see-also"></a>Consulte também

[Acesso Thread-Safe na Biblioteca Padrão C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Referência da biblioteca padrão C++](../standard-library/cpp-standard-library-reference.md)<br/>
