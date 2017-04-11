---
title: Ferramentas de vinculador LNK1123 erro | Documentos do Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1123
dev_langs:
- C++
helpviewer_keywords:
- LNK1123
ms.assetid: fe47af69-0f42-4792-9133-541192cd8514
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: f31e8946dcf8d8333eb62df3cac9b995cccdef3b
ms.lasthandoff: 02/25/2017

---
# <a name="linker-tools-error-lnk1123"></a>Erro das Ferramentas de Vinculador LNK1123
falha durante a conversão para COFF: arquivo inválido ou corrompido  
  
 Os arquivos de entrada devem ter o formato COFF (Common Object File Format). Se um arquivo de entrada não for COFF, o vinculador tenta converter automaticamente objetos OMF de 32 bits para COFF ou executa CVTRES.EXE para converter arquivos de recurso. Essa mensagem indica que o vinculador não pode converter o arquivo. Isso também ocorre ao usar uma versão incompatível do CVTRES.EXE de outra instalação do Visual Studio, do Windows Development Kit ou do .NET Framework.  
  
> [!NOTE]
>  Se você estiver executando uma versão anterior do Visual Studio, pode não haver suporte para a conversão automática.  
  
### <a name="to-fix-the-problem"></a>Para corrigir o problema  
  
-   Aplica todos os service packs e atualizações para sua versão do Visual Studio. Isso é especialmente importante para o Visual Studio 2010.  
  
-   Tente compilar com a vinculação incremental desabilitada. Na barra de menus, escolha **Projeto**, **Propriedades**. No **páginas de propriedade** caixa de diálogo caixa, expanda **propriedades de configuração**, **vinculador**. Altere o valor de **habilitar vinculação Incremental** para **não**.  
  
-   Verifique se a versão do CVTRES.EXE encontrada primeiro na variável de ambiente PATH combina com a versão das ferramentas de compilação ou com a versão do Conjunto de Ferramentas de Plataforma, usado no projeto.  
  
-   Tente desativar a opção de inserir manifesto. Na barra de menus, escolha **Projeto**, **Propriedades**. No **páginas de propriedade** caixa de diálogo caixa, expanda **propriedades de configuração**, **ferramenta de manifesto**, **de entrada e saída**. Altere o valor de **Inserir manifesto** para **não**.  
  
-   Verifique se o tipo de arquivo é válido. Por exemplo, verifique se um objeto OMF é de 32 bits e não de 16 bits. Para obter mais informações, consulte [. Arquivos obj como entrada de vinculador](../../build/reference/dot-obj-files-as-linker-input.md) e [Microsoft PE e COFF especificação](http://go.microsoft.com/fwlink/p/?LinkId=93292).  
  
-   Verifique se o arquivo não está corrompido. Recompile-o, se necessário.  
  
## <a name="see-also"></a>Consulte também  
 [. Arquivos obj como entrada de vinculador](../../build/reference/dot-obj-files-as-linker-input.md)   
 [Referência de EDITBIN](../../build/reference/editbin-reference.md)   
 [Referência de DUMPBIN](../../build/reference/dumpbin-reference.md)