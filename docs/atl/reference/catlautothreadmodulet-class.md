---
title: Classe CAtlAutoThreadModuleT | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT::GetDefaultThreads
dev_langs:
- C++
helpviewer_keywords:
- CAtlAutoThreadModuleT class
ms.assetid: ae1667c6-3fb8-47bc-b35d-9ea5e9896d7f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 46198390ce25cb655b94c0ca4769321fc3e9362d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099688"
---
# <a name="catlautothreadmodulet-class"></a>Classe CAtlAutoThreadModuleT

Essa classe fornece métodos para implementar um servidor COM em pool de thread, o modelo de apartment.

> [!IMPORTANT]
>  Essa classe e seus membros não podem ser usados em aplicativos executados no tempo de execução do Windows.

## <a name="syntax"></a>Sintaxe

```
template <class T,
         class ThreadAllocator = CComSimpleThreadAllocator,
         DWORD dwWait = INFINITE>
class ATL_NO_VTABLE CAtlAutoThreadModuleT : public IAtlAutoThreadModule
```

#### <a name="parameters"></a>Parâmetros

*T*<br/>
A classe que implementará o servidor COM.

*ThreadAllocator*<br/>
A classe de gerenciamento de seleção de thread. O valor padrão é [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).

*dwWait*<br/>
Especifica o intervalo de tempo limite em milissegundos. O padrão é infinito, o que significa que o intervalo de tempo limite do método nunca tiver decorrido.

## <a name="members"></a>Membros

### <a name="public-methods"></a>Métodos Públicos

|Nome|Descrição|
|----------|-----------------|
|[CAtlAutoThreadModuleT::GetDefaultThreads](#getdefaultthreads)|A função estática dinamicamente calcula e retorna o número máximo de threads para o módulo do EXE, com base no número de processadores.|

## <a name="remarks"></a>Comentários

A classe [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) deriva `CAtlAutoThreadModuleT` para implementar um servidor COM em pool de thread, o modelo de apartment. Ele substitui a classe obsoleta [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).

> [!NOTE]
>  Essa classe não deve ser usada em uma DLL, como o padrão *dwWait* valor infinito causará um deadlock quando a DLL é descarregada.

## <a name="inheritance-hierarchy"></a>Hierarquia de herança

`IAtlAutoThreadModule`

`CAtlAutoThreadModuleT`

## <a name="requirements"></a>Requisitos

**Cabeçalho:** atlbase. h

##  <a name="getdefaultthreads"></a>  CAtlAutoThreadModuleT::GetDefaultThreads

A função estática dinamicamente calcula e retorna o número máximo de threads para o módulo do EXE, com base no número de processadores.

```
static int GetDefaultThreads();
```

### <a name="return-value"></a>Valor de retorno

O número de threads a ser criado no módulo do EXE.

### <a name="remarks"></a>Comentários

Substitua este método se você quiser usar um método diferente para calcular o número de threads. Por padrão, o número de threads com base no número de processadores.

## <a name="see-also"></a>Consulte também

[Classe de IAtlAutoThreadModule](../../atl/reference/iatlautothreadmodule-class.md)<br/>
[Visão geral da classe](../../atl/atl-class-overview.md)<br/>
[Classe de IAtlAutoThreadModule](../../atl/reference/iatlautothreadmodule-class.md)<br/>
[Classes de módulo](../../atl/atl-module-classes.md)
