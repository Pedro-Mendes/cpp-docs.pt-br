---
title: Builds de versão | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- debugging [C++], release builds
- release builds
- debug builds, converting to release build
ms.assetid: fa9a78fa-f4b5-4722-baf4-aec655c4ff0f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b8d4f0d9b1bf0401cc6630b61449e87d72ff675
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722118"
---
# <a name="release-builds"></a>Builds de lançamento

Um build de versão usa otimizações. Quando você usa otimizações para criar um build de versão, o compilador não produzirá informações de depuração simbólicas. A ausência de informações de depuração simbólicas, além do fato de que o código não é gerado para o rastreamento e ASSERT chama, significa que o tamanho do seu arquivo executável é reduzido e, portanto, será mais rápida.

Esta seção apresenta informações sobre por que e quando você desejaria mudar de uma compilação de depuração para um build de versão. Ele também aborda alguns dos problemas que você pode encontrar ao mudar de uma depuração para um build de versão:

- [Criação de um Build de versão](../../build/reference/how-to-create-a-release-build.md)

- [Problemas comuns durante a criação de um build de versão](../../build/reference/common-problems-when-creating-a-release-build.md)

- [Corrigindo problemas do build de versão](../../build/reference/fixing-release-build-problems.md)

   - [Examinando instruções ASSERT](../../build/reference/using-verify-instead-of-assert.md)

   - [Usando o Build de depuração para verificação de substituição de memória](../../build/reference/using-the-debug-build-to-check-for-memory-overwrite.md)

   - [Um Build de versão de depuração](../../build/reference/how-to-debug-a-release-build.md)

   - [Verificando se há substituições de memória](../../build/reference/checking-for-memory-overwrites.md)

## <a name="see-also"></a>Consulte também

[Compilando projetos do C++ no Visual Studio](../../ide/building-cpp-projects-in-visual-studio.md)<br/>
[Referência de build C/C++](../../build/reference/c-cpp-building-reference.md)