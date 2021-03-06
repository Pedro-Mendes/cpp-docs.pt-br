---
title: 'Controles ActiveX MFC: Usando páginas de propriedade de estoque | Microsoft Docs'
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CLSID_CPicturePropPage
- CLSID_CColorPropPage
- CLSID_CFontPropPage
dev_langs:
- C++
helpviewer_keywords:
- picture stock property pages [MFC]
- CLSID_CFontPropPage [MFC]
- color stock property pages [MFC]
- CLSID_CColorPropPage [MFC]
- fonts [MFC], ActiveX controls
- stock properties [MFC], stock property pages
- CLSID_CPicturePropPage [MFC]
- MFC ActiveX controls [MFC], property pages
ms.assetid: 22638d86-ff3e-4124-933e-54b7c2a25968
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6fadc159f0924c3714616778cd1fd148b5ff0e84
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46423051"
---
# <a name="mfc-activex-controls-using-stock-property-pages"></a>Controles ActiveX MFC: usando páginas de propriedade de estoque

Este artigo discute as páginas de propriedade de estoque disponíveis para os controles ActiveX e como usá-los.

>[!IMPORTANT]
> ActiveX é uma tecnologia herdada que não deve ser usada para novos desenvolvimentos. Para obter mais informações sobre tecnologias modernas que substituem as ActiveX, consulte [controles ActiveX](activex-controls.md).

Para obter mais informações sobre como usar páginas de propriedades em um controle ActiveX, consulte os seguintes artigos:

- [Controles ActiveX do MFC: páginas de propriedade](../mfc/mfc-activex-controls-property-pages.md)

- [Controles ActiveX do MFC: adicionando outra página de propriedades personalizada](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)

O MFC fornece três páginas de propriedade de estoque para uso com controles ActiveX: `CLSID_CColorPropPage`, `CLSID_CFontPropPage`, e `CLSID_CPicturePropPage`. Essas páginas exibem uma interface do usuário de estoque cor, fonte e propriedades da imagem, respectivamente.

Para incorporar essas páginas de propriedades em um controle, adicione suas IDs para o código que inicializa a matriz de IDs de página de propriedade do controle. No exemplo a seguir, esse código, localizado no arquivo de implementação de controle (. CPP), inicializa a matriz para conter todos os três páginas de propriedade de estoque e a página de propriedades padrão (denominada `CMyPropPage` neste exemplo):

[!code-cpp[NVC_MFC_AxOpt#21](../mfc/codesnippet/cpp/mfc-activex-controls-using-stock-property-pages_1.cpp)]

Observe que a contagem de páginas de propriedades, na macro BEGIN_PROPPAGEIDS, é 4. Isso representa o número de páginas de propriedade compatível com o controle ActiveX.

Depois de fazer essas modificações, recompile o projeto. Agora, o controle tiver páginas de propriedades para a fonte, imagem e propriedades de cor.

> [!NOTE]
>  Se as páginas de propriedade de estoque de controle não podem ser acessadas, é possível que a DLL do MFC (compartilhadas) não foi registrada corretamente com o sistema operacional atual. Isso geralmente resulta de instalar o Visual C++ em um sistema operacional diferente em execução no momento.

> [!TIP]
>  Se suas páginas de propriedade de estoque não são visíveis (consulte nota anterior), registrar a DLL executando RegSvr32.exe da linha de comando com o nome de caminho completo para a DLL.

## <a name="see-also"></a>Consulte também

[Controles ActiveX do MFC](../mfc/mfc-activex-controls.md)<br/>
[Controles ActiveX do MFC: adicionando propriedades de estoque](../mfc/mfc-activex-controls-adding-stock-properties.md)

