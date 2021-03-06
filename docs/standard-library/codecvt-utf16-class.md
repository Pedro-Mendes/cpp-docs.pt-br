---
title: codecvt_utf16 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- codecvt/std::codecvt_utf16
dev_langs:
- C++
helpviewer_keywords:
- codecvt_utf16 class
ms.assetid: a9897f98-f84d-4db6-90ad-858b2727570c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aa4147f28e7b780e9d916526f0e46e91432fd1ce
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714227"
---
# <a name="codecvtutf16"></a>codecvt_utf16

Representa uma faceta de [localidade](../standard-library/locale-class.md) convertida entre caracteres largos codificados como UCS-2 ou UCS-4 e um fluxo de bytes codificado como UTF-16LE ou UTF-16BE.

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf16 : public std::codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>Parâmetros

*Elem*<br/>
O tipo de elemento de caractere largo.

*Maxcode*<br/>
O número máximo de caracteres da faceta de localidade.

*Modo*<br/>
Informações de configuração para a faceta de localidade.

## <a name="remarks"></a>Comentários

Essa classe de modelo é convertida entre caracteres largos codificados como UCS-2 ou UCS-4 e um fluxo de bytes codificado como UTF-16LE, se o modo & little_endian ou UTF-16BE caso contrário.

O fluxo de bytes deve ser gravado em um arquivo binário. Ele pode ser corrompido se gravado em um arquivo de texto.

## <a name="requirements"></a>Requisitos

Cabeçalho: \<codecvt >

Namespace: std