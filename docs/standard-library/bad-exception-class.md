---
title: Classe bad_exception | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: exception/std::bad_exception
dev_langs: C++
helpviewer_keywords: bad_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b5b91f3019a46aa011f95ae26434456d1e41de08
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="badexception-class"></a>Classe bad_exception
A classe descreve uma exceção que pode ser gerada de um manipulador inesperado.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
class bad_exception    : public exception {};  
```  
  
## <a name="remarks"></a>Comentários  
 [unexpected](../standard-library/exception-functions.md#unexpected) lançará um `bad_exception`, em vez de encerrar ou em vez de chamar outra função especificada com [set_unexpected](../standard-library/exception-functions.md#set_unexpected) se `bad_exception` estiver incluído na lista de lançamento de uma função.  
  
 O valor retornado por **o quê** é uma cadeia de caracteres C definida pela implementação. Nenhuma das funções de membro lança exceções.  
  
 Para obter uma lista de membros herdados pela classe `bad_exception`, consulte a [Classe exception](../standard-library/exception-class.md).  
  
## <a name="example"></a>Exemplo  
 Consulte [set_unexpected](../standard-library/exception-functions.md#set_unexpected) para obter um exemplo do uso de [unexpected](../standard-library/exception-functions.md#unexpected) gerando um `bad_exception`.  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** \<exception>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Consulte também  
[Classe de exceção](../standard-library/exception-class.md) [segurança de threads na biblioteca padrão C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
