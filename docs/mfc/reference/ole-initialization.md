---
title: "Inicialização OLE | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.ole
dev_langs:
- C++
helpviewer_keywords:
- OLE initialization
ms.assetid: aa8a54a7-24c3-4344-b2c6-dbcf6084fa31
caps.latest.revision: 13
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
ms.sourcegitcommit: b943ef8dd652df061965fe81ecc9c08115636141
ms.openlocfilehash: c598a2c78e92725e656de82397418f1635d4f92d
ms.lasthandoff: 04/04/2017

---
# <a name="ole-initialization"></a>Inicialização OLE
Antes de um aplicativo pode usar os serviços do sistema OLE, ele deve inicializar as DLLs do sistema OLE e verifique se as DLLs são da versão correta. O **AfxOleInit** função inicializa a DLLs do sistema OLE.  
  
### <a name="ole-initialization"></a>Inicialização OLE  
  
|||  
|-|-|  
|[AfxOleInit](#afxoleinit)|Inicializa as bibliotecas OLE.| 
|[AfxEnableControlContainer](#afxenablecontrolcontainer)|Chamar essa função em seu objeto de aplicativo `InitInstance` função para habilitar o suporte para contenção de controles OLE.| 


## <a name="afxenablecontrolcontainer"></a>AfxEnableControlContainer
Chamar essa função em seu objeto de aplicativo `InitInstance` função para habilitar o suporte para contenção de controles OLE.  
   
### <a name="syntax"></a>Sintaxe    
```
void AfxEnableControlContainer( );  
```  
   
### <a name="remarks"></a>Comentários  
 Para obter mais informações sobre controles OLE (agora chamado de controles ActiveX), consulte [tópicos de controle ActiveX](../mfc-activex-controls.md).  
   
### <a name="requirements"></a>Requisitos  
 **Cabeçalho:** afxdisp.h  

  
##  <a name="afxoleinit"></a>AfxOleInit  
 Inicializa o suporte do OLE para o aplicativo.  
  
``` 
BOOL AFXAPI AfxOleInit(); 
```  
  
### <a name="return-value"></a>Valor de retorno  
 Diferente de zero se for bem-sucedida; 0 se a inicialização falhar, possivelmente porque versões incorretas das DLLs do sistema OLE estão instaladas.  
  
### <a name="remarks"></a>Comentários  
 Chame essa função para inicializar o suporte OLE para um aplicativo do MFC. Quando esta função é chamada, ocorrem as seguintes ações:  
  
-   Inicializa a biblioteca de data/hora de apartment atual do aplicativo de chamada. Para obter mais informações, consulte [OleInitialize](http://msdn.microsoft.com/library/windows/desktop/ms690134).  
  
-   Cria um objeto de filtro de mensagem, Implementando a [IMessageFilter](http://msdn.microsoft.com/library/windows/desktop/ms693740) interface. Esse filtro de mensagem pode ser acessado com uma chamada para [AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter).  
  
> [!NOTE]
>  Se **AfxOleInit** é chamado de uma DLL MFC, a chamada falhará. A falha ocorre porque a função pressupõe que, se ele é chamado de uma DLL, o sistema OLE era inicializado anteriormente pelo aplicativo de chamada.  
  
> [!NOTE]
>  Aplicativos MFC devem ser inicializados como apartment threaded único (STA). Se você chamar [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) no seu `InitInstance` substituir, especifique `COINIT_APARTMENTTHREADED` (em vez de `COINIT_MULTITHREADED`). Para obter mais informações, consulte PRB: aplicativos MFC para de responder quando você inicializar o aplicativo como um Multi-Threaded Apartment (828643) em [http://support.microsoft.com/default.aspxscid=kb;en-us;828643](http://support.microsoft.com/default.aspxscid=kb;en-us;828643).  

### <a name="requirements"></a>Requisitos  
 **Cabeçalho:** afxdisp.h

## <a name="see-also"></a>Consulte também  
 [Macros e globais](../../mfc/reference/mfc-macros-and-globals.md)
