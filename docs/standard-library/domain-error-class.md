---
title: Classe domain_error | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- domain_error
- std::domain_error
- std.domain_error
- stdexcept/std::domain_error
dev_langs:
- C++
helpviewer_keywords:
- domain_error class
ms.assetid: a1d8245d-61c2-4d1e-973f-073bd5dd5fa3
caps.latest.revision: 19
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 3398a26e6c245eeb7e46d490fd3830ea6e1899ee
ms.lasthandoff: 02/25/2017

---
# <a name="domainerror-class"></a>Classe domain_error
A classe serve como a classe base para todas as exceções geradas para relatar um erro de domínio.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
class domain_error : public logic_error {  
public:  
    explicit domain_error(const string& message);

    explicit domain_error(const char *message);

};  
```  
  
## <a name="remarks"></a>Comentários  
 O valor retornado por [what](../standard-library/exception-class.md) é uma cópia de **message**`.`[data](../standard-library/basic-string-class.md#basic_string__data).  
  
## <a name="example"></a>Exemplo  
  
```cpp  
// domain_error.cpp  
// compile with: /EHsc /GR  
#include <iostream>  
  
using namespace std;  
  
int main( )  
{  
   try   
   {  
      throw domain_error( "Your domain is in error!" );  
   }  
   catch (exception &e)   
   {  
      cerr << "Caught: " << e.what( ) << endl;  
      cerr << "Type: " << typeid(e).name( ) << endl;  
   };  
}  
\* Output:   
Caught: Your domain is in error!  
Type: class std::domain_error  
*\  
```  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** \<stdexcept>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Consulte também  
 [Classe logic_error](../standard-library/logic-error-class.md)   
 [Acesso Thread-Safe na Biblioteca Padrão C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

