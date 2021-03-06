---
title: Criando um consumidor sem usar um assistente | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumers, creating
ms.assetid: e8241cfe-5faf-48f8-9de3-241203de020b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a20abb132d0446874b099119dc6c54979aef4638
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46023586"
---
# <a name="creating-a-consumer-without-using-a-wizard"></a>Criando um consumidor sem usar um assistente

O exemplo a seguir pressupõe que você está adicionando o suporte de consumidor do OLE DB a um projeto existente do ATL. Se você quiser adicionar suporte de consumidor do OLE DB para um aplicativo do MFC, você deve executar o Assistente de aplicativo do MFC, que cria todo o suporte necessário e invoca as rotinas MFC necessárias para executar o aplicativo.  
  
Para adicionar suporte de consumidor do OLE DB sem usar a ATL OLE DB Assistente de consumidor:  
  
- Em seu arquivo Stdafx. h, acrescente o seguinte `#include` instruções:  
  
    ```cpp  
    #include <atlbase.h>  
    #include <atldbcli.h>  
    #include <atldbsch.h> // if you are using schema templates  
    ```  
  
Programaticamente, um consumidor normalmente executa a seguinte sequência de operações:  
  
- Crie uma classe de registro de usuário que associa as colunas para variáveis locais. Neste exemplo, `CMyTableNameAccessor` é a classe de registro de usuário (consulte [registros de usuário](../../data/oledb/user-records.md)). Essa classe contém o mapa de coluna e o mapa de parâmetro. Declarar um membro de dados na classe de registro de usuário de cada campo que você especificar no seu mapa de coluna; para cada um desses membros de dados, também declare um membro de dados de status e um membro de dados de comprimento. Para obter mais informações, consulte [membros de dados de Status de campo em acessadores de Wizard-Generated](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md).  
  
    > [!NOTE]
    >  Se você escrever seu próprios consumidor, as variáveis de dados devem vir antes das variáveis de status e o comprimento.  
  
- Crie uma instância de uma fonte de dados e uma sessão. Decidir o tipo de conjunto de linhas e o acessador de usar e, em seguida, criar uma instância de um conjunto de linhas usando [CCommand](../../data/oledb/ccommand-class.md) ou [CTable](../../data/oledb/ctable-class.md):  
  
    ```cpp  
    CDataSource ds;  
    CSession ss;  
    class CMyTableName : public CCommand<CAccessor<CMyTableNameAccessor>>  
    ```  
  
- Chamar `CoInitialize` ao inicializar COM. Isso geralmente é chamado no código principal. Por exemplo:  
  
    ```cpp  
    HRESULT hr = CoInitialize(NULL);  
    ```  
  
- Chame [cdatasource:: Open](../../data/oledb/cdatasource-open.md) ou uma de suas variações.  
  
- Abra uma conexão à fonte de dados, abrir a sessão e abra e inicializar o conjunto de linhas (e se um comando, também executá-lo):  
  
    ```cpp  
    hr = ds.Open();  
    hr = ss.Open(ds);  
    hr = rs.Open();            // (Open also executes the command)  
    ```  
  
- Opcionalmente, o conjunto de linhas propriedades usando `CDBPropSet::AddProperty` e passá-los como um parâmetro para `rs.Open`. Para obter um exemplo de como isso é feito, consulte GetRowsetProperties na [Consumer Wizard-Generated métodos](../../data/oledb/consumer-wizard-generated-methods.md).  
  
- Agora você pode usar o conjunto de linhas para recuperar/manipular os dados.  
  
- Quando seu aplicativo for concluído, feche a conexão, sessão e conjunto de linhas:  
  
    ```cpp  
    rs.Close();  
    ss.Close();  
    ds.Close();  
    ```  
  
     Se você estiver usando um comando, você talvez queira chamar `ReleaseCommand` depois de `Close`. O exemplo de código [ccommand:: Close](../../data/oledb/ccommand-close.md) mostra como chamar `Close` e `ReleaseCommand`.  
  
- Chamar `CoUnInitialize` Cancelar COM. a Isso geralmente é chamado no código principal.  
  
    ```  
    CoUninitialize();  
    ```  
  
## <a name="see-also"></a>Consulte também  

[Criando um consumidor do OLE DB](../../data/oledb/creating-an-ole-db-consumer.md)