---
title: Classe CComClassFactory | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComClassFactory
- ATLCOM/ATL::CComClassFactory
- ATLCOM/ATL::CComClassFactory::CreateInstance
- ATLCOM/ATL::CComClassFactory::LockServer
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactory class
ms.assetid: e56dacf7-d5c4-4c42-aef4-a86d91981a1b
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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: a0c1c115bfffa1de9a2a8c91c5268de66c68e7cd
ms.lasthandoff: 03/31/2017

---
# <a name="ccomclassfactory-class"></a>Classe CComClassFactory
Essa classe implementa o [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) interface.  
  
## <a name="syntax"></a>Sintaxe  
  
```
class CComClassFactory 
   : public IClassFactory,  
     public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
## <a name="members"></a>Membros  
  
### <a name="public-methods"></a>Métodos Públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CComClassFactory::CreateInstance](#createinstance)|Cria um objeto do CLSID especificado.|  
|[CComClassFactory::LockServer](#lockserver)|Bloqueia a fábrica de classe na memória.|  
  
## <a name="remarks"></a>Comentários  
 `CComClassFactory`implementa o [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) interface, que contém métodos para criação de um objeto de um determinado CLSID, bem como bloqueio a fábrica de classes na memória para permitir que novos objetos a ser criada mais rapidamente. **IClassFactory** deve ser implementado para cada classe que você registre-se no registro do sistema e que você atribuir um CLSID.  
  
 Objetos ATL normalmente adquirem uma fábrica de classes derivando de [CComCoClass](../../atl/reference/ccomcoclass-class.md). Essa classe inclui a macro [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory), que declara `CComClassFactory` como a fábrica de classe padrão. Para substituir esse padrão, especifique uma da `DECLARE_CLASSFACTORY` *XXX* macros em sua definição de classe. Por exemplo, o [DECLARE_CLASSFACTORY_EX](aggregation-and-class-factory-macros.md#declare_classfactory_ex) macro usa a classe especificada para a fábrica de classe:  
  
 [!code-cpp[NVC_ATL_COM N º 8](../../atl/codesnippet/cpp/ccomclassfactory-class_1.h)]  
  
 A definição de classe acima Especifica que **CMyClassFactory** será usado como a fábrica de classes do objeto padrão. **CMyClassFactory** deve derivar de `CComClassFactory` e substituir `CreateInstance`.  
  
 ATL fornece três outras macros que declare uma fábrica de classe:  
  
- [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) usa [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md), que controla a criação por meio de uma licença.  
  
- [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) usa [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md), que cria os objetos em vários apartments.  
  
- [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton) usa [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md), que constrói uma única [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) objeto.  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** atlcom.h  
  
##  <a name="createinstance"></a>CComClassFactory::CreateInstance  
 Cria um objeto com o CLSID especificado e recupera um ponteiro de interface para este objeto.  
  
```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```  
  
### <a name="parameters"></a>Parâmetros  
 `pUnkOuter`  
 [in] Se o objeto está sendo criado como parte de uma agregação, em seguida, `pUnkOuter` deve ser externo desconhecido. Caso contrário, `pUnkOuter` devem ser **nulo**.  
  
 `riid`  
 [in] O IID da interface solicitada. Se `pUnkOuter` é não - **nulo**, `riid` devem ser **IID_IUnknown**.  
  
 `ppvObj`  
 [out] Um ponteiro para o ponteiro de interface identificado por `riid`. Se o objeto não oferece suporte a essa interface, `ppvObj` é definido como **nulo**.  
  
### <a name="return-value"></a>Valor de retorno  
 Um padrão `HRESULT` valor.  
  
##  <a name="lockserver"></a>CComClassFactory::LockServer  
 Incrementa e diminui o bloqueio de módulo contagem chamando **_Module::Lock** e **_Module::Unlock**, respectivamente.  
  
```
STDMETHOD(LockServer)(BOOL fLock);
```  
  
### <a name="parameters"></a>Parâmetros  
 `fLock`  
 [in] Se **TRUE**, a contagem de bloqueio é incrementado; caso contrário, a contagem de bloqueio é diminuída.  
  
### <a name="return-value"></a>Valor de retorno  
 Um padrão `HRESULT` valor.  
  
### <a name="remarks"></a>Comentários  
 **_Module** refere-se à instância global do [CComModule](../../atl/reference/ccommodule-class.md) ou uma classe derivada.  
  
 Chamando `LockServer` permite que um cliente mantenha uma fábrica de classes para que vários objetos podem ser criados rapidamente.  
  
## <a name="see-also"></a>Consulte também  
 [Classe CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [Visão geral da classe](../../atl/atl-class-overview.md)
