---
title: Criar um. Arquivo SBR | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- SBR files
- BSCMAKE, input files
- .sbr files
- source browser files
- local symbols in browse information
- symbols
ms.assetid: bdb4b93c-a88a-441a-84fd-01087d03be25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ac872dd13458c3fe15971f30a72b06e5510c5bd0
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723678"
---
# <a name="creating-an-sbr-file"></a>Criando um arquivo .Sbr

Os arquivos de entrada para BSCMAKE são arquivos. SBR. O compilador cria um arquivo. SBR para cada arquivo de objeto (. obj) compilá-lo. Quando você criar ou atualizar o arquivo de informações de procura, todos os arquivos. SBR para seu projeto devem estar disponíveis no disco.

Para criar um arquivo. SBR com todas as informações possíveis, especifique [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md).

Para criar um arquivo. SBR que não contém símbolos locais, especifique [/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md). Se os arquivos. SBR contêm símbolos locais, você pode ainda omiti-los do arquivo. bsc por meio do BSCMAKE [opção /El](../../build/reference/bscmake-options.md)`.`

Você pode criar um arquivo. SBR sem executar uma compilação completa. Por exemplo, você pode especificar a opção /Zs ao compilador para executar uma verificação de sintaxe e ainda se você especificar /FR ou /Fr., gerar um arquivo. SBR

O processo de compilação pode ser mais eficiente se os arquivos. SBR primeiro são incluídos para remover as definições não referenciadas. O compilador automaticamente pacotes de arquivos. SBR.

## <a name="see-also"></a>Consulte também

[Compilando um arquivo .Bsc](../../build/reference/building-a-dot-bsc-file.md)