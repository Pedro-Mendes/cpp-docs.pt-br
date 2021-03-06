---
title: Resumo do tempo de vida e visibilidade | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- lifetime, and visibility
- visibility, identifiers
ms.assetid: ea05a253-7658-482c-9a6b-abd71169c42d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6ef73c7e9592f1365e946d32d2aecc5894899316
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061520"
---
# <a name="summary-of-lifetime-and-visibility"></a>Resumo de tempo de vida e visibilidade

A tabela a seguir é um resumo das características do tempo de vida e de visibilidade para a maioria dos identificadores. As três primeiras colunas dão os atributos que definem o tempo de vida e visibilidade. Um identificador com os atributos dados pelas três primeiras colunas tem o tempo de vida e a visibilidade mostrados na quarta e quinta colunas. No entanto, a tabela não abrange todos os casos possíveis. Consulte [Classes de armazenamento](../c-language/c-storage-classes.md) para obter mais informações.

### <a name="summary-of-lifetime-and-visibility"></a>Resumo de tempo de vida e visibilidade

|Atributos:<br /><br /> Nível|Item|Storage-Class<br /><br /> Especificador|Resultado:<br /><br /> Tempo de vida|Visibilidade|
|---------------------------|----------|----------------------------------|--------------------------|----------------|
|Escopo de arquivo|Definição de variável|**static**|Global|Restante do arquivo de origem no qual ocorre|
||Declaração de variável|**extern**|Global|Restante do arquivo de origem no qual ocorre|
||Protótipo ou definição de função|**static**|Global|Arquivo único de origem|
||Protótipo da função|**extern**|Global|Restante do arquivo de origem|
|Escopo de bloco|Declaração de variável|**extern**|Global|Bloco|
||Definição de variável|**static**|Global|Bloco|
||Definição de variável|**auto** ou **registrar**|Local|Bloco|

## <a name="example"></a>Exemplo

### <a name="description"></a>Descrição

O exemplo a seguir ilustra blocos, aninhamento e visibilidade das variáveis:

### <a name="code"></a>Código

```
// Lifetime_and_Visibility.c

#include <stdio.h>

int i = 1;  // i defined at external level

int main()  // main function defined at external level
{
    printf_s( "%d\n", i ); // Prints 1 (value of external level i)
    {                                 // Begin first nested block
        int i = 2, j = 3;          // i and j defined at internal level
        printf_s( "%d %d\n", i, j );  // Prints 2, 3
        {                             // Begin second nested block
            int i = 0;                // i is redefined
            printf_s( "%d %d\n", i, j ); // Prints 0, 3
        }                             // End of second nested block
        printf_s( "%d\n", i );        // Prints 2 (outer definition
                                      //  restored)
    }                                 // End of first nested block
    printf_s( "%d\n", i );            // Prints 1 (external level
                                      // definition restored)
    return 0;
}
```

### <a name="comments"></a>Comentários

Neste exemplo, há quatro níveis de visibilidade: o nível externo e três níveis de bloco. Os valores são impressos na tela como observado nos comentários após cada instrução.

## <a name="see-also"></a>Consulte também

[Tempo de vida, escopo, visibilidade e vinculação](../c-language/lifetime-scope-visibility-and-linkage.md)