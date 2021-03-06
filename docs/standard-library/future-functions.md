---
title: Funções &lt;future&gt; | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- future/std::async
- future/std::future_category
- future/std::make_error_code
- future/std::make_error_condition
- future/std::swap
ms.assetid: 1e3acc1e-736a-42dc-ade2-b2fe69aa96bc
helpviewer_keywords:
- std::async [C++]
- std::future_category [C++]
- std::make_error_code [C++]
- std::make_error_condition [C++]
- std::swap [C++]
ms.openlocfilehash: 9b4a8b148dc8b72c7dcc1931802c503be783e9ea
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44108559"
---
# <a name="ltfuturegt-functions"></a>Funções &lt;future&gt;

||||
|-|-|-|
|[async](#async)|[future_category](#future_category)|[make_error_code](#make_error_code)|
|[make_error_condition](#make_error_condition)|[swap](#swap)|

## <a name="async"></a>  async

Representa um *provedor assíncrono*.

```cpp
template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(Fn&& fn, ArgTypes&&... args);

template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(launch policy, Fn&& fn, ArgTypes&&... args);
```

### <a name="parameters"></a>Parâmetros

*Política*<br/>
Um valor [launch](../standard-library/future-enums.md#launch).

### <a name="remarks"></a>Comentários

Definições das abreviações:

|||
|-|-|
|*dfn*|O resultado da chamada para `decay_copy(forward<Fn>(fn))`.|
|*dargs*|Os resultados das chamadas para `decay_copy(forward<ArgsTypes>(args...))`.|
|*Ty*|O tipo `result_of<Fn(ArgTypes...)>::type`.|

A primeira função de modelo retorna `async(launch::any, fn, args...)`.

A segunda função retorna um objeto `future<Ty>` cujo *estado assíncrono associado* contém um resultado em conjunto com os valores de *dfn* e *dargs*, bem como um objeto de thread para gerenciar um thread de execução separado.

A menos que `decay<Fn>::type` não seja do tipo launch, a segunda função não participará da resolução da sobrecarga.

O padrão C++ declara que, se a política é launch::async, a função cria um novo thread. No entanto a implementação da Microsoft é atualmente não conformes. Ele obtém seus threads do ThreadPool Windows, que, em alguns casos, pode fornecer a um thread reciclado, em vez de um novo. Isso significa que o `launch::async` política, na verdade, é implementada como `launch::async|launch::deferred`.  Outra implicação a implementação baseada no ThreadPool é que não há nenhuma garantia de que as variáveis locais de thread serão destruídas quando o thread ser concluído. Se o thread será reciclado e fornecido para uma nova chamada para `async`, as variáveis antigas ainda existirão. Portanto, recomendamos que você não use variáveis de local de thread com `async`.

Se *diretiva* é `launch::deferred`, a função marcará seu estado assíncrono associado como contendo um *adiada função* e retorna. A primeira chamada para qualquer função não temporizada que aguarda que o estado assíncrono associado fique pronto chama a função adiada avaliando `INVOKE(dfn, dargs..., Ty)`.

Em todos caso, o estado assíncrono associado do objeto `future` não é definido como *ready* até que a avaliação de `INVOKE(dfn, dargs..., Ty)` seja concluída, seja lançando uma exceção ou retornando normalmente. O resultado do estado assíncrono associado é uma exceção se uma tiver sido gerada ou qualquer valor que for retornado pela avaliação.

> [!NOTE]
> Para um `future`— ou o último [shared_future](../standard-library/shared-future-class.md) — anexado a uma tarefa iniciada com `std::async`, os destruidor é bloqueado se a tarefa não tiver sido concluída, ou seja, ele é bloqueado se esse thread ainda não tiver chamado `.get()` ou `.wait()` e a tarefa ainda estiver em execução. Se um `future` obtido de `std::async` for movido para fora do escopo local, outro código que o utiliza deve estar ciente de que seu destruidor pode ser bloqueado para que o estado compartilhado fique pronto.

A pseudo função `INVOKE` é definida em [\<functional>](../standard-library/functional.md).

## <a name="future_category"></a>  future_category

Retorna uma referência ao objeto [error_category](../standard-library/error-category-class.md) que caracteriza erros associados a objetos `future`.

```cpp
const error_category& future_category() noexcept;
```

## <a name="make_error_code"></a>  make_error_code

Cria um [error_code](../standard-library/error-code-class.md) com o objeto [error_category](../standard-library/error-category-class.md) que caracteriza erros de [future](../standard-library/future-class.md).

```cpp
inline error_code make_error_code(future_errc Errno) noexcept;
```

### <a name="parameters"></a>Parâmetros

*errno*<br/>
Um valor de [future_errc](../standard-library/future-enums.md#future_errc) que identifica o erro relatado.

### <a name="return-value"></a>Valor de retorno

`error_code(static_cast<int>(Errno), future_category());`

## <a name="make_error_condition"></a>  make_error_condition

Cria um [error_condition](../standard-library/error-condition-class.md) com o objeto [error_category](../standard-library/error-category-class.md) que caracteriza erros de [future](../standard-library/future-class.md).

```cpp
inline error_condition make_error_condition(future_errc Errno) noexcept;
```

### <a name="parameters"></a>Parâmetros

*errno*<br/>
Um valor de [future_errc](../standard-library/future-enums.md#future_errc) que identifica o erro relatado.

### <a name="return-value"></a>Valor de retorno

`error_condition(static_cast<int>(Errno), future_category());`

## <a name="swap"></a>  swap

Troca o *estado assíncrono associado* de um objeto `promise` pelo de outro objeto.

```cpp
template <class Ty>
void swap(promise<Ty>& Left, promise<Ty>& Right) noexcept;

template <class Ty, class... ArgTypes>
void swap(packaged_task<Ty(ArgTypes...)>& Left, packaged_task<Ty(ArgTypes...)>& Right) noexcept;
```

### <a name="parameters"></a>Parâmetros

*Esquerda*<br/>
O objeto `promise` à esquerda.

*Direita*<br/>
O objeto `promise` à direita.

## <a name="see-also"></a>Consulte também

[\<future>](../standard-library/future.md)<br/>
