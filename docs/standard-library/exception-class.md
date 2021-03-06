---
title: Classe exception | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- exception
dev_langs:
- C++
helpviewer_keywords:
- exception class
ms.assetid: 4f181f67-5888-4b50-89a6-745091ffb2fe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ec1cfe2be7f6a2172b6624f15cb3dcde4f0ba3c2
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38957012"
---
# <a name="exception-class"></a>Classe exception

A classe atua como a classe base de todas as exceções lançadas por determinadas expressões e pela biblioteca padrão C++.

## <a name="syntax"></a>Sintaxe

```cpp
class exception {
   public:
   exception();
   exception(const char* const &message);
   exception(const char* const &message, int);
   exception(const exception &right);
   exception& operator=(const exception &right);
   virtual ~exception();
   virtual const char *what() const;
   };
```

## <a name="remarks"></a>Comentários

Especificamente, essa classe base é a raiz das classes de exceção padrão definidas em [\<stdexcept>](../standard-library/stdexcept.md). O valor da cadeia de caracteres C retornado por `what` é deixado como não especificado pelo construtor padrão, mas pode ser definido por construtores para determinadas classes derivadas como uma cadeia de caracteres C definida pela implementação. Nenhuma das funções de membro lança exceções.

O **int** parâmetro permite que você especifique que a memória não deve ser alocada. O valor de **int** será ignorado.

> [!NOTE]
> Os construtores `exception(const char* const &message)` e `exception(const char* const &message, int)` são extensões da Microsoft à biblioteca padrão C++.

## <a name="example"></a>Exemplo

Para obter exemplos de uso das classes de exceção padrão que herdam da classe `exception`, consulte uma das classes definidas em [\<stdexcept>](../standard-library/stdexcept.md).

## <a name="requirements"></a>Requisitos

**Cabeçalho:** \<exception>

**Namespace:** std

## <a name="see-also"></a>Consulte também

[Acesso Thread-Safe na Biblioteca Padrão C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
