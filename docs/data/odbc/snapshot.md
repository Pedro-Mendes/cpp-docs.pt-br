---
title: "Instantâneo | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ODBC cursor library [ODBC], snapshots
- cursors [ODBC], static
- recordsets, snapshots
- snapshots, support in ODBC
- static cursors
- ODBC recordsets, snapshots
- cursor library [ODBC], snapshots
- snapshots
ms.assetid: b5293a52-0657-43e9-bd71-fe3785b21c7e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c31e08fdda3cef526f46946e45ef956f9ad1adaa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="snapshot"></a>Instantâneo
Um instantâneo é um conjunto de registros que reflete uma exibição estática dos dados que existia no momento em que o instantâneo foi criado. Quando você abre o instantâneo e move para todos os registros, o conjunto de registros que ele contém e seus valores não são alteradas até que você recria o instantâneo chamando **Requery**.  
  
> [!NOTE]
>  Este tópico se aplica às classes MFC ODBC. Se você estiver usando as classes DAO MFC em vez de classes MFC ODBC, consulte [CDaoRecordset::Open](../../mfc/reference/cdaorecordset-class.md#open) para obter uma descrição do conjunto de registros do tipo de instantâneo.  
  
 Você pode criar instantâneos atualizáveis ou somente leitura com as classes de banco de dados. Ao contrário de dynaset, um instantâneo atualizável não reflete as alterações para gravar valores feitos por outros usuários, mas refletir atualizações e exclusões feitas por seu programa. Registros adicionados a um instantâneo não se tornarão visíveis para o instantâneo até que você chame **Requery**.  
  
> [!TIP]
>  Um instantâneo é um cursor estático do ODBC. Cursores estáticos não têm, na verdade, uma linha de dados até que você rola para esse registro. Para garantir que todos os registros são recuperados imediatamente, você pode rolar até o final do seu conjunto de registros e, em seguida, role até o primeiro registro que você deseja ver. No entanto, observe que rolar até o final envolve sobrecarga extra e pode reduzir o desempenho.  
  
 Os instantâneos são mais valiosos quando precisar que os dados permaneçam fixo durante as operações, como quando você está gerando um relatório ou executar cálculos. Mesmo assim, o fonte de dados pode divergir consideravelmente do seu instantâneo, então você pode querer recriá-lo em vez.  
  
 Suporte a instantâneo baseia-se a biblioteca de cursores ODBC, que fornece os cursores estáticos e posicionar atualizações (necessárias para a capacidade de atualização) para qualquer driver de nível 1. A biblioteca de cursores DLL deve ser carregada na memória para esse suporte. Quando você cria um `CDatabase` objeto e chame seu `OpenEx` função de membro, você deve especificar o **CDatabase::useCursorLib** opção do `dwOptions` parâmetro. Se você chamar o **abrir** função de membro, a biblioteca de cursores é carregada por padrão. Se você estiver usando dynasets em vez de instantâneos, você não deseja fazer com que a biblioteca de cursor a ser carregado.  
  
 Instantâneos estão disponíveis somente se a biblioteca de cursores ODBC foi carregada quando o `CDatabase` objeto foi construído ou o driver ODBC que você está usando dá suporte a Cursores estáticos.  
  
> [!NOTE]
>  Para alguns drivers ODBC, os instantâneos (Cursores estáticos) podem não ser atualizáveis. Verifique a documentação do driver para tipos de cursor com suporte e os tipos de simultaneidade, que eles oferecem suporte. Para garantir que os instantâneos atualizáveis, certifique-se de carregar a biblioteca de cursores na memória quando você cria um `CDatabase` objeto. Para obter mais informações, consulte [ODBC: A biblioteca de cursores ODBC](../../data/odbc/odbc-the-odbc-cursor-library.md).  
  
> [!NOTE]
>  Se você quiser usar instantâneos e dynasets, você deve baseá-los em dois `CDatabase` objetos (duas conexões diferentes).  
  
 Para obter mais informações sobre o compartilhamento de instantâneos de propriedades com todos os conjuntos de registros, consulte [conjunto de registros (ODBC)](../../data/odbc/recordset-odbc.md). Para obter mais informações sobre ODBC e instantâneos, incluindo a biblioteca de cursores ODBC, consulte [ODBC](../../data/odbc/odbc-basics.md).  
  
## <a name="see-also"></a>Consulte também  
 [ODBC (conectividade de banco de dados aberto)](../../data/odbc/open-database-connectivity-odbc.md)