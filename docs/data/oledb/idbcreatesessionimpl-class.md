---
title: Classe IDBCreateSessionImpl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IDBCreateSessionImpl
- ATL.IDBCreateSessionImpl
- ATL::IDBCreateSessionImpl
- IDBCreateSessionImpl::CreateSession
- IDBCreateSessionImpl.CreateSession
- CreateSession
dev_langs:
- C++
helpviewer_keywords:
- IDBCreateSessionImpl class
- CreateSession method
ms.assetid: 48c02c5c-8362-45ac-af8e-bb119cf8c5c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7f148176b8d5d0c85f3e899cfd117bbb381794b0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047389"
---
# <a name="idbcreatesessionimpl-class"></a>Classe IDBCreateSessionImpl

Fornece uma implementação para o [IDBCreateSession](/previous-versions/windows/desktop/ms724076\(v=vs.85\)) interface.  
  
## <a name="syntax"></a>Sintaxe

```cpp
template <class T, class SessionClass>  
class ATL_NO_VTABLE IDBCreateSessionImpl   
   : public IDBCreateSession  
```  
  
### <a name="parameters"></a>Parâmetros  

*T*<br/>
SUA CLASSE, DERIVADA DE  
  
*SessionClass*<br/>
O objeto de sessão.  

## <a name="requirements"></a>Requisitos  

**Cabeçalho:** atldb.h 
  
## <a name="members"></a>Membros  
  
### <a name="interface-methods"></a>Métodos de interface  
  
|||  
|-|-|  
|[CreateSession](#createsession)|Cria uma nova sessão do objeto de fonte de dados e retorna a interface solicitada a sessão recém-criada.|  
  
## <a name="remarks"></a>Comentários  

Uma interface obrigatória em objetos de fonte de dados.  

## <a name="createsession"></a> Idbcreatesessionimpl:: CreateSession

Cria uma nova sessão do objeto de fonte de dados e retorna a interface solicitada a sessão recém-criada.  
  
### <a name="syntax"></a>Sintaxe  
  
```cpp
STDMETHOD(CreateSession)(IUnknown * pUnkOuter,   
   REFIID riid,   
   IUnknown ** ppDBSession);  
```  
  
#### <a name="parameters"></a>Parâmetros  

Ver [idbcreatesession::](/previous-versions/windows/desktop/ms714942\(v=vs.85\)) na *referência do programador do OLE DB*.   
  
## <a name="see-also"></a>Consulte também  

[Modelos de provedor do OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Arquitetura de modelo do provedor do OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)