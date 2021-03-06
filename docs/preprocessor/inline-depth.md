---
title: inline_depth | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- inline_depth_CPP
- vc-pragma.inline_depth
dev_langs:
- C++
helpviewer_keywords:
- pragmas, inline_depth
- inline_depth pragma
ms.assetid: 2bba60fe-43ea-4d09-90f7-aafaba3bad07
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cbb90d36ea3da8e443eede8a3d74a35246077d52
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46410254"
---
# <a name="inlinedepth"></a>inline_depth
Especifica a profundidade, da pesquisa heurística embutida, de modo que nenhuma função seja embutida se ele estiver em uma profundidade (no grafo de chamadas) maior que *n*.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
#pragma inline_depth( [n] )  
```  
  
## <a name="remarks"></a>Comentários  
 
Este pragma controla o processo de embutir das funções assinaladas [embutido](../cpp/inline-functions-cpp.md) e [inline](../cpp/inline-functions-cpp.md) ou embutidas automaticamente sob o `/Ob2` opção.  
  
*n* pode ser um valor entre 0 e 255, onde 255 significa profundidade ilimitada no grafo de chamadas, e zero inibe a expansão embutida.  Quando *n* não for especificado, o padrão (254) é usado.  
  
O **inline_depth** pragma controla o número de vezes que uma série de chamadas de função pode ser expandida. Por exemplo, se a profundidade embutida for quatro, e se A chamar B e B chamar C, as três chamadas serão embutidas expandidas. No entanto, se a expansão embutida mais próxima for dois, somente A e B serão expandidos, e C permanecerá como uma chamada de função.  
  
Para usar esse pragma, você deve definir o `/Ob` opção do compilador para 1 ou 2. A profundidade definida com esse pragma entra em vigor na primeira chamada de função após o pragma.  
  
A profundidade embutida pode ser diminuída durante a expansão, mas não pode ser aumentada. Se a profundidade embutida for seis e, durante a expansão, o pré-processador encontrar um **inline_depth** pragma com um valor de oito, a profundidade permanecerá seis.  
  
O **inline_depth** pragma não tem nenhum efeito em funções marcadas com `__forceinline`.  
  
> [!NOTE]
> As funções recursivas podem ser substituídas embutidas até a profundidade máxima de 16 chamadas.  
  
## <a name="see-also"></a>Consulte também  
 
[Diretivas Pragma e a palavra-chave __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)<br/>
[inline_recursion](../preprocessor/inline-recursion.md)