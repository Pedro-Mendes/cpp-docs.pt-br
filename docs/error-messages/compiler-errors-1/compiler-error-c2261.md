---
title: Erro do compilador C2261 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2261
dev_langs:
- C++
helpviewer_keywords:
- C2261
ms.assetid: 60969482-9e83-49b5-9631-a04bc844da12
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ed43dc43fb6ceaf514a8e7452b06eb7bdaf7362
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051640"
---
# <a name="compiler-error-c2261"></a>Erro do compilador C2261

'string': referência de assembly é inválida e não pode ser resolvida

Um valor não era válido.

<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> é usado para especificar um assembly amigável. Por exemplo, se quiser. dll especificar o b. dll como um assembly amigável, você especificaria (em dll): InternalsVisibleTo("b"). O tempo de execução, em seguida, permite que a b. dll acessar tudo na DLL (exceto tipos privados).

Para obter mais informações sobre a sintaxe correta ao especificar assemblies amigáveis, consulte [Assemblies de amigo (C++)](../../dotnet/friend-assemblies-cpp.md).

## <a name="example"></a>Exemplo

O exemplo a seguir gera C2261.

```
// C2261.cpp
// compile with: /clr /c
using namespace System::Runtime::CompilerServices;
[assembly: InternalsVisibleTo("a,a,a")];   // C2261
[assembly: InternalsVisibleTo("a.a")];   // OK
[assembly: InternalsVisibleTo("a")];   // OK
```