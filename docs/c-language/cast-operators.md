---
title: Operadores cast | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- cast operators
- type casts, operators
- operators [C++], cast
- type conversion, cast operators
ms.assetid: 43b90bbd-39ef-43e6-ae5d-e8a67a01de40
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: abb4b84519b943d02eca277c9372a128f7d6c2fe
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098493"
---
# <a name="cast-operators"></a>Operadores cast

Uma conversão de tipo fornece um método para conversão explícita do tipo de um objeto em uma situação específica.

## <a name="syntax"></a>Sintaxe

*cast-expression*: *unary-expression*

**(**  *type-name*  **)**  *cast-expression*

O compilador trata *cast-expression* como tipo *type-name* depois que uma conversão de tipo é feita. As conversões podem ser usadas para converter objetos de qualquer tipo escalar em ou de qualquer outro tipo escalar. As conversões de tipo explícito são restringidas pelas mesmas regras que determinam os efeitos de conversões implícitas, descritos em [Conversões de atribuição](../c-language/assignment-conversions.md). As restrições adicionais de conversões podem resultar de tamanhos reais ou de representação de tipos específicos. Consulte [Armazenamento de tipos básicos](../c-language/storage-of-basic-types.md) para obter informações sobre tamanhos reais de tipos integrais. Para obter mais informações sobre conversões de tipos, consulte [Conversões Type-Cast](../c-language/type-cast-conversions.md).

## <a name="see-also"></a>Consulte também

[Operador cast: ()](../cpp/cast-operator-parens.md)