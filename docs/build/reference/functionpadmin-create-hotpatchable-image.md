---
title: /FUNCTIONPADMIN (Criar imagem Hotpatchable) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /functionpadmin
dev_langs:
- C++
helpviewer_keywords:
- -FUNCTIONPADMIN linker option
- /FUNCTIONPADMIN linker option
ms.assetid: 25b02c13-1add-4fbd-add9-fcb30eb2cae7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a82611c453a96e9247e414d6adb777c07320482
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703983"
---
# <a name="functionpadmin-create-hotpatchable-image"></a>/FUNCTIONPADMIN (Criar imagem hotpatchable)

Prepara uma imagem para patch instantâneo.

## <a name="syntax"></a>Sintaxe

> **/FUNCTIONPADMIN**[**:**_space_]

### <a name="arguments"></a>Arguments

*space*<br/>
A quantidade de preenchimento a ser adicionado ao início de cada função em bytes. Em x86, o padrão será a 5 bytes de preenchimento e em x64, o padrão será a 6 bytes. Em outros destinos, um valor deve ser fornecido.

## <a name="remarks"></a>Comentários

Em ordem para o vinculador produzir uma imagem de hotpatchable, os arquivos. obj devem ter sido compilados com [/hotpatch (Criar imagem de Hotpatchable)](../../build/reference/hotpatch-create-hotpatchable-image.md).

Quando você compila e vincula uma imagem com uma única chamada de cl.exe, **/hotpatch** implica **/functionpadmin**.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Para definir esta opção do vinculador no ambiente de desenvolvimento do Visual Studio

1. Abra a caixa de diálogo **Páginas de Propriedades** do projeto. Para obter detalhes, consulte [configuração de propriedades do projeto Visual C++](../../ide/working-with-project-properties.md).

1. Selecione o **propriedades de configuração** > **vinculador** > **linha de comando** página de propriedades.

1. Insira o **/FUNCTIONPADMIN** opção **opções adicionais**. Escolher **Okey** para salvar suas alterações.

### <a name="to-set-this-linker-option-programmatically"></a>Para definir esta opção do vinculador por meio de programação

- Consulte <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Consulte também

[Definindo opções de vinculador](../../build/reference/setting-linker-options.md)<br/>
[Opções do vinculador](../../build/reference/linker-options.md)
