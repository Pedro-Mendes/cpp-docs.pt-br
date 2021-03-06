---
title: Automação em uma DLL | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], Automation
- Automation [C++], DLLs
ms.assetid: 2728ecd1-14e2-4ae0-a946-e749e11dbb74
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cde5d0e400f1bdd3f5a851d47da581380273b04a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717763"
---
# <a name="automation-in-a-dll"></a>Automação em um DLL

Quando você escolhe a opção de automação no Assistente de DLL do MFC, o assistente fornece o seguinte:

- Uma linguagem de descrição do objeto inicial (. Arquivo ODL)

- Uma diretiva de inclusão no arquivo Stdafx. h para Afxole.h

- Uma implementação de `DllGetClassObject` função, que chama o **AfxDllGetClassObject** função

- Uma implementação de `DllCanUnloadNow` função, que chama o **AfxDllCanUnloadNow** função

- Uma implementação de `DllRegisterServer` função, que chama o [COleObjectFactory::UpdateRegistryAll](../mfc/reference/coleobjectfactory-class.md#updateregistryall) função

## <a name="what-do-you-want-to-know-more-about"></a>Que mais você deseja saber?

- [Servidores de automação](../mfc/automation-servers.md)

## <a name="see-also"></a>Consulte também

[DLLs no Visual C++](../build/dlls-in-visual-cpp.md)