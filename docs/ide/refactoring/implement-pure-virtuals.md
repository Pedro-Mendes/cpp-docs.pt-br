---
title: Implementar virtuais puros | Microsoft Docs
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: ea9b4719-34a3-474a-b4ec-05b1859f80f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 234ae9a67bcbc60ea156fbacb5169d0bd1573a91
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442754"
---
# <a name="implement-pure-virtuals"></a>Implementar Virtuais Puros
**O quê:** permite gerar imediatamente o código necessário para implementar todos os métodos virtuais puros em uma classe.

**Quando:** você deseja herdar de uma classe com funções virtuais puras.

**Por quê:** você pode implementar todas as funções virtuais puras manualmente uma por uma; no entanto, esse recurso gerará todas as assinaturas de método automaticamente.

**Como:**

1. Coloque o cursor de texto ou do mouse sobre a classe na qual deseja implementar as funções virtuais puras da classe base.

   ![Código realçado](images/virtuals_highlight.png)

1. Depois, siga um destes procedimentos:
   * **Teclado**
     * Pressione **Ctrl +.** para disparar o menu **Ações Rápidas e Refatorações** e selecione **Implementar todos os Virtuais Puros para a classe '*ClassName*'** no menu de contexto, em que *ClassName* é o nome da classe selecionada.
   * **Mouse**
     * Clique com o botão direito do mouse, selecione o menu **Ações Rápidas e Refatorações** e selecione **Implementar todos os Virtuais Puros para a classe '*ClassName*'** no menu de contexto, em que *ClassName* é o nome da classe selecionada.

1. As assinaturas de método virtuais puras serão criadas automaticamente, prontas para serem implementadas.

   ![Resultado de Implementar Virtuais Puros](images/virtuals_result.png)
