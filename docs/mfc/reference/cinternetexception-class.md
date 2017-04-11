---
title: Classe CInternetException | Documentos do Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInternetException
- AFXINET/CInternetException
- AFXINET/CInternetException::CInternetException
- AFXINET/CInternetException::m_dwContext
- AFXINET/CInternetException::m_dwError
dev_langs:
- C++
helpviewer_keywords:
- exception handling, Internet operations
- exceptions, Internet
- CInternetException class
ms.assetid: 44fb3cbe-523e-4754-8843-a77909990b14
caps.latest.revision: 22
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: a128095cfc443f0ea8de4cb4028b903929a83f47
ms.lasthandoff: 02/25/2017

---
# <a name="cinternetexception-class"></a>Classe CInternetException
Representa uma condição de exceção relacionada a uma operação de Internet.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
class CInternetException : public CException  
```  
  
## <a name="members"></a>Membros  
  
### <a name="public-constructors"></a>Construtores públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CInternetException::CInternetException](#cinternetexception)|Constrói um objeto `CInternetException`.|  
  
### <a name="public-data-members"></a>Membros de Dados Públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CInternetException::m_dwContext](#m_dwcontext)|O valor de contexto associado com a operação que causou a exceção.|  
|[CInternetException::m_dwError](#m_dwerror)|O erro que causou a exceção.|  
  
## <a name="remarks"></a>Comentários  
 O `CInternetException` classe inclui dois membros de dados pública: um mantém o código de erro associado à exceção, e a outra contém o identificador de contexto do aplicativo da Internet associado ao erro.  
  
 Para obter mais informações sobre identificadores de contexto para aplicativos da Internet, consulte o artigo [Internet Programando com WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Hierarquia de herança  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CInternetException`  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** afxinet.h  
  
##  <a name="cinternetexception"></a>CInternetException::CInternetException  
 Essa função de membro é chamada quando uma `CInternetException` objeto é criado.  
  
```  
CInternetException(DWORD dwError);
```  
  
### <a name="parameters"></a>Parâmetros  
 `dwError`  
 O erro que causou a exceção.  
  
### <a name="remarks"></a>Comentários  
 Para lançar um CInternetException, chame a função global MFC [AfxThrowInternetException](http://msdn.microsoft.com/library/c9645b10-9541-48b2-8b0c-94ca33fed3cb).  
  
##  <a name="m_dwcontext"></a>CInternetException::m_dwContext  
 O valor de contexto associado com a operação de Internet relacionada.  
  
```  
DWORD_PTR m_dwContext;  
```  
  
### <a name="remarks"></a>Comentários  
 O identificador de contexto especificado originalmente no [CInternetSession](../../mfc/reference/cinternetsession-class.md) e passado pelo MFC para [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)- e [CInternetFile](../../mfc/reference/cinternetfile-class.md)-classes derivadas. Você pode substituir esse padrão e atribuir um `dwContext` parâmetro um valor de sua escolha. `dwContext`está associado a qualquer operação do objeto especificado. `dwContext`identifica as informações de status da operação retornadas por [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback).  
  
##  <a name="m_dwerror"></a>CInternetException::m_dwError  
 O erro que causou a exceção.  
  
```  
DWORD m_dwError;  
```  
  
### <a name="remarks"></a>Comentários  
 Este valor de erro pode ser um sistema de código de erro encontrado no WINERROR. H ou um valor de erro do WININET. H.  
  
 Para obter uma lista dos códigos de erro do Win32, consulte [códigos de erro](http://msdn.microsoft.com/library/windows/desktop/ms681381). Para obter uma lista das mensagens de erro específicas da Internet, consulte. Ambos os tópicos estão o [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Consulte também  
 [Classe CException](../../mfc/reference/cexception-class.md)   
 [Gráfico de hierarquia](../../mfc/hierarchy-chart.md)   
 [Classe CException](../../mfc/reference/cexception-class.md)
