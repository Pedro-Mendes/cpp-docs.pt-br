---
title: '&lt;limites&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- limits/std::<limits>
- <limits>
dev_langs: C++
helpviewer_keywords: limits header
ms.assetid: e07d6379-5b00-4a3d-a789-40d41538b59e
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: eace3f5dd5d0693f5cb42b32e4d2c8c52a5eddfe
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="ltlimitsgt"></a>&lt;limites&gt;
Define a classe de modelo `numeric_limits` e duas enumerações relacionadas a representações de pontos flutuantes e arredondamento.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
#include <limits>  
  
```  
  
## <a name="remarks"></a>Comentários  
 Especializações explícitas da classe `numeric_limits` descrevem muitas propriedades dos tipos fundamentais, incluindo os tipos de ponto flutuante, caractere e inteiro, bem como `bool`, que são definidos pela implementação e não fixados pelas regras da linguagem C++. Propriedades descritas em \<limits> incluem precisão, representações de tamanho mínimo e máximo, arredondamento e erros de tipo de sinalização.  
  
### <a name="enumerations"></a>Enumerações  
  
|||  
|-|-|  
|[float_denorm_style](../standard-library/limits-enums.md#float_denorm_style)|A enumeração descreve os vários métodos que uma implementação pode escolher para representar um valor de ponto flutuante desnormalizado — um pequeno demais para ser representado como um valor normalizado:|  
|[float_round_style](../standard-library/limits-enums.md#float_round_style)|A enumeração descreve os vários métodos que uma implementação pode escolher para fazer o arredondamento de um valor de ponto flutuante para um valor inteiro.|  
  
### <a name="classes"></a>Classes  
  
|||  
|-|-|  
|[Classe numeric_limits](../standard-library/numeric-limits-class.md)|A classe de modelo descreve propriedades aritméticas de tipos numéricos internos.|  
  
## <a name="see-also"></a>Consulte também  
 [Referência de Arquivos de Cabeçalho](../standard-library/cpp-standard-library-header-files.md)   
 [Acesso Thread-Safe na Biblioteca Padrão C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)


