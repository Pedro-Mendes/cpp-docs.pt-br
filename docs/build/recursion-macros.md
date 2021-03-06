---
title: Macros de recursão | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, recursion macros
- recursion macros
- macros, recursion
ms.assetid: c53e5ae7-619e-46b1-bdc2-86d8c7798b1d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f91a5f327686a522608b6eec9fd7106cbab00028
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702034"
---
# <a name="recursion-macros"></a>Macros de recursão

Use macros de recursão para chamar recursivamente NMAKE. Sessões recursiva herdam macros de variável de ambiente e de linha de comando e as informações do Tools. ini. Eles não herdam as regras de inferência de tipos definidos pelo makefile ou **. SUFIXOS** e **. PRECIOSOS** especificações. Para passar a uma sessão NMAKE recursiva macros, definir uma variável de ambiente com SET antes da chamada recursiva, defina uma macro no comando para a chamada recursiva ou definir uma macro em Tools. ini.

|Macro|Definição|
|-----------|----------------|
|**VERIFIQUE**|Comando usado originalmente para invocar o NMAKE.<br /><br /> A macro $ (Make) fornece o caminho completo para nmake.exe.|
|**MAKEDIR**|Diretório atual quando NMAKE foi invocado.|
|**MAKEFLAGS**|Opções atualmente em vigor. Usar como `/$(MAKEFLAGS)`.  Observe que, /F não está incluído.|

## <a name="see-also"></a>Consulte também

[Macros NMAKE especiais](../build/special-nmake-macros.md)