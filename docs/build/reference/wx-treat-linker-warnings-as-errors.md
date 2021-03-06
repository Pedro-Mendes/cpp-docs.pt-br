---
title: -WX (tratar avisos do vinculador como erros) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /WX
dev_langs:
- C++
helpviewer_keywords:
- /WX linker option
- -WX linker option
- WX linker option
ms.assetid: e4ba97c7-93f7-43ae-a4bb-d866790926c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 91f73af0c270be4452a4b556d2cb77c0d55bed33
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722586"
---
# <a name="wx-treat-linker-warnings-as-errors"></a>/WX (tratar avisos do vinculador como erros)

```
/WX[:NO]
```

## <a name="remarks"></a>Comentários

/WX faz com que nenhum arquivo de saída a ser gerado se o vinculador gera um aviso.

Isso é semelhante à **/WX** para o compilador (consulte [/w, /W0, / W1, / w2, / w3, / W4, / W1, / w2, / w3, / W4, /Wall, /wd, /, /wo, /Wv, /WX (nível de aviso)](../../build/reference/compiler-option-warning-level.md) para obter mais informações). No entanto, especificando **/WX** para a compilação não implica em que **/WX** também estará em vigor para a fase de link; você deve especificar explicitamente **/WX** para cada ferramenta.

Por padrão, **/WX** não está em vigor. Para tratar avisos do vinculador como erros, especifique **/WX**. **/WX:no** é o mesmo que não especificar **/WX**.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Para definir esta opção do vinculador no ambiente de desenvolvimento do Visual Studio

1. Abra a caixa de diálogo **Páginas de Propriedades** do projeto. Para obter detalhes, consulte [configuração de propriedades do projeto Visual C++](../../ide/working-with-project-properties.md).

1. Clique o **vinculador** pasta.

1. Clique o **linha de comando** página de propriedades.

1. Digite a opção para o **opções adicionais** caixa.

### <a name="to-set-this-linker-option-programmatically"></a>Para definir esta opção do vinculador por meio de programação

1. Consulte <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Consulte também

[Definindo opções de vinculador](../../build/reference/setting-linker-options.md)<br/>
[Opções do vinculador](../../build/reference/linker-options.md)