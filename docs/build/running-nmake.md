---
title: Executando NMAKE | Microsoft Docs
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- targets, building
- response files, NMAKE
- targets
- command files
- NMAKE program, targets
- NMAKE program, running
- command files, NMAKE
ms.assetid: 0421104d-8b7b-4bf3-86c1-928d9b7c1a8c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bdc9d89dbc0e77a8002cc34e5d010ee49d761da4
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706687"
---
# <a name="running-nmake"></a>Executando NMAKE

## <a name="syntax"></a>Sintaxe

> **NMAKE** [*opção* ...] [*macros* ...] [*destinos* ...] [**\@**<em>commandfile</em> ...]

## <a name="remarks"></a>Comentários

Compilações NMAKE só especificadas *destinos* ou, se nenhum for especificado, o primeiro destino no makefile. O primeiro destino makefile pode ser um [pseudotarget](../build/pseudotargets.md) que cria outros destinos. NMAKE usa makefiles especificado com /F; Se /F não for especificado, ele usa o arquivo de Makefile no diretório atual. Se nenhum makefile for especificado, ele usa regras de inferência para criar linha de comando *destinos*.

O *commandfile* arquivo de texto (ou arquivo de resposta) contém uma entrada de linha de comando. Outras entradas podem vir antes ou depois \@ *commandfile*. Um caminho é permitido. Na *commandfile*, quebras de linha são tratadas como espaços. Coloque as definições de macro entre aspas se contiverem espaços.

## <a name="what-do-you-want-to-know-more-about"></a>Que mais você deseja saber?

[Opções de NMAKE](../build/nmake-options.md)

[Tools.ini e NMAKE](../build/tools-ini-and-nmake.md)

[Códigos de saída de NMAKE](../build/exit-codes-from-nmake.md)

## <a name="see-also"></a>Consulte também

[Referência a NMAKE](../build/nmake-reference.md)