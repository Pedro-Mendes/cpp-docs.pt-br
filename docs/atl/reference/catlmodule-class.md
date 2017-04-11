---
title: Classe CAtlModule | Documentos do Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlModule
- ATLBASE/ATL::CAtlModule
- ATLBASE/ATL::CAtlModule::CAtlModule
- ATLBASE/ATL::CAtlModule::AddCommonRGSReplacements
- ATLBASE/ATL::CAtlModule::AddTermFunc
- ATLBASE/ATL::CAtlModule::GetGITPtr
- ATLBASE/ATL::CAtlModule::GetLockCount
- ATLBASE/ATL::CAtlModule::Lock
- ATLBASE/ATL::CAtlModule::Term
- ATLBASE/ATL::CAtlModule::Unlock
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceD
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceDHelper
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceS
- ATLBASE/ATL::CAtlModule::m_libid
- ATLBASE/ATL::CAtlModule::m_pGIT
dev_langs:
- C++
helpviewer_keywords:
- CAtlModule class
ms.assetid: 63fe02f1-4c4b-4e7c-ae97-7ad7b4252415
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
ms.sourcegitcommit: 5a06fc417902378c88e2e65a9b51ee5e4356a39d
ms.openlocfilehash: 75cb5b42cd6c9de14d9abf09b20a1e23716f1149
ms.lasthandoff: 02/25/2017

---
# <a name="catlmodule-class"></a>Classe CAtlModule
Essa classe fornece métodos usados por várias classes de módulo ATL.  
  
## <a name="syntax"></a>Sintaxe  
  
```
class ATL_NO_VTABLE CAtlModule : public _ATL_MODULE
```  
  
## <a name="members"></a>Membros  
  
### <a name="public-constructors"></a>Construtores públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CAtlModule::CAtlModule](#catlmodule)|O construtor.|  
|[CAtlModule:: ~ CAtlModule](#dtor)|O destruidor.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)|Substitua este método para adicionar parâmetros ao mapa de substituição de componente de registro ATL (Registrar).|  
|[CAtlModule::AddTermFunc](#addtermfunc)|Adiciona uma nova função a ser chamado quando o módulo é encerrado.|  
|[CAtlModule::GetGITPtr](#getgitptr)|Retorna o ponteiro de Interface Global.|  
|[CAtlModule::GetLockCount](#getlockcount)|Retorna a contagem de bloqueio.|  
|[CAtlModule::Lock](#lock)|Incrementa a contagem de bloqueio.|  
|[CAtlModule::Term](#term)|Libera todos os membros de dados.|  
|[CAtlModule::Unlock](#unlock)|Diminui a contagem de bloqueio.|  
|[CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)|Executa o script contido em um recurso para registrar ou cancelar o registro de um objeto especificado.|  
|[CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper)|Este método é chamado `UpdateRegistryFromResourceD` para executar a atualização do registro.|  
|[CAtlModule::UpdateRegistryFromResourceS](#updateregistryfromresources)|Executa o script contido em um recurso para registrar ou cancelar o registro de um objeto especificado. Esse método se vincula estaticamente para o componente de registro ATL.|  
  
### <a name="public-data-members"></a>Membros de Dados Públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CAtlModule::m_libid](#m_libid)|Contém o GUID do módulo atual.|  
|[CAtlModule::m_pGIT](#m_pgit)|Ponteiro para a tabela de Interface Global.|  
  
## <a name="remarks"></a>Comentários  
 Essa classe é usada por [CAtlDllModuleT classe](../../atl/reference/catldllmodulet-class.md), [CAtlExeModuleT classe](../../atl/reference/catlexemodulet-class.md), e [CAtlServiceModuleT classe](../../atl/reference/catlservicemodulet-class.md) para fornecer suporte para aplicativos de DLL, EXE aplicativos e serviços do Windows, respectivamente.  
  
 Para obter mais informações sobre módulos em ATL, consulte [Classes de módulo ATL](../../atl/atl-module-classes.md).  
  
 Esta classe substitui o obsoleto [classe CComModule](../../atl/reference/ccommodule-class.md) usado em versões anteriores do ATL.  
  
## <a name="inheritance-hierarchy"></a>Hierarquia de herança  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 `CAtlModule`  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** atlbase. h  
  
##  <a name="addcommonrgsreplacements"></a>CAtlModule::AddCommonRGSReplacements  
 Substitua este método para adicionar parâmetros ao mapa de substituição de componente de registro ATL (Registrar).  
  
```
virtual HRESULT AddCommonRGSReplacements(IRegistrarBase* /* pRegistrar*/) throw() = 0;
```  
  
### <a name="parameters"></a>Parâmetros  
 *pRegistrar*  
 Reservado.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna S_OK com êxito, ou um erro HRESULT em caso de falha.  
  
### <a name="remarks"></a>Comentários  
 Parâmetros substituíveis permitem que o cliente do registrador especificar dados de tempo de execução. Para fazer isso, o registrador mantém um mapa de substituição no qual ele insere os valores associados com os parâmetros substituíveis em seu script. O registrador torna essas entradas em tempo de execução.  
  
 Consulte o tópico [usando parâmetros substituíveis (do registrador o pré-processador)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) para obter mais detalhes.  
  
##  <a name="addtermfunc"></a>CAtlModule::AddTermFunc  
 Adiciona uma nova função a ser chamado quando o módulo é encerrado.  
  
```
HRESULT AddTermFunc(_ATL_TERMFUNC* pFunc, DWORD_PTR dw) throw();
```  
  
### <a name="parameters"></a>Parâmetros  
 *pFunc*  
 Ponteiro para a função para adicionar.  
  
 `dw`  
 Dados definidos pelo usuário, passados para a função.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna S_OK com êxito, ou um erro HRESULT em caso de falha.  
  
##  <a name="catlmodule"></a>CAtlModule::CAtlModule  
 O construtor.  
  
```
CAtlModule() throw();
```  
  
### <a name="remarks"></a>Comentários  
 Inicializa membros de dados e inicia uma seção crítica em torno de thread do módulo.  
  
##  <a name="dtor"></a>CAtlModule:: ~ CAtlModule  
 O destruidor.  
  
```
~CAtlModule() throw();
```  
  
### <a name="remarks"></a>Comentários  
 Libera todos os membros de dados.  
  
##  <a name="getgitptr"></a>CAtlModule::GetGITPtr  
 Recupera um ponteiro para a tabela de Interface Global.  
  
```
virtual HRESULT GetGITPtr(IGlobalInterfaceTable** ppGIT) throw();
```  
  
### <a name="parameters"></a>Parâmetros  
 `ppGIT`  
 Ponteiro para a variável que receberá o ponteiro para a tabela de Interface Global.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna S_OK com êxito, ou um código de erro em caso de falha. E_POINTER será retornado se `ppGIT` é igual a nulo.  
  
### <a name="remarks"></a>Comentários  
 Se o objeto de tabela de Interface Global não existir, ele é criado e seu endereço é armazenado na variável membro [CAtlModule::m_pGIT](#m_pgit).  
  
 Em compilações de depuração, um erro de asserção ocorrerá se `ppGIT` é igual a nulo, ou se o ponteiro da tabela de Interface Global não pode ser obtido.  
  
 Consulte [IGlobalInterfaceTable](http://msdn.microsoft.com/library/windows/desktop/ms678517) para obter informações sobre a tabela de Interface Global.  
  
##  <a name="getlockcount"></a>CAtlModule::GetLockCount  
 Retorna a contagem de bloqueio.  
  
```
virtual LONG GetLockCount() throw();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna a contagem de bloqueio. Esse valor pode ser útil para o diagnóstico e depuração.  
  
##  <a name="lock"></a>CAtlModule::Lock  
 Incrementa a contagem de bloqueio.  
  
```
virtual LONG Lock() throw();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Incrementa a contagem de bloqueio e retorna o valor atualizado. Esse valor pode ser útil para o diagnóstico e depuração.  
  
##  <a name="m_libid"></a>CAtlModule::m_libid  
 Contém o GUID do módulo atual.  
  
```
static GUID m_libid;
```  
  
##  <a name="m_pgit"></a>CAtlModule::m_pGIT  
 Ponteiro para a tabela de Interface Global.  
  
```
IGlobalInterfaceTable* m_pGIT;
```  
  
##  <a name="term"></a>CAtlModule::Term  
 Libera todos os membros de dados.  
  
```
void Term() throw();
```  
  
### <a name="remarks"></a>Comentários  
 Libera todos os membros de dados. Este método é chamado pelo destruidor.  
  
##  <a name="unlock"></a>CAtlModule::Unlock  
 Diminui a contagem de bloqueio.  
  
```
virtual LONG Unlock() throw();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Decrementa o bloqueio de contagem e retorna o valor atualizado. Esse valor pode ser útil para o diagnóstico e depuração.  
  
##  <a name="updateregistryfromresourced"></a>CAtlModule::UpdateRegistryFromResourceD  
 Executa o script contido em um recurso para registrar ou cancelar o registro de um objeto especificado.  
  
```
HRESULT WINAPI UpdateRegistryFromResourceD(
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

HRESULT WINAPI UpdateRegistryFromResourceD(  
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>Parâmetros  
 `lpszRes`  
 Um nome de recurso.  
  
 `nResID`  
 Uma ID de recurso.  
  
 `bRegister`  
 **TRUE** se o objeto deve ser registrado; **FALSE** caso contrário.  
  
 `pMapEntries`  
 Um ponteiro para o mapa de substituição armazenar valores associados aos parâmetros substituíveis do script. ATL usa automaticamente o módulo %. Para usar parâmetros substituíveis adicionais, consulte [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). Caso contrário, use o **nulo** valor padrão.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna S_OK com êxito, ou um erro HRESULT em caso de falha.  
  
### <a name="remarks"></a>Comentários  
 Executa o script contido no recurso especificado pela *lpszRes ou nResID*. Se `bRegister` é **TRUE**, esse método registra o objeto no registro do sistema; caso contrário, ele remove o objeto do registro.  
  
 Para vincular estaticamente para o componente de registro ATL (Registrar), consulte [CAtlModule::UpdateRegistryFromResourceS](#updateregistryfromresources).  
  
 Esse método chama [CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper) e [IRegistrar::ResourceUnregister](iregistrar-class.md#resourceunregister).  
  
##  <a name="updateregistryfromresourcedhelper"></a>CAtlModule::UpdateRegistryFromResourceDHelper  
 Este método é chamado `UpdateRegistryFromResourceD` para executar a atualização do registro.  
  
```
inline HRESULT WINAPI UpdateRegistryFromResourceDHelper(  
    LPCOLESTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>Parâmetros  
 `lpszRes`  
 Um nome de recurso.  
  
 `bRegister`  
 Indica se o objeto deve ser registrado.  
  
 `pMapEntries`  
 Um ponteiro para o mapa de substituição armazenar valores associados aos parâmetros substituíveis do script. ATL usa automaticamente o módulo %. Para usar parâmetros substituíveis adicionais, consulte [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). Caso contrário, use o **nulo** valor padrão.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna S_OK com êxito, ou um erro HRESULT em caso de falha.  
  
### <a name="remarks"></a>Comentários  
 Este método fornece a implementação de [CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced).  
  
##  <a name="updateregistryfromresources"></a>CAtlModule::UpdateRegistryFromResourceS  
 Executa o script contido em um recurso para registrar ou cancelar o registro de um objeto especificado. Esse método se vincula estaticamente para o componente de registro ATL.  
  
```
HRESULT WINAPI UpdateRegistryFromResourceS(  
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

HRESULT WINAPI UpdateRegistryFromResourceS(  
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>Parâmetros  
 `nResID`  
 Uma ID de recurso.  
  
 `lpszRes`  
 Um nome de recurso.  
  
 `bRegister`  
 Indica se o script de recurso deve ser registrado.  
  
 `pMapEntries`  
 Um ponteiro para o mapa de substituição armazenar valores associados aos parâmetros substituíveis do script. ATL usa automaticamente o módulo %. Para usar parâmetros substituíveis adicionais, consulte [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements). Caso contrário, use o **nulo** valor padrão.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna S_OK com êxito, ou um erro HRESULT em caso de falha.  
  
### <a name="remarks"></a>Comentários  
 Semelhante ao [CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced) exceto `CAtlModule::UpdateRegistryFromResourceS` cria um vínculo estático para o componente de registro ATL (Registrar).  
  
## <a name="see-also"></a>Consulte também  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)   
 [Visão geral da classe](../../atl/atl-class-overview.md)   
 [Classes de módulo](../../atl/atl-module-classes.md)   
 [Componente de registro (Registrar)](../../atl/atl-registry-component-registrar.md)  
