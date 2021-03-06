---
title: strict_gs_check | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- strict_gs_check
- strict_gs_check_CPP
dev_langs:
- C++
helpviewer_keywords:
- strict_gs_check pragma
ms.assetid: decfec81-c916-42e0-a07f-8cc26df6a7ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7c6797e9a75e9150718655ed7fcd72d7f343e591
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430196"
---
# <a name="strictgscheck"></a>strict_gs_check
Este pragma fornece verificação de segurança aprimorada.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
#pragma strict_gs_check([push,] on )   
#pragma strict_gs_check([push,] off )   
#pragma strict_gs_check(pop)  
```  
  
## <a name="remarks"></a>Comentários  
 
Ele instrui o compilador a inserir um cookie aleatório na pilha de função para ajudar a detectar algumas categorias de saturação de buffer baseada em fila. Por padrão, o `/GS` (Buffer Security Check) a opção de compilador não insere um cookie para todas as funções. Para obter mais informações, consulte [/GS (verificação de segurança do buffer)](../build/reference/gs-buffer-security-check.md).  
  
Você deve compilar com `/GS` (Buffer Security Check) para habilitar **strict_gs_check**.  
  
Use este pragma em módulos de código que são expostos a dados potencialmente nocivos. Este pragma é muito agressivo. Ele é aplicado às funções que podem não precisar dessa defesa, mas é otimizado para minimizar seu efeito no desempenho do aplicativo resultante.  
  
Mesmo ao usar esse pragma, o ideal é escrever um código seguro. Ou seja, certifique-se de que seu código não tem nenhum estouros de buffer. **strict_gs_check** pode proteger seu aplicativo contra estouros de buffer que permanecem em seu código.  
  
## <a name="example"></a>Exemplo  
 
No código a seguir, uma saturação de buffer ocorre quando copiamos uma matriz para uma matriz local. Quando você compilar esse código com `/GS`, nenhum cookie é inserido na pilha, porque o tipo de dados de matriz é um ponteiro. Adicionando o **strict_gs_check** pragma força o cookie da pilha na pilha da função.  
  
```cpp  
// pragma_strict_gs_check.cpp  
// compile with: /c  
  
#pragma strict_gs_check(on)  
  
void ** ReverseArray(void **pData,  
                     size_t cData)  
{  
    // *** This buffer is subject to being overrun!! ***  
    void *pReversed[20];  
  
    // Reverse the array into a temporary buffer  
    for (size_t j = 0, i = cData; i ; --i, ++j)  
        // *** Possible buffer overrun!! ***  
            pReversed[j] = pData[i];   
  
    // Copy temporary buffer back into input/output buffer  
    for (size_t i = 0; i < cData ; ++i)   
        pData[i] = pReversed[i];  
  
    return pData;  
}  
```  
  
## <a name="see-also"></a>Consulte também  
 
[Diretivas Pragma e a palavra-chave __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)<br/>
[/GS (verificação de segurança do buffer)](../build/reference/gs-buffer-security-check.md)