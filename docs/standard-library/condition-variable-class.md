---
title: Classe condition_variable | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- condition_variable/std::condition
- condition_variable/std::condition_variable::condition_variable
- condition_variable/std::condition_variable::native_handle
- condition_variable/std::condition_variable::notify_all
- condition_variable/std::condition_variable::notify_one
- condition_variable/std::condition_variable::wait
- condition_variable/std::condition_variable::wait_for
- condition_variable/std::condition_variable::wait_until
dev_langs:
- C++
ms.assetid: 80b1295c-b73d-4d46-b664-6e183f2eec1b
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::condition
- std::condition_variable::condition_variable
- std::condition_variable::native_handle
- std::condition_variable::notify_all
- std::condition_variable::notify_one
- std::condition_variable::wait
- std::condition_variable::wait_for
- std::condition_variable::wait_until
ms.workload:
- cplusplus
ms.openlocfilehash: 0e4d31a93ac8e0f7785ea567821c0ac6b0ad6a58
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44109830"
---
# <a name="conditionvariable-class"></a>Classe condition_variable

Use a classe `condition_variable` para aguardar um evento quando você tem um `mutex` do tipo `unique_lock<mutex>`. Os objetos desse tipo talvez tenham um desempenho melhor do que os objetos do tipo [condition_variable_any<unique_lock\<mutex>>](../standard-library/condition-variable-any-class.md).

## <a name="syntax"></a>Sintaxe

```cpp
class condition_variable;
```

## <a name="members"></a>Membros

### <a name="public-constructors"></a>Construtores Públicos

|Nome|Descrição|
|----------|-----------------|
|[condition_variable](#condition_variable)|Constrói um objeto `condition_variable`.|

### <a name="public-methods"></a>Métodos Públicos

|Nome|Descrição|
|----------|-----------------|
|[native_handle](#native_handle)|Retorna o tipo específico da implementação que representa o identificador condition_variable.|
|[notify_all](#notify_all)|Desbloqueia todos os threads que estão aguardando o objeto `condition_variable`.|
|[notify_one](#notify_one)|Desbloqueia um dos threads que estão aguardando o objeto `condition_variable`.|
|[wait](#wait)|Bloqueia um thread.|
|[wait_for](#wait_for)|Bloqueia um thread e define um intervalo de tempo após o qual o thread será desbloqueado.|
|[wait_until](#wait_until)|Bloqueia um thread e define um ponto máximo no tempo no qual o thread será desbloqueado.|

## <a name="requirements"></a>Requisitos

**Cabeçalho:** \<condition_variable >

**Namespace:** std

## <a name="condition_variable"></a>  Construtor condition_variable::condition_variable

Constrói um objeto `condition_variable`.

```cpp
condition_variable();
```

### <a name="remarks"></a>Comentários

Se não tiver memória suficiente disponível, o construtor gerará um objeto [system_error](../standard-library/system-error-class.md) que tem um código de erro `not_enough_memory`. Se o objeto não puder ser criado porque algum outro recurso não está disponível, o construtor gerará um objeto `system_error` que tem um código de erro `resource_unavailable_try_again`.

## <a name="native_handle"></a>  condition_variable::native_handle

Retorna o tipo específico da implementação que representa o identificador condition_variable.

```cpp
native_handle_type native_handle();
```

### <a name="return-value"></a>Valor de retorno

`native_handle_type` é definido como um ponteiro para estruturas de dados internas do Tempo de Execução de Simultaneidade.

## <a name="notify_all"></a>  condition_variable::notify_all

Desbloqueia todos os threads que estão aguardando o objeto `condition_variable`.

```cpp
void notify_all() noexcept;
```

## <a name="notify_one"></a>  condition_variable::notify_one

Desbloqueia um dos threads que estão aguardando o objeto `condition_variable`.

```cpp
void notify_one() noexcept;
```

## <a name="wait"></a>  condition_variable::wait

Bloqueia um thread.

```cpp
void wait(unique_lock<mutex>& Lck);

template <class Predicate>
void wait(unique_lock<mutex>& Lck, Predicate Pred);
```

### <a name="parameters"></a>Parâmetros

*Lck*<br/>
Um objeto [unique_lock\<mutex>](../standard-library/unique-lock-class.md).

*Pred*<br/>
Qualquer expressão que retorna **verdadeira** ou **falso**.

### <a name="remarks"></a>Comentários

O primeiro método bloqueia até que o objeto `condition_variable` seja sinalizado por uma chamada para [notify_one](#notify_one) ou [notify_all](#notify_all). Ela também pode ser ativada falsamente.

Na verdade, o segundo método executa o código a seguir.

```cpp
while(!Pred())
    wait(Lck);
```

## <a name="wait_for"></a>  condition_variable::wait_for

Bloqueia um thread e define um intervalo de tempo após o qual o thread será desbloqueado.

```cpp
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

*Lck*<br/>
Um objeto [unique_lock\<mutex>](../standard-library/unique-lock-class.md).

*Rel_time*<br/>
Um objeto `chrono::duration` que especifica a quantidade de tempo antes que o thread seja ativado.

*Pred*<br/>
Qualquer expressão que retorna **verdadeira** ou **falso**.

### <a name="return-value"></a>Valor de retorno

O primeiro método retorna `cv_status::timeout` se a espera terminar quando *Rel_time* tiver decorrido. Do contrário, o método retorna `cv_status::no_timeout`.

O segundo método retorna o valor de *Pred*.

### <a name="remarks"></a>Comentários

O primeiro método bloqueia até que o `condition_variable` objeto é sinalizado por uma chamada para [notify_one](#notify_one) ou [notify_all](#notify_all) ou até que o intervalo de tempo *Rel_time* tiver decorrido. Ela também pode ser ativada falsamente.

Na verdade, o segundo método executa o código a seguir.

```cpp
while(!Pred())
    if(wait_for(Lck, Rel_time) == cv_status::timeout)
    return Pred();

return true;
```

## <a name="wait_until"></a>  condition_variable::wait_until

Bloqueia um thread e define um ponto máximo no tempo no qual o thread será desbloqueado.

```cpp
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

*Lck*<br/>
Um objeto [unique_lock\<mutex>](../standard-library/unique-lock-class.md).

*Abs_time*<br/>
Um objeto [chrono::time_point](../standard-library/time-point-class.md).

*Pred*<br/>
Qualquer expressão que retorna **verdadeira** ou **falso**.

### <a name="return-value"></a>Valor de retorno

Os métodos que retornam um `cv_status` tipo de retorno `cv_status::timeout` se a espera terminar quando *Abs_time* tenha decorrido. Caso contrário, os métodos retornarão `cv_status::no_timeout`.

Os métodos que retornam um **bool** retornar o valor de *Pred*.

### <a name="remarks"></a>Comentários

O primeiro método bloqueia até que o objeto `condition_variable` seja sinalizado por uma chamada para [notify_one](#notify_one) ou [notify_all](#notify_all) ou até `Abs_time`. Ela também pode ser ativada falsamente.

Na verdade, o segundo método executa o código a seguir

```cpp
while(!Pred())
    if(wait_until(Lck, Abs_time) == cv_status::timeout)
    return Pred();

return true;
```

O terceiro e o quarto métodos usam um ponteiro para um objeto do tipo `xtime` para substituir o objeto `chrono::time_point`. O objeto `xtime` especifica a quantidade máxima de tempo para esperar um sinal.

## <a name="see-also"></a>Consulte também

[Referência de Arquivos de Cabeçalho](../standard-library/cpp-standard-library-header-files.md)<br/>
[<condition_variable>](../standard-library/condition-variable.md)<br/>
