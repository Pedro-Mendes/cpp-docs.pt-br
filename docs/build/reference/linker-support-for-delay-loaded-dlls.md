---
title: Suporte do vinculador para DLLs carregadas com atraso | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, linker support
ms.assetid: b2d7e449-2809-42b1-9c90-2c0ca5e31a14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 555a46ee65a5d5d5565128a15af01a2c1cf18540
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45711888"
---
# <a name="linker-support-for-delay-loaded-dlls"></a>Suporte de vinculador para DLLs carregadas com atraso

O vinculador do Visual C++ agora dá suporte o carregamento atrasado de DLLs. Isso libera você da necessidade de usar as funções do SDK do Windows **LoadLibrary** e **GetProcAddress** para implementar a DLL de carregamento com atraso.

Antes do Visual C++ 6.0, a única maneira de carregar uma DLL em tempo de execução era usando **LoadLibrary** e **GetProcAddress**; o sistema operacional carrega a DLL quando o arquivo executável ou DLL usando ele foi carregado.

Começando com o Visual C++ 6.0, ao vincular estaticamente com uma DLL, o vinculador fornece opções para atrasar a carregam a DLL até que o programa chama uma função nessa DLL.

Um aplicativo pode atrasar a carregar uma DLL usando o [/DELAYLOAD (importação de carga com atraso)](../../build/reference/delayload-delay-load-import.md) opção de vinculador com uma função auxiliar (implementação padrão fornecida pelo Visual C++). A função auxiliar carregará a DLL em tempo de execução chamando **LoadLibrary** e **GetProcAddress** para você.

Você deve considerar o atraso ao carregar uma DLL se:

- Seu programa não pode chamar uma função na DLL.

- Uma função na DLL não pode ser chamada até o final do execução do programa.

O carregamento atrasado de uma DLL pode ser especificado durante a compilação de um. EXE ou. Projeto de DLL. A. Projeto DLL que retarda o carregamento de uma ou mais DLLs não deve se chamar um ponto de entrada carregadas com atraso na Dllmain.

Os tópicos a seguir descrevem as DLLs de carregamento com atraso:

- [Especificando DLLs para carregamento com atraso](../../build/reference/specifying-dlls-to-delay-load.md)

- [Descarregando de maneira explícita uma DLL carregada com atraso](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md)

- [Carregando todas as importações para uma DLL carregada com atraso](../../build/reference/loading-all-imports-for-a-delay-loaded-dll.md)

- [Associando importações](../../build/reference/binding-imports.md)

- [Tratamento de erro e notificação](../../build/reference/error-handling-and-notification.md)

- [Despejando importações carregadas com atraso](../../build/reference/dumping-delay-loaded-imports.md)

- [Restrições para o carregamento de DLLs com atraso](../../build/reference/constraints-of-delay-loading-dlls.md)

- [Noções básicas sobre a função auxiliar](understanding-the-helper-function.md)

- [Desenvolvendo sua própria função auxiliar](../../build/reference/developing-your-own-helper-function.md)

## <a name="see-also"></a>Consulte também

[DLLs no Visual C++](../../build/dlls-in-visual-cpp.md)<br/>
[Vinculação](../../build/reference/linking.md)