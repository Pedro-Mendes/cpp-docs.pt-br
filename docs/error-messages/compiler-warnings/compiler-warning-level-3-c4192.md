---
title: Compilador aviso (nível 3) C4192 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4192
dev_langs:
- C++
helpviewer_keywords:
- C4192
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 671a8c83dcadcaa89372e53b6c3d677c5810b4a5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114404"
---
# <a name="compiler-warning-level-3-c4192"></a>Compilador aviso (nível 3) C4192

excluindo automaticamente 'name' durante a importação de biblioteca de tipos 'library'

Um `#import` biblioteca contém um item *nome*, que é também definida nos cabeçalhos do sistema de Win32. Devido a limitações de bibliotecas de tipos, nomes, como **IUnknown** ou GUID geralmente são definidos em uma biblioteca de tipos, duplicar a definição dos cabeçalhos do sistema. `#import` detecta esses itens e se recusar a incorporá-las nos arquivos de cabeçalho. TLH e. TLI.

Para substituir esse comportamento, use `#import` atributos [no_auto_exclude](../../preprocessor/no-auto-exclude.md) e [include ()](../../preprocessor/include-parens.md).