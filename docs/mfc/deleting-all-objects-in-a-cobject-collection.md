---
title: "Excluindo todos os objetos em uma coleção CObject | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- objects [MFC], deleting in collections
- objects in CObject collections, deleting
- CObject class [MFC], deleting in collection
- collection classes [MFC], deleting all objects
- CObject class collection
- objects in CObject collections
- collection classes [MFC], shared objects
ms.assetid: 81d2c1d5-a0a5-46e1-8ab9-82b45cf7afd2
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 04f1edc7f181bdb23e050d2fa608c9b3a2056749
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="deleting-all-objects-in-a-cobject-collection"></a>Excluindo todos os objetos em uma coleção CObject
Este artigo explica como excluir todos os objetos em uma coleção (sem excluir o próprio objeto de coleção).  
  
 Para excluir todos os objetos em uma coleção de `CObject`s (ou dos objetos derivados de `CObject`), você usar uma das técnicas de iteração descritas no artigo [acessar todos os membros de uma coleção](../mfc/accessing-all-members-of-a-collection.md) para excluir cada objeto em Ative.  
  
> [!CAUTION]
>  Objetos em coleções podem ser compartilhados. Ou seja, a coleção mantém um ponteiro para o objeto, mas outras partes do programa também podem ter ponteiros para o mesmo objeto. Você deve ter cuidado para não excluir um objeto que é compartilhado até que todas as partes terminar de usar o objeto.  
  
 Este artigo mostra como excluir os objetos em:  
  
-   [Uma lista](#_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject)  
  
-   [Uma matriz](#_core_to_delete_all_elements_in_an_array)  
  
-   [Um mapa](#_core_to_delete_all_elements_in_a_map)  
  
#### <a name="_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject"></a>Para excluir todos os objetos em uma lista de ponteiros para CObject  
  
1.  Use `GetHeadPosition` e `GetNext` para iterar através da lista.  
  
2.  Use o **excluir** operador excluir cada objeto que é encontrado na iteração.  
  
3.  Chamar o `RemoveAll` function para remover todos os elementos da lista após a exclusão de objetos associados a esses elementos.  
  
 O exemplo a seguir mostra como excluir todos os objetos em uma lista de `CPerson` objetos. Cada objeto na lista é um ponteiro para um `CPerson` objeto que foi originalmente alocado no heap.  
  
 [!code-cpp[NVC_MFCCollections#17](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_1.cpp)]  
  
 A última chamada de função, `RemoveAll`, é uma função de membro de lista que remove todos os elementos da lista. A função de membro `RemoveAt` remove um único elemento.  
  
 Observe a diferença entre a exclusão de objeto de um elemento e remover o elemento em si. Remover um elemento da lista simplesmente remove a referência da lista para o objeto. O objeto ainda existe na memória. Quando você exclui um objeto, ele deixa de existir e sua memória é recuperada. Portanto, é importante remover um elemento imediatamente após a exclusão de objeto do elemento para que a lista não tente acessar objetos que não existem mais.  
  
#### <a name="_core_to_delete_all_elements_in_an_array"></a>Para excluir todos os elementos em uma matriz  
  
1.  Use `GetSize` e valores de índice de inteiro para iterar por meio da matriz.  
  
2.  Use o **excluir** operador excluir cada elemento que é encontrado na iteração.  
  
3.  Chamar o `RemoveAll` function para remover todos os elementos da matriz após ele ter sido excluído.  
  
     O código para excluir todos os elementos de uma matriz é o seguinte:  
  
     [!code-cpp[NVC_MFCCollections#18](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_2.cpp)]  
  
 Como o exemplo da lista acima, você pode chamar `RemoveAll` para remover todos os elementos em uma matriz ou `RemoveAt` para remover um elemento individual.  
  
#### <a name="_core_to_delete_all_elements_in_a_map"></a>Para excluir todos os elementos em um mapa  
  
1.  Use `GetStartPosition` e `GetNextAssoc` para iterar por meio da matriz.  
  
2.  Use o **excluir** operador para excluir a chave e/ou o valor para cada elemento do mapa que for encontrado na iteração.  
  
3.  Chamar o `RemoveAll` function para remover todos os elementos do mapa após ele ter sido excluído.  
  
     O código para excluir todos os elementos de um `CMap` coleção é da seguinte maneira. Cada elemento no mapa tem uma cadeia de caracteres como a chave e um `CPerson` objeto (derivado de `CObject`) como o valor.  
  
     [!code-cpp[NVC_MFCCollections#19](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_3.cpp)]  
  
 Você pode chamar `RemoveAll` para remover todos os elementos em um mapa ou `RemoveKey` para remover um elemento individual com a chave especificada.  
  
## <a name="see-also"></a>Consulte também  
 [Acessando todos os membros de uma coleção](../mfc/accessing-all-members-of-a-collection.md)
