---
title: -GX (habilitar tratamento de exceções) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /gx
dev_langs:
- C++
helpviewer_keywords:
- exception handling, enabling
- /GX compiler option [C++]
- -GX compiler option [C++]
- cl.exe compiler, exception handling
- enable exception handling compiler option [C++]
- GX compiler option [C++]
ms.assetid: 933b43ba-de77-4ff8-a48b-7074de90bc1c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 095db3db73f2be4012efe39f3b8cd8e645ad46c3
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718310"
---
# <a name="gx-enable-exception-handling"></a>/GX (habilitar tratamento de exceções)

Preterido. Habilita o tratamento de exceções síncronas usando a suposição de que funções declarado usando `extern "C"` nunca geram uma exceção.

## <a name="syntax"></a>Sintaxe

```
/GX
```

## <a name="remarks"></a>Comentários

**/GX** foi preterido. Use o equivalente [/EHsc](../../build/reference/eh-exception-handling-model.md) opção em vez disso. Para obter uma lista de opções do compilador preterido, consulte o **preteridos e removidos opções do compilador** seção [opções de compilador listadas por categoria](../../build/reference/compiler-options-listed-by-category.md).

Por padrão, **/EHsc**, o equivalente **/GX**, está em vigor quando você compila usando o ambiente de desenvolvimento do Visual Studio. Ao usar as ferramentas de linha de comando, sem tratamento de exceções é especificado. Este é o equivalente de **/GX-**.

Para obter mais informações, consulte [tratamento de exceções de C++](../../cpp/cpp-exception-handling.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para definir esta opção do compilador no ambiente de desenvolvimento do Visual Studio

1. Abra a caixa de diálogo **Páginas de Propriedades** do projeto. Para obter detalhes, confira [Trabalhando com propriedades do projeto](../../ide/working-with-project-properties.md).

1. No painel de navegação, escolha **propriedades de configuração**, **C/C++**, **linha de comando**.

1. Digite a opção de compilador na **opções adicionais** caixa.

### <a name="to-set-this-compiler-option-programmatically"></a>Para definir essa opção do compilador via programação

- Consulte <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Consulte também

[Opções do Compilador](../../build/reference/compiler-options.md)<br/>
[Definindo opções do compilador](../../build/reference/setting-compiler-options.md)<br/>
[/EH (modelo de tratamento de exceções)](../../build/reference/eh-exception-handling-model.md)