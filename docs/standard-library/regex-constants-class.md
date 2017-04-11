---
title: Classe regex_constants | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- regex_constants
- std::regex_constants
- regex/std::regex_constants
- error_collate
- std::regex_constants::error_collate
- regex/std::regex_constants::error_collate
- error_ctype
- std::regex_constants::error_ctype
- regex/std::regex_constants::error_ctype
- error_escape
- std::regex_constants::error_escape
- regex/std::regex_constants::error_escape
- error_backref
- std::regex_constants::error_backref
- regex/std::regex_constants::error_backref
- error_brack
- std::regex_constants::error_brack
- regex/std::regex_constants::error_brack
- error_paren
- std::regex_constants::error_paren
- regex/std::regex_constants::error_paren
- error_brace
- std::regex_constants::error_brace
- regex/std::regex_constants::error_brace
- error_badbrace
- std::regex_constants::error_badbrace
- regex/std::regex_constants::error_badbrace
- error_range
- std::regex_constants::error_range
- regex/std::regex_constants::error_range
- error_space
- std::regex_constants::error_space
- regex/std::regex_constants::error_space
- error_badrepeat
- std::regex_constants::error_badrepeat
- regex/std::regex_constants::error_badrepeat
- error_complexity
- std::regex_constants::error_complexity
- regex/std::regex_constants::error_complexity
- error_stack
- std::regex_constants::error_stack
- regex/std::regex_constants::error_stack
- error_parse
- std::regex_constants::error_parse
- regex/std::regex_constants::error_parse
- error_syntax
- std::regex_constants::error_syntax
- regex/std::regex_constants::error_syntax
- match_default
- std::regex_constants::match_default
- regex/std::regex_constants::match_default
- match_not_bol
- std::regex_constants::match_not_bol
- regex/std::regex_constants::match_not_bol
- match_not_eol
- std::regex_constants::match_not_eol
- regex/std::regex_constants::match_not_eol
- match_not_bow
- std::regex_constants::match_not_bow
- regex/std::regex_constants::match_not_bow
- match_not_eow
- std::regex_constants::match_not_eow
- regex/std::regex_constants::match_not_eow
- match_any
- std::regex_constants::match_any
- regex/std::regex_constants::match_any
- match_not_null
- std::regex_constants::match_not_null
- regex/std::regex_constants::match_not_null
- match_continuous
- std::regex_constants::match_continuous
- regex/std::regex_constants::match_continuous
- match_prev_avail
- std::regex_constants::match_prev_avail
- regex/std::regex_constants::match_prev_avail
- format_default
- std::regex_constants::format_default
- regex/std::regex_constants::format_default
- format_sed
- std::regex_constants::format_sed
- regex/std::regex_constants::format_sed
- format_no_copy
- std::regex_constants::format_no_copy
- regex/std::regex_constants::format_no_copy
- format_first_only
- std::regex_constants::format_first_only
- regex/std::regex_constants::format_first_only
- std::regex_constants::ECMAScript
- regex/std::regex_constants::ECMAScript
- std::regex_constants::basic
- regex/std::regex_constants::basic
- std::regex_constants::extended
- regex/std::regex_constants::extended
- std::regex_constants::awk
- regex/std::regex_constants::awk
- std::regex_constants::grep
- regex/std::regex_constants::grep
- std::regex_constants::egrep
- regex/std::regex_constants::egrep
- std::regex_constants::icase
- regex/std::regex_constants::icase
- std::regex_constants::nosubs
- regex/std::regex_constants::nosubs
- std::regex_constants::optimize
- regex/std::regex_constants::optimize
- std::regex_constants::collate
- regex/std::regex_constants::collate
dev_langs:
- C++
helpviewer_keywords:
- regex_constants class
ms.assetid: 4a69c0ba-c46d-46e4-bd29-6f4efb805f26
caps.latest.revision: 18
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
ms.sourcegitcommit: 248e9ba676b906af62f6804f4939e04158a8e2ef
ms.openlocfilehash: 9330a5c4e1b487880f405478dd7e8838af739c44
ms.lasthandoff: 02/25/2017

---
# <a name="regexconstants-class"></a>Classe regex_constants
Namespace para sinalizadores de expressão regular.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
namespace regex_constants {  
    enum syntax_option_type;  
    enum match_flag_type;  
    enum error_type;  
 }  
```  
  
## <a name="remarks"></a>Comentários  
 O namespace `regex_constants` encapsula vários tipos de sinalizador e seus valores de sinalizador associados.  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** \<regex>  
  
 **Namespace:** std  
  
##  <a name="a-nameregexconstantserrortypea--regexconstantserrortype"></a><a name="regex_constants__error_type"></a>  regex_constants::error_type  
 Sinalizadores para relatar erros de sintaxe de expressão regular.  
  
```  
enum error_type
    {    // identify error
    error_collate,
    error_ctype,
    error_escape,
    error_backref,
    error_brack,
    error_paren,
    error_brace,
    error_badbrace,
    error_range,
    error_space,
    error_badrepeat,
    error_complexity,
    error_stack,
    error_parse,
    error_syntax
    };  
```  
  
### <a name="remarks"></a>Comentários  
 O tipo é um tipo enumerado que descreve um objeto que pode conter sinalizadores de erro. Os valores de sinalizador distintos são:  
  
 `error_backref` -- a expressão continha uma referência inversa inválida  
  
 `error_badbrace` -- a expressão continha uma contagem inválida em uma expressão { }  
  
 `error_badrepeat` -- uma expressão de repetição (um de '*', '', '+', '{' na maioria dos contextos) não era precedida por uma expressão  
  
 `error_brace` -- a expressão continha um '{' ou '}' sem correspondência  
  
 `error_brack` -- a expressão continha um '[' ou ']' sem correspondência  
  
 `error_collate` -- a expressão continha um nome de elemento de agrupamento inválido  
  
 `error_complexity` -- uma tentativa de correspondência falhou porque ela era muito complexa  
  
 `error_ctype` -- a expressão continha um nome de classe de caractere inválido  
  
 `error_escape` -- a expressão continha uma sequência de escape inválida  
  
 `error_paren` -- a expressão continha um '(' ou ')' sem correspondência  
  
 `error_parse` -- a expressão falhou durante a análise  
  
 `error_range` -- a expressão continha um especificador de intervalo de caracteres inválidos  
  
 `error_space` -- falha ao analisar uma expressão regular, pois não havia recursos suficientes disponíveis  
  
 `error_stack` -- uma tentativa de correspondência falhou porque não havia memória suficiente disponível  
  
 `error_syntax` -- falha ao analisar um erro de sintaxe  
  
 `error_backref` -- a expressão continha uma referência inversa inválida  
  
##  <a name="a-nameregexconstantsmatchflagtypea--regexconstantsmatchflagtype"></a><a name="regex_constants__match_flag_type"></a>  regex_constants::match_flag_type  
 Sinalizadores para opções de correspondência de expressões regulares.  
  
```  
enum match_flag_type 
    {    // specify matching and formatting rules
    match_default = 0x0000,
    match_not_bol = 0x0001,
    match_not_eol = 0x0002,
    match_not_bow = 0x0004,
    match_not_eow = 0x0008,
    match_any = 0x0010,
    match_not_null = 0x0020,
    match_continuous = 0x0040,
    match_prev_avail = 0x0100,
    format_default = 0x0000,
    format_sed = 0x0400,
    format_no_copy = 0x0800,
    format_first_only = 0x1000,
    _Match_not_null = 0x2000
    };  
```  
  
### <a name="remarks"></a>Comentários  
 O tipo é um tipo de máscara de bits que descreve as opções a serem usadas ao corresponder uma sequência de texto em uma expressão regular e os sinalizadores de formato a serem usados ao substituir o texto. As opções podem ser combinadas com `|`.  
  
 As opções de correspondência são:  
  
 `match_default`  
  
 `match_not_bol` -- não trate a primeira posição na sequência de destino como o início de uma linha  
  
 `match_not_eol` -- não trate a posição após o fim na sequência de destino como o fim de uma linha  
  
 `match_not_bow` -- não trate a primeira posição na sequência de destino como o início de uma palavra  
  
 `match_not_eow` -- não trate a posição após o fim na sequência de destino como o fim de uma palavra  
  
 `match_any` -- se mais de uma correspondência for possível, qualquer correspondência será aceitável  
  
 `match_not_null` -- não trate uma subsequência vazia como uma correspondência  
  
 `match_continuous` -- não pesquise correspondências diferentes no início da sequência de destino  
  
 `match_prev_avail` -- `--first` é um iterador válido; ignore `match_not_bol` e `match_not_bow` se definido  
  
 Os sinalizadores de formato são:  
  
 `format_default` -- use as regras de formato de ECMAScript  
  
 `format_sed` -- use regras no formato sed  
  
 `format_no_copy` -- não copie texto que não corresponde à expressão regular  
  
 `format_first_only` -- não pesquise correspondências depois da primeira  
  
##  <a name="a-nameregexconstantssyntaxoptiontypea--regexconstantssyntaxoptiontype"></a><a name="regex_constants__syntax_option_type"></a>  regex_constants::syntax_option_type  
 Sinalizadores para a seleção de opções de sintaxe.  
  
```  
enum syntax_option_type
    {    // specify RE syntax rules
    ECMAScript = 0x01,
    basic = 0x02,
    extended = 0x04,
    awk = 0x08,
    grep = 0x10,
    egrep = 0x20,
    _Gmask = 0x3F,

    icase = 0x0100,
    nosubs = 0x0200,
    optimize = 0x0400,
    collate = 0x0800
    };  
```  
  
### <a name="remarks"></a>Comentários  
 O tipo é um tipo de máscara de bits que descreve os especificadores de linguagem e modificadores de sintaxe a serem usados ao compilar uma expressão regular. As opções podem ser combinadas com `|`. Apenas um especificador de linguagem deve ser usado por vez.  
  
 Os especificadores de linguagem são:  
  
 `ECMAScript` -- compilar como ECMAScript  
  
 `basic` -- compilar como BRE  
  
 `extended` -- compilar como ERE  
  
 `awk` -- compilar como awk  
  
 `grep` -- compilar como grep  
  
 `egrep` -- compilar como egrep  
  
 Os modificadores de sintaxe são:  
  
 `icase` -- fazer as correspondências não diferenciarem maiúsculas de minúsculas  
  
 `nosubs` -- a implementação não precisa manter o controle do conteúdo de grupos de captura  
  
 `optimize` -- a implementação deve enfatizar a velocidade de correspondência em vez da velocidade de compilação da expressão regular  
  
 `collate` -- faz as correspondências distinguirem localidades  
  
## <a name="see-also"></a>Consulte também  
[\<regex>](../standard-library/regex.md)  
[Classe regex_error](../standard-library/regex-error-class.md)  
[\<Funções regex>](../standard-library/regex-functions.md)  
[Classe regex_iterator](../standard-library/regex-iterator-class.md)  
[\<Operadores regex>](../standard-library/regex-operators.md)  
[Classe regex_token_iterator](../standard-library/regex-token-iterator-class.md)  
[Classe regex_traits](../standard-library/regex-traits-class.md)  
[\<Typedef regex>](../standard-library/regex-typedefs.md)  
