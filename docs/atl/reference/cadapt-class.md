---
title: Classe CAdapt | Documentos do Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAdapt
- ATLCOMCLI/ATL::CAdapt
- ATLCOMCLI/ATL::CAdapt::CAdapt
- ATLCOMCLI/ATL::CAdapt::m_T
dev_langs:
- C++
helpviewer_keywords:
- address-of operator
- adapter objects
- '& operator, address-of operator'
- CAdapt class
ms.assetid: 0bb695a5-72fe-43d1-8f39-7e4da6e34765
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 8cdedc5cfac9d49df812ae6fcfcc548201b1edb5
ms.openlocfilehash: 84346b548e6d0fc7a1ce3078385aee45dfd0031e
ms.lasthandoff: 02/25/2017

---
# <a name="cadapt-class"></a>Classe CAdapt
Este modelo é usado para incluir classes que redefinem o operador address-of para retornar algo diferente do endereço do objeto.  
  
## <a name="syntax"></a>Sintaxe  
  
```
template <class T>  
class CAdapt
```  
  
#### <a name="parameters"></a>Parâmetros  
 `T`  
 O tipo adaptado.  
  
## <a name="members"></a>Membros  
  
### <a name="public-constructors"></a>Construtores públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CAdapt::CAdapt](#cadapt)|O construtor.|  
  
### <a name="public-operators"></a>Operadores públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CAdapt::operator const T < /](#operator_const_t_amp)|Retorna uma referência `const` para `m_T`.|  
|[CAdapt::operator T < /](#operator_t_amp)|Retorna uma referência para `m_T`.|  
|[CAdapt::operator](#operator_lt)|Compara um objeto do tipo adaptado com `m_T`.|  
|[CAdapt::operator =](#operator_eq)|Atribui um objeto do tipo adaptado a `m_T`.|  
|[CAdapt::operator = =](#operator_eq_eq)|Compara um objeto do tipo adaptado com `m_T`.|  
  
### <a name="public-data-members"></a>Membros de Dados Públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CAdapt::m_T](#m_t)|Os dados que estão sendo adaptados.|  
  
## <a name="remarks"></a>Comentários  
 `CAdapt`é um modelo simples usado para incluir classes que redefinem o operador address-of ( `operator &`) para retornar algo diferente do endereço do objeto. Exemplos dessas classes incluem as classes `CComBSTR`, `CComPtr` e `CComQIPtr` do ATL, e a classe de suporte ao COM do compilador, `_com_ptr_t`. Todas essas classes redefinem o operador address-of para retornar o endereço de um de seus membros de dados (`BSTR` no caso de `CComBSTR`, e um ponteiro de interface no caso de outras classes).  
  
 A função primária de `CAdapt` é ocultar o operador address-of definido pela classe `T`, mas ainda manter as características da classe adaptada. `CAdapt`desempenha essa função mantendo um membro público, [m_T](#m_t), do tipo `T`e definindo operadores de conversão, operadores de comparação e um construtor de cópia para permitir que especializações de `CAdapt` deve ser tratado como se fossem objetos do tipo `T`.  
  
 A classe de adaptador `CAdapt` é útil porque algumas classes do estilo contêiner esperam poder obter os endereços de seus objetos contidos usando o operador address-of. A redefinição do operador address-of pode confundir esse requisito, normalmente causando erros de compilação e evitando o uso do tipo não adaptado com classes que o esperam como “apenas trabalho”. `CAdapt` fornece uma maneira de contornar esses problemas.  
  
 Normalmente, você usará `CAdapt` quando quiser armazenar objetos `CComBSTR`, `CComPtr`, `CComQIPtr` ou `_com_ptr_t` em um o estilo de contêiner. Isso era o geralmente necessário para contêineres da biblioteca padrão C++ antes do suporte para o padrão C++11, mas os contêineres da biblioteca padrão C++11 funcionam automaticamente com tipos que sobrecarregaram `operator&()`. A biblioteca padrão obtém isso internamente usando [std::addressof()](http://msdn.microsoft.com/library/6243ddc8-486a-4961-8b0c-33e9dc2e0648) para obter os endereços verdadeiros dos objetos.  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** atlcomcli. h  
  
##  <a name="cadapt"></a>CAdapt::CAdapt  
 Os construtores permitem que um objeto de adaptador para ser construído, copiados de um objeto do tipo adaptado ou copiado de outro objeto do adaptador padrão.  
  
```
CAdapt();
CAdapt(const T& rSrc);
CAdapt(const CAdapt& rSrCA);
CAdapt(T&& rSrCA);  // (Visual Studio 2017)
CAdapt(CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Parâmetros  
 `rSrc`  
 Uma variável do tipo que está sendo adaptado para ser copiado para o objeto adaptador recentemente construído.  
  
 *rSrCA*  
 Um objeto de adaptador cujos dados contidos devem ser copiados (ou movidos) para o objeto de adaptador recentemente construído.  
  
##  <a name="m_t"></a>CAdapt::m_T  
 Contém os dados que está sendo adaptados.  
  
```
T m_T;
```  
  
### <a name="remarks"></a>Comentários  
 Isso **pública** membro de dados pode ser acessado diretamente ou indiretamente com [operador const T < /](#operator_const_t_amp) e [operador T < /](#operator_t_amp).  
  
##  <a name="operator_const_t_amp"></a>Const T CAdapt::operator&amp;  
 Retorna um **const** referência para o [m_T](#m_t) membro, permitindo que o objeto do adaptador deve ser tratado como se fosse um objeto do tipo `T`.  
  
```  
operator const T&() const;
```  
  
### <a name="return-value"></a>Valor de retorno  
 A **const** referência a `m_T`.  
  
##  <a name="operator_t_amp"></a>CAdapt::operator T&amp;  
 Retorna uma referência para o [m_T](#m_t) membro, permitindo que o objeto do adaptador deve ser tratado como se fosse um objeto do tipo `T`.  
  
```  
operator T&();
```     
  
### <a name="return-value"></a>Valor de retorno  
 Uma referência a `m_T`.  
  
##  <a name="operator_lt"></a>CAdapt::operator&lt;  
 Compara um objeto do tipo adaptado com [m_T](#m_t).  
  
```
bool operator<(const T& rSrc) const;
```  
  
### <a name="parameters"></a>Parâmetros  
 `rSrc`  
 Uma referência para o objeto a ser comparado.  
  
### <a name="return-value"></a>Valor de retorno  
 O resultado da comparação entre `m_T` e `rSrc`.  
  
##  <a name="operator_eq"></a>CAdapt::operator =  
 O operador de atribuição atribui o argumento `rSrc`, para o membro de dados [m_T](#m_t) e retorna o objeto atual do adaptador.  
  
```
CAdapt& operator= (const T& rSrc);
CAdapt& operator= (T&& rSrCA); // (Visual Studio 2017)
CAdapt& operator= (CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Parâmetros  
 `rSrc`  
 Uma referência a um objeto do tipo adaptado a ser copiado. 

 `rSrCA`
Uma referência a um objeto a ser movido. 
  
### <a name="return-value"></a>Valor de retorno  
 Uma referência ao objeto atual.  
  
##  <a name="operator_eq_eq"></a>CAdapt::operator = =  
 Compara um objeto do tipo adaptado com [m_T](#m_t).  
  
```
bool operator== (const T& rSrc) const;
```  
  
### <a name="parameters"></a>Parâmetros  
 `rSrc`  
 Uma referência para o objeto a ser comparado.  
  
### <a name="return-value"></a>Valor de retorno  
 O resultado da comparação entre `m_T` e `rSrc`.  
  
## <a name="see-also"></a>Consulte também  
 [Visão geral da classe](../../atl/atl-class-overview.md)
