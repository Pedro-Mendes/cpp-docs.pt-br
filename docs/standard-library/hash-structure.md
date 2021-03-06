---
title: Estrutura hash | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- typeindex/std::hash
dev_langs:
- C++
ms.assetid: e5a41202-ef3b-45d0-b3a7-4c2dbdc0487a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 22a7ea0679e170051c9b242b61e6739fb461283a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45721624"
---
# <a name="hash-structure"></a>Estrutura hash

A classe de modelo define seu método como um `val.hash_code()` de retorno. O método define uma função de hash que é usada para mapear valores do tipo [type_index](../standard-library/type-index-class.md) para uma distribuição de valores de índice.

## <a name="syntax"></a>Sintaxe

```cpp
template <>
struct hash<type_index>
: public unary_function<type_index, size_t>
{ // hashes a typeinfo object
    size_t operator()(type_index val) const;

};
```

## <a name="see-also"></a>Consulte também

[\<typeindex>](../standard-library/typeindex.md)<br/>
