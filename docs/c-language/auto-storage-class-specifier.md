---
title: Especificador de classe de armazenamento auto | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 8e73f57e-aa92-4e41-91ea-5c8ad2a2b332
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ca42eb26cc6bb08cd8a05e31b23e004b1cbeb8b2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057425"
---
# <a name="auto-storage-class-specifier"></a>Especificador de classe de armazenamento auto

O especificador de classe de armazenamento **auto** declara uma variável automática, uma variável com um tempo de vida local. Uma variável **auto** pode ser vista somente no bloco em que é declarada. As declarações de variáveis **auto** podem incluir inicializadores, conforme discutido em [Inicialização](../c-language/initialization.md). Como as variáveis com a classe de armazenamento **auto** não são inicializadas automaticamente, você deve inicializá-las explicitamente ao declará-las ou atribuir valores iniciais a elas em instruções no bloco. Os valores das variáveis **auto** não inicializadas estão indefinidos. (A variável local da classe de armazenamento **auto** ou **register** será inicializada sempre que aparecer no escopo, se um inicializador for fornecido.)

Uma variável interna **static** (uma variável estática com escopo local ou de bloco) pode ser inicializada com o endereço de qualquer item externo ou **static**, mas não com o endereço de outro item **auto**, pois o endereço de um item **auto** não é uma constante.

## <a name="see-also"></a>Consulte também

[Palavra-chave auto](../cpp/auto-keyword.md)