---
title: Classe const_mem_fun_t | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::const_mem_fun_t
dev_langs:
- C++
helpviewer_keywords:
- const_mem_fun_t class
ms.assetid: f169d381-019b-4a0e-a9a3-54da6d948270
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3b813128f07376d017a3ea76d6bb359db437f6f3
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44100190"
---
# <a name="constmemfunt-class"></a>Classe const_mem_fun_t

Uma classe de adaptador que permite que uma função de membro const que não usa argumentos seja chamada como um objeto de função unária quando inicializado com um argumento de referência.

## <a name="syntax"></a>Sintaxe

```cpp
template <class Result, class Type>
class const_mem_fun_t : public unary_function <Type *, Result>
{
    explicit const_mem_fun_t(Result (Type::* Pm)() const);
    Result operator()(const Type* Pleft) const;
};
```

### <a name="parameters"></a>Parâmetros

*PM*<br/>
Um ponteiro para a função membro da classe `Type` a ser convertida em um objeto de função.

*Pleft*<br/>
O objeto que o *Pm* função de membro é chamada em.

## <a name="return-value"></a>Valor de retorno

Uma função unária adaptável.

## <a name="remarks"></a>Comentários

A classe de modelo armazena uma cópia dos *Pm*, que deve ser um ponteiro para uma função de membro de classe `Type`, em um objeto de membro privado. Ela define sua função de membro `operator()` como de retorno ( `Pleft`->\* `Pm`)() **const**.

## <a name="example"></a>Exemplo

Normalmente, o construtor de `const_mem_fun_t` não é usado diretamente; a função auxiliar `mem_fun` é usada para adaptar funções membro. Consulte [mem_fun](../standard-library/functional-functions.md#mem_fun) para obter um exemplo de como usar adaptadores de função membro.

## <a name="requirements"></a>Requisitos

**Cabeçalho:** \<functional>

**Namespace:** std

## <a name="see-also"></a>Consulte também

[Acesso Thread-Safe na Biblioteca Padrão C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Referência da biblioteca padrão C++](../standard-library/cpp-standard-library-reference.md)<br/>
