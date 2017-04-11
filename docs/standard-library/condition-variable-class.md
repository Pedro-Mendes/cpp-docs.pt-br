---
title: Classe condition_variable | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- condition_variable/std::condition_variable
dev_langs:
- C++
ms.assetid: 80b1295c-b73d-4d46-b664-6e183f2eec1b
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 6ba1c9aae256029cc35f1815dbc7bfd3503254dc
ms.lasthandoff: 02/25/2017

---
# <a name="conditionvariable-class"></a>Classe condition_variable
Use a classe `condition_variable` para aguardar um evento quando você tem um `mutex` do tipo `unique_lock<mutex>`. Os objetos desse tipo talvez tenham um desempenho melhor do que os objetos do tipo [condition_variable_any<unique_lock\<mutex>>](../standard-library/condition-variable-any-class.md).  
  
## <a name="syntax"></a>Sintaxe  
  
```
class condition_variable;
```  
  
## <a name="members"></a>Membros  
  
### <a name="public-constructors"></a>Construtores públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[Construtor condition_variable::condition_variable](#condition_variable__condition_variable_constructor)|Constrói um objeto `condition_variable`.|  
  
### <a name="public-methods"></a>Métodos Públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[Método condition_variable::native_handle](#condition_variable__native_handle_method)|Retorna o tipo específico da implementação que representa o identificador condition_variable.|  
|[condition_variable::notify_all](#condition_variable__notify_all_method)|Desbloqueia todos os threads que estão aguardando o objeto `condition_variable`.|  
|[condition_variable::notify_one](#condition_variable__notify_one_method)|Desbloqueia um dos threads que estão aguardando o objeto `condition_variable`.|  
|[condition_variable::wait](#condition_variable__wait_method)|Bloqueia um thread.|  
|[condition_variable::wait_for](#condition_variable__wait_for_method)|Bloqueia um thread e define um intervalo de tempo após o qual o thread será desbloqueado.|  
|[condition_variable::wait_until](#condition_variable__wait_until_method)|Bloqueia um thread e define um ponto máximo no tempo no qual o thread será desbloqueado.|  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** condition_variable  
  
 **Namespace:** std  
  
##  <a name="a-nameconditionvariableconditionvariableconstructora--conditionvariableconditionvariable-constructor"></a><a name="condition_variable__condition_variable_constructor"></a>  Construtor condition_variable::condition_variable  
 Constrói um objeto `condition_variable`.  
  
```
condition_variable();
```  
  
### <a name="remarks"></a>Comentários  
 Se não tiver memória suficiente disponível, o construtor gerará um objeto [system_error](../standard-library/system-error-class.md) que tem um código de erro `not_enough_memory`. Se o objeto não puder ser criado porque algum outro recurso não está disponível, o construtor gerará um objeto `system_error` que tem um código de erro `resource_unavailable_try_again`.  
  
##  <a name="a-nameconditionvariablenativehandlemethoda--conditionvariablenativehandle"></a><a name="condition_variable__native_handle_method"></a>  condition_variable::native_handle  
 Retorna o tipo específico da implementação que representa o identificador condition_variable.  
  
```
native_handle_type native_handle();
```  
  
### <a name="return-value"></a>Valor de retorno  
 `native_handle_type` é definido como um ponteiro para estruturas de dados internas do Tempo de Execução de Simultaneidade.  
  
##  <a name="a-nameconditionvariablenotifyallmethoda--conditionvariablenotifyall"></a><a name="condition_variable__notify_all_method"></a>  condition_variable::notify_all  
 Desbloqueia todos os threads que estão aguardando o objeto `condition_variable`.  
  
```
void notify_all() noexcept;
```  
  
##  <a name="a-nameconditionvariablenotifyonemethoda--conditionvariablenotifyone"></a><a name="condition_variable__notify_one_method"></a>  condition_variable::notify_one  
 Desbloqueia um dos threads que estão aguardando o objeto `condition_variable`.  
  
```
void notify_one() noexcept;
```  
  
##  <a name="a-nameconditionvariablewaitmethoda--conditionvariablewait"></a><a name="condition_variable__wait_method"></a>  condition_variable::wait  
 Bloqueia um thread.  
  
```
void wait(unique_lock<mutex>& Lck);

template <class Predicate>
void wait(unique_lock<mutex>& Lck, Predicate Pred);
```  
  
### <a name="parameters"></a>Parâmetros  
 `Lck`  
 Um objeto [unique_lock\<mutex>](../standard-library/unique-lock-class.md).  
  
 `Pred`  
 Qualquer expressão que retorna `true` ou `false`.  
  
### <a name="remarks"></a>Comentários  
 O primeiro método bloqueia até que o objeto `condition_variable` seja sinalizado por uma chamada para [notify_one](#condition_variable__notify_one_method) ou [notify_all](#condition_variable__notify_all_method). Ela também pode ser ativada falsamente.  
  
 Na verdade, o segundo método executa o código a seguir.  
  
```cpp  
while(!Pred())
    wait(Lck);
```    
  
##  <a name="a-nameconditionvariablewaitformethoda--conditionvariablewaitfor"></a><a name="condition_variable__wait_for_method"></a>  condition_variable::wait_for  
 Bloqueia um thread e define um intervalo de tempo após o qual o thread será desbloqueado.  
  
```
template <class Rep, class Period>
cv_status wait_for(
    unique_lock<mutex>& Lck,
    const chrono::duration<Rep, Period>& Rel_time);

template <class Rep, class Period, class Predicate>
bool wait_for(
    unique_lock<mutex>& Lck,
    const chrono::duration<Rep, Period>& Rel_time, 
    Predicate Pred);
```  
  
### <a name="parameters"></a>Parâmetros  
 `Lck`  
 Um objeto [unique_lock\<mutex>](../standard-library/unique-lock-class.md).  
  
 `Rel_time`  
 Um objeto `chrono::duration` que especifica a quantidade de tempo antes que o thread seja ativado.  
  
 `Pred`  
 Qualquer expressão que retorna `true` ou `false`.  
  
### <a name="return-value"></a>Valor de retorno  
 O primeiro método retornará `cv_status::timeout` se a espera terminar quando `Rel_time` tiver decorrido. Do contrário, o método retorna `cv_status::no_timeout`.  
  
 O segundo método retorna o valor de `Pred`.  
  
### <a name="remarks"></a>Comentários  
 O primeiro método bloqueia até que o objeto `condition_variable` seja sinalizado por uma chamada para [notify_one](#condition_variable__notify_one_method) ou [notify_all](#condition_variable__notify_all_method) ou até que o intervalo de tempo `Rel_time` tenha decorrido. Ela também pode ser ativada falsamente.  
  
 Na verdade, o segundo método executa o código a seguir.  
  
```cpp  
while(!Pred())
    if(wait_for(Lck, Rel_time) == cv_status::timeout)
    return Pred();

return true;
```  
  
##  <a name="a-nameconditionvariablewaituntilmethoda--conditionvariablewaituntil"></a><a name="condition_variable__wait_until_method"></a>  condition_variable::wait_until  
 Bloqueia um thread e define um ponto máximo no tempo no qual o thread será desbloqueado.  
  
```
template <class Clock, class Duration>
cv_status wait_until(
    unique_lock<mutex>& Lck,
    const chrono::time_point<Clock, Duration>& Abs_time);

template <class Clock, class Duration, class Predicate>
bool wait_until(
    unique_lock<mutex>& Lck,
    const chrono::time_point<Clock, Duration>& Abs_time, 
    Predicate Pred);

cv_status wait_until(
    unique_lock<mutex>& Lck,
    const xtime* Abs_time);

template <class Predicate>
bool wait_until(
    unique_lock<mutex>& Lck,
    const xtime* Abs_time, 
    Predicate Pred);
```  
  
### <a name="parameters"></a>Parâmetros  
 `Lck`  
 Um objeto [unique_lock\<mutex>](../standard-library/unique-lock-class.md).  
  
 `Abs_time`  
 Um objeto [chrono::time_point](../standard-library/time-point-class.md).  
  
 `Pred`  
 Qualquer expressão que retorna `true` ou `false`.  
  
### <a name="return-value"></a>Valor de retorno  
 Os métodos que retornam um tipo `cv_status` retornarão `cv_status::timeout` se a espera terminar quando `Abs_time` for decorrido. Caso contrário, os métodos retornarão `cv_status::no_timeout`.  
  
 Os métodos que retornam um `bool` retornarão o valor de `Pred`.  
  
### <a name="remarks"></a>Comentários  
 O primeiro método bloqueia até que o objeto `condition_variable` seja sinalizado por uma chamada para [notify_one](#condition_variable__notify_one_method) ou [notify_all](#condition_variable__notify_all_method) ou até `Abs_time`. Ela também pode ser ativada falsamente.  
  
 Na verdade, o segundo método executa o código a seguir  
  
```cpp  
while(!Pred())
    if(wait_until(Lck, Abs_time) == cv_status::timeout)
    return Pred();

return true;
```  
  
 O terceiro e o quarto métodos usam um ponteiro para um objeto do tipo `xtime` para substituir o objeto `chrono::time_point`. O objeto `xtime` especifica a quantidade máxima de tempo para esperar um sinal.  
  
## <a name="see-also"></a>Consulte também  
 [Referência de Arquivos de Cabeçalho](../standard-library/cpp-standard-library-header-files.md)   
 [<condition_variable>](../standard-library/condition-variable.md)



