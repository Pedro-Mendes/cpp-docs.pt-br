---
title: Combinando C (estruturada) e exceções do C++ | Microsoft Docs
ms.custom: ''
ms.date: 08/14/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- exceptions [C++], mixed C and C++
- C++ exception handling, mixed-language
- structured exception handling [C++], mixed C and C++
- catch keyword [C++], mixed
- try-catch keyword [C++], mixed-language
ms.assetid: a149154e-36dd-4d1a-980b-efde2a563a56
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1edd35ac9f32a28a19c4ea54b7e9fba2820d6095
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031620"
---
# <a name="mixing-c-structured-and-c-exceptions"></a>Combinando C (estruturada) e exceções do C++

Se você quiser escrever um código portátil, não é recomendado o uso estruturado de manipulação de exceção (SEH) em um programa C++. No entanto, às vezes, convém compilar usando [/EHa](../build/reference/eh-exception-handling-model.md) e combinar exceções estruturadas e código-fonte C++ e precisar de algum recurso para lidar com ambos os tipos de exceções. Como um manipulador de exceção estruturada não tem nenhum conceito de objetos ou exceções tipadas, ela não pode manipular as exceções geradas por código C++. No entanto, C++ **catch** manipuladores podem tratar exceções estruturadas. Sintaxe de tratamento de exceções C++ (**tente**, **throw**, **catch**) não é aceito pelo compilador C, mas a sintaxe de tratamento de exceções estruturado (**Try**, **EXCEPT**, **Finally**) é suportado pelo compilador do C++.

Ver [set_se_translator](../c-runtime-library/reference/set-se-translator.md) para obter informações sobre como lidar com exceções estruturadas como exceções C++.

Se você combinar a estruturadas e exceções do C++, esteja ciente desses problemas potenciais:

- As exceções C++ e as exceções estruturadas não podem ser combinadas na mesma função.

- Manipuladores de terminação (**Finally** blocos) são sempre executados, mesmo durante o desenrolamento depois que uma exceção será lançada.

- Tratamento de exceções C++ pode capturar e preservar semânticas de desenrolamento em todos os módulos compilados com o [/EH](../build/reference/eh-exception-handling-model.md) opções do compilador, semântica de liberação que habilitar.

- Pode haver algumas situações nas quais as funções de destruidor não sejam chamadas de todos os objetos. Por exemplo, se uma exceção estruturada ocorre ao tentar fazer com que uma função chamada por meio de um ponteiro de função não inicializado, e essa função usa como parâmetros objetos que foram criados antes da chamada, os destruidores desses objetos não são chamados durante o desenrolamento de pilha.

## <a name="next-steps"></a>Próximas etapas

- [Usando setjmp ou longjmp em programas C++](../cpp/using-setjmp-longjmp.md)

  Veja mais informações sobre o uso de `setjmp` e `longjmp` em programas C++.

- [Tratar exceções estruturadas no C++](../cpp/exception-handling-differences.md)

  Consulte exemplos dos modos que você pode usar C++ para manipular estruturado de exceções.

## <a name="see-also"></a>Consulte também

[Tratamento de exceções em C++](../cpp/cpp-exception-handling.md)
