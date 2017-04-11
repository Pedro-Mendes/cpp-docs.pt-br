---
title: Classe shared_future | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- future/std::shared_future
dev_langs:
- C++
ms.assetid: 454ebedd-f42b-405f-99a5-a25cc9ad7c90
caps.latest.revision: 13
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: e21a48023b9f80a189d8f75e2480a8e86e19952f
ms.lasthandoff: 02/25/2017

---
# <a name="sharedfuture-class"></a>Classe shared_future
Descreve um *objeto de retorno assíncrono*. Diferente de um objeto [future](../standard-library/future-class.md), um *provedor assíncrono* pode ser associado a qualquer quantidade de objetos `shared_future`.  
  
## <a name="syntax"></a>Sintaxe  
  
```
template <class Ty>
class shared_future;
```  
  
## <a name="remarks"></a>Comentários  
 Não chame nenhum método diferente de `valid`, `operator=` e o destruidor em um objeto `shared_future` que seja *vazio*.  
  
 Objetos `shared_future` não estão sincronizados. Chamar métodos no mesmo objeto de vários threads gera uma corrida de dados com resultados imprevisíveis.  
  
## <a name="members"></a>Membros  
  
### <a name="public-constructors"></a>Construtores públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[Construtor shared_future::shared_future](#shared_future__shared_future_constructor)|Constrói um objeto `shared_future`.|  
  
### <a name="public-methods"></a>Métodos Públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[Método shared_future::get](#shared_future__get_method)|Recupera o resultado armazenado no *estado assíncrono associado*.|  
|[Método shared_future::valid](#shared_future__valid_method)|Especifica se o objeto não está vazio.|  
|[Método shared_future::wait](#shared_future__wait_method)|Bloqueia o thread atual até que o estado assíncrono associado esteja pronto.|  
|[Método shared_future::wait_for](#shared_future__wait_for_method)|Bloqueia até que o estado assíncrono associado esteja pronto ou até que o tempo especificado tenha decorrido.|  
|[Método shared_future::wait_until](#shared_future__wait_until_method)|Bloqueia até que o estado assíncrono associado esteja pronto ou até um ponto no tempo especificado.|  
  
### <a name="public-operators"></a>Operadores públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[shared_future::operator=](#shared_future__operator_eq)|Atribui um novo estado assíncrono associado.|  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** future  
  
 **Namespace:** std  
  
##  <a name="shared_future__get_method"></a> Método shared_future::get  
 Recupera o resultado armazenado no *estado assíncrono associado*.  
  
```
const Ty& get() const;

Ty& get() const;

void get() const;
```  
  
### <a name="remarks"></a>Comentários  
 Se o resultado for uma exceção, o método a gerará novamente. Caso contrário, o resultado será retornado.  
  
 Antes de recuperar o resultado, este método bloqueia o thread atual até que o estado assíncrono associado esteja pronto.  
  
 Para a especialização parcial `shared_future<Ty&>`, o valor armazenado será efetivamente uma referência ao objeto que foi passado para o *provedor assíncrono* como o valor retornado.  
  
 Como não existe nenhum valor armazenado para a especialização `shared_future<void>`, o método retorna `void`.  
  
##  <a name="shared_future__operator_eq"></a>  shared_future::operator=  
 Transfere o *estado assíncrono associado* de um objeto especificado.  
  
```
shared_future& operator=(shared_future&& Right) noexcept;
shared_future& operator=(const shared_future& Right);
```  
  
### <a name="parameters"></a>Parâmetros  
 `Right`  
 Um objeto `shared_future`.  
  
### <a name="return-value"></a>Valor de retorno  
 `*this`  
  
### <a name="remarks"></a>Comentários  
 Para o primeiro operador, `Right` não tem mais um estado assíncrono associado após a operação.  
  
 Para o segundo método, `Right` mantém seu estado assíncrono associado.  
  
##  <a name="shared_future__shared_future_constructor"></a> Construtor shared_future::shared_future  
 Constrói um objeto `shared_future`.  
  
```
shared_future() noexcept;
shared_future(future<Ty>&& Right) noexcept;
shared_future(shared_future&& Right) noexcept;
shared_future(const shared_future& Right);
```  
  
### <a name="parameters"></a>Parâmetros  
 `Right`  
 Um objeto [future](../standard-library/future-class.md) ou `shared_future`.  
  
### <a name="remarks"></a>Comentários  
 O primeiro construtor cria um objeto `shared_future` que não tem nenhum *estado assíncrono associado*.  
  
 O segundo e terceiro construtores criam um objeto `shared_future` e transferem o estado assíncrono associado de `Right`. `Right` não tem mais um estado assíncrono associado.  
  
 O quarto construtor cria um objeto `shared_future` que tem o mesmo estado assíncrono associado que `Right`.  
  
##  <a name="shared_future__valid_method"></a> Método shared_future::valid  
 Especifica se o objeto tem um *estado assíncrono associado*.  
  
```
bool valid() noexcept;
```  
  
### <a name="return-value"></a>Valor de retorno  
 `true` se o objeto tiver um estado assíncrono associado; caso contrário, `false`.  
  
##  <a name="shared_future__wait_method"></a> Método shared_future::wait  
 Bloqueia o thread atual até que o *estado assíncrono associado* esteja *pronto*.  
  
```
void wait() const;
```  
  
### <a name="remarks"></a>Comentários  
 Um estado assíncrono associado ficará pronto somente se seu provedor assíncrono tiver armazenado um valor retornado ou armazenado uma exceção.  
  
##  <a name="shared_future__wait_for_method"></a> Método shared_future::wait_for  
 Bloqueia o thread atual até que o estado assíncrono associado seja *ready* ou até que o intervalo de tempo especificado tenha decorrido.  
  
```
template <class Rep, class Period>
future_status wait_for(
    const chrono::duration<Rep, Period>& Rel_time) const;
```  
  
### <a name="parameters"></a>Parâmetros  
 `Rel_time`  
 Um objeto [chrono::duration](../standard-library/duration-class.md) que especifica um intervalo de tempo máximo durante o qual o thread fica bloqueado.  
  
### <a name="return-value"></a>Valor de retorno  
 Um [future_status](../standard-library/future-enums.md#future_status_enumeration) que indica o motivo do retorno.  
  
### <a name="remarks"></a>Comentários  
 Um estado assíncrono associado ficará *pronto* somente se seu provedor assíncrono tiver armazenado um valor retornado ou armazenado uma exceção.  
  
##  <a name="shared_future__wait_until_method"></a> Método shared_future::wait_until  
 Bloqueia o thread atual até que o estado assíncrono associado esteja *pronto* ou após um determinado ponto no tempo.  
  
```
template <class Clock, class Duration>
future_status wait_until(
    const chrono::time_point<Clock, Duration>& Abs_time) const;
```  
  
### <a name="parameters"></a>Parâmetros  
 `Abs_time`  
 Um objeto [chrono::time_point](../standard-library/time-point-class.md) que especifica um tempo após o qual o thread pode ser desbloqueado.  
  
### <a name="return-value"></a>Valor de retorno  
 Um [future_status](../standard-library/future-enums.md#future_status_enumeration) que indica o motivo do retorno.  
  
### <a name="remarks"></a>Comentários  
 Um estado assíncrono associado ficará pronto somente se seu provedor assíncrono tiver armazenado um valor retornado ou armazenado uma exceção.  
  
## <a name="see-also"></a>Consulte também  
 [Referência de Arquivos de Cabeçalho](../standard-library/cpp-standard-library-header-files.md)   
 [\<future>](../standard-library/future.md)



