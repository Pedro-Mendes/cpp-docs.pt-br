---
title: Criando um projeto de DLL MFC | Documentos do Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfcdll.project
dev_langs:
- C++
helpviewer_keywords:
- MFC DLLs [C++], creating projects
- DLLs [C++], MFC
- projects [C++], creating
- DLLs [C++], creating
ms.assetid: 05540b93-4781-4a90-aadf-55158313f5b2
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
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
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: c403d1351c43e043fd3048d342dafcf069951446
ms.lasthandoff: 02/25/2017

---
# <a name="creating-an-mfc-dll-project"></a>Criando um projeto DLL MFC
Uma DLL MFC é um arquivo binário que atua como uma biblioteca compartilhada de funções que podem ser usados simultaneamente por vários aplicativos. A maneira mais fácil de criar um projeto DLL MFC é usar o Assistente de DLL do MFC.  
  
> [!NOTE]
>  A aparência dos recursos no IDE pode depender de suas configurações ativas ou edição e pode diferir dos descritos na Ajuda. Para alterar as configurações, escolha **Importar e Exportar Configurações** no menu **Ferramentas**. Para obter mais informações, consulte [Personalizando configurações de desenvolvimento no Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-an-mfc-dll-project-using-the-mfc-dll-wizard"></a>Para criar um projeto de DLL do MFC usando o Assistente de DLL do MFC  
  
1.  Siga as instruções no tópico da Ajuda [criando um projeto com um Assistente de aplicativo do Visual C++](../../ide/creating-desktop-projects-by-using-application-wizards.md).  
  
 **Observação** no **novo projeto** caixa de diálogo, selecione o `MFC DLL` ícone no painel de modelos para abrir o Assistente de DLL do MFC.  
  
1.  Definir as configurações do aplicativo usando o [configurações do aplicativo](../../mfc/reference/application-settings-mfc-dll-wizard.md) página do [Assistente de DLL do MFC](../../mfc/reference/mfc-dll-wizard.md).  
  
    > [!NOTE]
    >  Ignore esta etapa para manter o Assistente de configurações padrão.  
  
2.  Clique em **concluir** para fechar o assistente e abrir o novo projeto em **Solution Explorer**.  
  
 Quando o projeto é criado, você pode exibir os arquivos criados no Gerenciador de soluções. Para obter mais informações sobre os arquivos que o assistente cria para seu projeto, consulte o arquivo de projeto gerado Readme. txt. Para obter mais informações sobre os tipos de arquivo, consulte [tipos de arquivo criados para projetos do Visual C++](../../ide/file-types-created-for-visual-cpp-projects.md).  
  
## <a name="see-also"></a>Consulte também  
 [Tipos de projeto do Visual C++](http://msdn.microsoft.com/library/912b4ba2-7719-43d5-b087-db33e3f9329a)   
 [Adicionando funcionalidade com assistentes de código](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Páginas de propriedade](../../ide/property-pages-visual-cpp.md)   
 [Implantando aplicativos](http://msdn.microsoft.com/en-us/4ff8881d-0daf-47e7-bfe7-774c625031b4)

