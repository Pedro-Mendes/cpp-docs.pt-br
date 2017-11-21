---
title: -/showIncludes (a lista inclui arquivos) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLWCECompilerTool.ShowIncludes
- VC.Project.VCCLCompilerTool.ShowIncludes
- /showincludes
dev_langs: C++
helpviewer_keywords:
- include files
- /showIncludes compiler option [C++]
- include files, displaying in compilation
- -showIncludes compiler option [C++]
- showIncludes compiler option [C++]
ms.assetid: 0b74b052-f594-45a6-a7c7-09e1a319547d
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 72f80202d2d1c8018e9c145951664d335ac759b7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="showincludes-list-include-files"></a>/showIncludes (listar arquivos de inclusão)
Faz com que o compilador gerar uma lista de inclusão de arquivos. Aninhados incluem arquivos também são exibidos (arquivos inclusos dos arquivos que você incluir).  
  
## <a name="syntax"></a>Sintaxe  
  
```  
/showIncludes  
```  
  
## <a name="remarks"></a>Comentários  
 Quando um arquivo de inclusão é encontrado durante a compilação, uma mensagem é saída, por exemplo:  
  
```  
Note: including file: d:\MyDir\include\stdio.h  
```  
  
 Aninhados incluem arquivos são indicados por um recuo, um espaço para cada nível de aninhamento, por exemplo:  
  
```  
Note: including file: d:\temp\1.h  
Note: including file:  d:\temp\2.h  
```  
  
 Nesse caso, `2.h` foi incluído de dentro de `1.h`, portanto, o recuo.  
  
 O **/showIncludes** opção emite para `stderr`, não `stdout`.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para definir esta opção do compilador no ambiente de desenvolvimento do Visual Studio  
  
1.  Abra a caixa de diálogo **Páginas de Propriedades** do projeto. Para obter detalhes, consulte [trabalhar com propriedades do projeto](../../ide/working-with-project-properties.md).  
  
2.  Clique o **C/C++** pasta.  
  
3.  Clique o **avançado** página de propriedades.  
  
4.  Modificar o **Mostrar inclui** propriedade.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Para definir essa opção do compilador via programação  
  
-   Consulte <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ShowIncludes%2A>.  
  
## <a name="see-also"></a>Consulte também  
 [Opções do compilador](../../build/reference/compiler-options.md)   
 [Definindo opções do compilador](../../build/reference/setting-compiler-options.md)