---
title: 'Páginas de propriedades de MIDL: Geral | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCMidlTool.PreprocessorDefinitions
- VC.Project.VCMidlTool.DefaultCharType
- VC.Project.VCMidlTool.WarnAsError
- VC.Project.VCMidlTool.AdditionalIncludeDirectories
- VC.Project.VCMidlTool.WarningLevel
- VC.Project.VCMidlTool.MkTypLibCompatible
- VC.Project.VCMidlTool.GenerateStublessProxies
- VC.Project.VCMidlTool.SuppressStartupBanner
- VC.Project.VCMidlTool.TargetEnvironment
- VC.Project.VCMidlTool.OVERWRITEStandardIncludePath
dev_langs:
- C++
helpviewer_keywords:
- MIDL, property pages
ms.assetid: 0692484c-a7e6-4270-8df7-981589368399
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 32e1c743844d252b391a4a747d803ba0e8c81c54
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46431418"
---
# <a name="midl-property-pages-general"></a>Páginas de propriedade MDL: geral

A página de propriedades **Geral** na pasta **MIDL** especifica as seguintes opções do compilador MIDL:

- Definições de pré-processador [(/D](https://msdn.microsoft.com/library/windows/desktop/aa367321))

- Diretórios de inclusão adicionais ([/I](https://msdn.microsoft.com/library/windows/desktop/aa367328))

- Ignorar caminho de inclusão padrão ([/no_def_idir](https://msdn.microsoft.com/library/windows/desktop/aa367347))

- Compatível com MkTypLib ([/mktyplib203](https://msdn.microsoft.com/library/windows/desktop/aa367332))

- Nível de aviso ([/W](https://msdn.microsoft.com/library/windows/desktop/aa367383))

- Avisar como erro ([/WX](https://msdn.microsoft.com/library/windows/desktop/aa367387))

- Suprimir faixa de inicialização ([/nologo](https://msdn.microsoft.com/library/windows/desktop/aa367341))

- Tipo de caractere MIDL ([/char](https://msdn.microsoft.com/library/windows/desktop/aa367314))

- Ambiente de destino ([/env](https://msdn.microsoft.com/library/windows/desktop/aa367323))

- Gerar proxies sem stub ([/Oicf](https://msdn.microsoft.com/library/windows/desktop/aa367352))

Para obter informações sobre como acessar a página de propriedades **Geral** na pasta **MIDL**, confira [Trabalhando com propriedades do projeto](../ide/working-with-project-properties.md).

Para obter informações sobre como acessar as opções de MIDL para projetos do C++ de forma programática, confira o objeto <xref:Microsoft.VisualStudio.VCProjectEngine.VCMidlTool>.

## <a name="see-also"></a>Consulte também

[Páginas de propriedades de MIDL](../ide/midl-property-pages.md)