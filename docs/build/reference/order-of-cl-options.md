---
title: Ordem de opções CL | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- cl
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, setting options
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ffe9a440396df14823775db335e52bca6cacdb3
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725010"
---
# <a name="order-of-cl-options"></a>Ordem de opções CL

As opções podem aparecer em qualquer lugar na linha de comando CL, exceto para a opção /link, que deve ocorrer pela última vez. O compilador começa com as opções especificadas na [variável de ambiente CL](../../build/reference/cl-environment-variables.md) e, em seguida, lê a linha de comando da esquerda para direita – processamento de arquivos de comando na ordem encontrá-las. Cada opção se aplica a todos os arquivos na linha de comando. Se o CL encontrar opções conflitantes, ele usa a opção mais à direita.

## <a name="see-also"></a>Consulte também

[Sintaxe de linha de comando do compilador](../../build/reference/compiler-command-line-syntax.md)