---
title: Classe mem_fun1_t | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mem_fun1_t
- std.mem_fun1_t
- std::mem_fun1_t
- xfunctional/std::mem_fun1_t
dev_langs:
- C++
helpviewer_keywords:
- mem_fun1_t class
ms.assetid: 01a8c2c2-b2f7-4e3f-869c-5b5b9f06ea54
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
ms.sourcegitcommit: 2d05749ba2837a3879c91886b9266de47dd2ece6
ms.openlocfilehash: 434e4032216922071d60d7a7ad6a36b7f6135f7e
ms.lasthandoff: 02/25/2017

---
# <a name="memfun1t-class"></a>Classe mem_fun1_t
Uma classe de adaptador que permite que uma função membro **non_const** que usa um único argumento seja chamada como um objeto de função binária quando inicializada com um argumento de ponteiro.  
  
## <a name="syntax"></a>Sintaxe  
  
```
template <class Result, class Type, class Arg>
class mem_fun1_t : public binary_function<Type *, Arg, Result> {
    explicit mem_fun1_t(
    Result (Type::* _Pm)(Arg));

    Result operator()(
    Type* _Pleft,
    Arg right) const;

 };
```  
  
#### <a name="parameters"></a>Parâmetros  
 `_Pm`  
 Um ponteiro para a função membro da classe **Type** a ser convertido em um objeto de função.  
  
 `_Pleft`  
 O objeto no qual a função membro `_Pm` é chamada.  
  
 `right`  
 O argumento que está sendo fornecido para `_Pm`.  
  
## <a name="return-value"></a>Valor de retorno  
 Uma função binária adaptável.  
  
## <a name="remarks"></a>Comentários  
 A classe de modelo armazena uma cópia de `_Pm`, que deve ser um ponteiro para uma função membro da classe **Type**, em um objeto de membro privado. Ela define sua função membro `operator()` como de retorno (**_Pleft**->\* `_Pm`)( **right**).  
  
## <a name="example"></a>Exemplo  
  Normalmente, o construtor de `mem_fun1_t` não é usado diretamente; a função auxiliar `mem_fun` é usada para adaptar funções membro. Consulte [mem_fun](../standard-library/functional-functions.md#mem_fun_function) para obter um exemplo de como usar adaptadores de função membro.  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** \<functional>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Consulte também  
 [Acesso Thread-Safe na Biblioteca Padrão C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Referência da biblioteca padrão C++](../standard-library/cpp-standard-library-reference.md)



