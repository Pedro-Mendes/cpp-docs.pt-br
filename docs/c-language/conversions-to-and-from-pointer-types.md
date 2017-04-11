---
title: "Conversões para e de tipos de ponteiro | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- pointers, converting
- conversions, pointer
- type casts, involving pointers
- void pointers
ms.assetid: 3facc56f-06d3-4570-b1a2-7d4927b83086
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 55922d46ffb661fbd3032cd0381479452e77058d
ms.lasthandoff: 02/25/2017

---
# <a name="conversions-to-and-from-pointer-types"></a>Conversões em e de tipos de ponteiro
Um ponteiro para um tipo de valor que pode ser convertido em um ponteiro para um tipo diferente. No entanto, o resultado pode ser indefinido devido aos requisitos de alinhamento e aos tamanhos de tipos diferentes em armazenamento. Um ponteiro para um objeto pode ser convertido em um ponteiro para um objeto cujo tipo exige menos alinhamento de armazenamento ou igualmente restrito, e reconverter sem modificação.  
  
 Um ponteiro para `void` pode ser convertido em ou de um ponteiro para qualquer tipo, sem restrição ou perda de informações. Se o resultado for reconvertido no tipo original, o ponteiro original será recuperado.  
  
 Se um ponteiro é convertido em outro ponteiro do mesmo tipo, mas com qualificadores diferentes ou adicionais, o novo ponteiro é o mesmo que o antigo, com a exceção das restrições impostas pelo novo qualificador.  
  
 Um valor de ponteiro pode ser convertido em um valor integral. O caminho de conversão depende do tamanho do ponteiro e do tamanho do tipo integral, de acordo com as seguintes regras:  
  
-   Se o tamanho do ponteiro for maior ou igual ao tamanho do tipo integral, o ponteiro se comportará como um valor sem sinal na conversão, mas não poderá ser convertido em um valor flutuante.  
  
-   Se o ponteiro for menor que o tipo integral, o ponteiro primeiro será convertido em um ponteiro do mesmo tamanho do tipo integral, e depois convertido no tipo integral.  
  
 Inversamente, um tipo integral pode ser convertido em um tipo de ponteiro de acordo com as seguintes regras:  
  
-   Se o tipo integral for do mesmo tamanho que o tipo de ponteiro, a conversão faz com que o valor integral seja tratado como um ponteiro (um número inteiro sem sinal).  
  
-   Se o tamanho do tipo integral for diferente do tamanho do tipo de ponteiro, o tipo integral é convertido primeiro no tamanho do ponteiro, usando os caminhos de conversão fornecidos nas tabelas [Conversão de tipos integrais com sinal](../c-language/conversions-from-signed-integral-types.md) e [Conversão de tipos integrais sem sinal](../c-language/conversions-from-unsigned-integral-types.md). Depois é tratado como um valor do ponteiro.  
  
 Uma expressão constante integral com valor 0 ou uma conversão da expressão em tipo **void \*** pode ser convertida por uma conversão de tipo, por atribuição ou por comparação, em um ponteiro de qualquer tipo. Isso gera um ponteiro nulo que é igual a outro ponteiro nulo do mesmo tipo, mas esse ponteiro nulo não é igual a nenhum ponteiro para uma função ou a um objeto. Os números inteiros diferentes da constante 0 podem ser convertidos no tipo de ponteiro, mas o resultado não é portátil.  
  
## <a name="see-also"></a>Consulte também  
 [Conversões de atribuição](../c-language/assignment-conversions.md)