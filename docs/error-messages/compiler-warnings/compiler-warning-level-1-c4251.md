---
title: Compilador aviso (nível 1) C4251 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4251
dev_langs:
- C++
helpviewer_keywords:
- C4251
ms.assetid: a9992038-f0c2-4fc4-a9be-4509442cbc1e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ad47d769dbfd09cc741be18598355dc34486bd54
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045686"
---
# <a name="compiler-warning-level-1-c4251"></a>Compilador aviso (nível 1) C4251

'identifier': classe 'type' precisa ter dll-interface a ser usado por clientes da classe 'type2'

Para minimizar a possibilidade de corrupção de dados ao exportar uma classe com [dllexport](../../cpp/dllexport-dllimport.md), certifique-se de que:

- Todos os seus dados estáticos é acessado por meio de funções exportadas da DLL.

- Nenhum método embutido da sua classe pode modificar dados estáticos.

- Nenhum método embutido da sua classe usa funções de CRT ou outras funções de biblioteca usam dados estáticos (consulte [potenciais erros passando CRT objetos entre limites de DLL](../../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md) para obter mais informações).

- Nenhum método de sua classe (independentemente de inlining) pode usar os tipos em que a instanciação no EXE e DLL têm diferenças de dados estáticos.

Você pode evitar a exportação de classes definindo a uma DLL que define uma classe com funções virtuais e funções que você pode chamar para instanciar e excluir objetos do tipo.  Você pode chamar funções virtuais apenas no tipo.

Para obter mais informações sobre como exportar modelos, consulte [ http://support.microsoft.com/default.aspx?scid=KB; EN-US; 168958](http://support.microsoft.com/default.aspx?scid=KB;EN-US;168958).

C4251 pode ser ignorado se você estiver derivando de um tipo na biblioteca padrão C++, Compilando uma versão de depuração (**/MTd**) e onde a mensagem de erro do compilador se refere ao _Container_base.

```
// C4251.cpp
// compile with: /EHsc /MTd /W2 /c
#include <vector>
using namespace std;
class Node;
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4251
```