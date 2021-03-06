---
title: Inferido dependentes e regras | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rules, inferred
- inferred dependents in NMAKE
- inferred rules in NMAKE
- dependents, inferred
ms.assetid: 9381e74a-53d9-445c-836d-0ff7ef6112d9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c13ae7784ff40b39642ce26fd062a1aab80f2d4c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707545"
---
# <a name="inferred-dependents-and-rules"></a>Dependentes inferidos e regras

NMAKE pressupõe um dependente inferido para um destino se existe uma regra de inferência de tipos aplicáveis. Uma regra se aplica se:

- *toext* corresponde à extensão de destino.

- *fromext* correspondências a extensão de um arquivo que tem o nome do destino base e que existe no diretório atual ou especificado.

- *fromext* está em [. SUFIXOS](../build/dot-directives.md); nenhuma outra *fromext* em uma regra de correspondência tem uma maior **. SUFIXOS** prioridade.

- Nenhum dependente explícita tem uma maior **. SUFIXOS** prioridade.

Dependentes inferidos podem causar efeitos colaterais inesperados. Se o bloco de descrição do destino contém comandos, NMAKE executa esses comandos em vez de comandos na regra.

## <a name="see-also"></a>Consulte também

[Regras de inferência](../build/inference-rules.md)