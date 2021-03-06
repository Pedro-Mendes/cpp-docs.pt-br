---
title: '&lt;limites&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- limits/std::<limits>
- <limits>
dev_langs:
- C++
helpviewer_keywords:
- limits header
ms.assetid: e07d6379-5b00-4a3d-a789-40d41538b59e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 66f9401bed0a6c9d0b1ffa09a10f98afa258069d
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964750"
---
# <a name="ltlimitsgt"></a>&lt;limites&gt;

Define a classe de modelo `numeric_limits` e duas enumerações relacionadas a representações de pontos flutuantes e arredondamento.

## <a name="syntax"></a>Sintaxe

```cpp
#include <limits>

```

## <a name="remarks"></a>Comentários

Especializações explícitas a `numeric_limits` classe descrevem muitas propriedades dos tipos fundamentais, incluindo o caractere, inteiro e tipos de ponto flutuante e **bool** que são implementação definida e não fixados pelas as regras da linguagem C++. Propriedades descritas em \<limits> incluem precisão, representações de tamanho mínimo e máximo, arredondamento e erros de tipo de sinalização.

### <a name="enumerations"></a>Enumerações

|||
|-|-|
|[float_denorm_style](../standard-library/limits-enums.md#float_denorm_style)|A enumeração descreve os vários métodos que uma implementação pode escolher para representar um valor de ponto flutuante desnormalizado — um pequeno demais para ser representado como um valor normalizado:|
|[float_round_style](../standard-library/limits-enums.md#float_round_style)|A enumeração descreve os vários métodos que uma implementação pode escolher para fazer o arredondamento de um valor de ponto flutuante para um valor inteiro.|

### <a name="classes"></a>Classes

|Classe|Descrição|
|-|-|
|[Classe numeric_limits](../standard-library/numeric-limits-class.md)|A classe de modelo descreve propriedades aritméticas de tipos numéricos internos.|

## <a name="see-also"></a>Consulte também

[Referência de Arquivos de Cabeçalho](../standard-library/cpp-standard-library-header-files.md)<br/>
[Acesso Thread-Safe na Biblioteca Padrão C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
