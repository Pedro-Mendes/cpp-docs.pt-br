---
title: Classe basic_istringstream | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::basic_istringstream
- sstream/std::basic_istringstream
- basic_istringstream
- std.basic_istringstream
dev_langs:
- C++
helpviewer_keywords:
- basic_istringstream class
ms.assetid: 1d5bb4b5-793d-4833-98e5-14676c451915
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
ms.openlocfilehash: ff32ad28b272e16273742b040e0ed62850e3e15e
ms.lasthandoff: 02/25/2017

---
# <a name="basicistringstream-class"></a>Classe basic_istringstream
Descreve um objeto que controla a extração de elementos e objetos codificados de um buffer de fluxo da classe [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>  
class basic_istringstream : public basic_istream<Elem, Tr>  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `Alloc`  
 A classe do alocador.  
  
 `Elem`  
 O tipo do elemento básico da cadeia de caracteres.  
  
 *Tr*  
 As características de caractere especializadas no elemento básico da cadeia de caracteres.  
  
## <a name="remarks"></a>Comentários  
 A classe de modelo descreve um objeto que controla a extração de elementos e objetos codificados de um buffer de fluxo da classe [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>, com elementos do tipo **Elem**, cujas características de caractere são determinadas pela classe **Tr** e cujos elementos são alocados por um alocador de classe `Alloc`. O objeto armazena um objeto da classe basic_stringbuf< **Elem**, **Tr**, `Alloc`>.  
  
### <a name="constructors"></a>Construtores  
  
|||  
|-|-|  
|[basic_istringstream](#basic_istringstream__basic_istringstream)|Constrói um objeto do tipo `basic_istringstream`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[allocator_type](#basic_istringstream__allocator_type)|O tipo é um sinônimo do parâmetro de modelo `Alloc`.|  
  
### <a name="member-functions"></a>Funções membro  
  
|||  
|-|-|  
|[rdbuf](#basic_istringstream__rdbuf)|Retorna o endereço do buffer de fluxo armazenado do tipo `pointer` para [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, `Alloc`>.|  
|[str](#basic_istringstream__str)|Define ou obtém o texto em um buffer de cadeia de caracteres sem alterar a posição de gravação.|  
|[swap](#basic_istringstream__swap)|Troca os valores nesse objeto `basic_istringstream` por aqueles do objeto fornecido.|  
  
### <a name="operators"></a>Operadores  
  
|||  
|-|-|  
|[operator=](#basic_istringstream__operator_eq)|Atribui os valores a esse objeto `basic_istringstream` do parâmetro de objeto.|  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** \<sstream>  
  
 **Namespace:** std  
  
##  <a name="a-namebasicistringstreamallocatortypea--basicistringstreamallocatortype"></a><a name="basic_istringstream__allocator_type"></a>  basic_istringstream::allocator_type  
 O tipo é um sinônimo do parâmetro de modelo `Alloc`.  
  
```  
typedef Alloc allocator_type;  
```  
  
##  <a name="a-namebasicistringstreambasicistringstreama--basicistringstreambasicistringstream"></a><a name="basic_istringstream__basic_istringstream"></a>  basic_istringstream::basic_istringstream  
 Constrói um objeto do tipo `basic_istringstream`.  
  
```  
explicit basic_istringstream(
    ios_base::openmode _Mode = ios_base::in);

explicit basic_istringstream(
    const basic_string<Elem, Tr, Alloc>& str,  
    ios_base::openmode _Mode = ios_base::in);

basic_istringstream(
    basic_istringstream&& right);
```  
  
### <a name="parameters"></a>Parâmetros  
 `_Mode`  
 Uma das enumerações em [ios_base::openmode](../standard-library/ios-base-class.md#ios_base__openmode).  
  
 ` str`  
 Um objeto do tipo `basic_string`.  
  
 ` right`  
 Uma referência rvalue de um objeto `basic_istringstream`.  
  
### <a name="remarks"></a>Comentários  
 O primeiro construtor inicializa a classe base chamando [basic_istream](../standard-library/basic-istream-class.md)( `sb`), em que `sb` é o objeto armazenado da classe [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, `Alloc`>. Também inicializa `sb` chamando `basic_stringbuf`< `Elem`, `Tr`, `Alloc`>( `_Mode` &#124; `ios_base::in`).  
  
 O segundo construtor inicializa a classe base chamando `basic_istream(sb)`. Também inicializa `sb` chamando `basic_stringbuf`< `Elem`, `Tr`, `Alloc`>( ` str`, `_Mode` &#124; `ios_base::in`).  
  
 O terceiro construtor inicializa o objeto com o conteúdo de ` right` tratado como uma referência rvalue.  
  
##  <a name="a-namebasicistringstreamoperatoreqa--basicistringstreamoperator"></a><a name="basic_istringstream__operator_eq"></a>  basic_istringstream::operator=  
 Atribui os valores a esse objeto `basic_istringstream` do parâmetro de objeto.  
  
```  
basic_istringstream& operator=(basic_istringstream&& right);
```  
  
### <a name="parameters"></a>Parâmetros  
 ` right`  
 Uma referência rvalue a um objeto `basic_istringstream`.  
  
### <a name="remarks"></a>Comentários  
 O operador de membro substitui o conteúdo do objeto pelo conteúdo de ` right`, tratado como uma atribuição de movimentação de referência rvalue.  
  
##  <a name="a-namebasicistringstreamrdbufa--basicistringstreamrdbuf"></a><a name="basic_istringstream__rdbuf"></a>  basic_istringstream::rdbuf  
 Retorna o endereço do buffer de fluxo armazenado do tipo **pointer** para [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>.  
  
```  
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```  
  
### <a name="return-value"></a>Valor de retorno  
 O endereço do buffer de fluxo armazenado do tipo **pointer** para basic_stringbuf< **Elem**, **Tr**, `Alloc`>.  
  
### <a name="example"></a>Exemplo  
  Consulte [basic_filebuf::close](../standard-library/basic-filebuf-class.md#basic_filebuf__close) para ver um exemplo que usa `rdbuf`.  
  
##  <a name="a-namebasicistringstreamstra--basicistringstreamstr"></a><a name="basic_istringstream__str"></a>  basic_istringstream::str  
 Define ou obtém o texto em um buffer de cadeia de caracteres sem alterar a posição de gravação.  
  
```  
basic_string<Elem, Tr, Alloc> str() const;

 
void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```  
  
### <a name="parameters"></a>Parâmetros  
 `_Newstr`  
 A nova cadeia de caracteres.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna um objeto da classe [basic_string](../standard-library/basic-string-class.md)< **Elem**, **Tr**, `Alloc`>, cuja sequência controlada é uma cópia da sequência controlada por **\*this**.  
  
### <a name="remarks"></a>Comentários  
 A primeira função membro retorna [rdbuf](#basic_istringstream__rdbuf) -> [str](../standard-library/basic-stringbuf-class.md#basic_stringbuf__str). As segunda função membro chama `rdbuf` -> **str**( `_Newstr`).  
  
### <a name="example"></a>Exemplo  
  Consulte [basic_stringbuf::str](../standard-library/basic-stringbuf-class.md#basic_stringbuf__str) para obter um exemplo que usa **str**.  
  
##  <a name="a-namebasicistringstreamswapa--basicistringstreamswap"></a><a name="basic_istringstream__swap"></a>  basic_istringstream::swap  
 Troca os valores de dois objetos `basic_istringstream`.  
  
```  
void swap(basic_istringstream& right);
```  
  
### <a name="parameters"></a>Parâmetros  
  
|Parâmetro|Descrição|  
|---------------|-----------------|  
|` right`|Uma referência `lvalue` a um objeto `basic_istringstream`.|  
  
### <a name="remarks"></a>Comentários  
 A função membro troca os valores desse objeto e os valores de ` right`.  
  
## <a name="see-also"></a>Consulte também  
 [Acesso Thread-Safe na Biblioteca Padrão C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Programação de iostream](../standard-library/iostream-programming.md)   
 [Convenções de iostreams](../standard-library/iostreams-conventions.md)

