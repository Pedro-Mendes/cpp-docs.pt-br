---
title: Caixa de diálogo Ferramenta de texto (C++) (Editor de imagens para ícones) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.texttool
dev_langs:
- C++
helpviewer_keywords:
- text, adding to an image
- Text Tool dialog box [C++]
ms.assetid: a6036ef4-1871-40db-8239-6ddbe8f422f5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e55ad361c9252cfc4989926f90a9fedfd523c7d9
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44313436"
---
# <a name="text-tool-dialog-box-c-image-editor-for-icons"></a>Caixa de diálogo Ferramenta de texto (C++) (Editor de imagens para ícones)

Use o **ferramenta de texto** caixa de diálogo para adicionar texto a um recurso de cursor, bitmap ou ícone.

Para acessar essa caixa de diálogo, abra o [Editor de imagens](../windows/window-panes-image-editor-for-icons.md). Selecione **ferramentas** da **imagem** menu e, em seguida, selecione o **ferramenta de texto** comando.

### <a name="font-button"></a>Botão de fonte

Abre o [caixa de diálogo fonte da ferramenta de texto](../windows/text-tool-font-dialog-box-image-editor-for-icons.md), na qual você pode alterar a fonte, estilo ou tamanho da fonte do cursor. As alterações são aplicadas ao texto exibido na **texto** área.

### <a name="text-area"></a>Área de texto

Exibe o texto que aparece como parte do recurso. Inicialmente, essa área está vazia.

> [!NOTE]
> Se **plano de fundo transparente** for definido, somente o texto será colocado na imagem. Se **tela de fundo opaca** estiver definido, um retângulo delimitador, preenchido com as [cor do plano de fundo](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md), será colocado atrás do texto. Para obter mais informações, consulte [escolhendo opaco e planos de fundo transparentes](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).

Clique duas vezes no **ferramenta de texto** caixa de diálogo para acessar um menu de atalho padrão que contém uma lista de comandos do Windows padrão.

## <a name="requirements"></a>Requisitos

Nenhum

## <a name="see-also"></a>Consulte também

[Editando recursos gráficos](../windows/editing-graphical-resources-image-editor-for-icons.md)