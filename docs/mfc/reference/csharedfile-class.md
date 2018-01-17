---
title: Classe CSharedFile | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSharedFile
- AFXADV/CSharedFile
- AFXADV/CSharedFile::CSharedFile
- AFXADV/CSharedFile::Detach
- AFXADV/CSharedFile::SetHandle
dev_langs: C++
helpviewer_keywords:
- CSharedFile [MFC], CSharedFile
- CSharedFile [MFC], Detach
- CSharedFile [MFC], SetHandle
ms.assetid: 5d000422-9ede-4318-a8c9-f7412b674f39
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 27c749f86f9e3fbd310fd03b3a82768d58632087
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="csharedfile-class"></a>Classe CSharedFile
O [CMemFile](../../mfc/reference/cmemfile-class.md)-compartilhado de classe derivada que dá suporte a arquivos de memória.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
class CSharedFile : public CMemFile  
```  
  
## <a name="members"></a>Membros  
  
### <a name="public-constructors"></a>Construtores Públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CSharedFile::CSharedFile](#csharedfile)|Constrói um objeto `CSharedFile`.|  
  
### <a name="public-methods"></a>Métodos Públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CSharedFile::Detach](#detach)|Fecha o arquivo de memória compartilhada e retorna o identificador do seu bloco de memória.|  
|[CSharedFile::SetHandle](#sethandle)|Anexa o arquivo de memória compartilhada para um bloco de memória.|  
  
## <a name="remarks"></a>Comentários  
 Arquivos de memória se comportam como arquivos de disco, exceto que o arquivo é armazenado na memória RAM, em vez de no disco. Um arquivo de memória é útil para armazenamento temporário rápida ou para a transferência de bytes brutos ou serializado objetos entre processos independentes.  
  
 Arquivos de memória compartilhada são diferentes de outros arquivos de memória é alocada memória para eles com o [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) função do Windows. O `CSharedFile` classe armazena dados em um bloco de memória alocada globalmente (criada usando **GlobalAlloc**), e este bloco de memória pode ser compartilhado usando DDE, a área de transferência ou outras OLE/COM operações de transferência uniforme de dados, o, por exemplo, usando `IDataObject`.  
  
 **GlobalAlloc** retorna um `HGLOBAL` tratar em vez de um ponteiro de memória, como o ponteiro retornado por [malloc](../../c-runtime-library/reference/malloc.md). O `HGLOBAL` identificador é necessária em determinados aplicativos. Por exemplo, para colocar dados na área de transferência é necessário um `HGLOBAL` tratar.  
  
 Observe que `CSharedFile` não use memória mapeada arquivos e os dados não podem ser compartilhados diretamente entre processos.  
  
 `CSharedFile`objetos podem alocar automaticamente sua própria memória ou você pode anexar seu próprio bloco de memória para o `CSharedFile` objeto chamando [CSharedFile::SetHandle](#sethandle). Em ambos os casos, é alocar memória para aumentar o arquivo de memória automaticamente em `nGrowBytes`-em incrementos de tamanho se `nGrowBytes` não for zero.  
  
 Para obter mais informações, consulte o artigo [arquivos no MFC](../../mfc/files-in-mfc.md) e [tratamento de arquivos](../../c-runtime-library/file-handling.md) no *referência da biblioteca de tempo de execução*.  
  
## <a name="inheritance-hierarchy"></a>Hierarquia de herança  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CMemFile](../../mfc/reference/cmemfile-class.md)  
  
 `CSharedFile`  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** afxadv.h  
  
##  <a name="csharedfile"></a>CSharedFile::CSharedFile  
 Constrói um `CSharedFile` de objeto e aloca memória para ela.  
  
```  
CSharedFile(
    UINT nAllocFlags = GMEM_DDESHARE | GMEM_MOVEABLE,  
    UINT nGrowBytes = 4096);
```  
  
### <a name="parameters"></a>Parâmetros  
 *nAllocFlags*  
 Sinalizadores indicando como for possível alocar memória. Consulte [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) para obter uma lista de valores de sinalizador válido.  
  
 `nGrowBytes`  
 O incremento de alocação de memória em bytes.  
  
##  <a name="detach"></a>CSharedFile::Detach  
 Chame essa função para fechar o arquivo de memória e desanexá-lo do bloco de memória.  
  
```  
HGLOBAL Detach();
```  
  
### <a name="return-value"></a>Valor de retorno  
 O identificador do bloco de memória que contém o conteúdo do arquivo de memória.  
  
### <a name="remarks"></a>Comentários  
 Você poderá reabri-lo chamando [SetHandle](#sethandle), usando o identificador retornado por **desanexar**.  
  
##  <a name="sethandle"></a>CSharedFile::SetHandle  
 Chamar essa função para anexar um bloco de memória global para o `CSharedFile` objeto.  
  
```  
void SetHandle(
    HGLOBAL hGlobalMemory,  
    BOOL bAllowGrow = TRUE);
```  
  
### <a name="parameters"></a>Parâmetros  
 *hGlobalMemory*  
 Identificador para a memória global a ser anexado ao `CSharedFile`.  
  
 `bAllowGrow`  
 Especifica se o bloco de memória pode crescer.  
  
### <a name="remarks"></a>Comentários  
 Se `bAllowGrow` é diferente de zero, o tamanho do bloco de memória aumenta conforme necessário, por exemplo, se uma tentativa for feita para gravar mais bytes para o arquivo que foi alocada para o bloco de memória.  
  
## <a name="see-also"></a>Consulte também  
 [Classe CMemFile](../../mfc/reference/cmemfile-class.md)   
 [Gráfico de hierarquia](../../mfc/hierarchy-chart.md)   
 [Classe CMemFile](../../mfc/reference/cmemfile-class.md)