---
title: Armazenando e carregando CObjects por meio de um arquivo morto | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CObject
dev_langs:
- C++
helpviewer_keywords:
- CObjects [MFC], loading through archives
- CArchive class [MFC], storing and loading objects
- Serialize method, vs. CArchive operators
- CObject class [MFC], CArchive objects
- CObjects [MFC]
ms.assetid: a829b6dd-bc31-47e0-8108-fbb946722db9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e19626fab2e44bf88b4a378d094daaf7c377ad5d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46436956"
---
# <a name="storing-and-loading-cobjects-via-an-archive"></a>Armazenando e carregando CObjects por meio de um arquivo morto

Armazenando e carregando `CObject`s por meio de um arquivo morto exige uma consideração extra. Em alguns casos, você deve chamar o `Serialize` função do objeto, onde o `CArchive` objeto é um parâmetro da `Serialize` chamada, em vez de usar os **< \<** ou **>>** operador do `CArchive`. O fato importante ter em mente é que o `CArchive` **>>** construções de operador a `CObject` na memória com base em `CRuntimeClass` previamente gravadas no arquivo pelo arquivamento de armazenamento de informações.

Portanto, se você usar o `CArchive` **< \<** e **>>** operadores, em vez de chamar `Serialize`, depende se você *precisa* o arquivo de carregamento para dinamicamente reconstruir o objeto com base em armazenado anteriormente `CRuntimeClass` informações. Use o `Serialize` função nos seguintes casos:

- Ao desserializar o objeto, saber com antecedência a classe exata do objeto.

- Ao desserializar o objeto, você já tem memória alocada para ele.

> [!CAUTION]
>  Se você carregar o objeto usando o `Serialize` função, você também deve armazenar o objeto usando o `Serialize` função. Não armazene usando o `CArchive` **<<** operador e, em seguida, de carga usando o `Serialize` funcionar ou armazenar usando o `Serialize` de função e, em seguida, carregar usando `CArchive >>` operador.

O exemplo a seguir ilustra os casos:

[!code-cpp[NVC_MFCSerialization#36](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_1.h)]

[!code-cpp[NVC_MFCSerialization#37](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_2.cpp)]

Em resumo, se sua classe serializável define inserida `CObject` como um membro, você deve *não* usar os `CArchive` **< \<** e **>>** operadores para esse objeto, mas deve chamar o `Serialize` function em vez disso. Além disso, se sua classe serializável define um ponteiro para um `CObject` (ou um objeto derivado de `CObject`) como um membro, mas as construções esse outro objeto no seu próprio construtor, você também deve chamar `Serialize`.

## <a name="see-also"></a>Consulte também

[Serialização: serializando um objeto](../mfc/serialization-serializing-an-object.md)

