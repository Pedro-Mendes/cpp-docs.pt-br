---
title: Classe out_of_memory | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- out_of_memory
- AMPRT/out_of_memory
- AMPRT/Concurrency::out_of_memory::out_of_memory
dev_langs:
- C++
helpviewer_keywords:
- out_of_memory class
ms.assetid: 3aa7e682-8f13-4ae6-9188-31fb423956e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3da944d519964105bd43135d61b5874ad96a6670
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378808"
---
# <a name="outofmemory-class"></a>Classe out_of_memory

A exceção que é lançada quando um método falhar devido à falta de memória do sistema ou do dispositivo.

## <a name="syntax"></a>Sintaxe

```
class out_of_memory : public runtime_exception;
```

## <a name="members"></a>Membros

### <a name="public-constructors"></a>Construtores Públicos

|Nome|Descrição|
|----------|-----------------|
|[Construtor de out_of_memory](#ctor)|Inicializa uma nova instância da classe `out_of_memory`.|

## <a name="inheritance-hierarchy"></a>Hierarquia de herança

`exception`

`runtime_exception`

`out_of_memory`

## <a name="requirements"></a>Requisitos

**Cabeçalho:** amprt. h

**Namespace:** Simultaneidade
## <a name="ctor"></a> out_of_memory

Inicializa uma nova instância da classe.

### <a name="syntax"></a>Sintaxe

```
explicit out_of_memory(
    const char * _Message ) throw();

out_of_memory () throw();
```

### <a name="parameters"></a>Parâmetros

*Mensagem*<br/>
Uma descrição do erro.

### <a name="return-value"></a>Valor de retorno

Uma nova instância da classe `out_of_memory`.

## <a name="see-also"></a>Consulte também

[Namespace de simultaneidade (C++ AMP)](concurrency-namespace-cpp-amp.md)
