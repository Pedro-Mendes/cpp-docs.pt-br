---
title: 'Como: integrar ferramentas personalizar as propriedades do projeto | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- msbuild.cpp.howto.integratecustomtools
dev_langs:
- C++
helpviewer_keywords:
- 'msbuild (c++), howto: integrate custom tools'
ms.assetid: f32d91a4-44e9-4de3-aa9a-1c7f709ad2ee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 800652b845294ebad4e1cca5310e0b95f6d79151
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720377"
---
# <a name="how-to-integrate-custom-tools-into-the-project-properties"></a>Como integrar ferramentas personalizar a propriedades de projeto

Você pode adicionar opções de ferramenta personalizada para o Visual Studio **páginas de propriedade** janela, criando um arquivo de esquema XML subjacente.

O **propriedades de configuração** seção o **páginas de propriedades** janela exibe os grupos de configurações que são conhecidos como *regras*. Cada regra contém as configurações para uma ferramenta ou um grupo de recursos. Por exemplo, o **vinculador** regra contém as configurações para a ferramenta do vinculador. As configurações em uma regra podem ser subdivididas em *categorias*.

Este documento explica como criar um arquivo em um diretório de conjunto que contém as propriedades para sua ferramenta personalizada para que as propriedades são carregadas quando o Visual Studio é iniciado. Para obter informações sobre como modificar o arquivo, consulte [plataforma Extensibilty parte 2](https://blogs.msdn.microsoft.com/vsproject/2009/06/18/platform-extensibility-part-2/) no blog da equipe de projeto do Visual Studio.

### <a name="to-add-or-change-project-properties"></a>Para adicionar ou alterar as propriedades do projeto

1. No editor de XML, crie um arquivo XML.

1. Salve o arquivo em que o Visual Studio 2017 `VCTargets\1033` pasta. Você terá um caminho diferente para cada idioma e de cada edição do Visual Studio 2017 instalado. Por exemplo, o caminho da pasta para o Visual Studio Enterprise edition em inglês é `%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets\1033`. Ajuste o caminho para seu idioma e a edição do Visual Studio. Cada regra na **páginas de propriedade** janela é representada por um arquivo XML nesta pasta. Certifique-se de que o arquivo é exclusivamente nomeado na pasta.

1. Copie o conteúdo `%ProgramFiles%\Microsoft Visual Studio\2017\<VS Edition>\Common7\IDE\VC\VCTargets\<LCID>\cl.xml`, fechá-lo sem salvar as alterações e, em seguida, cole o conteúdo no seu novo arquivo XML. Você pode usar qualquer arquivo de esquema XML - esse é apenas um que pode ser usado para que você pode começar com um modelo.

1. No novo arquivo XML, modifique o conteúdo de acordo com suas necessidades. Certifique-se de alterar o **nome da regra** e **Rule.DisplayName** na parte superior do arquivo.

1. Salve as alterações e feche o arquivo.

1. O XML de arquivos no `%ProgramFiles%\Microsoft Visual Studio\2017\<VS Edition>\Common7\IDE\VC\VCTargets\<LCID>` são carregados quando o Visual Studio é iniciado. Portanto, para testar o novo arquivo, reinicie o Visual Studio.

1. Na **Gerenciador de soluções**, clique em um projeto e, em seguida, clique em **propriedades**. No **páginas de propriedade** janela, no painel esquerdo, verifique se há um novo nó com o nome da sua regra.

## <a name="see-also"></a>Consulte também

[MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)
