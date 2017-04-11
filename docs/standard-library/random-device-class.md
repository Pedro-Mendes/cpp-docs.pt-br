---
title: Classe random_device | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- random_device
- std::random_device
- random/std::random_device
- std::random_device::min
- random/std::random_device::min
- std::random_device::max
- random/std::random_device::max
- std::random_device::entropy
- random/std::random_device::entropy
- std::random_device::operator()
- random/std::random_device::operator()
dev_langs:
- C++
helpviewer_keywords:
- random_device class
ms.assetid: 4393d515-0cb6-4e0d-a2ba-c780f05dc1bf
caps.latest.revision: 27
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
ms.sourcegitcommit: 28baed4badda4f2c1d7e5b20235fe8d40c2a7195
ms.openlocfilehash: d755f15b9f8dc575eb95d65822adfae3fdb568dd
ms.lasthandoff: 02/25/2017

---
# <a name="randomdevice-class"></a>Classe random_device
Gera uma sequência aleatória de um dispositivo externo.  
  
## <a name="syntax"></a>Sintaxe  
  
```
class random_device {  
public:  
   typedef unsigned int result_type;  
   
   // constructor 
   explicit random_device(const std::string& token = "");
   
   // properties 
   static result_type min();
   static result_type max();
   double entropy() const;
   
   // generate 
   result_type operator()();

   // no-copy functions 
   random_device(const random_device&) = delete;  
   void operator=(const random_device&) = delete;  
   };  
```  

## <a name="members"></a>Membros  
  
|||  
|-|-|  
|[random_device::random_device](#random_device__random_device)|[random_device::entropy](#random_device__entropy)|  
|[random_device::operator()](#random_device__operator__)||  
  
## <a name="remarks"></a>Comentários  
A classe descreve uma origem de números aleatórios e com permissão, embora não seja obrigada a ser não determinista ou protegida criptograficamente pelo padrão ISO C++. Na implementação do Visual Studio, os valores não são determinísticos e são protegidos criptograficamente, mas são executados mais devagar que os geradores criados de mecanismos e adaptadores de mecanismos (como [mersenne_twister_engine](../standard-library/mersenne-twister-engine-class.md), o mecanismo rápido e de alta qualidade preferido pela maioria dos aplicativos).  
  
Os resultados de `random_device` são distribuídos de maneira uniforme no intervalo fechado [ `0, 2`<sup>32</sup>).  
  
O `random_device` não tem garantia de resultar em uma chamada sem bloqueio.  
  
Em geral, o `random_device` é usado para semear outros geradores criados com mecanismos ou adaptadores de mecanismo. Para obter mais informações, consulte [\<random>](../standard-library/random.md).  
  
## <a name="example"></a>Exemplo  
O código a seguir demonstra a funcionalidade básica dessa classe e os exemplos de resultado. Devido à natureza não determinística de `random_device`, os valores aleatórios mostrados na seção **Saída** não corresponderão aos resultados. Isso é normal e esperado.  
  
```cpp  
// random_device_engine.cpp   
// cl.exe /W4 /nologo /EHsc /MTd   
#include <random>   
#include <iostream>   
using namespace std;  
  
int main()   
{   
    random_device gen;   
  
    cout << "entropy == " << gen.entropy() << endl;   
    cout << "min == " << gen.min() << endl;   
    cout << "max == " << gen.max() << endl;   
  
    cout << "a random value == " << gen() << endl;   
    cout << "a random value == " << gen() << endl;   
    cout << "a random value == " << gen() << endl;   
}  
```  
  
```Output  
entropy == 32
min == 0
max == 4294967295
a random value == 2378414971
a random value == 3633694716
a random value == 213725214
```  
  
Este exemplo é simplista e não representa o caso de uso geral desse gerador. Para obter um exemplo de código mais representativo, consulte [\<random>](../standard-library/random.md).  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** \<random>  
  
 **Namespace:** std  
  
##  <a name="a-namerandomdevicerandomdevicea--randomdevicerandomdevice"></a><a name="random_device__random_device"></a>  random_device::random_device  
Constrói o gerador.  
  
```  
random_device(const std::string& = "");
```  
  
### <a name="remarks"></a>Comentários  
O construtor inicia o gerador quando necessário, ignorando o parâmetro da cadeia de caracteres. Gera um valor de um tipo definido de implementação derivado de [exception](../standard-library/exception-class.md) se não foi possível iniciar `random_device`.  
  
##  <a name="a-namerandomdeviceentropya--randomdeviceentropy"></a><a name="random_device__entropy"></a>  random_device::entropy  
Estima a aleatoriedade da origem.  
  
```  
double entropy() const noexcept;  
```  
  
### <a name="remarks"></a>Comentários  
A função do membro retorna uma estimativa da aleatoriedade da origem, em bits.  
  
##  <a name="a-namerandomdeviceoperatora--randomdeviceoperator"></a><a name="random_device__operator__"></a>  random_device::operator()  
Retorna um valor aleatório.  
  
```  
result_type operator()();
```  
  
### <a name="remarks"></a>Comentários  
Retorna valores distribuídos uniformemente no intervalo fechado [ `min, max`] como determinado pelas funções membro `min()` e `max()`. Gera um valor do tipo definido pela implementação derivado de [exception](../standard-library/exception-class.md) se não for possível obter um número aleatório.  
  
## <a name="see-also"></a>Consulte também  
[\<random>](../standard-library/random.md)

