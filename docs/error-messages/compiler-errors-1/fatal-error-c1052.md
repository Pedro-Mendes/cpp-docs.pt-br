---
title: Erro fatal C1052 | Microsoft Docs
ms.custom: 
ms.date: 05/08/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1052
dev_langs:
- C++
helpviewer_keywords:
- C1052
ms.assetid: f2c09a2f-d3c1-4420-9501-ffcb65caf87b
caps.latest.revision: 0
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: f3ab91c1c79b822a4d9a33fb0ab5fbd88146fff0
ms.contentlocale: pt-br
ms.lasthandoff: 05/10/2017

---
# <a name="fatal-error-c1052"></a>Erro fatal C1052
arquivo de banco de dados do programa, '*filename*', foi gerado pelo vinculador com /debug: fastlink; compilador não pode atualizar esses arquivos PDB; exclua-o ou use /Fd para especificar um nome de arquivo PDB diferente  
  
O compilador não pode atualizar os mesmos arquivos de banco de dados (PDB) do programa que são gerados pelo vinculador quando o [/Debug: fastlink](../../build/reference/debug-generate-debug-info.md) opção é especificada. Normalmente, os arquivos PDB gerado pelo compilador e os arquivos PDB gerado pelo vinculador têm nomes diferentes. No entanto, se estiverem definidos para usar os mesmos nomes, esse erro pode resultar.  
  
Para corrigir esse problema, você pode excluir explicitamente os arquivos PDB antes de compilar novamente, ou você pode criar nomes diferentes para os arquivos PDB gerado pelo compilador e vinculador gerado. Para criar nomes de arquivo PDB de gerado pelo compilador diferentes na linha de comando, use o [/Fd](../../build/reference/fd-program-database-file-name.md) opção. Para gerar nomes de arquivo PDB diferentes no IDE, abra o **páginas de propriedade** caixa de diálogo para seu projeto e, no **propriedades de configuração**, **C/C++**, **arquivos de saída** , defina o **nome do arquivo de banco de dados de programa** propriedade. Por padrão, essa propriedade é `$(IntDir)vc$(PlatformToolsetVersion).pdb`. Como alternativa, você pode definir o nome do arquivo PDB gerado pelo vinculador. Abra o **páginas de propriedade** caixa de diálogo para seu projeto e, no **propriedades de configuração**, **vinculador**, **depuração** , defina o **gerar arquivo de banco de dados do programa** propriedade. Por padrão, essa propriedade é definida como `$(OutDir)$(TargetName).pdb`.  
