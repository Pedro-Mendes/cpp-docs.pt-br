---
title: Classe task_canceled | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- task_canceled
- CONCRT/concurrency::task_canceled
- CONCRT/concurrency::task_canceled::task_canceled
dev_langs:
- C++
helpviewer_keywords:
- task_canceled class
ms.assetid: c3f0b234-2cc1-435f-a48e-995f45b190be
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: da18db2f2dde145c565b6309d9b27cdbcc0744cf
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46437644"
---
# <a name="taskcanceled-class"></a>Classe task_canceled

Esta classe descreve uma exceção acionada pela camada de tarefas de PPL para forçar a cancelamento da tarefa atual. Ele também é gerado pela `get()` método no [tarefa](/visualstudio/extensibility/debugger/task-class-internal-members), para uma tarefa cancelada.

## <a name="syntax"></a>Sintaxe

```
class task_canceled : public std::exception;
```

## <a name="members"></a>Membros

### <a name="public-constructors"></a>Construtores Públicos

|Nome|Descrição|
|----------|-----------------|
|[task_canceled](#ctor)|Sobrecarregado. Constrói um objeto `task_canceled`.|

## <a name="inheritance-hierarchy"></a>Hierarquia de herança

`exception`

`task_canceled`

## <a name="requirements"></a>Requisitos

**Cabeçalho:** concrt. h

**Namespace:** simultaneidade

##  <a name="ctor"></a> task_canceled

Constrói um objeto `task_canceled`.

```
explicit _CRTIMP task_canceled(_In_z_ const char* _Message) throw();

task_canceled() throw();
```

### <a name="parameters"></a>Parâmetros

*Mensagem*<br/>
Uma mensagem descritiva do erro.

## <a name="see-also"></a>Consulte também

[Namespace de simultaneidade](concurrency-namespace.md)
