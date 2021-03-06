---
title: Testando uma caixa de diálogo (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Test Dialog command
- testing, dialog boxes
- dialog boxes [C++], testing
ms.assetid: 45034ee9-c554-4f4b-8c46-6ddefdee8951
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ca5e8cfc2a08b01d7917d540c61e04837169a457
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438594"
---
# <a name="testing-a-dialog-box-c"></a>Testando uma caixa de diálogo (C++)

Quando você estiver criando uma caixa de diálogo, você pode simular e testar seu comportamento de tempo de execução sem compilar seu programa. Nesse modo, você pode:

- Digite o texto, selecione nas listas de caixa de combinação, ativar ou desativar as opções e escolha os comandos.

- Teste a ordem de tabulação.

- Teste o agrupamento de controles como botões de opção e caixas de seleção.

- Teste os atalhos de teclado para controles na caixa de diálogo.

   > [!NOTE]
   > Conexões com o código de caixa de diálogo feito com assistentes não são incluídas na simulação.

Quando você testa uma caixa de diálogo, ele normalmente é exibida em um local relativo à janela principal do programa. Se você tiver definido a caixa de diálogo **alinhamento absoluto** propriedade **verdadeiro**, a caixa de diálogo é exibida em uma posição relativa ao canto superior esquerdo da tela.

### <a name="to-test-a-dialog-box"></a>Para testar uma caixa de diálogo

1. Quando o **caixa de diálogo** editor é a janela ativa, na barra de menus, escolha **formato** > **caixa de diálogo de teste**.

2. Para encerrar a simulação, pressione **Esc**, ou basta escolher o **fechar** botão na caixa de diálogo que você está testando.

Para obter informações sobre como adicionar recursos a projetos gerenciados, consulte [recursos em aplicativos de área de trabalho](/dotnet/framework/resources/index).

## <a name="requirements"></a>Requisitos

Win32

## <a name="see-also"></a>Consulte também

[Controles em caixas de diálogo](../windows/controls-in-dialog-boxes.md)<br/>
[Editor de caixa de diálogo](../windows/dialog-editor.md)<br/>
[Mostrando ou ocultando a barra de ferramentas do Editor de Caixa de Diálogo](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)