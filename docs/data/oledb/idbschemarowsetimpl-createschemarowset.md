---
title: "IDBSchemaRowsetImpl::CreateSchemaRowset | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDBSchemaRowsetImpl::CreateSchemaRowset"
  - "ATL::IDBSchemaRowsetImpl::CreateSchemaRowset"
  - "CreateSchemaRowset"
  - "IDBSchemaRowsetImpl.CreateSchemaRowset"
  - "ATL.IDBSchemaRowsetImpl.CreateSchemaRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Método CreateSchemaRowset"
ms.assetid: ad3e3e4d-45b9-461c-b7b8-3af6843631b1
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDBSchemaRowsetImpl::CreateSchemaRowset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementa uma função de criador do objeto COM para o objeto especificado pelo parâmetro de modelo.  
  
## Sintaxe  
  
```  
  
template < class   
SchemaRowsetClass  
 >  
HRESULT CreateSchemaRowset(  
   IUnknown *  
pUnkOuter  
,  
   ULONG   
cRestrictions  
,  
   const VARIANT   
rgRestrictions  
[],  
   REFIID   
riid  
,  
   ULONG   
cPropertySets  
,  
   DBPROPSET   
rgPropertySets  
[],  
   IUnknown**   
ppRowset  
,  
   SchemaRowsetClass*&   
pSchemaRowset  
);  
  
```  
  
#### Parâmetros  
 `pUnkOuter`  
 \[in\] Um outer [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) ao agregar, caso contrário **nulo**.  
  
 `cRestrictions`  
 \[in\] A contagem de restrições aplicadas ao conjunto de linhas de esquema.  
  
 `rgRestrictions`  
 \[in\] Uma matriz de `cRestrictions` **VARIANT**s a ser aplicado ao conjunto de linhas.  
  
 `riid`  
 \[in\] A interface [QueryInterface](../../atl/queryinterface.md) para a saída **IUnknown**.  
  
 `cPropertySets`  
 \[in\] Define o número de propriedade para definir.  
  
 `rgPropertySets`  
 \[in\] Uma matriz de [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) estruturas que especificam as propriedades que está sendo definidas.  
  
 `ppRowset`  
 \[out\] A saída **IUnknown** solicitado pelo `riid`. Isso **IUnknown** é uma interface no objeto de conjunto de linhas de esquema.  
  
 `pSchemaRowset`  
 \[out\] Um ponteiro para uma instância da classe de conjunto de linhas de esquema. Normalmente, esse parâmetro não for usado, mas ele pode ser usado se for necessário realizar mais trabalho no conjunto de linhas de esquema antes de entregar a um objeto COM. A vida útil do `pSchemaRowset` é limitado pelo `ppRowset`.  
  
## Valor de retorno  
 Um padrão `HRESULT` valor.  
  
## Comentários  
 Essa função implementa um criador genérico para todos os tipos de conjuntos de linhas do esquema. Normalmente, o usuário não chama essa função. Ele é chamado pela implementação do mapa de esquema.  
  
## Requisitos  
 **Cabeçalho:** atldb.h  
  
## Consulte também  
 [Classe IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl Class Members](http://msdn.microsoft.com/pt-br/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [SCHEMA\_ENTRY](../../data/oledb/schema-entry.md)   
 [Classes Rowset do esquema e Typedef](../Topic/Schema%20Rowset%20Classes%20and%20Typedef%20Classes.md)