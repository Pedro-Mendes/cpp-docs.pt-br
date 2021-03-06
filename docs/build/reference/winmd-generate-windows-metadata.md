---
title: -WINMD (gerar metadados do Windows) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadata
dev_langs:
- C++
ms.assetid: bcfb4901-411e-4c9e-9f78-23028b6e5fcc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 25b8b34e55fc0814653f4c44be50e545633be373
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705714"
---
# <a name="winmd-generate-windows-metadata"></a>/WINMD (Gera metadados do Windows

Habilita a geração de um arquivo de metadados de tempo de execução do Windows (. winmd).

```
/WINMD[:{NO|ONLY}]
```

## <a name="remarks"></a>Comentários

**/ WINMD**<br/>
A configuração padrão para aplicativos da plataforma Universal do Windows. O vinculador gera o arquivo executável binário e o arquivo de metadados. winmd.

**/WINMD:NO**<br/>
O vinculador gera apenas o arquivo executável binário, mas não é um arquivo. winmd.

**/ WINMD: APENAS**<br/>
O vinculador gera apenas o arquivo. winmd, mas não o arquivo executável binário.

Por padrão, o nome do arquivo de saída tem a forma `binaryname`. winmd. Para especificar um nome de arquivo diferente, use o [/WINMDFILE](../../build/reference/winmdfile-specify-winmd-file.md) opção.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Para definir esta opção do vinculador no ambiente de desenvolvimento do Visual Studio

1. Abra a caixa de diálogo **Páginas de Propriedades** do projeto. Para obter detalhes, confira [Trabalhando com propriedades do projeto](../../ide/working-with-project-properties.md).

1. Selecione o **vinculador** pasta.

1. Selecione o **metadados do Windows** página de propriedades.

1. No **gerar metadados do Windows** lista suspensa, selecione a opção desejada.

## <a name="see-also"></a>Consulte também

[Definindo opções de vinculador](../../build/reference/setting-linker-options.md)<br/>
[Opções do vinculador](../../build/reference/linker-options.md)