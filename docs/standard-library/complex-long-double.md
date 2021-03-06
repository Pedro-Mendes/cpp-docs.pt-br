---
title: complex&lt;long double&gt; | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- std::complex<long double>
- complex<long double>
- std.complex<long double>
dev_langs:
- C++
helpviewer_keywords:
- complex<long double> function
ms.assetid: 37591991-b385-46e9-b727-d534dbc10432
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 92b0a7c9ae697bc28ad9fe3bd89d37f22d7a8cdc
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44313462"
---
# <a name="complexltlong-doublegt"></a>complex&lt;long double&gt;

Descreve um objeto que armazena um par ordenado de objetos do tipo **longo duplo**, o primeiro representando a parte real de um número complexo e o segundo representando a parte imaginária.

## <a name="syntax"></a>Sintaxe

```cpp
template <>
class complex<long double> {
public:
    constexpr complex(
    long double _RealVal = 0,
    long double _ImagVal = 0);

complex(
    constexpr complex<long double>& complexNum);
// rest same as template class complex
};
```

### <a name="parameters"></a>Parâmetros

*_RealVal*<br/>
O valor do tipo **long double** da parte real do número complexo que está sendo construído.

*_ImagVal*<br/>
O valor do tipo **longo duplo** da parte imaginária do número complexo que está sendo construído.

*complexNum*<br/>
O número complexo do tipo **duplas** ou do tipo **float** cujas partes reais e imaginárias são usados para inicializar um número complexo do tipo **longo duplo** que está sendo construído.

## <a name="return-value"></a>Valor de retorno

Um número complexo do tipo **longo duplo**.

## <a name="remarks"></a>Comentários

A especialização explícita da classe de modelo complexa para uma classe complexa do tipo **longo duplo** difere somente nos construtores ele define a classe de modelo. A conversão de **longo duplo** à **float** pode ser implícita, mas a conversão de **double** para **longo duplo** é necessária para ser **explícita**. O uso de **explícito** exclui a iniciação com conversão de tipo usando a sintaxe de atribuição.

Para obter mais informações sobre a classe do modelo `complex`, consulte [Classe complexa](../standard-library/complex-class.md). Para obter uma lista de membros da classe do modelo `complex`, consulte.

## <a name="example"></a>Exemplo

```cpp
// complex_comp_ld.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
   using namespace std;
   double pi = 3.14159265359;

   // The first constructor specifies real & imaginary parts
   complex <long double> c1 ( 4.0 , 5.0 );
   cout << "Specifying initial real & imaginary parts,\n"
        << " as type float gives c1 = " << c1 << endl;

   // The second constructor initializes values of the real &
   // imaginary parts using those of complex number of type float
   complex <float> c2float ( 1.0 , 3.0 );
   complex <long double> c2longdouble ( c2float );
   cout << "Implicit conversion from type float to type long double,"
        << "\n gives c2longdouble = " << c2longdouble << endl;

   // The third constructor initializes values of the real &
   // imaginary parts using those of a complex number
   // of type double
   complex <double> c3double ( 3.0 , 4.0 );
   complex <long double> c3longdouble ( c3double );
   cout << "Implicit conversion from type long double to type float,"
        << "\n gives c3longdouble = " << c3longdouble << endl;

   // The modulus and argument of a complex number can be recovered
   double absc3 = abs ( c3longdouble );
   double argc3 = arg ( c3longdouble );
   cout << "The modulus of c3 is recovered from c3 using: abs ( c3 ) = "
        << absc3 << endl;
   cout << "Argument of c3 is recovered from c3 using:\n arg ( c3 ) = "
        << argc3 << " radians, which is " << argc3 * 180 / pi
        << " degrees." << endl;
}
/* Output:
Specifying initial real & imaginary parts,
as type float gives c1 = (4,5)
Implicit conversion from type float to type long double,
gives c2longdouble = (1,3)
Implicit conversion from type long double to type float,
gives c3longdouble = (3,4)
The modulus of c3 is recovered from c3 using: abs ( c3 ) = 5
Argument of c3 is recovered from c3 using:
arg ( c3 ) = 0.927295 radians, which is 53.1301 degrees.
*/
```

## <a name="requirements"></a>Requisitos

**Cabeçalho**: \<complexo>

**Namespace:** std

## <a name="see-also"></a>Consulte também

[Classe complex](../standard-library/complex-class.md)<br/>
[Acesso Thread-Safe na Biblioteca Padrão C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
