---
title: Criando um consumidor simples | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumers, creating
ms.assetid: ae32d657-72ea-4db8-9839-75cb5cff68ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 091a529bdd8eb80158fc093fd450e496bc4f18c2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46052342"
---
# <a name="creating-a-simple-consumer"></a>Criando um consumidor simples

Use o OLE DB Assistente de cliente ATL e ATL Project Wizard para gerar um consumidor de modelos OLE DB.  
  
### <a name="to-create-a-console-application-for-an-ole-db-consumer"></a>Para criar um aplicativo de console para um consumidor OLE DB  
  
1. No menu **Arquivo**, clique em **Novo** e clique em **Projeto**.  
  
     A caixa de diálogo **Novo Projeto** é exibida.  
  
1. No painel de tipos de projeto, clique o **projetos do Visual C++** pasta e clique o **Win32 Project** ícone no painel de modelos. No **nome** , digite o nome do seu projeto, por exemplo, **MyCons**.  
  
1. Clique em **OK**.  
  
     O Assistente de projeto do Win32 é exibida.  
  
1. Sobre o **configurações do aplicativo** página, selecione **aplicativo de Console**e, em seguida, selecione **adicionar suporte ATL**.  
  
1. Clique em **concluir** para fechar o assistente e gerar o projeto.  
  
Em seguida, use o ATL OLE DB consumidor Wizard para adicionar um objeto de consumidor do OLE DB.  
  
#### <a name="to-create-a-consumer-with-the-atl-ole-db-consumer-wizard"></a>Para criar um consumidor com a ATL OLE DB Assistente de consumidor  
  
1. No modo de exibição de classe, clique com botão direito do `MyCons` projeto.  
  
1. No menu de atalho, clique em **Add**e, em seguida, clique em **Adicionar classe**.  
  
     O **Adicionar classe** caixa de diálogo é exibida.  
  
1. No painel de categorias, clique em **Visual C++**, clique no **ATL OLE DB consumidor** ícone no painel de modelos e, em seguida, clique **abrir**.  
  
     O ATL OLE DB consumidor Wizard é exibida.  
  
1. Clique o **fonte de dados** botão.  
  
     O **propriedades de vínculo de dados** caixa de diálogo é exibida.  
  
1. No **propriedades de vínculo de dados** caixa de diálogo caixa, faça o seguinte:  
  
    -   Sobre o **provedor** guia, especifique um provedor OLE DB.  
  
    -   Sobre o **Conexão** , especifique o nome do servidor, a ID de logon e a senha para sua fonte de dados e o banco de dados no servidor.  
  
    > [!NOTE]
    >  Há um problema de segurança com o **permitir salvamento de senha** recurso da **propriedades de vínculo de dados** caixa de diálogo. No **insira as informações de logon para o servidor**, há dois botões de opção: **segurança integrada Use Windows NT** e **usar um determinado nome de usuário e senha**.  
  
    > [!NOTE]
    >  Se você selecionar **usar um determinado nome de usuário e senha**, você tem a opção de salvar a senha (usando o **permitir salvamento de senha** caixa de seleção); no entanto, essa opção não é segura. É recomendável que você selecione **a segurança integrada Use Windows NT**; essa opção usa o Windows NT para verificar sua identidade.  
  
    > [!NOTE]
    >  Se você não pode usar segurança integrada do Windows NT, você deve usar um aplicativo de camada intermediária para solicitar ao usuário a senha ou para armazenar a senha em um local com mecanismos de segurança para ajudar a protegê-lo (em vez de no código-fonte).  
  
     Depois de selecionar o provedor e outras configurações, clique em **Conexão de teste** para verificar as seleções feitas nas páginas de caixa de diálogo anterior. Se o **resultados** caixa relatórios `Test connection succeeded`, clique em **Okey** para criar o link de dados.  
  
     O **Selecionar objeto de banco de dados** caixa de diálogo é exibida.  
  
1. Use o controle de árvore para selecionar uma tabela, exibição ou procedimento armazenado. Para fins deste procedimento, selecione a tabela de produtos do banco de dados Northwind.  
  
1. Clique em **OK**. Isso retorna para o ATL OLE DB Assistente de consumidor.  
  
1. O assistente for concluído os nomes dos `Class` e **arquivo. h** com base no nome da tabela, exibição ou procedimento armazenado que você selecionou. Você pode editar esses nomes se você quiser.  
  
9. Desmarque a **atribuída** caixa de seleção para que o assistente cria o código consumidor usando [classes de modelo de banco de dados OLE](../../data/oledb/ole-db-consumer-templates-reference.md) em vez do padrão [atributos de consumidor do OLE DB](../../windows/ole-db-consumer-attributes.md).  
  
10. Sob **tipo**, selecione **comando**.  
  
     O assistente cria uma [CCommand](../../data/oledb/ccommand-class.md)-com base em consumo, se você selecionar **comando** ou uma [CTable](../../data/oledb/ctable-class.md)-com base em consumo, se você selecionar **tabela**. A classe de tabela ou o comando é nomeada após o objeto selecionado, mas você pode editar o nome.  
  
11. Sob **suporte**, deixe o **alteração**, **inserir**, e **excluir** caixas desmarcadas.  
  
     Selecione o **alteração**, **inserir**, e **excluir** caixas de seleção para suporte a alteração, inserção e exclusão de registros no conjunto de linhas, se necessário. Para obter mais informações sobre a gravação de dados para os dados de armazenamento, consulte [atualizando conjuntos de linhas](../../data/oledb/updating-rowsets.md).  
  
12. Clique em **concluir** para criar o consumidor.  
  
O assistente gera uma classe de comando e uma classe de registro de usuário, conforme mostrado na [Consumer Wizard-Generated Classes](../../data/oledb/consumer-wizard-generated-classes.md). A classe de comando terá o nome que você inseriu na `Class` caixa no Assistente (nesse caso, `CProducts`), e a classe de registro de usuário terá um nome no formato "*ClassName*acessador" (nesse caso, `CProductsAccessor`).  
  
> [!NOTE]
>  O assistente coloca Products.h a seguinte linha:  
  
```cpp  
#error Security Issue: The connection string may contain a password  
```  
  
> [!NOTE]
>  Essa linha impede que o aplicativo de consumidor da compilação e para lembrá-lo a cadeia de conexão para senhas codificadas. Depois de verificar a cadeia de conexão, você pode remover esta linha de código.  
  
## <a name="see-also"></a>Consulte também  

[Criando um consumidor do OLE DB usando um assistente](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)