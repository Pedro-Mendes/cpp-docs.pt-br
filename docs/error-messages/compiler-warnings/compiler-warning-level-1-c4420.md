---
title: Compilador aviso (nível 1) C4420 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4420
dev_langs:
- C++
helpviewer_keywords:
- C4420
ms.assetid: 44a37754-7ddd-4764-a5f7-d33e05c20091
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1ba4ef4c4fc006e1a5950d0d16dc530ccc06a1d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049742"
---
# <a name="compiler-warning-level-1-c4420"></a>Compilador aviso (nível 1) C4420

'operator': operador não está disponível, usando 'operator'; verificação de tempo de execução pode ser comprometida

Esse aviso é gerado quando você usa o [/RTCv](../../build/reference/rtc-run-time-error-checks.md) (vetor de verificação de novo/excluir) e quando nenhum formulário de vetor é encontrado. Nesse caso, a forma de vetor não é usada.

Para /RTCv funcione corretamente, o compilador deve sempre chamar o formulário de vetor de [novos](../../cpp/new-operator-cpp.md)/[excluir](../../cpp/delete-operator-cpp.md) se a sintaxe de vetor foi usada.