---
title: -IGNORE (Ignorar avisos específicos) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /OVERWRITE
dev_langs:
- C++
helpviewer_keywords:
- /IGNORE linker option
ms.assetid: 37e77387-8838-4697-898f-d376ac641124
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aee498951c01c332dffe720dbd6e3b77c8121aa5
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705855"
---
# <a name="ignore-ignore-specific-warnings"></a>/IGNORE (Ignorar os Avisos Específicos)

```
/IGNORE:warning[,warning]
```

## <a name="parameters"></a>Parâmetros

*warning*<br/>
O número de avisos do vinculador para suprimir, no intervalo de 4000 a 4999.

## <a name="remarks"></a>Comentários

Por padrão, o LINK relata todos os avisos. Especificar **ignorar:** `warning` para informar ao vinculador para suprimir um número específico de aviso. Para ignorar diversos avisos, separe os números de aviso com vírgulas.

O vinculador não permite que alguns avisos sejam ignorados. Esta tabela lista os avisos que não são suprimidos pela **ignorar**:

|Aviso do Vinculador||
|--------------------|-|
|LNK4017|A instrução `keyword` não é suportada para a plataforma de destino; ignorada|
|[LNK4044](../../error-messages/tool-errors/linker-tools-warning-lnk4044.md)|opção não reconhecida "`option`"; ignorada|
|LNK4062|'`option`'não é compatível com'`architecture`' máquina de destino; opção ignorada|
|[LNK4075](../../error-messages/tool-errors/linker-tools-warning-lnk4075.md)|Ignorando "`option1`" devido a especificação "`option2`"|
|[LNK4086](../../error-messages/tool-errors/linker-tools-warning-lnk4086.md)|O ponto de entrada "`function`" não é __stdcall com "`number`" bytes de argumentos; a imagem pode não ser executada|
|LNK4088|Imagem sendo gerada devido a opção /FORCE; a imagem pode não ser executada|
|[LNK4105](../../error-messages/tool-errors/linker-tools-warning-lnk4105.md)|nenhum argumento especificado com a opção "`option`"; ignorando o comutador|
|LNK4203|Erro ao ler o banco de dados do programa "`filename`"; vinculando objeto como se não houvesse informações de depuração|
|[LNK4204](../../error-messages/tool-errors/linker-tools-warning-lnk4204.md)|'`filename`' está faltando informações de depuração para módulo de referência; vinculando objeto quando sem informação de depuração|
|[LNK4205](../../error-messages/tool-errors/linker-tools-warning-lnk4205.md)|'`filename`' está faltando informações de depuração para módulo de referência; vinculando objeto quando sem informação de depuração|
|[LNK4206](../../error-messages/tool-errors/linker-tools-warning-lnk4206.md)|As informações sobre o tipo pré-compilado não foram encontradas; "`filename`" não vinculado ou substituído; vinculando objeto como se não houvesse informações de depuração|
|LNK4207|'`filename`' compilou /Yc /Yu/Z7; não é possível criar PDB; recompile com /Zi; vinculando objeto quando sem informação de depuração|
|LNK4208|Formato de PDB incompatível no "`filename`"; excluir e recompilar; vinculando objeto como se não houvesse informações de depuração|
|LNK4209|depurando informações corrompidas; recompilar módulo; vinculando objeto como se não houvesse informações de depuração|
|[LNK4224](../../error-messages/tool-errors/linker-tools-warning-lnk4224.md)|`option` não é mais suportado; ignorado|
|LNK4228|'`option`' inválido para uma DLL; ignorado|
|[LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)|Diretiva inválida /`directive` encontrada; ignorada|

Em geral, os avisos do vinculador que não podem ser ignorados representam falhas de compilação, erros de linha de comando ou erros de configuração que devem ser corrigidos.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Para definir esta opção do vinculador no ambiente de desenvolvimento do Visual Studio

1. Abra a caixa de diálogo **Páginas de Propriedades** do projeto. Para obter detalhes, confira [Trabalhando com propriedades do projeto](../../ide/working-with-project-properties.md).

1. No **vinculador** pasta, selecione a **linha de comando** página de propriedades.

1. Modificar a **opções adicionais** propriedade.

### <a name="to-set-this-linker-option-programmatically"></a>Para definir esta opção do vinculador por meio de programação

- Consulte <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.