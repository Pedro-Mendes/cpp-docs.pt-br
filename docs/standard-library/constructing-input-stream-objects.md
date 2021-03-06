---
title: Construindo objetos de fluxo de entrada | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- input stream objects
ms.assetid: ab94866e-6ffe-4f15-b4db-0bd23e636075
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2c640f1b338fa4b0aa6dbcc408e0729fbf8ff90a
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38963544"
---
# <a name="constructing-input-stream-objects"></a>Construindo objetos de fluxo de entrada

Se você usar somente o objeto `cin`, não será necessário construir um fluxo de entrada. Será necessário construir um fluxo de entrada se você usar:

- [Construtores de fluxo de arquivo de entrada](#vclrfinputfilestreamconstructorsanchor8)

- [Construtores de fluxo de cadeia de caracteres de entrada](#vclrfinputstringstreamconstructorsanchor9)

## <a name="vclrfinputfilestreamconstructorsanchor8"></a> Construtores de fluxo de arquivo de entrada

Há duas maneiras de criar um fluxo de arquivo de entrada:

- Use o **void** construtor de argumento, em seguida, chame o `open` função de membro:

   ```cpp
   ifstream myFile; // On the stack
   myFile.open("filename");

   ifstream* pmyFile = new ifstream; // On the heap
   pmyFile->open("filename");
   ```

- Especifique um nome de arquivo e sinalizadores de modo na invocação do construtor, abrindo o arquivo durante o processo de construção:

   ```cpp
   ifstream myFile("filename");
   ```

## <a name="vclrfinputstringstreamconstructorsanchor9"></a> Construtores de fluxo de cadeia de caracteres de entrada

Construtores de fluxo de cadeia de caracteres de entrada exigem o endereço do armazenamento pré-alocado e pré-inicializado:

```cpp
string s("123.45");

double amt;
istringstream myString(s);

//istringstream myString("123.45") also works
myString>> amt; // amt contains 123.45
```

## <a name="see-also"></a>Consulte também

[Fluxos de entrada](../standard-library/input-streams.md)<br/>
