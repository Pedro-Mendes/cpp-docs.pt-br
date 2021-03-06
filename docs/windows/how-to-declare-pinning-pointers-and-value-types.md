---
title: 'Como: declarar ponteiros de fixação e tipos de valor | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- value types, declaring
- pinning pointers
ms.assetid: 57c5ec8a-f85a-48c4-ba8b-a81268bcede0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 88c7b9d0b9ed8a39bae09e2ec1691de90549fc11
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42607143"
---
# <a name="how-to-declare-pinning-pointers-and-value-types"></a>Como declarar ponteiros de fixação e tipos de valor

Um tipo de valor pode ser convertido implicitamente. Você pode então declarar um ponteiro de fixação para o objeto de tipo de valor em si e use uma **pin_ptr** para o tipo de valor Demarcado.

## <a name="example"></a>Exemplo

### <a name="code"></a>Código

```cpp
// pin_ptr_value.cpp
// compile with: /clr
value struct V {
   int i;
};

int main() {
   V ^ v = gcnew V;   // imnplicit boxing
   v->i=8;
   System::Console::WriteLine(v->i);
   pin_ptr<V> mv = &*v;
   mv->i = 7;
   System::Console::WriteLine(v->i);
   System::Console::WriteLine(mv->i);
}
```

```Output
8
7
7
```

## <a name="see-also"></a>Consulte também

[pin_ptr (C++/CLI)](../windows/pin-ptr-cpp-cli.md)