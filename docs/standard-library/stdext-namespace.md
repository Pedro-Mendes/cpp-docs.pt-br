---
title: Namespace stdext | Microsoft Docs
ms.custom: 
ms.date: 09/06/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: stdext
dev_langs: C++
helpviewer_keywords:
- _DEFINE_DEPRECATED_HASH_CLASSES symbol
- stdext namespace
ms.assetid: 3e94fc89-0584-424f-bc09-081b73379545
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 59da07c0cea58e9fc4b544b9f3bad937b2951f9e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="stdext-namespace"></a>Namespace stdext

Membros de [ \<hash_map >](../standard-library/hash-map.md) e [ \<hash_set >](../standard-library/hash-set.md) arquivos de cabeçalho não são parte do padrão ISO C++. Portanto, esses tipos e membros foram movidos do `std` namespace para o namespace `stdext`, para permanecerem em conformidade com o padrão C++.

Ao compilar com [/Ze](../build/reference/za-ze-disable-language-extensions.md), que é o padrão, o compilador avisa sobre o uso de `std` para membros de \<hash_map > e \<hash_set > arquivos de cabeçalho. Para desabilitar o aviso, use o pragma [warning](../preprocessor/warning.md).

Para que o compilador gere um erro para o uso de `std` para membros de \<hash_map > e \<hash_set > arquivos de cabeçalho com **/Ze**, adicione a seguinte diretiva antes de `#include` quaisquer arquivos de cabeçalho de biblioteca padrão C++.

```cpp  
#define _DEFINE_DEPRECATED_HASH_CLASSES 0  
```  

Ao compilar com **/Za**, o compilador gerará um erro.  

## <a name="see-also"></a>Consulte também

[Visão geral da biblioteca padrão C++](../standard-library/cpp-standard-library-overview.md)
