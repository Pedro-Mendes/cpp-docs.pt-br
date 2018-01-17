---
title: '&lt;condition_variable&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: <condition_variable>
dev_langs: C++
ms.assetid: 8567f7cc-20bd-42a7-9137-87c46f878009
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: baabac0a4461c659a3e70c2c26bcb971f0e1c738
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="ltconditionvariablegt"></a>&lt;condition_variable&gt;
Define as classes [condition_variable](../standard-library/condition-variable-class.md) e [condition_variable_any](../standard-library/condition-variable-any-class.md) usadas para criar objetos que aguardam uma condição se tornar verdadeira.  
  
 Esse cabeçalho usa ConcRT (Tempo de Execução de Simultaneidade) para que você possa usá-lo juntamente com outros mecanismos ConcRT. Para obter mais informações sobre o ConcRT, consulte [Tempo de execução de simultaneidade](../parallel/concrt/concurrency-runtime.md).  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp  
#include <condition_variable>  
```  
  
> [!NOTE]
>  No código que é compilado usando **/clr**, esse cabeçalho é bloqueado.  
  
### <a name="remarks"></a>Comentários  
 Código que aguarda até que uma variável de condição também deva usar um `mutex`. Um thread de chamada deve bloquear `mutex` antes de chamar as funções que aguardam a variável de condição. O `mutex` está bloqueado quando a função chamada é retornada. O `mutex` não está bloqueado enquanto o thread aguarda a condição se tornar verdadeira. Portanto, para que não haja resultados imprevisíveis, cada thread que aguarda uma variável de condição deve usar o mesmo objeto `mutex`.  
  
 Os objetos do tipo `condition_variable_any` podem ser usados com um mutex de qualquer tipo. O tipo do mutex usado não precisa fornecer o método `try_lock`. Os objetos do tipo `condition_variable` podem ser usados com um mutex do tipo `unique_lock<mutex>`. Os objetos desse tipo podem ser mais rápidos do que os objetos do tipo `condition_variable_any<unique_lock<mutex>>`.  
  
 Para aguardar um evento, primeiro bloqueie o mutex e, em seguida, chame um dos métodos `wait` na variável de condição. A chamada `wait` é bloqueada até que outro thread sinalize a variável de condição.  
  
 *Ativações falsas* ocorrem quando os threads que estão aguardando variáveis de condição ficam desbloqueados sem as notificações adequadas. Para reconhecer essas ativações falsas, o código que aguarda uma condição se tornar verdadeira deverá verificar explicitamente essa condição quando o código retornar de uma função de espera. Geralmente, isso é feito usando um loop; é possível usar `wait(unique_lock<mutex>& lock, Predicate pred)` para realizar esse loop para você.  
  
```cpp  
while (condition is false)
    wait for condition variable;
```  
  
 As classes `condition_variable_any` e `condition_variable` têm, cada uma, três métodos que aguardam uma condição.  
  
- `wait` aguarda um período de tempo não associado.  
  
- `wait_until` aguarda até um `time` especificado.  
  
- `wait_for` aguarda um `time interval` especificado.  
  
 Cada um desses métodos tem duas versões sobrecarregadas. Um deles apenas aguarda e pode ser ativado falsamente. O outro usa um argumento de modelo adicional que define um predicado. O método não retorna até que o predicado seja `true`.  
  
 Cada classe também tem dois métodos usados para notificar uma variável de condição de que sua condição é `true`.  
  
- `notify_one` ativa um dos threads que está aguardando a variável de condição.  
  
- `notify_all` ativa todos os threads que estão aguardando a variável de condição.  
  
## <a name="see-also"></a>Consulte também  
 [Referência de Arquivos de Cabeçalho](../standard-library/cpp-standard-library-header-files.md)   
 [Classe condition_variable](../standard-library/condition-variable-class.md)   
 [Classe condition_variable_any](../standard-library/condition-variable-any-class.md)