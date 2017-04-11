---
title: Classe error_condition | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- system_error/std::error_condition
- std::error_condition
- error_condition
- std.error_condition
dev_langs:
- C++
helpviewer_keywords:
- error_condition class
ms.assetid: 6690f481-97c9-4554-a0ff-851dc96b7a06
caps.latest.revision: 16
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
ms.openlocfilehash: 4b9bc9b48c09c2b50b25eeb71a7fe9b5ad812157
ms.lasthandoff: 02/25/2017

---
# <a name="errorcondition-class"></a>Classe error_condition
Representa códigos de erro definidos pelo usuário.  
  
## <a name="syntax"></a>Sintaxe  
  
```
class error_condition;
```  
  
## <a name="remarks"></a>Comentários  
 Um objeto do tipo `error_condition` armazena um valor de código de erro e um ponteiro para um objeto que representa uma [categoria](../standard-library/error-category-class.md) de códigos de erro usados para os erros relatados definidos pelo usuário.  
  
### <a name="constructors"></a>Construtores  
  
|||  
|-|-|  
|[error_condition](#error_condition__error_condition)|Constrói um objeto do tipo `error_condition`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[value_type](#error_condition__value_type)|Um tipo que representa o valor do código de erro armazenado.|  
  
### <a name="member-functions"></a>Funções membro  
  
|||  
|-|-|  
|[assign](#error_condition__assign)|Atribui um valor de código de erro e categoria a uma condição de erro.|  
|[category](#error_condition__category)|Retorna a categoria de erro.|  
|[clear](#error_condition__clear)|Limpa o valor do código de erro e a categoria.|  
|[message](#error_condition__message)|Retorna o nome do código de erro.|  
  
### <a name="operators"></a>Operadores  
  
|||  
|-|-|  
|[operator==](#error_condition__operator_eq_eq)|Testa a igualdade entre objetos `error_condition`.|  
|[operator!=](#error_condition__operator_neq)|Testa a desigualdade entre objetos `error_condition`.|  
|[operator<](#error_condition__operator_lt_)|Testa se o objeto `error_condition` é menor que o objeto `error_code` passado para comparação.|  
|[operator=](#error_condition__operator_eq)|Atribui um novo valor de enumeração ao objeto `error_condition`.|  
|[operator bool](#error_condition__operator_bool)|Converte uma variável do tipo `error_condition`.|  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** \<system_error>  
  
 **Namespace:** std  
  
##  <a name="a-nameerrorconditionassigna--errorconditionassign"></a><a name="error_condition__assign"></a>  error_condition::assign  
 Atribui um valor de código de erro e categoria a uma condição de erro.  
  
```
void assign(value_type val, const error_category& _Cat);
```  
  
### <a name="parameters"></a>Parâmetros  
  
|Parâmetro|Descrição|  
|---------------|-----------------|  
|`val`|O valor de código de erro para armazenar em `error_code`.|  
|`_Cat`|A categoria de erro para armazenar em `error_code`.|  
  
### <a name="remarks"></a>Comentários  
 A função de membro armazena `val` como o valor de código de erro e um ponteiro para `_Cat`.  
  
##  <a name="a-nameerrorconditioncategorya--errorconditioncategory"></a><a name="error_condition__category"></a>  error_condition::category  
 Retorna a categoria de erro.  
  
```
const error_category& category() const;
```  
  
### <a name="return-value"></a>Valor de retorno  
 Uma referência à categoria do erro armazenado  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="a-nameerrorconditioncleara--errorconditionclear"></a><a name="error_condition__clear"></a>  error_condition::clear  
 Limpa o valor do código de erro e a categoria.  
  
```
clear();
```  
  
### <a name="remarks"></a>Comentários  
 A função de membro armazena um valor zero de código de erro e um ponteiro para o objeto [generic_category](../standard-library/system-error-functions.md#generic_category).  
  
##  <a name="a-nameerrorconditionerrorconditiona--errorconditionerrorcondition"></a><a name="error_condition__error_condition"></a>  error_condition::error_condition  
 Constrói um objeto do tipo `error_condition`.  
  
```
error_condition();

error_condition(value_type val, const error_category& _Cat);

template <class _Enum>
error_condition(_Enum _Errcode,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    error_code>::type* = 0);
```  
  
### <a name="parameters"></a>Parâmetros  
  
|Parâmetro|Descrição|  
|---------------|-----------------|  
|`val`|O valor de código de erro para armazenar em `error_condition`.|  
|`_Cat`|A categoria de erro para armazenar em `error_condition`.|  
|`_Errcode`|O valor da enumeração para armazenar em `error_condition`.|  
  
### <a name="remarks"></a>Comentários  
 O primeiro construtor armazena um valor zero de código de erro e um ponteiro para [generic_category](../standard-library/system-error-functions.md#generic_category).  
  
 O segundo construtor armazena `val` como o valor de código de erro e um ponteiro para [error_category](http://msdn.microsoft.com/en-us/6fe57a15-63a1-4e79-8af4-6738e43e19c8).  
  
 O terceiro construtor armazena `(value_type)_Errcode` como o valor de código de erro e um ponteiro para [generic_category](../standard-library/system-error-functions.md#generic_category).  
  
##  <a name="a-nameerrorconditionmessagea--errorconditionmessage"></a><a name="error_condition__message"></a>  error_condition::message  
 Retorna o nome do código de erro.  
  
```
string message() const;
```  
  
### <a name="return-value"></a>Valor de retorno  
 Uma `string` que representa o nome do código de erro.  
  
### <a name="remarks"></a>Comentários  
 Essa função membro retorna `category().message(value())`.  
  
##  <a name="a-nameerrorconditionoperatoreqeqa--errorconditionoperator"></a><a name="error_condition__operator_eq_eq"></a>  error_condition::operator==  
 Testa a igualdade entre objetos `error_condition`.  
  
```
bool operator==(const error_condition& right) const;
```  
  
### <a name="parameters"></a>Parâmetros  
  
|Parâmetro|Descrição|  
|---------------|-----------------|  
|`right`|O objeto a ser testado quanto à igualdade.|  
  
### <a name="return-value"></a>Valor de retorno  
 **true** se os objetos forem iguais; **false** se os objetos não forem iguais.  
  
### <a name="remarks"></a>Comentários  
 O operador de membro retorna `category() == right.category() && value == right.value()`.  
  
##  <a name="a-nameerrorconditionoperatorneqa--errorconditionoperator"></a><a name="error_condition__operator_neq"></a>  error_condition::operator!=  
 Testa a desigualdade entre objetos `error_condition`.  
  
```
bool operator!=(const error_condition& right) const;
```  
  
### <a name="parameters"></a>Parâmetros  
  
|Parâmetro|Descrição|  
|---------------|-----------------|  
|`right`|O objeto a ser testado quanto à desigualdade.|  
  
### <a name="return-value"></a>Valor de retorno  
 **true** se o objeto `error_condition` não for igual ao objeto `error_condition` passado em `right`. Caso contrário, **false**.  
  
### <a name="remarks"></a>Comentários  
 O operador de membro retorna `!(*this == right)`.  
  
##  <a name="a-nameerrorconditionoperatorlta--errorconditionoperatorlt"></a><a name="error_condition__operator_lt_"></a>  error_condition::operator&lt;  
 Testa se o objeto `error_condition` é menor que o objeto `error_code` passado para comparação.  
  
```
bool operator<(const error_condition& right) const;
```  
  
### <a name="parameters"></a>Parâmetros  
  
|Parâmetro|Descrição|  
|---------------|-----------------|  
|`right`|O objeto `error_condition` a ser comparado.|  
  
### <a name="return-value"></a>Valor de retorno  
 **true** se o objeto `error_condition` for menor que o objeto `error_condition` passado para comparação. Caso contrário, **false**.  
  
### <a name="remarks"></a>Comentários  
 O operador de membro retorna `category() < right.category() || category() == right.category() && value < right.value()`.  
  
##  <a name="a-nameerrorconditionoperatoreqa--errorconditionoperator"></a><a name="error_condition__operator_eq"></a>  error_condition::operator=  
 Atribui um novo valor de enumeração ao objeto `error_condition`.  
  
```
template <class _Enum>
error_condition(_Enum error,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    error_condition>::type&
 operator=(Enum _Errcode);
```  
  
### <a name="parameters"></a>Parâmetros  
  
|Parâmetro|Descrição|  
|---------------|-----------------|  
|`_Errcode`|O valor de enumeração a ser atribuído ao objeto `error_condition`.|  
  
### <a name="return-value"></a>Valor de retorno  
 Uma referência ao objeto `error_condition` ao qual está sendo atribuído um novo valor de enumeração pela função de membro.  
  
### <a name="remarks"></a>Comentários  
 O operador membro armazena `(value_type)error` como o valor de código de erro e um ponteiro para [generic_category](../standard-library/system-error-functions.md#generic_category). Ele retorna `*this`.  
  
##  <a name="a-nameerrorconditionoperatorboola--errorconditionoperator-bool"></a><a name="error_condition__operator_bool"></a>  error_condition::operator bool  
 Converte uma variável do tipo `error_condition`.  
  
```
explicit operator bool() const;
```  
  
### <a name="return-value"></a>Valor de retorno  
 O valor booliano do objeto `error_condition`.  
  
### <a name="remarks"></a>Comentários  
 O operador retornará um valor que pode ser convertido em `true` somente se o [valor](#error_condition__value) não for igual a zero. O tipo de retorno é pode ser convertido apenas para `bool`, não para `void *` ou outros tipos escalares conhecidos.  
  
##  <a name="a-nameerrorconditionvaluea--errorconditionvalue"></a><a name="error_condition__value"></a>  error_condition::value  
 Retorna o valor de código de erro armazenado.  
  
```
value_type value() const;
```  
  
### <a name="return-value"></a>Valor de retorno  
 O valor do código de erro armazenado do tipo [value_type](#error_condition__value_type).  
  
### <a name="remarks"></a>Comentários  
  
##  <a name="a-nameerrorconditionvaluetypea--errorconditionvaluetype"></a><a name="error_condition__value_type"></a>  error_condition::value_type  
 Um tipo que representa o valor do código de erro armazenado.  
  
```
typedef int value_type;
```  
  
### <a name="remarks"></a>Comentários  
 Esta definição de tipo é um sinônimo para `int`.  
  
## <a name="see-also"></a>Consulte também  
 [Classe error_category](../standard-library/error-category-class.md)   
 [<system_error>](../standard-library/system-error.md)



