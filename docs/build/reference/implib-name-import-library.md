---
title: -IMPLIB (nomear biblioteca de importação) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /implib
- VC.Project.VCLinkerTool.ImportLIbrary
dev_langs:
- C++
helpviewer_keywords:
- IMPLIB linker option
- /IMPLIB linker option
- -IMPLIB linker option
- import libraries, overriding default name
ms.assetid: fe8f71ab-7055-41b5-8ef8-2b97cfa4a432
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 25d997bf7df96d3f6ee518a8b7ca0568a44efa93
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707636"
---
# <a name="implib-name-import-library"></a>/IMPLIB (nomear biblioteca de importações)

> /IMPLIB:*filename*

## <a name="parameters"></a>Parâmetros

*filename*<br/>
Um nome especificado pelo usuário para a biblioteca de importação. Ele substitui o nome padrão.

## <a name="remarks"></a>Comentários

A opção de /IMPLIB substitui o nome padrão para a biblioteca de importação que o LINK cria quando ele compila um programa que contém exportações. O nome padrão é formado pelo nome base do arquivo de saída principal e a extensão. lib. Um programa contém exportações, se forem especificadas uma ou mais das seguintes opções:

- O [dllexport](../../cpp/dllexport-dllimport.md) palavra-chave no código-fonte

- [Exportações](../../build/reference/exports.md) instrução em um arquivo. def

- Uma [/exportação](../../build/reference/export-exports-a-function.md) especificação em um comando LINK

O LINK ignora /IMPLIB quando uma biblioteca de importação não está sendo criada. Se nenhuma exportação forem especificadas, o LINK não cria uma biblioteca de importação. Se um arquivo de exportação é usado na compilação, o LINK pressupõe que uma biblioteca de importação já existe e não cria uma. Para obter informações sobre bibliotecas de importação e exportação de arquivos, consulte [referência de LIB](../../build/reference/lib-reference.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Para definir esta opção do vinculador no ambiente de desenvolvimento do Visual Studio

1. Abra a caixa de diálogo **Páginas de Propriedades** do projeto. Para obter detalhes, consulte [configuração de propriedades do projeto Visual C++](../../ide/working-with-project-properties.md).

1. Clique o **vinculador** pasta.

1. Clique o **avançado** página de propriedades.

1. Modificar a **biblioteca de importação** propriedade.

### <a name="to-set-this-linker-option-programmatically"></a>Para definir esta opção do vinculador por meio de programação

- Consulte <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ImportLibrary%2A>.

## <a name="see-also"></a>Consulte também

[Definindo opções de vinculador](../../build/reference/setting-linker-options.md)<br/>
[Opções do vinculador](../../build/reference/linker-options.md)