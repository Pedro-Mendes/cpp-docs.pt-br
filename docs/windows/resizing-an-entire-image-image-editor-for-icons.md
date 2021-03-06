---
title: Redimensionando uma imagem inteira (Editor de imagens para ícones) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Image editor [C++], resizing images
- size [C++], images
- images [C++], resizing
- resizing images
ms.assetid: 10782937-7eb4-4340-bdec-618ee7d7904b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2326918b6efd4c8da5f74527166d8f373dbacefc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376832"
---
# <a name="resizing-an-entire-image-image-editor-for-icons"></a>Redimensionando uma imagem inteira (editor de imagens para ícones)

### <a name="to-resize-an-entire-image-using-the-properties-window"></a>Para redimensionar uma imagem inteira usando a janela Propriedades

1. Abra a imagem cujas propriedades você deseja alterar.

2. No **largura** e **altura** nas caixas de [janela propriedades](/visualstudio/ide/reference/properties-window), digite as dimensões que você deseja.

   Se você está aumentando o tamanho da imagem, o **imagem** editor estende a imagem à direita, para baixo, ou ambos e preenche a nova região com a cor de plano de fundo atual. A imagem não é estendida.

   Se você está diminuindo o tamanho da imagem, o **imagem** editor corta a imagem na borda direita ou inferior, ou ambos.

   > [!NOTE]
   > Você pode usar o **largura** e **altura** propriedades redimensionar somente a imagem inteira, não para redimensionar uma seleção parcial.

Para obter informações sobre como adicionar recursos a projetos gerenciados, consulte [recursos em aplicativos de área de trabalho](/dotnet/framework/resources/index) na *guia do desenvolvedor do .NET Framework*. Para obter informações sobre como adicionar manualmente os arquivos de recursos a projetos gerenciados, acessar recursos, exibir recursos estáticos e atribuir cadeias de caracteres de recurso a propriedades, consulte [criando arquivos de recursos para aplicativos de área de trabalho](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Para obter informações sobre globalização e localização de recursos em aplicativos gerenciados, consulte [Globalizing e Localizando aplicativos do .NET Framework](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Requisitos

Nenhum

## <a name="see-also"></a>Consulte também

[Teclas de aceleração](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Redimensionando uma imagem](../windows/resizing-an-image-image-editor-for-icons.md)