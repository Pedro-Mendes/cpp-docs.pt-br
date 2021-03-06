---
title: Propriedade de tipo de acelerador (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Type property
- VIRTKEY
ms.assetid: 8c349bc4-e6ad-43fa-959e-f29168af35b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1b0d02ab8dfec7b6a3f286b09daf9797d62f0990
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46384761"
---
# <a name="accelerator-type-property-c"></a>Propriedade de tipo de acelerador (C++)

O acelerador **tipo** propriedade determina se a combinação de teclas de atalho associada com a ID do acelerador é uma combinação de teclas virtual ou um valor de chave ASCII/ANSI:

- Se o **tipo** propriedade é ASCII, o [modificador](../windows/accelerator-modifier-property.md) só podem ser `None` ou `Alt`, ou pode ter um acelerador que usa o **Ctrl** chave (especificada pelo precede a chave com um `^`).

- Se o **tipo** propriedade é VIRTKEY, qualquer combinação de `Modifier` e `Key` valores é válido.

   > [!NOTE]
   > Se você quiser inserir um valor para a tabela de Aceleradores e têm o valor a ser tratado como ASCII/ANSI, basta clicar o **tipo** para a entrada na tabela e selecione ASCII na lista suspensa. No entanto, se você usar o **próxima chave digitada** comando (**editar** menu) para especificar o `Key`, você deve alterar o **tipo** propriedade de VIRTKEY para ASCII *antes de* inserindo o `Key` código.

## <a name="requirements"></a>Requisitos

Win32

## <a name="see-also"></a>Consulte também

[Configurando propriedades do acelerador](../windows/setting-accelerator-properties.md)<br/>
[Editor de aceleradores](../windows/accelerator-editor.md)