---
title: 'Como: criar projetos C++ verificáveis (C + + / CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- verifiable assemblies [C++], creating
- conversions, C++ projects
- Visual C++ projects
ms.assetid: 4ef2cc1a-e3e5-4d67-8d8d-9c614f8ec5d3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a84fcd660f8cc7ef5686fe0e03f9b520d1251bc4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408928"
---
# <a name="how-to-create-verifiable-c-projects-ccli"></a>Como: criar projetos do C++ verificáveis (C + + / CLI)

Assistentes de aplicativo do Visual C++ não criam projetos verificáveis.

> [!IMPORTANT]
> Preterido do Visual Studio 2015 e Visual Studio 2017 não oferece suporte a **/clr: pure** e **/CLR: safe** criação de projetos verificáveis. Se você precisar de código verificável, recomendamos que você converter seu código para c#.

No entanto, se você estiver usando uma versão mais antiga do conjunto de ferramentas de compilador do Visual C++ que dá suporte a **/clr: pure** e **/CLR: safe**, projetos podem ser convertidos para que seja verificável. Este tópico descreve como definir as propriedades do projeto e modificar arquivos de origem do projeto para transformar seus projetos do Visual C++ para produzir aplicativos verificáveis.

## <a name="compiler-and-linker-settings"></a>Configurações de compilador e vinculador

Por padrão, os projetos do .NET usam o sinalizador do compilador /clr e configurar o vinculador para hardware x86 de destino. Para código verificável, você deve usar o sinalizador de /CLR: safe, e você deve instruir o vinculador para gerar MSIL, em vez de instruções nativas da máquina.

### <a name="to-change-the-compiler-and-linker-settings"></a>Para alterar as configurações de compilador e vinculador

1. Exiba o página de propriedades do projeto. Para obter mais informações, confira [Trabalhando com propriedades do projeto](../ide/working-with-project-properties.md).

1. No **gerais** página sob a **propriedades de configuração** conjunto de nós, o **suporte a Common Language Runtime** propriedade para **seguro MSIL Common Language Suporte de tempo de execução (/ /CLR: Safe)**.

1. No **avançado** página sob a **vinculador** conjunto de nós, o **tipo de imagem CLR** propriedade a ser **forçar imagem IL segura (/ /CLRIMAGETYPE: Safe)**.

## <a name="removing-native-data-types"></a>Removendo tipos de dados nativos

Como os tipos de dados nativos são não verificáveis, mesmo se eles não são realmente usados, você deve remover todos os arquivos de cabeçalho que contém os tipos nativos.

> [!NOTE]
> O procedimento a seguir se aplicam a projetos de aplicativo de formulários do Windows (.NET) e o aplicativo de Console (.NET).

### <a name="to-remove-references-to-native-data-types"></a>Para remover referências a tipos de dados nativos

1. Comentar tudo no arquivo Stdafx. h.

## <a name="configuring-an-entry-point"></a>Configurando um ponto de entrada

Porque aplicativos verificáveis não é possível usar as bibliotecas de tempo de execução C (CRT), eles não podem depender de CRT para chamar a função principal como o ponto de entrada padrão. Isso significa que você deve fornecer explicitamente o nome da função a ser chamado inicialmente para o vinculador. (Nesse caso, Main () é usado em vez de Main () ou _tmain() para indicar um ponto de entrada não CRT, mas porque o ponto de entrada deve ser especificado explicitamente, esse nome é arbitrário.)

> [!NOTE]
> Os procedimentos a seguir se aplicam a projetos de aplicativo de Console (.NET).

#### <a name="to-configure-an-entry-point"></a>Para configurar um ponto de entrada

1. Altere _tmain() para Main () no arquivo. cpp principal do projeto.

1. Exiba o página de propriedades do projeto. Para obter mais informações, confira [Trabalhando com propriedades do projeto](../ide/working-with-project-properties.md).

1. No **Advanced** página sob a **vinculador** nó, insira `Main` como o **ponto de entrada** valor da propriedade.

## <a name="see-also"></a>Consulte também

- [Código puro e verificável (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)
