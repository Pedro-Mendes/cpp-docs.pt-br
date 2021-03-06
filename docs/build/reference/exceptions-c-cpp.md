---
title: Exceções (C/C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- ERROR_MOD_NOT_FOUND
- vcppException
- ERROR_SEVERITY_ERROR
dev_langs:
- C++
helpviewer_keywords:
- vcppException
- C++ exception handling, delayed loading of DLLs
- delayed loading of DLLs, exceptions
- ERROR_SEVERITY_ERROR exception
- ERROR_MOD_NOT_FOUND exception
ms.assetid: c03be05d-1c39-4f35-84cf-00c9af3bae9a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7d32b22d0ac8a065d59030dccd144236a79c6ac8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705674"
---
# <a name="exceptions-cc"></a>Exceções (C/C++)

Dois códigos de exceção podem ser gerados quando são encontradas falhas:

- Para um **LoadLibrary** falha

- Para um **GetProcAddress** falha

Eis aqui as informações de exceção:

```
//
// Exception information
//
#define FACILITY_VISUALCPP  ((LONG)0x6d)
#define VcppException(sev,err)  ((sev) | (FACILITY_VISUALCPP<<16) | err)
```

Os códigos de exceção lançados são o padrão VcppException (ERROR_SEVERITY_ERROR, ERROR_MOD_NOT_FOUND) e os valores de VcppException (ERROR_SEVERITY_ERROR, ERROR_PROC_NOT_FOUND). A exceção passa um ponteiro para um **DelayLoadInfo** estrutura no valor LPDWORD que pode ser recuperado pela **GetExceptionInformation** no [EXCEPTION_RECORD](/windows/desktop/api/winnt/ns-winnt-_exception_record) estrutura, o campo ExceptionInformation [0].

Além disso, se os bits incorretos forem definidos no campo grAttrs, a exceção ERROR_INVALID_PARAMETER é lançada. Essa exceção é, para todas as intenções e finalidades, fatal.

Ver [definições de estrutura e constante](../../build/reference/structure-and-constant-definitions.md) para obter mais informações.

## <a name="see-also"></a>Consulte também

[Tratamento de erro e notificação](../../build/reference/error-handling-and-notification.md)