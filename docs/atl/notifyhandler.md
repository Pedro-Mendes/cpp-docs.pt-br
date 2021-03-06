---
title: NotifyHandler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- NotifyHandler
dev_langs:
- C++
helpviewer_keywords:
- NotifyHandler function
ms.assetid: 5ff953ec-de35-42bc-8b3c-d384d636c139
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8f11c698b0f89e0584b673a112da10e82250cf5c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035767"
---
# <a name="notifyhandler"></a>NotifyHandler

O nome da função identificado pelo terceiro parâmetro da macro NOTIFY_HANDLER no seu mapa de mensagem.

## <a name="syntax"></a>Sintaxe

```cpp
LRESULT NotifyHandler(
    int idCtrl,
    LPNMHDR pnmh,
    BOOL& bHandled);
```

#### <a name="parameters"></a>Parâmetros

*idCtrl*<br/>
O identificador do controle que está enviando a mensagem.

*pnmh*<br/>
Endereço de um [NMHDR](/windows/desktop/api/richedit/ns-richedit-_nmhdr) estrutura que contém o código de notificação e informações adicionais. Para algumas mensagens de notificação, este parâmetro aponta para uma estrutura maior que tem o `NMHDR` estrutura como seu primeiro membro.

*bHandled*<br/>
Os conjuntos de mapa de mensagem *bHandled* como TRUE antes *NotifyHandler* é chamado. Se *NotifyHandler* totalmente não manipular a mensagem, ela deverá definir *bHandled* para **FALSE** para indicar que a mensagem precisa de processamento adicional.

## <a name="return-value"></a>Valor de retorno

O resultado do processamento de mensagens. 0 se for bem-sucedido.

## <a name="remarks"></a>Comentários

Para obter um exemplo de como usar este manipulador de mensagens em um mapa de mensagem, consulte [NOTIFY_HANDLER](reference/message-map-macros-atl.md#notify_handler)).

## <a name="see-also"></a>Consulte também

[Implementando uma janela](../atl/implementing-a-window.md)<br/>
[Mapas de mensagem](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](https://msdn.microsoft.com/library/windows/desktop/bb775583)
