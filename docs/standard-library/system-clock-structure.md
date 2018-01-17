---
title: Estrutura system_clock | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- chrono/std::chrono::system_clock
- chrono/std::chrono::system_clock::from_time_t
- chrono/std::chrono::system_clock::now
- chrono/std::chrono::system_clock::to_time_t
- chrono/std::chrono::system_clock::is_monotonic Constant
- chrono/std::chrono::system_clock::is_steady Constant
dev_langs: C++
ms.assetid: a97bd46e-267a-4836-9f7d-af1f664e99ae
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 603415b438578258e982f0934161d2de436e2a3f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="systemclock-structure"></a>Estrutura system_clock
Representa um *tipo de relógio* baseado no relógio em tempo real do sistema.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
struct system_clock;  
```  
  
## <a name="remarks"></a>Comentários  
 Um *tipo de relógio* é usado para obter a hora atual como UTC. O tipo incorpora uma instanciação de [duration](../standard-library/duration-class.md) e o modelo de classe [time_point](../standard-library/time-point-class.md) e define uma função membro estática `now()` que retorna a hora.  
  
 Um relógio será *monotônico* se o valor retornado por uma primeira chamada a `now()` for sempre menor ou igual ao valor retornado por uma chamada posterior a `now()`.  
  
 Um relógio será *estável* se ele for *monotônico* e se o tempo entre os tiques do relógio for constante.  
  
 Nessa implementação, um `system_clock` é sinônimo de um `high_resolution_clock`.  
  
## <a name="members"></a>Membros  
  
### <a name="public-typedefs"></a>Typedefs públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|`system_clock::duration`|Um sinônimo de `duration<rep, period>`.|  
|`system_clock::period`|Um sinônimo do tipo que é usado para representar o período de tiques na instanciação independente de `duration`.|  
|`system_clock::rep`|Um sinônimo do tipo que é usado para representar o número de tiques do relógio na instanciação independente de `duration`.|  
|`system_clock::time_point`|Um sinônimo de `time_point<Clock, duration>`, em que `Clock` é um sinônimo do próprio tipo de relógio ou de outro tipo de relógio que se baseia na mesma época e que tem o mesmo tipo `duration` aninhado.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[from_time_t](#from_time_t)|Estático. Retorna um `time_point` que mais se aproxima de um tempo especificado.|  
|[Agora](#now)|Estático. Retorna a data atual.|  
|[to_time_t](#to_time_t)|Estático. Retorna um objeto `time_t` que mais se aproxima de um `time_point` especificado.|  
  
### <a name="public-constants"></a>Constantes públicas  
  
|Nome|Descrição|  
|----------|-----------------|  
|[Constante system_clock::is_monotonic](#is_monotonic_constant)|Especifica se o tipo de relógio é monotônico.|  
|[Constante system_clock::is_steady](#is_steady_constant)|Especifica se o tipo de relógio é estável.|  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** \<chrono >  
  
 **Namespace:** std::chrono  
  
##  <a name="from_time_t"></a>system_clock:: from_time_t
 Método estático que retorna um [time_point](../standard-library/time-point-class.md) que mais se aproxima do tempo representado por `Tm`.  
  
```  
static time_point from_time_t(time_t Tm) noexcept;  
```  
  
### <a name="parameters"></a>Parâmetros  
 `Tm`  
 Um objeto [time_t](../c-runtime-library/standard-types.md).  
  
##  <a name="is_monotonic_constant"></a>  Constante system_clock::is_monotonic  
 Valor estático que especifica se o tipo de relógio é monotônico.  
  
```  
static const bool is_monotonic = false;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 Nessa implementação, `system_clock::is_monotonic` sempre retorna `false`.  
  
### <a name="remarks"></a>Comentários  
 Um relógio será *monotônico* se o valor retornado por uma primeira chamada a `now()` for sempre menor ou igual ao valor retornado por uma chamada posterior a `now()`.  
  
##  <a name="is_steady_constant"></a>  Constante system_clock::is_steady  
 Valor estático que especifica se o tipo de relógio é *estável*.  
  
```  
static const bool is_steady = false;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 Nessa implementação, `system_clock::is_steady` sempre retorna `false`.  
  
### <a name="remarks"></a>Comentários  
 Um relógio será *estável* se ele for [monotônico](#is_monotonic_constant) e se o tempo entre os tiques do relógio for constante.  
  
##  <a name="now"></a>system_clock:: Now
 Método estático que retorna a hora atual.  
  
```  
static time_point now() noexcept;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 Um objeto [time_point](../standard-library/time-point-class.md) que representa a hora atual.  
  
##  <a name="to_time_t"></a>system_clock:: to_time_t
 Método estático que retorna um [time_t](../c-runtime-library/standard-types.md) que mais se aproxima do tempo representado por `Time`.  
  
```  
static time_t to_time_t(const time_point& Time) noexcept;  
```  
  
### <a name="parameters"></a>Parâmetros  
 `Time`  
 Um objeto [time_point](../standard-library/time-point-class.md).  
  
## <a name="see-also"></a>Consulte também  
 [Referência de Arquivos de Cabeçalho](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono>](../standard-library/chrono.md)   
 [Struct steady_clock](../standard-library/steady-clock-struct.md)