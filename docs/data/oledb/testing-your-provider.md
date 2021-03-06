---
title: Testando o provedor | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- OLE DB providers, testing
ms.assetid: bf824fe4-81af-4ffb-beb3-4fa2928dc450
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d175216fedb2e6a9139d970fc7696672576f7423
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042891"
---
# <a name="testing-your-provider"></a>Testando o provedor

Antes de liberar um provedor, você deve executar os testes a seguir, na ordem indicada. Esses testes garantem que as funções de provedor corretamente para a maioria dos usuários em potencial.  
  
1. Teste-o usando um [consumidor](../../data/oledb/creating-an-ole-db-consumer.md) aplicativo escrito com os modelos de consumidor do OLE DB. O consumidor de teste deve cobrir todas as áreas funcionais do seu provedor (todo o código que você tenha adicionado ou modificado).  
  
1. Teste-o usando um aplicativo de consumidor escrito com o ADO. A maioria dos desenvolvedores (especialmente desenvolvedores Microsoft Visual Basic e c# Microsoft) usam o ADO ou ADO.NET para aplicativos de consumidor. O consumidor de teste deve cobrir todas as áreas funcionais do seu provedor. Para obter um exemplo de um aplicativo de consumidor do ADO, consulte [exemplos de código ADO no Microsoft Visual Basic](https://msdn.microsoft.com/library/ms807514.aspx).  
  
1. Execute os testes de conformidade com OLE DB (incluindo testes de conformidade do ADO) garantir que seu provedor satisfaça o nível padrão de 0 para provedores OLE DB. (Para obter uma explicação de nível 0, pesquise por "OLE DB nível 0 testes de conformidade" em [guia do programador do DB OLE](/previous-versions/windows/desktop/ms713643\(v=vs.85\)). Esses testes e a documentação associada são incluídos com o Visual C++ no SDK de acesso a dados. Esses testes também ajudam a garantir que seu provedor seja executado bem quando agregados por outros [provedores de serviço](../../data/oledb/ole-db-resource-pooling-and-services.md) e são especialmente úteis se você modificar ou adicionar propriedades. Para obter mais informações sobre os testes de conformidade, consulte o arquivo Leiame para o SDK de acesso de dados, que está localizado em um dos CDs do Visual Studio.  
  
## <a name="see-also"></a>Consulte também  

[Trabalhando com modelos de provedor do OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)