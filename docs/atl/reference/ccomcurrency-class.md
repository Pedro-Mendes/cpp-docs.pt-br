---
title: Classe CComCurrency | Documentos do Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComCurrency
- ATLCUR/ATL::CComCurrency
- ATLCUR/ATL::CComCurrency::CComCurrency
- ATLCUR/ATL::CComCurrency::GetCurrencyPtr
- ATLCUR/ATL::CComCurrency::GetFraction
- ATLCUR/ATL::CComCurrency::GetInteger
- ATLCUR/ATL::CComCurrency::Round
- ATLCUR/ATL::CComCurrency::SetFraction
- ATLCUR/ATL::CComCurrency::SetInteger
- ATLCUR/ATL::CComCurrency::m_currency
dev_langs:
- C++
helpviewer_keywords:
- CComCurrency class
ms.assetid: a1c3d10a-bba6-40cc-8bcf-aed9023c8a9e
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 1b0b4fa5f42bd060b08ef90d09eee8d9d2d76fe6
ms.lasthandoff: 02/25/2017

---
# <a name="ccomcurrency-class"></a>Classe CComCurrency
`CComCurrency`tem métodos e operadores para criar e gerenciar um objeto de moeda.  
  
## <a name="syntax"></a>Sintaxe  
  
```
class CComCurrency
```  
  
## <a name="members"></a>Membros  
  
### <a name="public-constructors"></a>Construtores públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CComCurrency::CComCurrency](#ccomcurrency)|O construtor para uma `CComCurrency` objeto.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CComCurrency::GetCurrencyPtr](#getcurrencyptr)|Retorna o endereço de uma `m_currency` membro de dados.|  
|[CComCurrency::GetFraction](#getfraction)|Chame esse método para retornar o componente frações de um `CComCurrency` objeto.|  
|[CComCurrency::GetInteger](#getinteger)|Chame esse método para retornar o componente inteiro de um `CComCurrency` objeto.|  
|[CComCurrency::Round](#round)|Chame este método para arredondar um `CComCurrency` objeto para o valor inteiro mais próximo.|  
|[CComCurrency::SetFraction](#setfraction)|Chame esse método para configurar o componente frações de um `CComCurrency` objeto.|  
|[CComCurrency::SetInteger](#setinteger)|Chame esse método para configurar o componente inteiro de uma `CComCurrency` objeto.|  
  
### <a name="public-operators"></a>Operadores públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CComCurrency::operator-](#operator_-)|Esse operador é usado para executar subtração em um `CComCurrency` objeto.|  
|[CComCurrency::operator! =](#operator_neq)|Compara dois objetos `CComCurrency` quanto à desigualdade.|  
|[CComCurrency::operator *](#operator_star)|Esse operador é usado para executar uma multiplicação em uma `CComCurrency` objeto.|  
|[CComCurrency::operator * =](#operator_star_eq)|Esse operador é usado para executar uma multiplicação em um `CComCurrency` do objeto e atribui o resultado.|  
|[CComCurrency::operator /](#operator_div)|Esse operador é usado para realizar a divisão em uma `CComCurrency` objeto.|  
|[CComCurrency::operator =](#operator_div_eq)|Esse operador é usado para realizar a divisão em um `CComCurrency` do objeto e atribui o resultado.|  
|[CComCurrency::operator +](#operator_add)|Esse operador é usado para executar a adição em um `CComCurrency` objeto.|  
|[+ = CComCurrency::operator](#operator_add_eq)|Esse operador é usado para executar a adição em um `CComCurrency` de objeto e atribuir o resultado para o objeto atual.|  
|[CComCurrency::operator](#operator_lt)|Este operador compara dois `CComCurrency` objetos para determinar o menor.|  
|[CComCurrency::operator<>](#operator_lt_eq)|Este operador compara dois `CComCurrency` objetos para determinar igualdade ou menor.|  
|[CComCurrency::operator =](#operator_eq)|Este operador atribui o `CComCurrency` objeto para um novo valor.|  
|[CComCurrency::operator =](#operator_-_eq)|Esse operador é usado para executar subtração em um `CComCurrency` do objeto e atribui o resultado.|  
|[CComCurrency::operator = =](#operator_eq_eq)|Este operador compara dois `CComCurrency` objetos para igualdade.|  
|[CComCurrency::operator >](#operator_gt)|Este operador compara dois `CComCurrency` objetos para determinar o maior.|  
|[CComCurrency::operator > =](#operator_gt_eq)|Este operador compara dois `CComCurrency` objetos para determinar igualdade ou maior.|  
|[CComCurrency::operator moeda](#operator_currency)|Conversões de uma `CURRENCY` objeto.|  
  
### <a name="public-data-members"></a>Membros de Dados Públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CComCurrency::m_currency](#m_currency)|O `CURRENCY` variável criada por sua instância de classe.|  
  
## <a name="remarks"></a>Comentários  
 `CComCurrency`é um wrapper para o **moeda** tipo de dados. **MOEDA** é implementado como um valor inteiro de 8 bytes complemento de dois dimensionado por 10.000. Isso fornece um número de ponto fixo com 15 dígitos à esquerda da vírgula decimal e 4 dígitos à direita. O **moeda** tipo de dados é extremamente útil para cálculos que envolvem dinheiro ou para os cálculos de ponto fixo em que a precisão é importante.  
  
 O **CComCurrency** wrapper implementa operações de aritmética, atribuição e comparação para este tipo de ponto fixo. Os aplicativos suportados foram selecionados para controlar os erros de arredondamento que podem ocorrer durante os cálculos de ponto fixo.  
  
 O `CComCurrency` objeto fornece acesso aos números em ambos os lados do ponto decimal na forma de dois componentes: um componente de número inteiro que armazena o valor à esquerda do ponto decimal e um componente fracionário que armazena o valor à direita do ponto decimal. O componente fracionário é armazenado internamente como um valor inteiro entre -9999 ( **CY_MIN_FRACTION**) e +9999 ( **CY_MAX_FRACTION**). O método [CComCurrency::GetFraction](#getfraction) retorna um valor reduzido por um fator de 10000 ( **CY_SCALE**).  
  
 Ao especificar o número inteiro e componentes fracionários de um **CComCurrency** de objeto, lembre-se de que o componente fracionário é um número no intervalo de 0 a 9999. Isso é importante ao lidar com uma moeda, como o dólar americano que expresse quantidades usando apenas dois dígitos após o ponto decimal. Embora os dois últimos dígitos não são exibidos, eles devem ser levados em conta.  
  
|Valor|Atribuições de CComCurrency possíveis|  
|-----------|---------------------------------------|  
|$10.50|CComCurrency(10,5000) *ou* CComCurrency(10.50)|  
|$10.05|CComCurrency(10,500) *ou* CComCurrency(10.05)|  
  
 Os valores **CY_MIN_FRACTION**, **CY_MAX_FRACTION**, e **CY_SCALE** são definidos em atlcur.h.  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** atlcur.h  
  
##  <a name="ccomcurrency"></a>CComCurrency::CComCurrency  
 O construtor.  
  
```
CComCurrency() throw();
CComCurrency(const CComCurrency& curSrc) throw();
CComCurrency(CURRENCY cySrc) throw();
CComCurrency(DECIMAL dSrc);
CComCurrency(ULONG ulSrc);  
CComCurrency(USHORT usSrc);  
CComCurrency(CHAR cSrc);  
CComCurrency(DOUBLE dSrc);  
CComCurrency(FLOAT fSrc);  
CComCurrency(LONG lSrc);  
CComCurrency(SHORT sSrc);  
CComCurrency(BYTE bSrc);  
CComCurrency(LONGLONG nInteger, SHORT nFraction);  
explicit CComCurrency(LPDISPATCH pDispSrc);  
explicit CComCurrency(const VARIANT& varSrc);  
explicit CComCurrency(LPCWSTR szSrc);  
explicit CComCurrency(LPCSTR szSrc);
```  
  
### <a name="parameters"></a>Parâmetros  
 `curSrc`  
 Um objeto `CComCurrency` existente.  
  
 `cySrc`  
 Uma variável do tipo **moeda**.  
  
 `bSrc`, `dSrc`, `fSrc`, `lSrc`, *sSrc*, *ulSrc, usSrc*  
 O valor inicial atribuído à variável de membro `m_currency`.  
  
 `cSrc`  
 Um caractere que contém o valor inicial atribuído à variável de membro `m_currency`.  
  
 `nInteger`, *nFraction*  
 O número inteiro e componentes fracionárias do valor monetário inicial. Consulte o [CComCurrency](../../atl/reference/ccomcurrency-class.md) visão geral para obter mais informações.  
  
 `pDispSrc`  
 Um `IDispatch` ponteiro.  
  
 *varSrc*  
 Uma variável do tipo **VARIANT**. A localidade do thread atual é usada para executar a conversão.  
  
 `szSrc`  
 Uma cadeia Unicode ou ANSI contendo o valor inicial. A localidade do thread atual é usada para executar a conversão.  
  
### <a name="remarks"></a>Comentários  
 O construtor define o valor inicial de [CComCurrency::m_currency](#m_currency)e aceita uma ampla variedade de tipos de dados, incluindo números inteiros, cadeias de caracteres, números de ponto flutuante, **moeda** variáveis e outros `CComCurrency` objetos. Se nenhum valor for fornecido, `m_currency` é definido como 0.  
  
 Se ocorrer um erro, como um estouro, os construtores sem uma especificação de exceção vazio ( **Throw ()**) chamada `AtlThrow` com um HRESULT que descreve o erro.  
  
 Observe que, ao usar valores de ponto flutuantes ou duplos para atribuir um valor, **CComCurrency(10.50)** é equivalente a **CComCurrency(10,5000)** e não **CComCurrency(10,50)**.  
  
##  <a name="getcurrencyptr"></a>CComCurrency::GetCurrencyPtr  
 Retorna o endereço de uma `m_currency` membro de dados.  
  
```
CURRENCY* GetCurrencyPtr() throw();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna o endereço de uma `m_currency` membro de dados  
  
##  <a name="getfraction"></a>CComCurrency::GetFraction  
 Chame esse método para retornar o componente frações do `CComCurrency` objeto.  
  
```
SHORT GetFraction() const;
```  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna o componente frações do `m_currency` membro de dados.  
  
### <a name="remarks"></a>Comentários  
 O componente fracionário é um valor inteiro de 4 dígitos entre -9999 ( **CY_MIN_FRACTION**) e +9999 ( **CY_MAX_FRACTION**). `GetFraction`Retorna o valor de escala de 10000 ( **CY_SCALE**). Os valores de **CY_MIN_FRACTION**, **CY_MAX_FRACTION**, e **CY_SCALE** são definidos em atlcur.h.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities&#50;](../../atl/codesnippet/cpp/ccomcurrency-class_1.cpp)]  
  
##  <a name="getinteger"></a>CComCurrency::GetInteger  
 Chamar esse método para o componente inteiro de um `CComCurrency` objeto.  
  
```
LONGLONG GetInteger() const;
```  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna o componente inteiro do `m_currency` membro de dados.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities&#51;](../../atl/codesnippet/cpp/ccomcurrency-class_2.cpp)]  
  
##  <a name="m_currency"></a>CComCurrency::m_currency  
 O **moeda** membro de dados.  
  
```
CURRENCY m_currency;
```  
  
### <a name="remarks"></a>Comentários  
 Esse membro mantém a moeda acessados e manipulados por métodos dessa classe.  
  
##  <a name="operator_-"></a>CComCurrency::operator-  
 Esse operador é usado para executar subtração em um `CComCurrency` objeto.  
  
```
CComCurrency operator-() const;
CComCurrency operator-(const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Parâmetros  
 `cur`  
 Um objeto `CComCurrency`.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna um `CComCurrency` objeto que representa o resultado da subtração. Se ocorrer um erro, como um estouro, esse operador chama `AtlThrow` com um HRESULT que descreve o erro.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities&#55;](../../atl/codesnippet/cpp/ccomcurrency-class_3.cpp)]  
  
##  <a name="operator_neq"></a>CComCurrency::operator! =  
 Este operador compara dois objetos de desigualdade.  
  
```
bool operator!= (const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Parâmetros  
 `cur`  
 O objeto `CComCurrency` a ser comparado.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna **true** se o item que está sendo comparado não for igual do `CComCurrency` objeto; caso contrário, **false**.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[56 NVC_ATL_Utilities](../../atl/codesnippet/cpp/ccomcurrency-class_4.cpp)]  
  
##  <a name="operator_star"></a>CComCurrency::operator *  
 Esse operador é usado para executar uma multiplicação em uma `CComCurrency` objeto.  
  
```
CComCurrency operator*(long nOperand) const;
CComCurrency operator*(const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Parâmetros  
 `nOperand`  
 O multiplicador.  
  
 `cur`  
 O `CComCurrency` objeto usado como o multiplicador.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna um `CComCurrency` que representa o resultado da multiplicação do objeto. Se ocorrer um erro, como um estouro, esse operador chama `AtlThrow` com um HRESULT que descreve o erro.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities&#57;](../../atl/codesnippet/cpp/ccomcurrency-class_5.cpp)]  
  
##  <a name="operator_star_eq"></a>CComCurrency::operator * =  
 Esse operador é usado para executar uma multiplicação em um `CComCurrency` do objeto e atribui o resultado.  
  
```
const CComCurrency& operator*= (long nOperand);
const CComCurrency& operator*= (const CComCurrency& cur);
```  
  
### <a name="parameters"></a>Parâmetros  
 `nOperand`  
 O multiplicador.  
  
 `cur`  
 O `CComCurrency` objeto usado como o multiplicador.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna a atualização `CComCurrency` objeto. Se ocorrer um erro, como um estouro, esse operador chama `AtlThrow` com um HRESULT que descreve o erro.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities&#58;](../../atl/codesnippet/cpp/ccomcurrency-class_6.cpp)]  
  
##  <a name="operator_div"></a>CComCurrency::operator /  
 Esse operador é usado para realizar a divisão em uma `CComCurrency` objeto.  
  
```
CComCurrency operator/(long nOperand) const;
```  
  
### <a name="parameters"></a>Parâmetros  
 `nOperand`  
 O divisor.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna um `CComCurrency` objeto que representa o resultado da divisão. Se o divisor for 0, ocorrerá uma falha de asserção.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities&#59;](../../atl/codesnippet/cpp/ccomcurrency-class_7.cpp)]  
  
##  <a name="operator_div_eq"></a>CComCurrency::operator =  
 Esse operador é usado para realizar a divisão em um `CComCurrency` do objeto e atribui o resultado.  
  
```
const CComCurrency& operator/= (long nOperand);
```  
  
### <a name="parameters"></a>Parâmetros  
 `nOperand`  
 O divisor.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna a atualização `CComCurrency` objeto. Se o divisor for 0, ocorrerá uma falha de asserção.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities&#60;](../../atl/codesnippet/cpp/ccomcurrency-class_8.cpp)]  
  
##  <a name="operator_add"></a>CComCurrency::operator +  
 Esse operador é usado para executar a adição em um `CComCurrency` objeto.  
  
```
CComCurrency operator+(const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Parâmetros  
 `cur`  
 O `CComCurrency` o objeto a ser adicionado ao objeto original.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna um `CComCurrency` que representa o resultado da adição de objeto. Se ocorrer um erro, como um estouro, esse operador chama `AtlThrow` com um HRESULT que descreve o erro.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities&#61;](../../atl/codesnippet/cpp/ccomcurrency-class_9.cpp)]  
  
##  <a name="operator_add_eq"></a>+ = CComCurrency::operator  
 Esse operador é usado para executar a adição em um `CComCurrency` de objeto e atribuir o resultado para o objeto atual.  
  
```
const CComCurrency& operator+= (const CComCurrency& cur);
```  
  
### <a name="parameters"></a>Parâmetros  
 `cur`  
 O objeto `CComCurrency`.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna a atualização `CComCurrency` objeto. Se ocorrer um erro, como um estouro, esse operador chama `AtlThrow` com um HRESULT que descreve o erro.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities&#62;](../../atl/codesnippet/cpp/ccomcurrency-class_10.cpp)]  
  
##  <a name="operator_lt"></a>CComCurrency::operator&lt;  
 Este operador compara dois `CComCurrency` objetos para determinar o menor.  
  
```
bool operator<(const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Parâmetros  
 `cur`  
 Um objeto `CComCurrency`.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna **true** se o primeiro objeto for menor que o segundo, **false** caso contrário.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities&#63;](../../atl/codesnippet/cpp/ccomcurrency-class_11.cpp)]  
  
##  <a name="operator_lt_eq"></a>CComCurrency::operator&lt;=  
 Este operador compara dois `CComCurrency` objetos para determinar igualdade ou menor.  
  
```
bool operator<= (const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Parâmetros  
 `cur`  
 Um objeto `CComCurrency`.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna **true** se o primeiro objeto é menor ou igual ao segundo **false** caso contrário.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities&#64;](../../atl/codesnippet/cpp/ccomcurrency-class_12.cpp)]  
  
##  <a name="operator_eq"></a>CComCurrency::operator =  
 Este operador atribui o `CComCurrency` objeto para um novo valor.  
  
```
const CComCurrency& operator= (const CComCurrency& curSrc) throw();
const CComCurrency& operator= (CURRENCY cySrc) throw();
const CComCurrency& operator= (FLOAT fSrc);
const CComCurrency& operator= (SHORT sSrc);
const CComCurrency& operator= (LONG lSrc);
const CComCurrency& operator= (BYTE bSrc);
const CComCurrency& operator= (USHORT usSrc);
const CComCurrency& operator= (DOUBLE dSrc);
const CComCurrency& operator= (CHAR cSrc);
const CComCurrency& operator= (ULONG ulSrc);
const CComCurrency& operator= (DECIMAL dSrc);
```  
  
### <a name="parameters"></a>Parâmetros  
 `curSrc`  
 A **CComCurrency** objeto.  
  
 `cySrc`  
 Uma variável do tipo **moeda**.  
  
 *sSrc*, `fSrc`, `lSrc`, *bSrc*, *usSrc*, `dSrc`, *cSrc*, *ulSrc*,`dSrc`  
 O valor numérico para atribuir ao `CComCurrency` objeto.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna a atualização `CComCurrency` objeto. Se ocorrer um erro, como um estouro, esse operador chama `AtlThrow` com um HRESULT que descreve o erro.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities&#65;](../../atl/codesnippet/cpp/ccomcurrency-class_13.cpp)]  
  
##  <a name="operator_-_eq"></a>CComCurrency::operator =  
 Esse operador é usado para executar subtração em um `CComCurrency` do objeto e atribui o resultado.  
  
```
const CComCurrency& operator-= (const CComCurrency& cur);
```  
  
### <a name="parameters"></a>Parâmetros  
 `cur`  
 Um objeto `CComCurrency`.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna a atualização `CComCurrency` objeto. Se ocorrer um erro, como um estouro, esse operador chama `AtlThrow` com um HRESULT que descreve o erro.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities&#66;](../../atl/codesnippet/cpp/ccomcurrency-class_14.cpp)]  
  
##  <a name="operator_eq_eq"></a>CComCurrency::operator = =  
 Este operador compara dois `CComCurrency` objetos para igualdade.  
  
```
bool operator== (const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Parâmetros  
 `cur`  
 O `CComCurrency` objeto a ser comparado.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna **true** se os objetos forem iguais (isto é, o `m_currency` membros de dados, ambas as integer e frações, nos dois objetos têm o mesmo valor), **false** caso contrário.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities&#67;](../../atl/codesnippet/cpp/ccomcurrency-class_15.cpp)]  
  
##  <a name="operator_gt"></a>CComCurrency::operator&gt;  
 Este operador compara dois `CComCurrency` objetos para determinar o maior.  
  
```
bool operator>(const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Parâmetros  
 `cur`  
 Um objeto `CComCurrency`.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna **true** se o primeiro objeto for maior que o segundo, **false** caso contrário.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities&#68;](../../atl/codesnippet/cpp/ccomcurrency-class_16.cpp)]  
  
##  <a name="operator_gt_eq"></a>CComCurrency::operator&gt;=  
 Este operador compara dois `CComCurrency` objetos para determinar igualdade ou maior.  
  
```
bool operator>= (const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Parâmetros  
 `cur`  
 Um objeto `CComCurrency`.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna **true** se o primeiro objeto é maior que ou igual ao segundo **false** caso contrário.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities&#69;](../../atl/codesnippet/cpp/ccomcurrency-class_17.cpp)]  
  
##  <a name="operator_currency"></a>CComCurrency::operator moeda  
 Esses operadores são usados para converter uma `CComCurrency` o objeto para um **moeda** tipo de dados.  
  
```  
operator CURRENCY&() throw();
operator const CURRENCY&() const throw();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna uma referência a um **moeda** objeto.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities&#70;](../../atl/codesnippet/cpp/ccomcurrency-class_18.cpp)]  
  
##  <a name="round"></a>CComCurrency::Round  
 Chame esse método para arredondar a moeda para um número especificado de casas decimais.  
  
```
HRESULT Roundint nDecimals);
```  
  
### <a name="parameters"></a>Parâmetros  
 *nDecimals*  
 O número de dígitos para o qual `m_currency` serão arredondados, no intervalo de 0 a 4.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna `S_OK` no sucesso ou erro `HRESULT` em caso de falha.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities&#52;](../../atl/codesnippet/cpp/ccomcurrency-class_19.cpp)]  
  
##  <a name="setfraction"></a>CComCurrency::SetFraction  
 Chame esse método para configurar o componente frações de um `CComCurrency` objeto.  
  
```
HRESULT SetFraction(SHORT nFraction);
```  
  
### <a name="parameters"></a>Parâmetros  
 *nFraction*  
 O valor a ser atribuído ao componente de frações de `m_currency` membro de dados. O sinal do componente fracionário deve ser o mesmo que o componente inteiro e o valor deve estar no intervalo de -9999 ( **CY_MIN_FRACTION**) para +9999 ( **CY_MAX_FRACTION**).  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna `S_OK` no sucesso ou erro `HRESULT` em caso de falha.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities&#53;](../../atl/codesnippet/cpp/ccomcurrency-class_20.cpp)]  
  
##  <a name="setinteger"></a>CComCurrency::SetInteger  
 Chame esse método para configurar o componente inteiro de uma `CComCurrency` objeto.  
  
```
HRESULT SetInteger(LONGLONG nInteger);
```  
  
### <a name="parameters"></a>Parâmetros  
 `nInteger`  
 O valor a ser atribuído ao componente de número inteiro a `m_currency` membro de dados. O sinal do componente inteiro deve corresponder ao sinal do componente fracionário existente.  
  
 `nInteger`deve estar no intervalo **CY_MIN_INTEGER** para **CY_MAX_INTEGER** inclusivo. Esses valores são definidos em atlcur.h.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna `S_OK` no sucesso ou erro `HRESULT` em caso de falha.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities&#54;](../../atl/codesnippet/cpp/ccomcurrency-class_21.cpp)]  
  
## <a name="see-also"></a>Consulte também  
 [Classe COleCurrency](../../mfc/reference/colecurrency-class.md)   
 [MOEDA](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e)   
 [Visão geral da classe](../../atl/atl-class-overview.md)
