---
title: Resolução de nomes para tipos dependentes | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 34066bb4-0c79-4fd8-bda7-539a60a277ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c17a29f0287ee25517ed72f1c98caa2d38a96195
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040138"
---
# <a name="name-resolution-for-dependent-types"></a>Resolução de nome para tipos dependentes

Use **typename** para nomes qualificados em definições de modelo para dizer ao compilador que o nome qualificado fornecido identifica um tipo. Para obter mais informações, consulte [typename](../cpp/typename.md).

```cpp
// template_name_resolution1.cpp
#include <stdio.h>
template <class T> class X
{
public:
   void f(typename T::myType* mt) {}
};

class Yarg
{
public:
   struct myType { };
};

int main()
{
   X<Yarg> x;
   x.f(new Yarg::myType());
   printf("Name resolved by using typename keyword.");
}
```

```Output
Name resolved by using typename keyword.
```

Pesquisa de nome para nomes dependentes examina nomes do contexto da definição de modelo — no exemplo a seguir, esse contexto encontraria `myFunction(char)`— e o contexto de instanciação de modelo. No exemplo a seguir, o modelo é instanciado em main; Portanto, o `MyNamespace::myFunction` é visível do ponto de instanciação e é escolhido como a melhor correspondência. Se `MyNamespace::myFunction` fosse renomeado, `myFunction(char)` seria chamado.

Todos os nomes são resolvidos como se fossem nomes dependentes. Entretanto, recomendamos que você use nomes totalmente qualificados se houver qualquer conflito possível.

```cpp
// template_name_resolution2.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

void myFunction(char)
{
   cout << "Char myFunction" << endl;
}

template <class T> class Class1
{
public:
   Class1(T i)
   {
      // If replaced with myFunction(1), myFunction(char)
      // will be called
      myFunction(i);
}
};

namespace MyNamespace
{
   void myFunction(int)
   {
      cout << "Int MyNamespace::myFunction" << endl;
   }
};

using namespace MyNamespace;

int main()
{
   Class1<int>* c1 = new Class1<int>(100);
}
```

### <a name="output"></a>Saída

```Output
Int MyNamespace::myFunction
```

### <a name="template-disambiguation"></a>Desambiguação de modelo

Visual Studio 2012 impõe as C + + 98/03/11 regras padrão para a desambiguação com a palavra-chave "template". No exemplo a seguir, o Visual C++ 2010 aceitaria aceitaria as linhas e as linhas em conformidade.  Visual Studio 2012 aceita apenas as linhas em conformidade.

```cpp
#include <iostream>
#include <ostream>
#include <typeinfo>
using namespace std;

template <typename T> struct Allocator {
    template <typename U> struct Rebind {
        typedef Allocator<U> Other;
    };
};

template <typename X, typename AY> struct Container {
    #if defined(NONCONFORMANT)
        typedef typename AY::Rebind<X>::Other AX; // nonconformant
    #elif defined(CONFORMANT)
        typedef typename AY::template Rebind<X>::Other AX; // conformant
    #else
        #error Define NONCONFORMANT or CONFORMANT.
    #endif
};

int main() {
    cout << typeid(Container<int, Allocator<float>>::AX).name() << endl;
}
```

A conformidade com as regras de desambiguação é necessária porque, por padrão, o C++ presume que `AY::Rebind` não seja um modelo e, assim, o compilador interpreta o seguinte “`<`” como menor que. Ele precisa saber que `Rebind` é um modelo para poder analisar corretamente “`<`” como um colchete angular.

## <a name="see-also"></a>Consulte também

[Resolução de nome](../cpp/templates-and-name-resolution.md)