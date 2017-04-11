---
title: "Bibliotecas seguras: Biblioteca Padrão C++ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _SCL_SECURE_NO_DEPRECATE
dev_langs:
- C++
helpviewer_keywords:
- Safe Libraries
- Safe Libraries, C++ Standard Library
- Safe C++ Standard Library
ms.assetid: 3993340f-1f29-4d81-b3f5-52a52bc8e148
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 704101f267c1d63ffc5def918f031bfc9b257e67
ms.lasthandoff: 02/25/2017

---
# <a name="safe-libraries-c-standard-library"></a>Bibliotecas seguras: Biblioteca Padrão C++
Vários aprimoramentos foram feitos para as bibliotecas fornecidas com o Visual C++, incluindo a Biblioteca Padrão C++, para torná-los mais seguros.  
  
 Vários métodos na Biblioteca Padrão C++ foram identificados como potencialmente não seguros porque podem causar um estouro de buffer ou outros defeitos de código. Não é recomendado usar esses métodos e métodos mais novos e mais seguros foram criados para substituí-los. Todos esses novos métodos terminam em `_s`.  
  
 Também foram feitas várias melhorias para tornar os iteradores e algoritmos mais seguros. Para obter mais informações, consulte [Verificar iteradores](../standard-library/checked-iterators.md), [Suporte a iterador de depuração](../standard-library/debug-iterator-support.md) e [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).  
  
## <a name="remarks"></a>Comentários  
 A tabela a seguir lista os métodos de Biblioteca Padrão C++ que são potencialmente não seguros, bem como seus equivalentes mais seguros:  
  
|Método potencialmente não seguro|Equivalente mais seguro|  
|-------------------------------|----------------------|  
|[basic_string::copy](../standard-library/basic-string-class.md#basic_string__copy)|[basic_string::_Copy_s](../standard-library/basic-string-class.md#basic_string___copy_s)|  
|[char_traits::copy](../standard-library/char-traits-struct.md#char_traits__copy)|[char_traits::_Copy_s](../standard-library/char-traits-struct.md#char_traits___copy_s)|  
  
 Se você chamar qualquer um dos métodos potencialmente não seguros acima ou se usar iteradores incorretamente, o compilador gerará o [Aviso do Compilador (nível 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Para obter informações sobre como desabilitar esses avisos, consulte [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md).  
  
## <a name="in-this-section"></a>Nesta seção  
 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)  
  
 [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md)  
  
 [Iteradores verificados](../standard-library/checked-iterators.md)  
  
 [Suporte ao iterador de depuração](../standard-library/debug-iterator-support.md)  
  
## <a name="see-also"></a>Consulte também  
 [Visão geral da biblioteca padrão C++](../standard-library/cpp-standard-library-overview.md)

