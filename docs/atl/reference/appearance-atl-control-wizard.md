---
title: Aparência, o Assistente de controle ATL | Microsoft Docs
ms.custom: ''
ms.date: 08/31/2018
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.control.misc
dev_langs:
- C++
helpviewer_keywords:
- ATL Control Wizard, appearance
ms.assetid: cc16d7ff-74d7-4c15-9ebd-4b19201ff457
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 132930c1ad7d4b9fc4ae9c3a875bbd2c6ec6f9d2
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43755119"
---
# <a name="appearance-atl-control-wizard"></a>Aparência, o Assistente de controle ATL

Insira "Resultados da pesquisa" Resumo aqui.

Use esta página do Assistente para identificar as opções de elemento de usuário adicionais para o controle. Esta página está disponível para controles identificados como **controles padrão** sob **tipo de controle** no [opções, Assistente de controle ATL](../../atl/reference/options-atl-control-wizard.md) página.

## <a name="uielement-list"></a>Lista UIElement

- **Exibir status**

   Define a aparência do controle dentro do contêiner.

   - **Opaco**: define o VIEWSTATUS_OPAQUE bit na [VIEWSTATUS](/windows/desktop/api/ocidl/ne-ocidl-tagviewstatus) enumeração e desenha o retângulo de controle inteiro passado para o [CComControlBase::OnDraw](../../atl/reference/ccomcontrolbase-class.md#ondraw) método. O controle aparece completamente opaco e nenhum contêiner mostra atrás dos limites do controle.

      Essa configuração ajuda o contêiner de desenhar o controle mais rapidamente. Se essa opção não for selecionada, o controle pode conter partes transparentes.

      Somente um controle opaco pode ter um plano de fundo sólido.

   - **Plano de fundo sólido**: define o VIEWSTATUS_SOLIDBKGND bit na enumeração Exibir status. Plano de fundo do controle é exibido como uma cor sólida com nenhum padrão.

      Essa opção está disponível somente se o **opaco** também está selecionada.

- **Adicionar um controle com base em**

   Define o controle deve ser baseado em um tipo de controle do Windows com a adição de um [CContainedWindow](ccontainedwindowt-class.md) membro de dados para a classe que implementa o controle. Ele também adiciona um mapa de mensagem e funções de manipulador de mensagens para lidar com mensagens do Windows para o controle. Na lista, escolha o tipo de controle de Windows que você deseja criar, se houver.

   - **Button**

   - **ListBox**

   - **SysAnimate32**

   - **SysListView32**

   - **ComboBox**

   - **RichEdit**

   - **SysDateTimePick32**

   - **SysMonthCal32**

   - **ComboBoxEx32**

   - **ScrollBar**

   - **SysHeader32**

   - **SysTabControl32**

   - **Editar**

   - **Estático**

   - **SysIPAddress32**

   - **SysTreeView32**

- **Status Misc**

   Define as opções de aparência e comportamento adicionais para o controle.

   - **Invisível em tempo de execução**: define o controle seja invisível em tempo de execução. Você pode usar controles invisíveis para executar operações em segundo plano, como acionar eventos em intervalos regulares.

   - **Atua como o botão**: define o OLEMISC_ACTSLIKEBUTTON bit na [OLEMISC](/windows/desktop/api/oleidl/ne-oleidl-tagolemisc) enumeração para ativar um controle atuar como um botão. Se o contêiner foi marcado como site de cliente do controle como um botão padrão, esta opção permite que o controle de botão para exibir a próprio como um botão padrão por desenhar-se com um quadro mais espesso. Ver [CComControlBase::GetAmbientDisplayAsDefault](../../atl/reference/ccomcontrolbase-class.md#getambientdisplayasdefault) para obter mais informações.

   - **Atua como o rótulo**: define o OLEMISC_ACTSLIKELABEL bit na enumeração OLEMISC para ativar um controle substituir o rótulo de nativa do contêiner. O contêiner determina o que fazer com esse sinalizador, se nada.

- **Outros**

   Define opções de comportamento adicional para o controle.

   - **Normalizados DC**: define o controle para criar um contexto de dispositivo normalizado quando ele é chamado para desenhar a mesmo. Essa ação padroniza a aparência do controle, mas ele torna o desenho menos eficiente.

   - **Somente a janela**: Especifica que o controle não pode ser sem janelas. Se você não selecionar essa opção, o controle é automaticamente sem janelas em contêineres que dão suporte a objetos sem janelas e é automaticamente em janelas em contêineres que não dão suporte a objetos sem janelas. Selecionar essa opção força o controle ser em janelas, mesmo em contêineres que oferecem suporte a objetos sem janelas.

   - **Inserível**: Selecione esta opção para que seu controle apareça na **Inserir objeto** caixa de diálogo de aplicativos como Word e Excel. Seu controle, em seguida, pode ser inserido por qualquer aplicativo que dá suporte a objetos inseridos por meio da caixa de diálogo.

## <a name="see-also"></a>Consulte também

[Assistente de Controle da ATL](../../atl/reference/atl-control-wizard.md)<br/>
[Exemplo de SUBEDIT: Superclassificar um controle padrão do Windows](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit)

