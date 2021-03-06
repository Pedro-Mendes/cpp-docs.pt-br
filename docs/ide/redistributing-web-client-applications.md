---
title: Redistribuindo aplicativos cliente Web | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Web applications [C++], redistributing
- deploying applications [C++], Web applications
- Internet applications [C++], redistributing
- application deployment [C++], Web applications
ms.assetid: fe05988b-dee8-4a46-b381-016b5103a6bf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cdde0f8d4edc13e8c1e1a53d8f4393dc7c2dac40
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46372464"
---
# <a name="redistributing-web-client-applications"></a>Redistribuindo aplicativos de cliente Web

Se o aplicativo usa as classes MFC que implementam o controle WebBrowser (por exemplo, `CHtmlView` ou `CHtmlEditView`), o Microsoft Internet Explorer 4.0 ou posterior precisa, pelo menos, estar minimamente instalado no computador de destino.

A instalação da última versão do Internet Explorer também garante que o computador de destino tenha os últimos arquivos de controle comum.

Mais informações sobre como instalar os componentes mínimos do Internet Explorer estão disponíveis no seguinte artigo da Base de Dados de Conhecimento:

- Q185375, HOWTO: Criar uma instalação única de EXE do Internet Explorer ([http://support.microsoft.com/support/kb/articles/q185/3/75.asp](http://support.microsoft.com/support/kb/articles/q185/3/75.asp))

Encontre outros artigos da Base de Dados de Conhecimento na Biblioteca MSDN ou em [http://support.microsoft.com](http://support.microsoft.com).

## <a name="see-also"></a>Consulte também

[Implantando aplicativos da área de trabalho](../ide/deploying-native-desktop-applications-visual-cpp.md)