---
title: Classe value_compare | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::value_compare
- std.value_compare
- value_compare
dev_langs:
- C++
helpviewer_keywords:
- value_compare class
ms.assetid: c306c5b9-3505-4357-aa6b-216451b951ed
caps.latest.revision: 20
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
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: c82ae35feadcf1f28af47d3f055e854f7bcf6a34
ms.lasthandoff: 02/25/2017

---
# <a name="valuecompare-class"></a>Classe value_compare
Fornece um objeto de função que pode comparar os elementos de um hash_map comparando os valores de suas chaves para determinar sua ordem relativa no hash_map.  
  
## <a name="syntax"></a>Sintaxe  
  
```
class value_compare
 : std::public binary_function<value_type, value_type, bool>
{
public:
    bool operator()(
    const value_type& left,
    const value_type& right) const
 {
    return (comp(left.first, right.first));

 }
protected:
    value_compare(const key_compare& c) : comp (c) { }
    key_compare comp;
};
```  
  
## <a name="remarks"></a>Comentários  
 Os critérios de comparação fornecidos por value_compare entre **value_types** de elementos inteiros contidos por um hash_map são induzidos de uma comparação entre as chaves dos respectivos elementos pela construção da classe auxiliar. O operador da função membro usa o objeto **comp** do tipo `key_compare` armazenado no objeto da função fornecido por value_compare para comparar os componentes da chave de classificação de dois elementos.  
  
 Para hash_sets e hash_multisets, que são contêineres simples nos quais os valores de chave são idênticos aos valores dos elementos, value_compare é equivalente a `key_compare`; para hash_maps e hash_multimaps eles não são, uma vez que o valor dos elementos do tipo `pair` não é idêntico ao valor da chave do elemento.  
  
 No Visual C++ .NET 2003, membros dos arquivos de cabeçalho [<hash_map>](../standard-library/hash-map.md) e [<hash_set>](../standard-library/hash-set.md) não estão mais no namespace std e foram movidos para o namespace stdext. Consulte [Namespace stdext](../standard-library/stdext-namespace.md) para obter mais informações.  
  
## <a name="example"></a>Exemplo  
 Veja o exemplo de [hash_map::value_comp](../standard-library/hash-map-class.md#hash_map__value_comp) para obter um exemplo de como declarar e usar value_compare.  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** \<hash_map>  
  
 **Namespace:** stdext  
  
## <a name="see-also"></a>Consulte também  
 [Struct binary_function](../standard-library/binary-function-struct.md)   
 [Acesso Thread-Safe na Biblioteca Padrão C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Referência da biblioteca padrão C++](../standard-library/cpp-standard-library-reference.md)



