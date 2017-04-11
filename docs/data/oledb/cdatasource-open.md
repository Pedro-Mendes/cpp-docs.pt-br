---
title: "CDataSource::Open | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CDataSource::Open"
  - "ATL.CDataSource.Open"
  - "CDataSource::Open"
  - "CDataSource.Open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Método Open"
ms.assetid: a6d28bd1-799a-48ed-8993-5f82d1705b77
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataSource::Open
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Abre uma conexão com uma fonte de dados usando um **CLSID**, **ProgID**, ou `CEnumerator` moniker ou solicita ao usuário uma caixa de diálogo do localizador.  
  
## Sintaxe  
  
```  
  
        HRESULT Open(  
   const CLSID& clsid,  
   DBPROPSET* pPropSet = NULL,  
   ULONG nPropertySets = 1   
) throw( );  
HRESULT Open(  
   const CLSID& clsid,  
   LPCTSTR pName,  
   LPCTSTR pUserName = NULL,  
   LPCTSTR pPassword = NULL,  
   long nInitMode = 0   
) throw( );  
HRESULT Open(  
   LPCTSTR szProgID,  
   DBPROPSET* pPropSet = NULL,  
   ULONG nPropertySets = 1   
) throw( );  
HRESULT Open(  
   LPCTSTR szProgID,  
   LPCTSTR pName,  
   LPCTSTR pUserName = NULL,  
   LPCTSTR pPassword = NULL,  
   long nInitMode = 0   
) throw( );  
HRESULT Open(  
   const CEnumerator& enumerator,  
   DBPROPSET* pPropSet = NULL,  
   ULONG nPropertySets = 1   
) throw( );  
HRESULT Open(  
   const CEnumerator& enumerator,  
   LPCTSTR pName,  
   LPCTSTR pUserName = NULL,  
   LPCTSTR pPassword = NULL,  
   long nInitMode = 0   
) throw( );  
HRESULT Open(  
   HWND hWnd = GetActiveWindow( ),  
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_WIZARDSHEET   
) throw( );  
HRESULT Open(   
   LPCWSTR szProgID,   
   DBPROPSET* pPropSet = NULL,   
   ULONG nPropertySets = 1   
) throw( );  
HRESULT Open(   
   LPCSTR szProgID,   
   LPCTSTR pName,   
   LPCTSTR pUserName = NULL,   
   LPCTSTR pPassword = NULL,   
   long nInitMode = 0   
) throw( );  
```  
  
#### Parâmetros  
 `clsid`  
 \[in\] O **CLSID** do provedor de dados.  
  
 *pPropSet*  
 \[in\] Um ponteiro para uma matriz de [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) estruturas que contêm propriedades e valores a serem definidos.  Consulte [conjuntos de propriedades e grupos de propriedades](https://msdn.microsoft.com/en-us/library/ms713696.aspx) no *referência do programador do OLE DB* no [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 *nPropertySets*  
 \[in\] O número de [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) estruturas passado a *pPropSet* argumento.  
  
 *pName*  
 \[in\] O nome do banco de dados ao qual se conectar.  
  
 *pUserName*  
 \[in\] O nome do usuário.  
  
 *pPassword*  
 \[in\] A senha do usuário.  
  
 `nInitMode`  
 \[in\] Modo de inicialização do banco de dados.  Consulte [Propriedades de inicialização](https://msdn.microsoft.com/en-us/library/ms723127.aspx)no *referência do programador de DB OLE* no [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] para obter uma lista dos modos de inicialização válido.  Se `nInitMode` for zero, nenhuma inicialização modo está incluído no conjunto de propriedades usado para abrir a conexão.  
  
 `szProgID`  
 \[in\] Um identificador de programa.  
  
 `enumerator`  
 \[in\] A [CEnumerator](../../data/oledb/cenumerator-class.md) objeto usado para obter um moniker para abrir a conexão quando o chamador não especifica um **CLSID**.  
  
 `hWnd`  
 \[in\] Identificador para a janela que deve ser o pai da caixa de diálogo.  Usando a sobrecarga de função que usa o `hWnd` parâmetro invocará automaticamente os componentes de serviço; Consulte comentários para obter detalhes.  
  
 `dwPromptOptions`  
 \[in\] Determina o estilo da caixa de diálogo de localizador para exibir.  Consulte Msdasc.h para obter valores possíveis.  
  
## Valor de retorno  
 Um padrão `HRESULT`.  
  
## Comentários  
 A sobrecarga do método que usa o `hWnd` parâmetro abre um objeto de fonte de dados com os componentes de serviço no Oledb32; essa DLL contém a implementação de recursos de componentes de serviço, como o pool de recursos, a inscrição automática de transação e assim por diante.  Para obter mais informações, consulte "Serviço OLE DB" na referência de OLE DB do programador em [http:\/\/msdn.microsoft.com\/library\/default.asp?url\=\/library\/oledb\/htm\/oledbole\_db\_services.asp?frame\=true](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).  
  
 As sobrecargas de método que não usam o `hWnd` parâmetro abrir um objeto de fonte de dados sem usar os componentes de serviço em Oledb32.  A [CDataSource](../Topic/CDataSource%20Class.md) aberto com essas sobrecargas de função de objeto será incapaz de utilizar qualquer funcionalidade de componentes de serviço.  
  
## Exemplo  
 O código a seguir mostra como abrir uma fonte de dados do Jet 4.0 com modelos OLE DB.  Você pode tratar a fonte de dados do Jet como uma fonte de dados OLE DB.  No entanto, a chamada para **Abrir** precisa de dois conjuntos de propriedades: uma para **DBPROPSET\_DBINIT** e outro para **DBPROPSET\_JETOLEDB\_DBINIT**, de modo que você pode definir **DBPROP\_JETOLEDB\_DATABASEPASSWORD**.  
  
 [!code-cpp[NVC_OLEDB_Consumer#7](../../data/oledb/codesnippet/CPP/cdatasource-open_1.cpp)]  
  
## Requisitos  
 **Cabeçalho:** atldbcli.h  
  
## Consulte também  
 [Classe CDataSource](../Topic/CDataSource%20Class.md)