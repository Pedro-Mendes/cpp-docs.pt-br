---
title: 'Como: coletor de eventos do Windows Forms de Classes C++ nativas | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- event handling, managed/native interop
- event handling, sinking .NET in C++
- event handling, .NET/native interop
- event handling, Windows Forms in C++
ms.assetid: 6e30ddee-d058-4c8d-9956-2a43d86f19d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9316d27637d335bc0e3a71656a5d7b9c8796ec28
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424971"
---
# <a name="how-to-sink-windows-forms-events-from-native-c-classes"></a>Como coletar eventos dos Windows Forms a partir de classes C++ nativas

Você pode habilitar as classes nativas do C++ receber retornos de chamada de eventos gerenciados gerados a partir de controles dos Windows Forms ou outras formas com o formato de mapa de macro do MFC. Eventos em exibições e caixas de diálogo de coletor é similar ao fazer a mesma tarefa para controles.

Para fazer isso, você precisa:

- Anexar um `OnClick` manipulador de eventos para o controle usando [MAKE_DELEGATE](../mfc/reference/delegate-and-interface-maps.md#make_delegate).

- Criar um mapa de delegado usando [BEGIN_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#begin_delegate_map), [END_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#end_delegate_map), e [EVENT_DELEGATE_ENTRY](../mfc/reference/delegate-and-interface-maps.md#event_delegate_entry).

Este exemplo continua o trabalho feito na [como: fazer o associação de dados do DDX/DDV com o Windows Forms](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md).

Agora, você associará o controle MFC (`m_MyControl`) com um delegado de manipulador de eventos gerenciado chamado `OnClick` gerenciado <xref:System.Windows.Forms.Control.Click> eventos.

### <a name="to-attach-the-onclick-event-handler"></a>Para anexar o manipulador de eventos OnClick:

1. Adicione o seguinte código à implementação de BOOL CMFC01Dlg::OnInitDialog:

    ```
    m_MyControl.GetControl()->button1->Click += MAKE_DELEGATE( System::EventHandler, OnClick );
    ```

1. Adicione o seguinte código para a seção pública na declaração de classe CMFC01Dlg: CDialog público.

    ```
    // delegate map
    BEGIN_DELEGATE_MAP( CMFC01Dlg )
    EVENT_DELEGATE_ENTRY( OnClick, System::Object^, System::EventArgs^ )
    END_DELEGATE_MAP()

    void OnClick( System::Object^ sender, System::EventArgs^ e );
    ```

1. Por fim, adicione a implementação para `OnClick` para CMFC01Dlg.cpp:

    ```
    void CMFC01Dlg::OnClick(System::Object^ sender, System::EventArgs^ e)
    {
        AfxMessageBox(_T("Button clicked"));
    }
    ```

## <a name="see-also"></a>Consulte também

[MAKE_DELEGATE](../mfc/reference/delegate-and-interface-maps.md#make_delegate)<br/>
[BEGIN_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#begin_delegate_map)<br/>
[END_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#end_delegate_map)<br/>
[EVENT_DELEGATE_ENTRY](../mfc/reference/delegate-and-interface-maps.md#event_delegate_entry)