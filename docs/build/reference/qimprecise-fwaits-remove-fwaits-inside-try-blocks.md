---
title: -Qimprecise_fwaits (remover fwaits dentro de blocos Try) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Qimprecise_fwaits
dev_langs:
- C++
helpviewer_keywords:
- -Qimprecise_fwaits compiler option (C++)
- /Qimprecise_fwaits compiler option (C++)
ms.assetid: b1501f21-7e08-4fea-95e8-176ec03a635b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cad23ebdd2289791b50b0e956368b934fe0f1087
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46385190"
---
# <a name="qimprecisefwaits-remove-fwaits-inside-try-blocks"></a>/Qimprecise_fwaits (remover fwaits dentro de blocos Try)

Remove o `fwait` comandos internos para `try` bloqueia quando você usa o [/fp: except](../../build/reference/fp-specify-floating-point-behavior.md) opção de compilador.

## <a name="syntax"></a>Sintaxe

```
/Qimprecise_fwaits
```

## <a name="remarks"></a>Comentários

Essa opção não tem nenhum efeito se **/fp: except** também não for especificado. Se você especificar o **/fp: exceto** opção, o compilador inserirá um `fwait` comando ao redor de cada linha de código em um `try` bloco. Dessa forma, o compilador pode identificar a linha de código que gera uma exceção específica. **/Qimprecise_fwaits** remove interno `fwait` instruções, deixando apenas as esperas em torno de `try` bloco. Isso melhora o desempenho, mas o compilador só será capaz de dizer qual `try` bloco faz com que uma exceção, não a linha.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para definir esta opção do compilador no ambiente de desenvolvimento do Visual Studio

1. Abra a caixa de diálogo **Páginas de Propriedades** do projeto. Para obter detalhes, confira [Trabalhando com propriedades do projeto](../../ide/working-with-project-properties.md).

1. Clique o **C/C++** pasta.

1. Clique o **linha de comando** página de propriedades.

1. Digite a opção de compilador na **opções adicionais** caixa.

### <a name="to-set-this-compiler-option-programmatically"></a>Para definir essa opção do compilador via programação

- Consulte <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Consulte também

[Opções /Q (operações de nível baixo)](../../build/reference/q-options-low-level-operations.md)<br/>
[Opções do Compilador](../../build/reference/compiler-options.md)<br/>
[Definindo opções do compilador](../../build/reference/setting-compiler-options.md)