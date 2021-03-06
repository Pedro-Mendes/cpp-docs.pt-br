---
title: Redistribuindo um aplicativo ATL | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ATL, redistributing
- redistributing ATL
- redistributing OLE DB templates
- OLE DB templates, redistributing
ms.assetid: 9a696b22-2345-43ec-826b-be7cb8cfd676
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6db7e553d2f9e268b39bb9c02e70bb59815aef3a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405926"
---
# <a name="redistributing-an-atl-application"></a>Redistribuindo um aplicativo ATL

Do Visual Studio 2012 em diante, a ATL (Active Template Library) é uma biblioteca somente de cabeçalho. Os projetos ATL não têm uma opção Link Dinâmico para ATL. Nenhuma biblioteca ATL redistribuível é necessária.

Se você redistribuir um aplicativo executável ATL, precisará registrar o arquivo .exe (e os controles dentro dele) emitindo o seguinte comando:

```
filename /regserver
```

em que `filename` é o nome do arquivo executável.

No Visual Studio 2010, um projeto ATL pode ser compilado para uma configuração de MinDependency ou de MinSize. Uma configuração de MinDependency é o que você obtém quando define a propriedade **Uso da ATL** como **Link Estático para ATL** na página de propriedades **Geral** e define a propriedade **Biblioteca em Tempo de Execução** como **Multi-threaded (/MT)** na página de propriedades **Geração de Código** (pasta C/C++).

Uma configuração de MinSize é o que você obtém quando define a propriedade **Uso da ATL** como **Link Dinâmico para ATL** na página de propriedades **Geral** ou define a propriedade **Biblioteca em Tempo de Execução** como **DLL Multi-threaded (/MD)** na página de propriedades **Geração de Código** (pasta C/C++).

MinSize torna o arquivo de saída o menor possível, mas exige que ATL100.dll e Msvcr100.dll (se você selecionou a opção **DLL Multi-threaded (/MD)**) estejam no computador de destino. ATL100.dll deve ser registrada no computador de destino para garantir que todas as funcionalidades da ATL estejam presente. ATL100.dll contém exportações ANSI e Unicode.

Caso você compile o projeto de Modelos ATL ou OLE DB para um destino MinDependency, não precisará instalar e registrar ATL100.dll no computador de destino, embora você possa obter uma imagem de programa maior.

Se você redistribuir um aplicativo executável ATL, precisará registrar o arquivo .exe (e os controles dentro dele) emitindo o seguinte comando:

```
filename /regserver
```

em que `filename` é o nome do arquivo executável.

## <a name="see-also"></a>Consulte também

[Redistribuindo arquivos do Visual C++](../ide/redistributing-visual-cpp-files.md)