---
title: Classe CAtlList | Documentos do Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlList
- ATLCOLL/ATL::CAtlList
- ATLCOLL/ATL::CAtlList::INARGTYPE
- ATLCOLL/ATL::CAtlList::CAtlList
- ATLCOLL/ATL::CAtlList::AddHead
- ATLCOLL/ATL::CAtlList::AddHeadList
- ATLCOLL/ATL::CAtlList::AddTail
- ATLCOLL/ATL::CAtlList::AddTailList
- ATLCOLL/ATL::CAtlList::AssertValid
- ATLCOLL/ATL::CAtlList::Find
- ATLCOLL/ATL::CAtlList::FindIndex
- ATLCOLL/ATL::CAtlList::GetAt
- ATLCOLL/ATL::CAtlList::GetCount
- ATLCOLL/ATL::CAtlList::GetHead
- ATLCOLL/ATL::CAtlList::GetHeadPosition
- ATLCOLL/ATL::CAtlList::GetNext
- ATLCOLL/ATL::CAtlList::GetPrev
- ATLCOLL/ATL::CAtlList::GetTail
- ATLCOLL/ATL::CAtlList::GetTailPosition
- ATLCOLL/ATL::CAtlList::InsertAfter
- ATLCOLL/ATL::CAtlList::InsertBefore
- ATLCOLL/ATL::CAtlList::IsEmpty
- ATLCOLL/ATL::CAtlList::MoveToHead
- ATLCOLL/ATL::CAtlList::MoveToTail
- ATLCOLL/ATL::CAtlList::RemoveAll
- ATLCOLL/ATL::CAtlList::RemoveAt
- ATLCOLL/ATL::CAtlList::RemoveHead
- ATLCOLL/ATL::CAtlList::RemoveHeadNoReturn
- ATLCOLL/ATL::CAtlList::RemoveTail
- ATLCOLL/ATL::CAtlList::RemoveTailNoReturn
- ATLCOLL/ATL::CAtlList::SetAt
- ATLCOLL/ATL::CAtlList::SwapElements
dev_langs:
- C++
helpviewer_keywords:
- CAtlList class
ms.assetid: 09e98053-64b2-4efa-99ab-d0542caaf981
caps.latest.revision: 19
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
ms.openlocfilehash: b1ed350da625695f610980f9f48a6ae11394d3c8
ms.lasthandoff: 02/25/2017

---
# <a name="catllist-class"></a>Classe CAtlList
Essa classe fornece métodos para criar e gerenciar um objeto de lista.  
  
## <a name="syntax"></a>Sintaxe  
  
```
template<typename E, class ETraits = CElementTraits<E>>  
class CAtlList
```  
  
#### <a name="parameters"></a>Parâmetros  
 `E`  
 O tipo de elemento.  
  
 `ETraits`  
 O código usado para copiar ou mover elementos. Consulte [CElementTraits classe](../../atl/reference/celementtraits-class.md) para obter mais detalhes.  
  
## <a name="members"></a>Membros  
  
### <a name="public-typedefs"></a>Typedefs públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CAtlList::INARGTYPE](#inargtype)||  
  
### <a name="public-constructors"></a>Construtores públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CAtlList::CAtlList](#catllist)|O construtor.|  
|[CAtlList:: ~ CAtlList](#dtor)|O destruidor.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CAtlList::AddHead](#addhead)|Chame esse método para adicionar um elemento para o topo da lista.|  
|[CAtlList::AddHeadList](#addheadlist)|Chame esse método para adicionar uma lista existente para o topo da lista.|  
|[CAtlList::AddTail](#addtail)|Chame esse método para adicionar um elemento ao final dessa lista.|  
|[CAtlList::AddTailList](#addtaillist)|Chame esse método para adicionar uma lista existente até o final dessa lista.|  
|[CAtlList::AssertValid](#assertvalid)|Chame esse método para confirmar que a lista é válida.|  
|[CAtlList::Find](#find)|Chame esse método para pesquisar a lista para o elemento especificado.|  
|[CAtlList::FindIndex](#findindex)|Chame esse método para obter a posição de um elemento, dado um valor de índice.|  
|[CAtlList::GetAt](#getat)|Chame esse método para retornar o elemento em uma posição especificada na lista.|  
|[CAtlList::GetCount](#getcount)|Chame esse método para retornar o número de objetos na lista.|  
|[CAtlList::GetHead](#gethead)|Chame esse método para retornar o elemento no topo da lista.|  
|[CAtlList::GetHeadPosition](#getheadposition)|Chame esse método para obter a posição do cabeçalho da lista.|  
|[CAtlList::GetNext](#getnext)|Chame esse método para retornar o próximo elemento da lista.|  
|[CAtlList::GetPrev](#getprev)|Chame esse método para retornar o elemento anterior da lista.|  
|[CAtlList::GetTail](#gettail)|Chame esse método para retornar o elemento ao final da lista.|  
|[CAtlList::GetTailPosition](#gettailposition)|Chame esse método para obter a posição no final da lista.|  
|[CAtlList::InsertAfter](#insertafter)|Chame esse método para inserir um novo elemento na lista após a posição especificada.|  
|[CAtlList::InsertBefore](#insertbefore)|Chame esse método para inserir um novo elemento na lista antes da posição especificada.|  
|[CAtlList::IsEmpty](#isempty)|Chame esse método para determinar se a lista está vazia.|  
|[CAtlList::MoveToHead](#movetohead)|Chame esse método para mover o elemento especificado para o topo da lista.|  
|[CAtlList::MoveToTail](#movetotail)|Chame esse método para mover o elemento especificado até o final da lista.|  
|[CAtlList::RemoveAll](#removeall)|Chame esse método para remover todos os elementos da lista.|  
|[CAtlList::RemoveAt](#removeat)|Chame esse método para remover um único elemento da lista.|  
|[CAtlList::RemoveHead](#removehead)|Chame esse método para remover o elemento no topo da lista.|  
|[CAtlList::RemoveHeadNoReturn](#removeheadnoreturn)|Chame esse método para remover o elemento no topo da lista sem retornar um valor.|  
|[CAtlList::RemoveTail](#removetail)|Chame esse método para remover o elemento ao final da lista.|  
|[CAtlList::RemoveTailNoReturn](#removetailnoreturn)|Chame esse método para remover o elemento ao final da lista sem retornar um valor.|  
|[CAtlList::SetAt](#setat)|Chame esse método para definir o valor do elemento em uma determinada posição na lista.|  
|[CAtlList::SwapElements](#swapelements)|Chame esse método para trocar os elementos na lista.|  
  
## <a name="remarks"></a>Comentários  
 O `CAtlList` suporta ordenados listas de objetos não exclusivos acessíveis em sequência ou por valor. `CAtlList`listas se comportam como listas duplamente vinculadas. Cada lista possui um cabeçalho e uma final, e novos elementos (ou listas em alguns casos) podem ser adicionadas a qualquer uma das extremidades da lista ou inseridas antes ou depois de elementos específicos.  
  
 A maioria do `CAtlList` métodos fazem uso de um valor de posição. Esse valor é usado pelos métodos para fazer referência ao local de memória real em que os elementos são armazenados e devem não ser calculados ou previstos diretamente. Se for necessário para acessar o *n*º elemento na lista, o método [CAtlList::FindIndex](#findindex) retornará o valor da posição correspondente para um determinado índice. Os métodos [CAtlList::GetNext](#getnext) e [CAtlList::GetPrev](#getprev) pode ser usado para iterar os objetos na lista.  
  
 Para obter mais informações sobre as classes de coleção disponíveis com a ATL, consulte [Classes de coleção ATL](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** atlcoll.h  
  
##  <a name="addhead"></a>CAtlList::AddHead  
 Chame esse método para adicionar um elemento para o topo da lista.  
  
```
POSITION AddHead();
POSITION AddHead(INARGTYPE element);
```  
  
### <a name="parameters"></a>Parâmetros  
 `element`  
 O novo elemento.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna a posição do elemento recém-adicionado.  
  
### <a name="remarks"></a>Comentários  
 Se a primeira versão é usada, um elemento vazio é criado usando o construtor padrão, em vez de seu construtor de cópia.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities&13;](../../atl/codesnippet/cpp/catllist-class_1.cpp)]  
  
##  <a name="addheadlist"></a>CAtlList::AddHeadList  
 Chame esse método para adicionar uma lista existente para o topo da lista.  
  
```
void AddHeadList(const CAtlList<E, ETraits>* plNew);
```  
  
### <a name="parameters"></a>Parâmetros  
 `plNew`  
 A lista a ser adicionado.  
  
### <a name="remarks"></a>Comentários  
 A lista apontada por `plNew` é inserida no início da lista existente. Em compilações de depuração, uma falha de asserção ocorrerá se `plNew` é igual a nulo.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities&#14;](../../atl/codesnippet/cpp/catllist-class_2.cpp)]  
  
##  <a name="addtail"></a>CAtlList::AddTail  
 Chame esse método para adicionar um elemento ao final dessa lista.  
  
```
POSITION AddTail();
POSITION AddTail(INARGTYPE element);
```  
  
### <a name="parameters"></a>Parâmetros  
 `element`  
 O elemento a ser adicionado.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna a posição do elemento recém-adicionado.  
  
### <a name="remarks"></a>Comentários  
 Se a primeira versão é usada, um elemento vazio é criado usando o construtor padrão, em vez de seu construtor de cópia. O elemento é adicionado ao final da lista, e então fica agora a parte final. Esse método pode ser usado com uma lista vazia.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities&#15;](../../atl/codesnippet/cpp/catllist-class_3.cpp)]  
  
##  <a name="addtaillist"></a>CAtlList::AddTailList  
 Chame esse método para adicionar uma lista existente até o final dessa lista.  
  
```
void AddTailList(const CAtlList<E, ETraits>* plNew);
```  
  
### <a name="parameters"></a>Parâmetros  
 `plNew`  
 A lista a ser adicionado.  
  
### <a name="remarks"></a>Comentários  
 A lista apontada por `plNew` é inserido após o último elemento (se houver) no objeto da lista. O último elemento no `plNew` lista, portanto, torna-se a parte final. Em compilações de depuração, uma falha de asserção ocorrerá se *plNew* é igual a nulo.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities n º&16;](../../atl/codesnippet/cpp/catllist-class_4.cpp)]  
  
##  <a name="assertvalid"></a>CAtlList::AssertValid  
 Chame esse método para confirmar que a lista é válida.  
  
```
void AssertValid() const;
```  
  
### <a name="remarks"></a>Comentários  
 Compilações de depuração, uma falha de asserção ocorrerá se o objeto da lista não é válido. Para ser válida, uma lista vazia deve ter o cabeçalho e o final apontando para NULL, e uma lista que não esteja vazia deve ter o cabeçalho e o final apontando para endereços válidos.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[17 NVC_ATL_Utilities](../../atl/codesnippet/cpp/catllist-class_5.cpp)]  
  
##  <a name="catllist"></a>CAtlList::CAtlList  
 O construtor.  
  
```
CAtlList(UINT nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>Parâmetros  
 `nBlockSize`  
 O tamanho do bloco.  
  
### <a name="remarks"></a>Comentários  
 O construtor para o `CAtlList` objeto. O tamanho do bloco é uma medida da quantidade de memória alocada quando um novo elemento é necessário. Tamanhos maiores de bloco reduzem chamadas para rotinas de alocação de memória, mas usam mais recursos.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities n º&18;](../../atl/codesnippet/cpp/catllist-class_6.cpp)]  
  
##  <a name="dtor"></a>CAtlList:: ~ CAtlList  
 O destruidor.  
  
```
~CAtlList() throw();
```  
  
### <a name="remarks"></a>Comentários  
 Libera todos os recursos alocados, incluindo uma chamada para [CAtlList::RemoveAll](#removeall) para remover todos os elementos da lista.  
  
 Em compilações de depuração, uma falha de asserção ocorrerá se a lista ainda contém alguns elementos após a chamada para `RemoveAll`.  
  
##  <a name="find"></a>CAtlList::Find  
 Chame esse método para pesquisar a lista para o elemento especificado.  
  
```
POSITION Find(INARGTYPE element, POSITION posStartAfter = NULL) const throw();
```  
  
### <a name="parameters"></a>Parâmetros  
 `element`  
 O elemento a ser encontrado na lista.  
  
 `posStartAfter`  
 A posição inicial da pesquisa. Se nenhum valor for especificado, a pesquisa começa com o elemento principal.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna o valor da posição do elemento se encontrado, caso contrário, retornará NULL.  
  
### <a name="remarks"></a>Comentários  
 Em compilações de depuração, uma falha de asserção ocorrerá se o objeto da lista não é válido ou se o `posStartAfter` valor está fora do intervalo.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[19 NVC_ATL_Utilities](../../atl/codesnippet/cpp/catllist-class_7.cpp)]  
  
##  <a name="findindex"></a>CAtlList::FindIndex  
 Chame esse método para obter a posição de um elemento, dado um valor de índice.  
  
```
POSITION FindIndex(size_t iElement) const throw();
```  
  
### <a name="parameters"></a>Parâmetros  
 `iElement`  
 O índice baseado em zero do elemento lista necessária.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna o valor da posição correspondente, ou NULL se `iElement` está fora do intervalo.  
  
### <a name="remarks"></a>Comentários  
 Esse método retorna a posição correspondente a um valor de índice fornecido, permitindo o acesso para o *n*º elemento na lista.  
  
 Compilações de depuração, uma falha de asserção ocorrerá se o objeto da lista não é válido.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[20 NVC_ATL_Utilities](../../atl/codesnippet/cpp/catllist-class_8.cpp)]  
  
##  <a name="getat"></a>CAtlList::GetAt  
 Chame esse método para retornar o elemento em uma posição especificada na lista.  
  
```
E& GetAt(POSITION pos) throw();
const E& GetAt(POSITION pos) const throw();
```  
  
### <a name="parameters"></a>Parâmetros  
 `pos`  
 O valor da posição especificando um elemento específico.  
  
### <a name="return-value"></a>Valor de retorno  
 Uma referência ao ou uma cópia do elemento.  
  
### <a name="remarks"></a>Comentários  
 Se a lista for **const**, `GetAt` retorna uma cópia do elemento. Isso permite que o método a ser usado apenas no lado direito de uma instrução de atribuição e protege a lista de modificação.  
  
 Se a lista não é **const**, `GetAt` retorna uma referência ao elemento. Isso permite que o método a ser usado em ambos os lados de uma instrução de atribuição e, portanto, permite que as entradas da lista a ser modificada.  
  
 Em compilações de depuração, uma falha de asserção ocorrerá se `pos` é igual a nulo.  
  
### <a name="example"></a>Exemplo  
 Veja o exemplo de [CAtlList::FindIndex](#findindex).  
  
##  <a name="getcount"></a>CAtlList::GetCount  
 Chame esse método para retornar o número de objetos na lista.  
  
```
size_t GetCount() const throw();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna o número de elementos na lista.  
  
### <a name="example"></a>Exemplo  
 Veja o exemplo de [CAtlList::Find](#find).  
  
##  <a name="gethead"></a>CAtlList::GetHead  
 Chame esse método para retornar o elemento no topo da lista.  
  
```
E& GetHead() throw();
const E& GetHead() const throw();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna uma referência ou uma cópia do elemento no topo da lista.  
  
### <a name="remarks"></a>Comentários  
 Se a lista for **const**, `GetHead` retorna uma cópia do elemento no topo da lista. Isso permite que o método a ser usado apenas no lado direito de uma instrução de atribuição e protege a lista de modificação.  
  
 Se a lista não é **const**, `GetHead` retorna uma referência ao elemento no topo da lista. Isso permite que o método a ser usado em ambos os lados de uma instrução de atribuição e, portanto, permite que as entradas da lista a ser modificada.  
  
 Compilações de depuração, uma falha de asserção ocorrerá se o cabeçalho da lista aponta para NULL.  
  
### <a name="example"></a>Exemplo  
 Veja o exemplo de [CAtlList::AddHead](#addhead).  
  
##  <a name="getheadposition"></a>CAtlList::GetHeadPosition  
 Chame esse método para obter a posição do cabeçalho da lista.  
  
```
POSITION GetHeadPosition() const throw();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna o valor da posição correspondente ao elemento no topo da lista.  
  
### <a name="remarks"></a>Comentários  
 Se a lista estiver vazia, o valor retornado é NULL.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities&#21;](../../atl/codesnippet/cpp/catllist-class_9.cpp)]  
  
##  <a name="getnext"></a>CAtlList::GetNext  
 Chame esse método para retornar o próximo elemento da lista.  
  
```
E& GetNext(POSITION& pos) throw();
const E& GetNext(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>Parâmetros  
 `pos`  
 Um valor de posição, retornado por uma chamada anterior a `GetNext`, [CAtlList::GetHeadPosition](#getheadposition), ou outras `CAtlList` método.  
  
### <a name="return-value"></a>Valor de retorno  
 Se a lista for **const**, `GetNext` retorna uma cópia do próximo elemento da lista. Isso permite que o método a ser usado apenas no lado direito de uma instrução de atribuição e protege a lista de modificação.  
  
 Se a lista não é **const**, `GetNext` retorna uma referência para o próximo elemento da lista. Isso permite que o método a ser usado em ambos os lados de uma instrução de atribuição e, portanto, permite que as entradas da lista a ser modificada.  
  
### <a name="remarks"></a>Comentários  
 O contador de posição, `pos`, é atualizado para apontar para o próximo elemento na lista ou NULL se não existem mais elementos. Em compilações de depuração, uma falha de asserção ocorrerá se `pos` é igual a nulo.  
  
### <a name="example"></a>Exemplo  
 Veja o exemplo de [CAtlList::GetHeadPosition](#getheadposition).  
  
##  <a name="getprev"></a>CAtlList::GetPrev  
 Chame esse método para retornar o elemento anterior da lista.  
  
```
E& GetPrev(POSITION& pos) throw();
const E& GetPrev(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>Parâmetros  
 `pos`  
 Um valor de posição, retornado por uma chamada anterior a `GetPrev`, [CAtlList::GetTailPosition](#gettailposition), ou outras `CAtlList` método.  
  
### <a name="return-value"></a>Valor de retorno  
 Se a lista for **const**, `GetPrev` retorna uma cópia de um elemento da lista. Isso permite que o método a ser usado apenas no lado direito de uma instrução de atribuição e protege a lista de modificação.  
  
 Se a lista não é **const**, `GetPrev` retorna uma referência a um elemento da lista. Isso permite que o método a ser usado em ambos os lados de uma instrução de atribuição e, portanto, permite que as entradas da lista a ser modificada.  
  
### <a name="remarks"></a>Comentários  
 O contador de posição, `pos`, é atualizado para apontar para o elemento anterior na lista, ou nulo se não existem mais elementos. Em compilações de depuração, uma falha de asserção ocorrerá se `pos` é igual a nulo.  
  
### <a name="example"></a>Exemplo  
 Veja o exemplo de [CAtlList::GetTailPosition](#gettailposition).  
  
##  <a name="gettail"></a>CAtlList::GetTail  
 Chame esse método para retornar o elemento ao final da lista.  
  
```
E& GetTail() throw();
const E& GetTail() const throw();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna uma referência ou uma cópia do elemento ao final da lista.  
  
### <a name="remarks"></a>Comentários  
 Se a lista for **const**, `GetTail` retorna uma cópia do elemento no topo da lista. Isso permite que o método a ser usado apenas no lado direito de uma instrução de atribuição e protege a lista de modificação.  
  
 Se a lista não é **const**, `GetTail` retorna uma referência ao elemento no topo da lista. Isso permite que o método a ser usado em ambos os lados de uma instrução de atribuição e, portanto, permite que as entradas da lista a ser modificada.  
  
 Compilações de depuração, uma falha de asserção ocorrerá se o final da lista de pontos para NULL.  
  
### <a name="example"></a>Exemplo  
 Veja o exemplo de [CAtlList::AddTail](#addtail).  
  
##  <a name="gettailposition"></a>CAtlList::GetTailPosition  
 Chame esse método para obter a posição no final da lista.  
  
```
POSITION GetTailPosition() const throw();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna o valor da posição correspondente ao elemento ao final da lista.  
  
### <a name="remarks"></a>Comentários  
 Se a lista estiver vazia, o valor retornado é NULL.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities&#22;](../../atl/codesnippet/cpp/catllist-class_10.cpp)]  
  
##  <a name="inargtype"></a>CAtlList::INARGTYPE  
 Tipo usado quando um elemento é passado como um argumento de entrada.  
  
```
typedef ETraits::INARGTYPE INARGTYPE;
```  
  
##  <a name="insertafter"></a>CAtlList::InsertAfter  
 Chame esse método para inserir um novo elemento na lista após a posição especificada.  
  
```
POSITION InsertAfter(POSITION pos, INARGTYPE element);
```  
  
### <a name="parameters"></a>Parâmetros  
 `pos`  
 O valor da posição após o qual o novo elemento será inserido.  
  
 `element`  
 O elemento a ser inserido.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna o valor da posição do novo elemento.  
  
### <a name="remarks"></a>Comentários  
 Compilações de depuração, uma falha de asserção ocorrerá se a lista não é válida, se a inserção falhar, ou se for feita uma tentativa de inserir o elemento após o final.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities&#23;](../../atl/codesnippet/cpp/catllist-class_11.cpp)]  
  
##  <a name="insertbefore"></a>CAtlList::InsertBefore  
 Chame esse método para inserir um novo elemento na lista antes da posição especificada.  
  
```
POSITION InsertBefore(POSITION pos, INARGTYPE element);
```  
  
### <a name="parameters"></a>Parâmetros  
 `pos`  
 O novo elemento será inserido na lista antes desse valor de posição.  
  
 `element`  
 O elemento a ser inserido.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna o valor da posição do novo elemento.  
  
### <a name="remarks"></a>Comentários  
 Compilações de depuração, uma falha de asserção ocorrerá se a lista não é válida, se a inserção falhar, ou se for feita uma tentativa de inserir o elemento de cabeçalho.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities&#24;](../../atl/codesnippet/cpp/catllist-class_12.cpp)]  
  
##  <a name="isempty"></a>CAtlList::IsEmpty  
 Chame esse método para determinar se a lista está vazia.  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Retornará true se a lista não contém objetos, caso contrário, falsos.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[25 NVC_ATL_Utilities](../../atl/codesnippet/cpp/catllist-class_13.cpp)]  
  
##  <a name="movetohead"></a>CAtlList::MoveToHead  
 Chame esse método para mover o elemento especificado para o topo da lista.  
  
```
void MoveToHead(POSITION pos) throw();
```  
  
### <a name="parameters"></a>Parâmetros  
 `pos`  
 O valor da posição do elemento para mover.  
  
### <a name="remarks"></a>Comentários  
 O elemento especificado é movido de sua posição atual para o topo da lista. Em compilações de depuração, uma falha de asserção ocorrerá se `pos` é igual a nulo.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities&#26;](../../atl/codesnippet/cpp/catllist-class_14.cpp)]  
  
##  <a name="movetotail"></a>CAtlList::MoveToTail  
 Chame esse método para mover o elemento especificado até o final da lista.  
  
```
void MoveToTail(POSITION pos) throw();
```  
  
### <a name="parameters"></a>Parâmetros  
 `pos`  
 O valor da posição do elemento para mover.  
  
### <a name="remarks"></a>Comentários  
 O elemento especificado é movido de sua posição atual até o final da lista. Em compilações de depuração, uma falha de asserção ocorrerá se `pos` é igual a nulo.  
  
### <a name="example"></a>Exemplo  
 Veja o exemplo de [CAtlList::MoveToHead](#movetohead).  
  
##  <a name="removeall"></a>CAtlList::RemoveAll  
 Chame esse método para remover todos os elementos da lista.  
  
```
void RemoveAll() throw();
```  
  
### <a name="remarks"></a>Comentários  
 Esse método Remove todos os elementos da lista e libera a memória alocada. Um ATLASSERT em compilações de depurações, será gerado se todos os elementos não são excluídos ou se a estrutura da lista foi corrompida.  
  
### <a name="example"></a>Exemplo  
 Veja o exemplo de [CAtlList::IsEmpty](#isempty).  
  
##  <a name="removeat"></a>CAtlList::RemoveAt  
 Chame esse método para remover um único elemento da lista.  
  
```
void RemoveAt(POSITION pos) throw();
```  
  
### <a name="parameters"></a>Parâmetros  
 `pos`  
 O valor da posição do elemento a ser removido.  
  
### <a name="remarks"></a>Comentários  
 O elemento referenciado pelo `pos` for removido, e a memória é liberada. É aceitável usar `RemoveAt` para remover o início ou o final da lista.  
  
 Compilações de depuração, uma falha de asserção ocorrerá se a lista não é válida ou se remover o elemento faz com que a lista para a memória de acesso que não faz parte da estrutura da lista.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities&#27;](../../atl/codesnippet/cpp/catllist-class_15.cpp)]  
  
##  <a name="removehead"></a>CAtlList::RemoveHead  
 Chame esse método para remover o elemento no topo da lista.  
  
```
E RemoveHead();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna o elemento no topo da lista.  
  
### <a name="remarks"></a>Comentários  
 O principal elemento é excluído da lista e memória é liberada. Uma cópia do elemento é retornada. Compilações de depuração, uma falha de asserção ocorrerá se a lista está vazia.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities&#28;](../../atl/codesnippet/cpp/catllist-class_16.cpp)]  
  
##  <a name="removeheadnoreturn"></a>CAtlList::RemoveHeadNoReturn  
 Chame esse método para remover o elemento no topo da lista sem retornar um valor.  
  
```
void RemoveHeadNoReturn() throw();
```  
  
### <a name="remarks"></a>Comentários  
 O principal elemento é excluído da lista e memória é liberada. Compilações de depuração, uma falha de asserção ocorrerá se a lista está vazia.  
  
### <a name="example"></a>Exemplo  
 Veja o exemplo de [CAtlList::IsEmpty](#isempty).  
  
##  <a name="removetail"></a>CAtlList::RemoveTail  
 Chame esse método para remover o elemento ao final da lista.  
  
```
E RemoveTail();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna o elemento ao final da lista.  
  
### <a name="remarks"></a>Comentários  
 O elemento final é excluído da lista e memória é liberada. Uma cópia do elemento é retornada. Compilações de depuração, uma falha de asserção ocorrerá se a lista está vazia.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[29 NVC_ATL_Utilities](../../atl/codesnippet/cpp/catllist-class_17.cpp)]  
  
##  <a name="removetailnoreturn"></a>CAtlList::RemoveTailNoReturn  
 Chame esse método para remover o elemento ao final da lista sem retornar um valor.  
  
```
void RemoveTailNoReturn() throw();
```  
  
### <a name="remarks"></a>Comentários  
 O elemento final é excluído da lista e memória é liberada. Compilações de depuração, uma falha de asserção ocorrerá se a lista está vazia.  
  
### <a name="example"></a>Exemplo  
 Veja o exemplo de [CAtlList::IsEmpty](#isempty).  
  
##  <a name="setat"></a>CAtlList::SetAt  
 Chame esse método para definir o valor do elemento em uma determinada posição na lista.  
  
```
void SetAt(POSITION pos, INARGTYPE element);
```  
  
### <a name="parameters"></a>Parâmetros  
 `pos`  
 O valor da posição correspondente ao elemento para alterar.  
  
 `element`  
 O novo valor do elemento.  
  
### <a name="remarks"></a>Comentários  
 Substitui o valor existente com `element`. Em compilações de depuração, uma falha de asserção ocorrerá se `pos` é igual a nulo.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[30 NVC_ATL_Utilities](../../atl/codesnippet/cpp/catllist-class_18.cpp)]  
  
##  <a name="swapelements"></a>CAtlList::SwapElements  
 Chame esse método para trocar os elementos na lista.  
  
```
void SwapElements(POSITION pos1, POSITION pos2) throw();
```  
  
### <a name="parameters"></a>Parâmetros  
 *pos1*  
 O primeiro valor da posição.  
  
 *pos2*  
 O segundo valor da posição.  
  
### <a name="remarks"></a>Comentários  
 Troca os elementos em duas posições especificadas. Compilações de depuração, uma falha de asserção ocorrerá se o valor da posição é igual a nulo.  
  
### <a name="example"></a>Exemplo  
 [!code-cpp[NVC_ATL_Utilities&#31;](../../atl/codesnippet/cpp/catllist-class_19.cpp)]  
  
## <a name="see-also"></a>Consulte também  
 [Classe CList](../../mfc/reference/clist-class.md)   
 [Visão geral da classe](../../atl/atl-class-overview.md)
