---
title: -F (Definir tamanho da pilha) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /f
dev_langs:
- C++
helpviewer_keywords:
- set stack size compiler option
- F compiler option [C++]
- -F compiler option [C++]
- /F compiler option [C++]
- stack, setting size
ms.assetid: 17320b6f-8305-445b-9ec2-75833f4b29e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 244fea4b776f0713b6fb2281563e39d27a910a2d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45704231"
---
# <a name="f-set-stack-size"></a>/F (definir tamanho da pilha)

Define o tamanho da pilha de programa em bytes.

## <a name="syntax"></a>Sintaxe

> **/F** *número*

## <a name="arguments"></a>Arguments

*número*<br/>
O tamanho da pilha em bytes.

## <a name="remarks"></a>Comentários

Sem essa opção o tamanho da pilha padrão é 1 MB. O *número* argumento pode ser em decimal ou notação de linguagem C. O argumento pode variar de 1 para o tamanho de pilha máximo aceito pelo vinculador. O vinculador Arredonda o valor especificado para o mais próximo de 4 bytes. O espaço entre **/F** e *número* é opcional.

Talvez você precise aumentar o tamanho da pilha, se seu programa obtém mensagens de estouro de pilha.

Você também pode definir o tamanho da pilha:

- Usando o **/Stack** a opção de vinculador. Para obter mais informações, consulte [/Stack](../../build/reference/stack.md).

- Usando EDITBIN no arquivo .exe. Para obter mais informações, consulte [referência de EDITBIN](../../build/reference/editbin-reference.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para definir esta opção do compilador no ambiente de desenvolvimento do Visual Studio

1. Abra a caixa de diálogo **Páginas de Propriedades** do projeto. Para obter detalhes, confira [Trabalhando com propriedades do projeto](../../ide/working-with-project-properties.md).

1. Selecione o **propriedades de configuração** > **C/C++** > **linha de comando** página de propriedades.

1. Digite a opção de compilador na **opções adicionais** caixa.

### <a name="to-set-this-compiler-option-programmatically"></a>Para definir essa opção do compilador via programação

- Consulte <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Consulte também

[Opções do Compilador](../../build/reference/compiler-options.md)<br/>
[Definindo opções do compilador](../../build/reference/setting-compiler-options.md)