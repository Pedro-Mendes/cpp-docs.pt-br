---
title: região, endregion | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.endregion
- endregion_CPP
- region_CPP
- vc-pragma.region
dev_langs:
- C++
helpviewer_keywords:
- pragmas, region
- pragmas, endregion
- endregion pragma
- region pragma
ms.assetid: c697f807-622f-4796-851b-68a42bbecd84
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dac2df26f393b7491d94abdb6d987a8e424723e1
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715543"
---
# <a name="region-endregion"></a>region, endregion
`#pragma region` permite que você especifique um bloco de código que você pode expandir ou recolher ao usar o [recurso de estrutura de tópicos](/visualstudio/ide/outlining) do Editor de código do Visual Studio.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
#pragma region name  
#pragma endregion comment  
```  
  
### <a name="parameters"></a>Parâmetros  
*comment*  
(Opcional) Um comentário que será exibido no editor de códigos.  
  
*name*  
(Opcional) O nome da região.  Esse nome será exibido no editor de códigos.  
  
## <a name="remarks"></a>Comentários  
 
`#pragma endregion` marca o fim de um `#pragma region` bloco.  
  
Um `#region` bloco deverá ser encerrado com `#pragma endregion`.  
  
## <a name="example"></a>Exemplo  
  
```cpp  
// pragma_directives_region.cpp  
#pragma region Region_1  
void Test() {}  
void Test2() {}  
void Test3() {}  
#pragma endregion Region_1  
  
int main() {}  
```  
  
## <a name="see-also"></a>Consulte também  
 
[Diretivas Pragma e a palavra-chave __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)