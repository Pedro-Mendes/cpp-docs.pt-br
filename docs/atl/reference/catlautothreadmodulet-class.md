---
title: Classe CAtlAutoThreadModuleT | Documentos do Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 86b35f0a6a3ab43c170ee710838ec9ba0e2fc5b0
ms.lasthandoff: 02/25/2017

---
# <a name="catlautothreadmodulet-class"></a>Classe CAtlAutoThreadModuleT
Essa classe fornece métodos para a implementação de um servidor de pool de thread, o modelo de apartment COM.  
  
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
 `T`  
 A classe que implementará o servidor COM.  
  
 `ThreadAllocator`  
 A classe de gerenciamento de seleção de thread. O valor padrão é [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).  
  
 `dwWait`  
 Especifica o intervalo de tempo limite em milissegundos. O padrão é infinito, o que significa que o intervalo de tempo limite do método nunca tiver decorrido.  
  
## <a name="members"></a>Membros  
  
### <a name="public-methods"></a>Métodos Públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CAtlAutoThreadModuleT::GetDefaultThreads](#getdefaultthreads)|A função estática dinamicamente calcula e retorna o número máximo de threads para o módulo EXE, com base no número de processadores.|  
  
## <a name="remarks"></a>Comentários  
 A classe [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) deriva `CAtlAutoThreadModuleT` para implementar um servidor de pool de thread, o modelo de apartment COM. Ele substitui a classe obsoleta [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  
  
> [!NOTE]
>  Essa classe não deve ser usada em uma DLL, como o padrão `dwWait` valor infinito causará um deadlock quando a DLL é descarregada.  
  
## <a name="inheritance-hierarchy"></a>Hierarquia de herança  
 `IAtlAutoThreadModule`  
  
 `CAtlAutoThreadModuleT`  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** atlbase. h  
  
##  <a name="getdefaultthreads"></a>CAtlAutoThreadModuleT::GetDefaultThreads  
 A função estática dinamicamente calcula e retorna o número máximo de threads para o módulo EXE, com base no número de processadores.  
  
```
static int GetDefaultThreads();
```  
  
### <a name="return-value"></a>Valor de retorno  
 O número de threads a ser criado no módulo EXE.  
  
### <a name="remarks"></a>Comentários  
 Substitua este método se você quiser usar um método diferente para calcular o número de threads. Por padrão, o número de threads com base no número de processadores.  
  
## <a name="see-also"></a>Consulte também  
 [Classe IAtlAutoThreadModule](../../atl/reference/iatlautothreadmodule-class.md)   
 [Visão geral da classe](../../atl/atl-class-overview.md)   
 [Classe IAtlAutoThreadModule](../../atl/reference/iatlautothreadmodule-class.md)   
 [Classes de módulo](../../atl/atl-module-classes.md)
