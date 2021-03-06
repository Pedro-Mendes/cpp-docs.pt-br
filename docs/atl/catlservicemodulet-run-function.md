---
title: 'Função catlservicemodulet:: Run | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- CServiceModule::Run
- CServiceModule.Run
- CSecurityDescriptor
dev_langs:
- C++
helpviewer_keywords:
- ATL services, security
ms.assetid: 42c010f0-e60e-459c-a63b-a53a24cda93b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1f7306e11bd1cc23e4de17e67f0941d2b3ee8473
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055263"
---
# <a name="catlservicemoduletrun-function"></a>Função catlservicemodulet:: Run

`Run` contém as chamadas para `PreMessageLoop`, `RunMessageLoop`, e `PostMessageLoop`. Depois de ser chamado, `PreMessageLoop` primeiro armazena a ID do thread. do serviço O serviço usará essa ID para se fechar enviando uma mensagem WM_QUIT usando a função de API do Win32 [PostThreadMessage](https://msdn.microsoft.com/library/windows/desktop/ms644946).

`PreMessageLoop` em seguida, chama `InitializeSecurity`. Por padrão, `InitializeSecurity` chamadas [CoInitializeSecurity](/windows/desktop/api/combaseapi/nf-combaseapi-coinitializesecurity) com o descritor de segurança definido como NULL, o que significa que qualquer usuário tenha acesso ao seu objeto.

Se você não quiser que o serviço para especificar sua própria segurança, substitua `PreMessageLoop` e não chame `InitializeSecurity`, e COM, em seguida, irá determinar as configurações de segurança do registro. Uma maneira conveniente de definir configurações do registro é com o [DCOMCNFG](../atl/dcomcnfg.md) utilitário discutido posteriormente nesta seção.

Depois que a segurança for especificada, o objeto é registrado em com para que novos clientes podem se conectar ao programa. Por fim, o programa informa ao Gerenciador de controle de serviço (SCM) que ele está em execução e o programa entrar em um loop de mensagem. O programa permanece em execução até que ele envia uma mensagem quit durante o desligamento do serviço.

## <a name="see-also"></a>Consulte também

[Serviços](../atl/atl-services.md)<br/>
[Classe CSecurityDesc](../atl/reference/csecuritydesc-class.md)<br/>
[Classe CSid](../atl/reference/csid-class.md)<br/>
[Classe CDacl](../atl/reference/cdacl-class.md)<br/>
[Catlservicemodulet:: Run](../atl/reference/catlservicemodulet-class.md#run)

