---
title: Colocando o controle em uma página da Web (ATL Tutorial, parte 7) | Microsoft Docs
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 50dc4c95-c95b-4006-b88a-9826f7bdb222
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: edc45522aaff12077de6115105b344ecf41e187e
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43762818"
---
# <a name="putting-the-control-on-a-web-page-atl-tutorial-part-7"></a>Colocando o controle em uma página da Web (Tutorial ATL, parte 7)

O controle está concluído. Para ver seu controle funcionar em uma situação de mundo real, coloque-o em uma página da Web. Um arquivo HTML que contém o controle foi criado quando você definiu o seu controle. Abrir o arquivo Polyctl **Gerenciador de soluções**, e você pode ver seu controle em uma página da Web.

Nesta etapa, você criará um script de página da Web para responder a eventos. Você também modificará o controle para permitir que o Internet Explorer sabe que o controle é seguro para script.

## <a name="scripting-the-web-page"></a>A página da Web de script

O controle não faz nada ainda. Portanto, altere a página da Web para responder aos eventos que você enviar.

#### <a name="to-script-the-web-page"></a>Para gerar script de página da Web

1. Abra o Polyctl. e selecione o modo de exibição HTML. Adicione as seguintes linhas ao código HTML. Eles devem ser adicionados após `</OBJECT>` , mas antes `</BODY>`.

    ```html
    <SCRIPT LANGUAGE="VBScript">
    <!--
        Sub PolyCtl_ClickIn(x, y)
            PolyCtl.Sides = PolyCtl.Sides + 1
        End Sub
        Sub PolyCtl_ClickOut(x, y)
            PolyCtl.Sides = PolyCtl.Sides - 1
        End Sub
    -->
    </SCRIPT>
    ```

2. Salve o arquivo HTM.

Você adicionou código VBScript que obtém a propriedade dos lados do controle e aumenta o número de lados por um, se você clicar no controle. Se você clicar fora do controle, você reduzir o número de lados por um.

## <a name="indicating-that-the-control-is-safe-for-scripting"></a>Que indica que o controle é seguro para script

Você pode exibir a página da Web com o controle no Internet Explorer ou, mais conveniente, usar a exibição de navegador da Web compilada no Visual C++. Para ver seu controle no modo de exibição de navegador da Web, clique com botão direito Polyctl e clique em **exibir no navegador**.

Com base em suas configurações de segurança atuais do Internet Explorer, você poderá receber um alerta de segurança caixa de diálogo informando que o controle pode não ser seguro para script e poderia potencialmente causar danos. Por exemplo, se você tivesse um controle que exibia um arquivo, mas também tinha um `Delete` método que um arquivo excluído, seria seguro se você simplesmente o exibisse em uma página. Não seria seguro criar um script, no entanto, porque alguém poderia chamar o `Delete` método.

> [!IMPORTANT]
> Para este tutorial, você pode alterar as configurações de segurança no Internet Explorer para executar controles ActiveX não marcados como seguros. No painel de controle, clique em **propriedades da Internet** e clique em **segurança** para alterar as configurações apropriadas. Quando você concluiu o tutorial, altere as configurações de segurança para seu estado original.

Você pode programaticamente alertar do Internet Explorer que ele não precisa exibir a caixa de diálogo de alerta de segurança para este controle específico. Você pode fazer isso com o `IObjectSafety` interface e o ATL fornece uma implementação dessa interface na classe [IObjectSafetyImpl](../atl/reference/iobjectsafetyimpl-class.md). Para adicionar a interface ao seu controle, adicione `IObjectSafetyImpl` à sua lista de classes herdadas e adicione uma entrada para ele no seu mapa COM.

#### <a name="to-add-iobjectsafetyimpl-to-the-control"></a>Para adicionar IObjectSafetyImpl ao controle

1. Adicione a seguinte linha ao final da lista de classes herdadas em polyctl. H e adicione uma vírgula na linha anterior:

[!code-cpp[NVC_ATL_Windowing#62](../atl/codesnippet/cpp/putting-the-control-on-a-web-page-atl-tutorial-part-7_1.h)]

2. Adicione a seguinte linha ao mapa de COM em polyctl. H:

[!code-cpp[NVC_ATL_Windowing#63](../atl/codesnippet/cpp/putting-the-control-on-a-web-page-atl-tutorial-part-7_2.h)]

## <a name="building-and-testing-the-control"></a>Compilar e testar o controle

Compile o controle. Depois que a compilação for concluída, abra Polyctl no modo de exibição de navegador novamente. Neste momento, a página da Web deve ser exibida diretamente sem a caixa de diálogo de alerta de segurança. Clique dentro do polígono; o número de lados aumenta em um. Clique fora do polígono para reduzir o número de lados. Se você tentar reduzir o número de lados para abaixo de três, você verá a mensagem de erro que você definir.

[Volte para a etapa 6](../atl/adding-a-property-page-atl-tutorial-part-6.md)

## <a name="next-steps"></a>Próximas etapas

Isso conclui o tutorial da ATL. Para obter links para obter mais informações sobre o ATL, consulte o [página inicial do ATL](../atl/active-template-library-atl-concepts.md).

## <a name="see-also"></a>Consulte também

[Tutorial](../atl/active-template-library-atl-tutorial.md)
