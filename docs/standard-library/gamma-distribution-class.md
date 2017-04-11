---
title: Classe gamma_distribution| Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- gamma_distribution
- std::gamma_distribution
- random/std::gamma_distribution
- std::gamma_distribution::reset
- random/std::gamma_distribution::reset
- std::gamma_distribution::alpha
- random/std::gamma_distribution::alpha
- std::gamma_distribution::beta
- random/std::gamma_distribution::beta
- std::gamma_distribution::param
- random/std::gamma_distribution::param
- std::gamma_distribution::min
- random/std::gamma_distribution::min
- std::gamma_distribution::max
- random/std::gamma_distribution::max
- std::gamma_distribution::operator()
- random/std::gamma_distribution::operator()
- std::gamma_distribution::param_type
- random/std::gamma_distribution::param_type
- std::gamma_distribution::param_type::alpha
- random/std::gamma_distribution::param_type::alpha
- std::gamma_distribution::param_type::beta
- random/std::gamma_distribution::param_type::beta
- std::gamma_distribution::param_type::operator==
- random/std::gamma_distribution::param_type::operator==
- std::gamma_distribution::param_type::operator!=
- random/std::gamma_distribution::param_type::operator!=
dev_langs:
- C++
helpviewer_keywords:
- gamma_distribution
- gamma_distribution class
ms.assetid: 2a6798ac-6152-41d7-8ef6-d684d92f1572
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
ms.sourcegitcommit: 0194fbc3e45c270ca7537285c5c6b4e768c65a90
ms.openlocfilehash: ed2b198b9bed7f67284691ca7ec00d09e17f15f7
ms.lasthandoff: 02/25/2017

---
# <a name="gammadistribution-class"></a>Classe gamma_distribution
Gera uma distribuição gama.  
  
## <a name="syntax"></a>Sintaxe  
```  
template<class RealType = double>
class gamma_distribution {
public:    
    // types 
    typedef RealType result_type;    
    struct param_type;  

    // constructors and reset functions 
    explicit gamma_distribution(result_type alpha = 1.0, result_type beta = 1.0);
    explicit gamma_distribution(const param_type& parm);
    void reset();
    
    // generating functions
    template <class URNG>  
    result_type operator()(URNG& gen);
    template <class URNG>
    result_type operator()(URNG& gen, const param_type& parm);
    
    // property functions
    result_type alpha() const;
    result_type beta() const;
    param_type param() const;
    void param(const param_type& parm);
    result_type min() const;
    result_type max() const;
};
```    
#### <a name="parameters"></a>Parâmetros  
*RealType*  
O tipo de resultado de ponto flutuante assume `double` como padrão. Para ver os tipos possíveis, consulte [\<random>](../standard-library/random.md).  
  
*URNG* O mecanismo gerador de números aleatórios uniformes. Para ver os tipos possíveis, consulte [\<random>](../standard-library/random.md).  
  
## <a name="remarks"></a>Comentários  
A classe de modelo descreve uma distribuição que produz valores de um tipo de ponto flutuante especificado pelo usuário ou um tipo `double` caso nenhum seja fornecido, distribuído de acordo com a Distribuição Gamma. A tabela a seguir contém links para artigos sobre cada um dos membros.  
  
||||  
|-|-|-|  
|[gamma_distribution::gamma_distribution](#gamma_distribution__gamma_distribution)|`gamma_distribution::alpha`|`gamma_distribution::param`|  
|`gamma_distribution::operator()`|`gamma_distribution::beta`|[gamma_distribution::param_type](#gamma_distribution__param_type)|  
  
As funções de propriedade `alpha()` e `beta()` retornam seus respectivos valores para os parâmetros de distribuição armazenados *alpha* e *beta*.  
  
O membro da propriedade `param()` define ou retorna o pacote de parâmetros de distribuição armazenado `param_type`.  

As funções membro `min()` e `max()` retornam o menor resultado possível e o maior resultado possível, respectivamente.  
  
A função membro `reset()` descarta qualquer valor armazenado em cache, de forma que o resultado da próxima chamada para `operator()` não dependerá dos valores obtidos do mecanismo antes da chamada.  
  
As funções membro `operator()` retornam o próximo valor gerado com base no mecanismo URNG, do pacote de parâmetros atual ou do pacote de parâmetros especificado.
  
Para obter mais informações sobre as classes de distribuição e seus membros, consulte [\<random>](../standard-library/random.md).  
  
Para obter informações detalhadas sobre a Distribuição Gamma, consulte o artigo da Wolfram MathWorld [Gamma Distribution](http://go.microsoft.com/fwlink/LinkId=401111).  
  
## <a name="example"></a>Exemplo  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
void test(const double a, const double b, const int s) {  
  
    // uncomment to use a non-deterministic generator  
    //    std::random_device gen;  
  
    std::mt19937 gen(1701);  
  
    std::gamma_distribution<> distr(a, b);  
  
    std::cout << std::endl;  
    std::cout << "min() == " << distr.min() << std::endl;  
    std::cout << "max() == " << distr.max() << std::endl;  
    std::cout << "alpha() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.alpha() << std::endl;  
    std::cout << "beta() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.beta() << std::endl;  
  
    // generate the distribution as a histogram  
    std::map<double, int> histogram;  
    for (int i = 0; i < s; ++i) {  
        ++histogram[distr(gen)];  
    }  
  
    // print results  
    std::cout << "Distribution for " << s << " samples:" << std::endl;  
    int counter = 0;  
    for (const auto& elem : histogram) {  
        std::cout << std::fixed << std::setw(11) << ++counter << ": "  
            << std::setw(14) << std::setprecision(10) << elem.first << std::endl;  
    }  
    std::cout << std::endl;  
}  
  
int main()  
{  
    double a_dist = 0.0;  
    double b_dist = 1;  
  
    int samples = 10;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter a floating point value for the 'alpha' distribution parameter (must be greater than zero): ";  
    std::cin >> a_dist;  
    std::cout << "Enter a floating point value for the 'beta' distribution parameter (must be greater than zero): ";  
    std::cin >> b_dist;  
    std::cout << "Enter an integer value for the sample count: ";  
    std::cin >> samples;  
  
    test(a_dist, b_dist, samples);  
}  
```  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a floating point value for the 'alpha' distribution parameter (must be greater than zero): 1  
Enter a floating point value for the 'beta' distribution parameter (must be greater than zero): 1  
Enter an integer value for the sample count: 10  
 
min() == 4.94066e-324  
max() == 1.79769e+308  
alpha() == 1.0000000000  
beta() == 1.0000000000  
Distribution for 10 samples:  
    1: 0.0936880533  
    2: 0.1225944894  
    3: 0.6443593183  
    4: 0.6551171649  
    5: 0.7313457551  
    6: 0.7313557977  
    7: 0.7590097389  
    8: 1.4466885214  
    9: 1.6434088411  
    10: 2.1201210996  
```  
  
## <a name="requirements"></a>Requisitos  
**Cabeçalho:** \<random>  
  
**Namespace:** std  
  
##  <a name="a-namegammadistributiongammadistributiona--gammadistributiongammadistribution"></a><a name="gamma_distribution__gamma_distribution"></a>  gamma_distribution::gamma_distribution  
Constrói a distribuição.  
  
```  
explicit gamma_distribution(result_type alpha = 1.0, result_type beta = 1.0);
explicit gamma_distribution(const param_type& parm);
```  
  
### <a name="parameters"></a>Parâmetros  
*alpha*  
O parâmetro de distribuição `alpha`.  
  
*beta*  
O parâmetro de distribuição `beta`.  
  
*parm*  
A estrutura do parâmetro usada para construir a distribuição.  
  
### <a name="remarks"></a>Comentários  
**Precondição:** `0.0 < alpha` e `0.0 < beta`  
  
O primeiro construtor constrói um objeto cujo valor `alpha` armazenado contém o valor *alpha* e cujo valor armazenado `beta` contém o valor *beta*.  
  
O segundo construtor cria um objeto cujos parâmetros armazenados são inicializados de *parm*. Você pode chamar a função de membro `param()` para obter e definir os parâmetros atuais de uma distribuição existente.  
  
##  <a name="a-namegammadistributionparamtypea--gammadistributionparamtype"></a><a name="gamma_distribution__param_type"></a>  gamma_distribution::param_type  
Armazena os parâmetros da distribuição.  
  
```cpp   
struct param_type {  
   typedef gamma_distribution<result_type> distribution_type;  
   param_type(result_type alpha = 1.0, result_type beta 1.0);
   result_type alpha() const;
   result_type beta() const;

   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };  
```  
### <a name="parameters"></a>Parâmetros  
*alpha*  
O parâmetro de distribuição `alpha`.  
  
*beta*  
O parâmetro de distribuição `beta`.  
  
*right*  
O instância de `param_type` a ser comparada com isto.  
  
### <a name="remarks"></a>Comentários  
**Precondição:** `0.0 < alpha` e `0.0 < beta`  
  
Essa estrutura pode ser enviada ao construtor de classe de distribuição na instanciação, para a função de membro `param()` para definir os parâmetros armazenados de uma distribuição existente e para `operator()` a ser usado no lugar dos parâmetros armazenados.  
  
## <a name="see-also"></a>Consulte também  
[\<random>](../standard-library/random.md)



