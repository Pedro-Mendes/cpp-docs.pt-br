---
title: Caixa de diálogo Avançado, Ferramenta de Manifesto, Propriedades de Configuração, Páginas de Propriedades de &lt;Projectname&gt; | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCManifestTool.KeyFile
- VC.Project.VCManifestTool.UpdateFileHashes
- VC.Project.VCManifestTool.UpdateFileHashesSearchPath
- VC.Project.VCManifestTool.ValidateSignature
- VC.Project.VCManifestTool.KeyContainer
dev_langs:
- C++
ms.assetid: 3d587366-05ea-4956-a978-313069660735
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a86489e18220e674f48222ef1590b61d7c5defcf
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716505"
---
# <a name="advanced-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>Caixa de diálogo Avançado, Ferramenta de Manifesto, Propriedades de Configuração, Páginas de Propriedades de &lt;Projectname&gt;
Use essa caixa de diálogo para especificar opções avançadas para [Mt.exe](https://msdn.microsoft.com/library/aa375649).  
  
 Para acessar essa caixa de diálogo da página de propriedades, abra as páginas de propriedades do projeto ou da folha de propriedades. Expanda o nó **Ferramenta de Manifesto** em **Propriedades de Configuração** e, em seguida, selecione **Avançado**.  
  
## <a name="uielement-list"></a>Lista UIElement

- **Atualizar Hashes de Arquivo**

   Usa a opção /hashupdate para especificar que a ferramenta de manifesto calculará o hash dos arquivos especificados em elementos `<file>` e, em seguida, atualizará os atributos de hash com o valor calculado.  
  
- **Atualizar Caminho de Pesquisa de Hashes de Arquivo**

   Especifica o caminho de pesquisa para arquivos referenciados em elementos `<file>`. Essa opção também usa a opção /hashupdate.  
  
## <a name="see-also"></a>Consulte também  
 [\<Elemento file>](/visualstudio/deployment/file-element-clickonce-application)   
 [Manifesto do aplicativo ClickOnce](/visualstudio/deployment/clickonce-application-manifest)   
 [Páginas de propriedades da Ferramenta de Manifesto](../ide/manifest-tool-property-pages.md)   
 [Trabalhando com Propriedades do Projeto](../ide/working-with-project-properties.md)   