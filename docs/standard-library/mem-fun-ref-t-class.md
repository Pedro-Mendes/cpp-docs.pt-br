---
title: Classe mem_fun_ref_t | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::mem_fun_ref_t
dev_langs:
- C++
helpviewer_keywords:
- mem_fun_ref_t class
ms.assetid: 7dadcac3-8d33-4e4b-a792-81bd53d3df39
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a2dffdb71b8121073775af52ed42cda205c70589
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44100164"
---
# <a name="memfunreft-class"></a>Classe mem_fun_ref_t

Uma classe de adaptador que permite uma `non_const` função de membro que não usa argumentos seja chamada como um objeto de função unária quando inicializado com um argumento de referência.

## <a name="syntax"></a>Sintaxe

```cpp
template <class Result, class Type>
class mem_fun_ref_t : public unary_function<Type, Result> {
    explicit mem_fun_ref_t(
    Result (Type::* _Pm)());

    Result operator()(Type& left) const;

};
```

### <a name="parameters"></a>Parâmetros

*_Pm*<br/>
Um ponteiro para a função membro da classe `Type` a ser convertida em um objeto de função.

*left*<br/>
O objeto que o *_Pm* função de membro é chamada em.

## <a name="return-value"></a>Valor de retorno

Uma função unária adaptável.

## <a name="remarks"></a>Comentários

A classe de modelo armazena uma cópia dos *_Pm*, que deve ser um ponteiro para uma função de membro de classe `Type`, em um objeto de membro privado. Ela define sua função membro `operator()` como de retorno (**left**.* `_Pm`)( ).

## <a name="example"></a>Exemplo

Normalmente, o construtor de `mem_fun_ref_t` não é usado diretamente; a função auxiliar `mem_fun_ref` é usada para adaptar funções membro. Consulte [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref) para obter um exemplo de como usar adaptadores de função membro.

## <a name="requirements"></a>Requisitos

**Cabeçalho:** \<functional>

**Namespace:** std

## <a name="see-also"></a>Consulte também

[Acesso Thread-Safe na Biblioteca Padrão C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Referência da biblioteca padrão C++](../standard-library/cpp-standard-library-reference.md)<br/>
