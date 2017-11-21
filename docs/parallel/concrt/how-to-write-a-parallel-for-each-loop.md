---
title: 'Como: gravar um Loop parallel_for_each | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- writing a parallel_for_each loop [Concurrency Runtime]
- parallel_for_each function, example
ms.assetid: fa9c0ba6-ace0-4f88-8681-c7c1f52aff20
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c3d641fe0437e371fdd45e2d497fbf865e41fa3c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-write-a-parallelforeach-loop"></a>Como gravar um loop parallel_for_each
Este exemplo mostra como usar o [Concurrency:: parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritmo para calcular a contagem de números primos em uma [std:: array](../../standard-library/array-class-stl.md) objeto em paralelo.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir calcula a contagem de números primos em uma matriz de duas vezes. O exemplo primeiro usa o [std::for_each](../../standard-library/algorithm-functions.md#for_each) algoritmo para calcular a contagem em série. O exemplo usa o `parallel_for_each` algoritmo para realizar a mesma tarefa em paralelo. O exemplo também imprime no console o tempo necessário para executar ambos os cálculos.  
  
 [!code-cpp[concrt-parallel-count-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-each-loop_1.cpp)]  
  
 A seguinte saída de exemplo é para um computador com quatro processadores.  
  
```Output  
serial version:  
found 17984 prime numbers  
took 6115 ms  
 
parallel version:  
found 17984 prime numbers  
took 1653 ms  
```  
  
## <a name="compiling-the-code"></a>Compilando o código  
 Para compilar o código, copiá-lo e, em seguida, cole-o em um projeto do Visual Studio ou colá-lo em um arquivo chamado `parallel-count-primes.cpp` e, em seguida, execute o seguinte comando em uma janela de Prompt de comando do Visual Studio.  
  
 **cl.exe /EHsc paralelo-contagem-primes.cpp**  
  
## <a name="robust-programming"></a>Programação robusta  
 A expressão lambda que o exemplo passa para o `parallel_for_each` usa o algoritmo de `InterlockedIncrement` função para habilitar paralelas iterações do loop para incrementar o contador simultaneamente. Se você usar funções como `InterlockedIncrement` para sincronizar o acesso aos recursos compartilhados, você pode apresentar os gargalos de desempenho em seu código. Você pode usar um mecanismo de sincronização sem bloqueio, por exemplo, o [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) classe, para eliminar o acesso simultâneo a recursos compartilhados. Para obter um exemplo que usa o `combinable` classe dessa maneira, consulte [como: usar Combinável para melhorar o desempenho](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md).  
  
## <a name="see-also"></a>Consulte também  
 [Algoritmos paralelos](../../parallel/concrt/parallel-algorithms.md)   
 [Função parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each)

