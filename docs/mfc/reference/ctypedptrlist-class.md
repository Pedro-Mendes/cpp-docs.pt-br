---
title: Classe CTypedPtrList | Documentos do Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTypedPtrList
- AFXTEMPL/CTypedPtrList
- AFXTEMPL/CTypedPtrList::AddHead
- AFXTEMPL/CTypedPtrList::AddTail
- AFXTEMPL/CTypedPtrList::GetAt
- AFXTEMPL/CTypedPtrList::GetHead
- AFXTEMPL/CTypedPtrList::GetNext
- AFXTEMPL/CTypedPtrList::GetPrev
- AFXTEMPL/CTypedPtrList::GetTail
- AFXTEMPL/CTypedPtrList::RemoveHead
- AFXTEMPL/CTypedPtrList::RemoveTail
- AFXTEMPL/CTypedPtrList::SetAt
dev_langs:
- C++
helpviewer_keywords:
- CTypedPtrList class
- type-safe collections
- lists [C++]
- template classes, CTypedPtrList class
- linked lists [C++]
- pointer lists
ms.assetid: c273096e-1756-4340-864b-4a08b674a65e
caps.latest.revision: 24
author: mikeblome
ms.author: mblome
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: ca8d868333aa977710e387fc1bb13271dc8f99fa
ms.lasthandoff: 02/25/2017

---
# <a name="ctypedptrlist-class"></a>Classe CTypedPtrList
Fornece um "wrapper" de tipo seguro para objetos da classe `CPtrList`.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
template<class BASE_CLASS, class TYPE>  
class CTypedPtrList : public BASE_CLASS  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `BASE_CLASS`  
 Classe base da classe ponteiro tipado lista; deve ser uma classe de lista do ponteiro ( `CObList` ou `CPtrList`).  
  
 `TYPE`  
 Tipo dos elementos armazenados na lista de classe base.  
  
## <a name="members"></a>Membros  
  
### <a name="public-methods"></a>Métodos Públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CTypedPtrList::AddHead](#addhead)|Adiciona um elemento (ou todos os elementos em outra lista) para o topo da lista (faz um novo cabeçalho).|  
|[CTypedPtrList::AddTail](#addtail)|Adiciona um elemento (ou todos os elementos em outra lista) até o final da lista (faz uma nova final).|  
|[CTypedPtrList::GetAt](#getat)|Obtém o elemento na posição especificada.|  
|[CTypedPtrList::GetHead](#gethead)|Retorna o elemento principal da lista (não pode ser vazio).|  
|[CTypedPtrList::GetNext](#getnext)|Obtém o próximo elemento de iteração.|  
|[CTypedPtrList::GetPrev](#getprev)|Obtém o elemento anterior para iteração.|  
|[CTypedPtrList::GetTail](#gettail)|Retorna o elemento final da lista (não pode ser vazio).|  
|[CTypedPtrList::RemoveHead](#removehead)|Remove o elemento do cabeçalho da lista.|  
|[CTypedPtrList::RemoveTail](#removetail)|Remove o elemento final da lista.|  
|[CTypedPtrList::SetAt](#setat)|Define o elemento na posição especificada.|  
  
## <a name="remarks"></a>Comentários  
 Quando você usa `CTypedPtrList` em vez de `CObList` ou `CPtrList`, o recurso de verificação de tipo C++ ajuda a eliminar erros causados por tipos de ponteiro incompatíveis.  
  
 Além disso, o `CTypedPtrList` wrapper executa muito a conversão que seria necessária se você usou `CObList` ou `CPtrList`.  
  
 Porque todos os `CTypedPtrList` funções embutidas, uso deste modelo não afeta significativamente o tamanho ou a velocidade do seu código.  
  
 Listas derivam de `CObList` pode ser serializada, mas os derivados de `CPtrList` não é possível.  
  
 Quando um `CTypedPtrList` objeto é excluído, ou quando seus elementos são removidos, somente os ponteiros são removidos, não as entidades que fazem referência.  
  
 Para obter mais informações sobre como usar o `CTypedPtrList`, consulte os artigos [coleções](../../mfc/collections.md) e [Classes com base no modelo](../../mfc/template-based-classes.md).  
  
## <a name="example"></a>Exemplo  
 Este exemplo cria uma instância de `CTypedPtrList`, adiciona um objeto, serializa a lista para o disco e, em seguida, exclui o objeto:  
  
 [!code-cpp[NVC_MFCCollections&#110;](../../mfc/codesnippet/cpp/ctypedptrlist-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCCollections&#111;](../../mfc/codesnippet/cpp/ctypedptrlist-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hierarquia de herança  
 `BASE_CLASS`  
  
 `_CTypedPtrList`  
  
 `CTypedPtrList`  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** afxtempl.h  
  
##  <a name="addhead"></a>CTypedPtrList::AddHead  
 Chama essa função de membro `BASE_CLASS` **:: AddHead**.  
  
```  
POSITION AddHead(TYPE newElement);  
void AddHead(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```  
  
### <a name="parameters"></a>Parâmetros  
 *TIPO*  
 Tipo dos elementos armazenados na lista de classe base.  
  
 `newElement`  
 O ponteiro de objeto a ser adicionado a essa lista. A **nulo** valor permitido.  
  
 `BASE_CLASS`  
 Classe base da classe ponteiro tipado lista; deve ser uma classe de lista do ponteiro ( [CObList](../../mfc/reference/coblist-class.md) ou [CPtrList](../../mfc/reference/cptrlist-class.md)).  
  
 `pNewList`  
 Um ponteiro para outro [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) objeto. Os elementos no `pNewList` serão adicionados a essa lista.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna a primeira versão do **posição** valor do elemento recém-inserido.  
  
### <a name="remarks"></a>Comentários  
 A primeira versão adiciona um novo elemento antes do início da lista. A segunda versão adiciona outra lista de elementos antes do título.  
  
##  <a name="addtail"></a>CTypedPtrList::AddTail  
 Chama essa função de membro `BASE_CLASS` **:: AddTail**.  
  
```  
POSITION AddTail(TYPE newElement);  
void AddTail(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```  
  
### <a name="parameters"></a>Parâmetros  
 *TIPO*  
 Tipo dos elementos armazenados na lista de classe base.  
  
 `newElement`  
 O ponteiro de objeto a ser adicionado a essa lista. A **nulo** valor permitido.  
  
 `BASE_CLASS`  
 Classe base da classe ponteiro tipado lista; deve ser uma classe de lista do ponteiro ( [CObList](../../mfc/reference/coblist-class.md) ou [CPtrList](../../mfc/reference/cptrlist-class.md)).  
  
 `pNewList`  
 Um ponteiro para outro [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) objeto. Os elementos no `pNewList` serão adicionados a essa lista.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna a primeira versão do **posição** valor do elemento recém-inserido.  
  
### <a name="remarks"></a>Comentários  
 A primeira versão adiciona um novo elemento após o final da lista. A segunda versão adiciona outra lista de elementos após o final da lista.  
  
##  <a name="getat"></a>CTypedPtrList::GetAt  
 Uma variável do tipo **posição** é uma chave para a lista.  
  
```  
TYPE& GetAt(POSITION position);  
TYPE GetAt(POSITION position) const;  
```  
  
### <a name="parameters"></a>Parâmetros  
 *TIPO*  
 Especifica o tipo de elementos armazenados na lista de parâmetro de modelo.  
  
 *posição*  
 A **posição** valor retornado por uma anterior `GetHeadPosition` ou **localizar** chamada de função de membro.  
  
### <a name="return-value"></a>Valor de retorno  
 Se a lista é acessada através de um ponteiro para um **CTypedPtrList const**, em seguida, `GetAt` retorna um ponteiro do tipo especificado pelo parâmetro de modelo *tipo*. Isso permite que a função a ser usada apenas no lado direito de uma instrução de atribuição e, portanto, protege a lista de modificação.  
  
 Se a lista é acessada diretamente ou através de um ponteiro para um `CTypedPtrList`, em seguida, `GetAt` retorna uma referência a um ponteiro do tipo especificado pelo parâmetro de modelo *tipo*. Isso permite que a função a ser usada em ambos os lados de uma instrução de atribuição e, portanto, permite que as entradas da lista a ser modificada.  
  
### <a name="remarks"></a>Comentários  
 Não é o mesmo que um índice, e você não pode operar em um **posição** valor por conta própria. `GetAt`recupera o `CObject` associado a uma determinada posição do ponteiro.  
  
 Você deve garantir que seu **posição** valor representa uma posição válida na lista. Se for inválido, a versão de depuração da Microsoft Foundation Class Library declara.  
  
 Essa função embutida chama `BASE_CLASS` **:: GetAt**.  
  
##  <a name="gethead"></a>CTypedPtrList::GetHead  
 Obtém o ponteiro que representa o elemento principal desta lista.  
  
```  
TYPE& GetHead();  
TYPE GetHead() const;  
```  
  
### <a name="parameters"></a>Parâmetros  
 *TIPO*  
 Especifica o tipo de elementos armazenados na lista de parâmetro de modelo.  
  
### <a name="return-value"></a>Valor de retorno  
 Se a lista é acessada através de um ponteiro para um **CTypedPtrList const**, em seguida, `GetHead` retorna um ponteiro do tipo especificado pelo parâmetro de modelo *tipo*. Isso permite que a função a ser usada apenas no lado direito de uma instrução de atribuição e, portanto, protege a lista de modificação.  
  
 Se a lista é acessada diretamente ou através de um ponteiro para um `CTypedPtrList`, em seguida, `GetHead` retorna uma referência a um ponteiro do tipo especificado pelo parâmetro de modelo *tipo*. Isso permite que a função a ser usada em ambos os lados de uma instrução de atribuição e, portanto, permite que as entradas da lista a ser modificada.  
  
### <a name="remarks"></a>Comentários  
 Certifique-se de que a lista não está vazia antes de chamar `GetHead`. Se a lista estiver vazia, a versão de depuração da Microsoft Foundation Class Library declara. Use [IsEmpty](../../mfc/reference/coblist-class.md#isempty) para verificar se a lista contém elementos.  
  
##  <a name="getnext"></a>CTypedPtrList::GetNext  
 Obtém o elemento de lista identificado por `rPosition`, em seguida, define `rPosition` para o **posição** valor da próxima entrada na lista.  
  
```  
TYPE& GetNext(POSITION& rPosition);  
TYPE GetNext(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Parâmetros  
 *TIPO*  
 Parâmetro de modelo especificando o tipo de elementos contidos nessa lista.  
  
 `rPosition`  
 Uma referência a um **posição** valor retornado por uma anterior `GetNext`, `GetHeadPosition`, ou outra chamada de função de membro.  
  
### <a name="return-value"></a>Valor de retorno  
 Se a lista é acessada através de um ponteiro para um **CTypedPtrList const**, em seguida, `GetNext` retorna um ponteiro do tipo especificado pelo parâmetro de modelo *tipo*. Isso permite que a função a ser usada apenas no lado direito de uma instrução de atribuição e, portanto, protege a lista de modificação.  
  
 Se a lista é acessada diretamente ou através de um ponteiro para um `CTypedPtrList`, em seguida, `GetNext` retorna uma referência a um ponteiro do tipo especificado pelo parâmetro de modelo *tipo*. Isso permite que a função a ser usada em ambos os lados de uma instrução de atribuição e, portanto, permite que as entradas da lista a ser modificada.  
  
### <a name="remarks"></a>Comentários  
 Você pode usar `GetNext` em um loop de iteração direta se estabelecer a posição inicial com uma chamada para `GetHeadPosition` ou [CPtrList::Find](../../mfc/reference/coblist-class.md#find).  
  
 Você deve garantir que seu **posição** valor representa uma posição válida na lista. Se for inválido, a versão de depuração da Microsoft Foundation Class Library declara.  
  
 Se o elemento recuperado é o último da lista, em seguida, o novo valor de `rPosition` é definido como **nulo**.  
  
 É possível remover um elemento durante uma iteração. Veja o exemplo de [CObList::RemoveAt](../../mfc/reference/coblist-class.md#removeat).  
  
##  <a name="getprev"></a>CTypedPtrList::GetPrev  
 Obtém o elemento de lista identificado por `rPosition`, em seguida, define `rPosition` para o **posição** valor da entrada anterior na lista.  
  
```  
TYPE& GetPrev(POSITION& rPosition);  
TYPE GetPrev(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Parâmetros  
 *TIPO*  
 Parâmetro de modelo especificando o tipo de elementos contidos nessa lista.  
  
 `rPosition`  
 Uma referência a um **posição** valor retornado por uma anterior `GetPrev` ou outra chamada de função de membro.  
  
### <a name="return-value"></a>Valor de retorno  
 Se a lista é acessada através de um ponteiro para um **CTypedPtrList const**, em seguida, `GetPrev` retorna um ponteiro do tipo especificado pelo parâmetro de modelo *tipo*. Isso permite que a função a ser usada apenas no lado direito de uma instrução de atribuição e, portanto, protege a lista de modificação.  
  
 Se a lista é acessada diretamente ou através de um ponteiro para um `CTypedPtrList`, em seguida, `GetPrev` retorna uma referência a um ponteiro do tipo especificado pelo parâmetro de modelo *tipo*. Isso permite que a função a ser usada em ambos os lados de uma instrução de atribuição e, portanto, permite que as entradas da lista a ser modificada.  
  
### <a name="remarks"></a>Comentários  
 Você pode usar `GetPrev` em um loop de iteração inversa se estabelecer a posição inicial com uma chamada para `GetTailPosition` ou **localizar**.  
  
 Você deve garantir que seu **posição** valor representa uma posição válida na lista. Se for inválido, a versão de depuração da Microsoft Foundation Class Library declara.  
  
 Se o elemento recuperado for o primeiro na lista, em seguida, o novo valor de `rPosition` é definido como **nulo**.  
  
##  <a name="gettail"></a>CTypedPtrList::GetTail  
 Obtém o ponteiro que representa o elemento principal desta lista.  
  
```  
TYPE& GetTail();  
TYPE GetTail() const;  
```  
  
### <a name="parameters"></a>Parâmetros  
 *TIPO*  
 Especifica o tipo de elementos armazenados na lista de parâmetro de modelo.  
  
### <a name="return-value"></a>Valor de retorno  
 Se a lista é acessada através de um ponteiro para um **CTypedPtrList const**, em seguida, `GetTail` retorna um ponteiro do tipo especificado pelo parâmetro de modelo *tipo*. Isso permite que a função a ser usada apenas no lado direito de uma instrução de atribuição e, portanto, protege a lista de modificação.  
  
 Se a lista é acessada diretamente ou através de um ponteiro para um `CTypedPtrList`, em seguida, `GetTail` retorna uma referência a um ponteiro do tipo especificado pelo parâmetro de modelo *tipo*. Isso permite que a função a ser usada em ambos os lados de uma instrução de atribuição e, portanto, permite que as entradas da lista a ser modificada.  
  
### <a name="remarks"></a>Comentários  
 Certifique-se de que a lista não está vazia antes de chamar `GetTail`. Se a lista estiver vazia, a versão de depuração da Microsoft Foundation Class Library declara. Use [IsEmpty](../../mfc/reference/coblist-class.md#isempty) para verificar se a lista contém elementos.  
  
##  <a name="removehead"></a>CTypedPtrList::RemoveHead  
 Remove o elemento do cabeçalho da lista e o retorna.  
  
```  
TYPE RemoveHead();
```  
  
### <a name="parameters"></a>Parâmetros  
 *TIPO*  
 Especifica o tipo de elementos armazenados na lista de parâmetro de modelo.  
  
### <a name="return-value"></a>Valor de retorno  
 O ponteiro anteriormente no topo da lista. Esse ponteiro é do tipo especificado pelo parâmetro de modelo *tipo*.  
  
### <a name="remarks"></a>Comentários  
 Certifique-se de que a lista não está vazia antes de chamar `RemoveHead`. Se a lista estiver vazia, a versão de depuração da Microsoft Foundation Class Library declara. Use [IsEmpty](../../mfc/reference/coblist-class.md#isempty) para verificar se a lista contém elementos.  
  
##  <a name="removetail"></a>CTypedPtrList::RemoveTail  
 Remove o elemento final da lista e o retorna.  
  
```  
TYPE RemoveTail();
```  
  
### <a name="parameters"></a>Parâmetros  
 *TIPO*  
 Especifica o tipo de elementos armazenados na lista de parâmetro de modelo.  
  
### <a name="return-value"></a>Valor de retorno  
 O ponteiro anteriormente ao final da lista. Esse ponteiro é do tipo especificado pelo parâmetro de modelo *tipo*.  
  
### <a name="remarks"></a>Comentários  
 Certifique-se de que a lista não está vazia antes de chamar `RemoveTail`. Se a lista estiver vazia, a versão de depuração da Microsoft Foundation Class Library declara. Use [IsEmpty](../../mfc/reference/coblist-class.md#isempty) para verificar se a lista contém elementos.  
  
##  <a name="setat"></a>CTypedPtrList::SetAt  
 Chama essa função de membro `BASE_CLASS` **:: SetAt**.  
  
```  
void SetAt(POSITION pos, TYPE newElement);
```  
  
### <a name="parameters"></a>Parâmetros  
 `pos`  
 O **posição** do elemento a ser definido.  
  
 *TIPO*  
 Tipo dos elementos armazenados na lista de classe base.  
  
 `newElement`  
 O ponteiro de objeto a serem gravados para a lista.  
  
### <a name="remarks"></a>Comentários  
 Uma variável do tipo **posição** é uma chave para a lista. Não é o mesmo que um índice, e você não pode operar em um **posição** valor por conta própria. `SetAt`grava o ponteiro de objeto para a posição especificada na lista.  
  
 Você deve garantir que seu **posição** valor representa uma posição válida na lista. Se for inválido, a versão de depuração da Microsoft Foundation Class Library declara.  
  
 Para obter mais comentários, consulte [CObList::SetAt](../../mfc/reference/coblist-class.md#setat).  
  
## <a name="see-also"></a>Consulte também  
 [Exemplo MFC COLETAR](../../visual-cpp-samples.md)   
 [Gráfico de hierarquia](../../mfc/hierarchy-chart.md)   
 [Classe CPtrList](../../mfc/reference/cptrlist-class.md)   
 [Classe cObList](../../mfc/reference/coblist-class.md)
