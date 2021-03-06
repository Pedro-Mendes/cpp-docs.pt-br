---
title: Operadores &lt;allocators&gt; | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- allocators/std::operator!=
- allocators/std::operator==
dev_langs:
- C++
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
ms.openlocfilehash: 0bc4ce7c36d3ba097b04b1704fea7633eb7d26ea
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38962950"
---
# <a name="ltallocatorsgt-operators"></a>Operadores &lt;alocadores&gt;

Essas são as funções de operador de modelo global definidas &lt;alocadores&gt;. Para funções de operador de membro de classe, consulte a documentação da classe.

|||
|-|-|
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a>  operator!=

Testa a desigualdade entre objetos do alocador de uma classe especificada.

```cpp
template <class Type, class Sync>
bool operator!=(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```

### <a name="parameters"></a>Parâmetros

|Parâmetro|Descrição|
|---------------|-----------------|
|*left*|Um dos objetos alocadores a serem testados quanto à desigualdade.|
|*right*|Um dos objetos alocadores a serem testados quanto à desigualdade.|

### <a name="return-value"></a>Valor de retorno

**true** se os objetos alocadores não forem iguais, **false** se eles forem iguais.

### <a name="remarks"></a>Comentários

O operador de modelo retorna `!(left == right)`.

## <a name="op_eq_eq"></a>  operator==

Testa a igualdade entre objetos do alocador de uma classe especificada.

```cpp
template <class Type, class Sync>
bool operator==(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```

### <a name="parameters"></a>Parâmetros

|Parâmetro|Descrição|
|---------------|-----------------|
|*left*|Um dos objetos alocadores a serem testados quanto à igualdade.|
|*right*|Um dos objetos alocadores a serem testados quanto à igualdade.|

### <a name="return-value"></a>Valor de retorno

**true** se os objetos alocadores forem iguais, **false** se eles não forem iguais.

### <a name="remarks"></a>Comentários

Esse operador de modelo retorna `left.equals(right)`.

## <a name="see-also"></a>Consulte também

[\<allocators>](../standard-library/allocators-header.md)
