---
title: Criar Declaração/Definição | Microsoft Docs
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: 6b1cdcb2-765e-4b93-8cef-92b861f64eba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 383691a5c2da2af6e4a992ab8766cd99ffa3d781
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408382"
---
# <a name="create-declaration--definition"></a>Criar Declaração/Definição
**O quê:** permite gerar imediatamente a declaração ou a definição de uma função.

**Quando:** você tem uma função que precisa de uma declaração ou vice-versa.

**Por quê:** você pode criar a declaração/definição manualmente, mas isso vai criá-la automaticamente, criando o arquivo de código/cabeçalho, se necessário.

**Como:**

1. Coloque o cursor de texto ou do mouse sobre a função para a qual você deseja criar a declaração ou a definição.

   ![Código realçado](images/createdefinition_highlight.png)

1. Depois, siga um destes procedimentos:
   * **Teclado**
     * Pressione **Ctrl +.** para disparar o menu **Ações Rápidas e Refatorações** e selecione **Criar Declaração/Definição** no menu de contexto.
   * **Mouse**
     * Clique com o botão direito do mouse, selecione o menu **Ações Rápidas e Refatorações** e selecione **Criar Declaração/Definição** no menu de contexto.

1. A declaração/definição da função será criada no arquivo de origem ou de cabeçalho, que você verá em uma janela pop-up de visualização.  Caso o arquivo de origem ou de cabeçalho não exista, ele também será criado e colocado no projeto.

   ![Resultado de Criar Declaração/Definição](images/createdefinition_result.png)
