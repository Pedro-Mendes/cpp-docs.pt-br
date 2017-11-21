---
title: Ganchos de falha | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: delayed loading of DLLs, failure hooks
ms.assetid: 12bb303b-ffe6-4471-bffe-9ef4f8bb2d30
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 86f3f27d06b353d0e34a62b636dc7ae0313a462c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="failure-hooks"></a>Ganchos de falha
O gancho de falha é habilitado da mesma maneira como o [gancho de notificação](../../build/reference/notification-hooks.md). As necessidades de rotina de gancho para retornar um valor adequado para que o processamento podem continuar (um HINSTANCE ou FARPROC) ou 0 para indicar que uma exceção deve ser gerada.  
  
 A variável de ponteiro refere-se para a função definida pelo usuário é:  
  
```  
// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}  
ExternC  
PfnDliHook   __pfnDliFailureHook2;  
```  
  
 O **DelayLoadInfo** estrutura contém todos os dados pertinentes necessários para relatórios precisos do erro, incluindo o valor de `GetLastError`.  
  
 Se a notificação é **dliFailLoadLib**, a função de gancho pode retornar:  
  
-   0, se ele não pode lidar com falhas.  
  
-   Um HMODULE, se o gancho de falha foi corrigido o problema e carregado da própria biblioteca.  
  
 Se a notificação é **dliFailGetProc**, a função de gancho pode retornar:  
  
-   0, se ele não pode lidar com falhas.  
  
-   Um endereço de processo válido (endereço da função de importação), se conectar-se a falha foi bem-sucedida na obtenção do próprio endereço.  
  
## <a name="see-also"></a>Consulte também  
 [Tratamento de erro e notificação](../../build/reference/error-handling-and-notification.md)