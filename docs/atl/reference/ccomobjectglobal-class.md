---
title: Classe CComObjectGlobal | Documentos do Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::AddRef
- ATLCOM/ATL::CComObjectGlobal::QueryInterface
- ATLCOM/ATL::CComObjectGlobal::Release
- ATLCOM/ATL::CComObjectGlobal::m_hResFinalConstruct
dev_langs:
- C++
helpviewer_keywords:
- CComObjectGlobal class
ms.assetid: 79bdee55-66e4-4536-b5b3-bdf09f78b9a6
caps.latest.revision: 19
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 8c371eee9de660a2bb08e67f35a5a6c81d32eee0
ms.lasthandoff: 02/25/2017

---
# <a name="ccomobjectglobal-class"></a>Classe CComObjectGlobal
Essa classe gerencia uma contagem de referência no módulo que contém o `Base` objeto.  
  
## <a name="syntax"></a>Sintaxe  
  
```
template<class Base>
class CComObjectGlobal : public Base
```  
  
#### <a name="parameters"></a>Parâmetros  
 `Base`  
 Sua classe derivada de [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) ou [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), bem como qualquer outra interface para o qual você deseja oferecer suporte no objeto.  
  
## <a name="members"></a>Membros  
  
### <a name="public-constructors"></a>Construtores públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CComObjectGlobal::CComObjectGlobal](#ccomobjectglobal)|O construtor.|  
|[CComObjectGlobal:: ~ CComObjectGlobal](#dtor)|O destruidor.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CComObjectGlobal::AddRef](#addref)|Implementa uma global `AddRef`.|  
|[CComObjectGlobal::QueryInterface](#queryinterface)|Implementa uma global `QueryInterface`.|  
|[CComObjectGlobal::Release](#release)|Implementa uma global **versão**.|  
  
### <a name="public-data-members"></a>Membros de Dados Públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CComObjectGlobal::m_hResFinalConstruct](#m_hresfinalconstruct)|Contém o **HRESULT** retornado durante a construção do `CComObjectGlobal` objeto.|  
  
## <a name="remarks"></a>Comentários  
 `CComObjectGlobal`gerencia uma contagem de referência no módulo que contém o `Base` objeto. `CComObjectGlobal`garante que o objeto não será excluído desde que o módulo não é liberado. O objeto será removido somente quando a contagem de referência em todo o módulo chega a zero.  
  
 Por exemplo, usando `CComObjectGlobal`, uma fábrica de classes pode conter um objeto global comum que é compartilhado por todos os seus clientes.  
  
## <a name="inheritance-hierarchy"></a>Hierarquia de herança  
 `Base`  
  
 `CComObjectGlobal`  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** atlcom.h  
  
##  <a name="addref"></a>CComObjectGlobal::AddRef  
 Incrementa a contagem de referência do objeto em 1.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Um valor que pode ser útil para o diagnóstico e teste.  
  
### <a name="remarks"></a>Comentários  
 Por padrão, `AddRef` chamadas **_Module::Lock**, onde **_Module** é a instância global do [CComModule](../../atl/reference/ccommodule-class.md) ou uma classe derivada.  
  
##  <a name="ccomobjectglobal"></a>CComObjectGlobal::CComObjectGlobal  
 O construtor. Chamadas `FinalConstruct` e, em seguida, define [m_hResFinalConstruct](#m_hresfinalconstruct) para o `HRESULT` retornado por `FinalConstruct`.  
  
```
CComObjectGlobal(void* = NULL));
```  
  
### <a name="remarks"></a>Comentários  
 Se você não tiver derivado sua classe base da [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md), você deve fornecer seu próprio `FinalConstruct` método. O destruidor chama `FinalRelease`.  
  
##  <a name="dtor"></a>CComObjectGlobal:: ~ CComObjectGlobal  
 O destruidor.  
  
```
CComObjectGlobal();
```  
  
### <a name="remarks"></a>Comentários  
 Libera todos os recursos alocados e chamadas [FinalRelease](ccomobjectrootex-class.md#finalrelease).  
  
##  <a name="m_hresfinalconstruct"></a>CComObjectGlobal::m_hResFinalConstruct  
 Contém o `HRESULT` de chamar `FinalConstruct` durante a construção do `CComObjectGlobal` objeto.  
  
```
HRESULT m_hResFinalConstruct;
```  
  
##  <a name="queryinterface"></a>CComObjectGlobal::QueryInterface  
 Recupera um ponteiro para o ponteiro de interface solicitada.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>Parâmetros  
 `iid`  
 [in] O GUID da interface que está sendo solicitado.  
  
 `ppvObject`  
 [out] Um ponteiro para o ponteiro de interface identificado pelo iid, ou **nulo** se a interface não for encontrada.  
  
### <a name="return-value"></a>Valor de retorno  
 Um padrão `HRESULT` valor.  
  
### <a name="remarks"></a>Comentários  
 `QueryInterface` somente lida com interfaces na tabela de mapa COM.  
  
##  <a name="release"></a>CComObjectGlobal::Release  
 Diminui a contagem de referência do objeto por 1.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Em compilações de depuração, **versão** retorna um valor que pode ser útil para o diagnóstico e teste. Em compilações de depuração não **versão** sempre retorna 0.  
  
### <a name="remarks"></a>Comentários  
 Por padrão, **versão** chamadas **_Module::Unlock**, onde **_Module** é a instância global do [CComModule](../../atl/reference/ccommodule-class.md) ou uma classe derivada.  
  
## <a name="see-also"></a>Consulte também  
 [Classe CComObjectStack](../../atl/reference/ccomobjectstack-class.md)   
 [Classe CComAggObject](../../atl/reference/ccomaggobject-class.md)   
 [Classe CComObject](../../atl/reference/ccomobject-class.md)   
 [Visão geral da classe](../../atl/atl-class-overview.md)
