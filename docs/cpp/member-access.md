---
title: Acesso de membro | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- member-selection operators [C++]
- pointers, smart
- member access, overloaded operators
- operator overloading [C++], member access operators
- smart pointers, definition
- smart pointers
ms.assetid: 8c7b2c43-eb92-4d42-9a8e-61aa37d71333
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2aadccd883738fe2e6e9f57cc63f67cde6d6a6c4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099922"
---
# <a name="member-access"></a>Acesso de membro

Acesso de membro de classe pode ser controlado pela sobrecarga de operador de acesso a membro (**->**). Esse operador é considerado um operador unário nesse uso, e a função sobrecarregada do operador deve ser uma função de membro da classe. Portanto, a declaração dessa função é:

## <a name="syntax"></a>Sintaxe

```
class-type *operator->()
```

## <a name="remarks"></a>Comentários

em que *tipo de classe* é o nome da classe à qual esse operador pertence. A função do operador de acesso do membro deve ser uma função de membro não estático.

Esse operador é usado (frequentemente em conjunto com o operador de desreferência de ponteiro) para implementar "ponteiros inteligentes" que validam os ponteiros antes da desreferência ou do uso da contagem.

O elemento de linguagem **.** operador de acesso de membro não pode ser sobrecarregado.

## <a name="see-also"></a>Consulte também

[Sobrecarga de Operador](../cpp/operator-overloading.md)