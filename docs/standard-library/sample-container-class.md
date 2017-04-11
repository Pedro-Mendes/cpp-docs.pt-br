---
title: Classe Sample Container | Microsoft Docs
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
- container classes
ms.assetid: 5b1451f2-c708-45da-bbf0-9e42fd687a1a
caps.latest.revision: 10
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 0f45ecbb6746c8d660e699ac0f7c08ecfb5dbb68
ms.lasthandoff: 02/25/2017

---
# <a name="sample-container-class"></a>Exemplo de Classe de Contêiner
> [!NOTE]
>  Este tópico faz parte da documentação do Visual C++ como um exemplo não funcional de contêineres usados na Biblioteca Padrão C++. Para obter mais informações, consulte [Contêineres da biblioteca padrão C++](../standard-library/stl-containers.md).  
  
 Descreve um objeto que controla uma sequência de elementos de comprimento variado, geralmente do tipo **Ty**. A sequência é armazenada de diferentes maneiras, dependendo do contêiner real.  
  
 Uma função de construtor ou membro de contêiner pode ser a ocasião para chamar o construtor **Ty**(**const Ty&**) ou a função **Ty::operator=**(**const Ty&**). Se tal chamada gerar uma exceção, o objeto de contêiner é obrigado a manter sua integridade e a relançar as exceções que ele captura. É possível trocar, atribuir, apagar ou destruir um objeto de contêiner com segurança depois que ele gera uma dessas exceções. Em geral, no entanto, não é possível prever de outra forma o estado da sequência controlada pelo objeto de contêiner.  
  
 Algumas limitações adicionais:  
  
-   Se a expressão **~Ty** gerar uma exceção, o estado resultante do objeto contêiner é indefinido.  
  
-   Se o contêiner armazenar um objeto de alocador *al* e *al* gera uma exceção diferente como resultado de uma chamada para *al***.allocate**, o estado resultante do objeto do contêiner é indefinido.  
  
-   Se o contêiner armazenar um objeto de função *comp*, para determinar como ordenar a sequência controlada, *comp* gera uma exceção de qualquer tipo, o estado resultante do objeto de contêiner é indefinido.  
  
 As classes de contêiner definidas pela Biblioteca Padrão C++ satisfazem a vários requisitos adicionais, conforme descrito nos parágrafos a seguir.  
  
 A classe de modelo de contêiner [lista](../standard-library/list-class.md) fornece comportamento determinístico e útil, mesmo na presença das exceções descritas acima. Pro exemplo, se uma exceção for gerada durante a inserção de um ou mais elementos, o contêiner permanecerá inalterado e a exceção será gerada novamente.  
  
 Para *todas* as classes de contêiner definidas pela Biblioteca Padrão C++, se uma exceção for gerada durante as chamadas para as seguintes funções membro:  
  
```  
<A NAME="vclrfcontainerinsert"></A>insert // single element inserted  
<A NAME="vclrfcontainerpushback"></A>push_back  
<A NAME="vclrfcontainerpushfront"></A>push_front  
```  
  
 o contêiner permanecerá inalterado e a exceção será gerada novamente.  
  
 Para *todas* as classes de contêiner definidas pela Biblioteca Padrão C++, nenhuma exceção é gerada durante as chamadas para as seguintes funções de membro:  
  
```  
<A NAME="vclrfcontainerpopback"></A>pop_back  
<A NAME="vclrfcontainerpopfront"></A>pop_front  
```  
  
 A função membro [erase](../standard-library/container-class-erase.md) gera uma exceção apenas se uma operação de cópia (construção de atribuição ou cópia) gerar uma exceção.  
  
 Além disso, nenhuma exceção é gerada ao copiar um iterador retornado por uma função membro.  
  
 A função de membro [swap](../standard-library/container-class-swap.md) faz promessas adicionais para *todas* as classes de contêiner definidas pela Biblioteca Padrão C++:  
  
-   A função de membro gera uma exceção apenas se o contêiner armazenar um objeto al alocador e `al` gera uma exceção quando copiado.  
  
-   Referências, ponteiros e iteradores que designam elementos das sequências controladas sendo trocados permanecem válidos.  
  
 Um objeto de uma classe de contêiner definido pela Biblioteca Padrão C++ aloca e libera armazenamento para a sequência controlada por meio de um objeto armazenado do tipo `Alloc`, que normalmente é um parâmetro de modelo. Esse objeto alocador deve ter a mesma interface externa que um objeto da classe **allocator\<Ty>**. Especificamente, `Alloc` deve ser do mesmo tipo que **Alloc::rebind<value_type>::other**  
  
 Para *todas* as classes de contêiner definidas pela Biblioteca Padrão C++, a função membro **Alloc get_allocator const;** retorna uma cópia do objeto alocador armazenado. Observe que o objeto alocador armazenado *não* é copiado quando o objeto de contêiner é atribuído. Todos os construtores inicializam o valor armazenado em **allocator** para `Alloc` se o construtor não contiver nenhum parâmetro alocador.  
  
 Segundo o Padrão C++, uma classe de contêiner definida pela Biblioteca Padrão C++ pode assumir que:  
  
-   Todos os objetos da classe `Alloc` são comparados igualmente.  
  
-   O tipo **Alloc::const_pointer** é o mesmo que **const Ty \***.  
  
-   O tipo **Alloc::const_reference** é o mesmo que **const Ty&**.  
  
-   O tipo **Alloc::pointer** é o mesmo que **Ty \***.  
  
-   O tipo **Alloc::reference** é o mesmo que **Ty&**.  
  
 Nessa implementação, no entanto, os contêineres não fazem essas pressuposições simplistas. Dessa forma, eles funcionam corretamente com objetos alocadores que são mais ambiciosos:  
  
-   Todos os objetos da classe `Alloc` não precisa ter comparação igual. (Você pode manter vários pools de armazenamento.)  
  
-   O tipo **Alloc::const_pointer** não precisa ser o mesmo que **const Ty \***. (Um ponteiro const pode ser uma classe.)  
  
-   O tipo **Alloc::pointer** não precisa ser o mesmo que **Ty \***. (Um ponteiro pode ser uma classe.)  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho**: \<sample container>  
  
## <a name="see-also"></a>Consulte também  
 [\<sample container>](../standard-library/sample-container.md)

