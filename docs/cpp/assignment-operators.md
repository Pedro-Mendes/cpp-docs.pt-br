---
title: "Operadores de atribui&#231;&#227;o | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - ">>="
  - "xor_eq"
  - "&="
  - "<<="
  - "-="
  - "and_eq"
  - "^="
  - "|="
  - "/="
  - "%="
  - "or_eq"
  - "+="
  - "*="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Operador %="
  - "Operador &="
  - "Operador *="
  - "Operador /="
  - "Operador ^="
  - "Operador |="
  - "Operador +="
  - "Operador <<="
  - "Operador ="
  - "Operador -="
  - "Operador >>="
  - "Operador and_eq"
  - "operadores de atribuição"
  - "operadores de atribuição, C++"
  - "Operador >>="
  - "operator>>="
  - "operadores [C++], atribuição"
  - "Operador or_eq"
  - "Operador xor_eq"
ms.assetid: b028cf35-2ff1-4f14-9027-fd53ebec8aa0
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Operadores de atribui&#231;&#227;o
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Sintaxe  
  
```  
  
        expression assignment-operator expression   
assignment-operator : one of  
   =   *=   /=   %=   +=   –=   <<=   >>=   &=   ^=   |=  
```  
  
## Comentários  
 Os operadores de atribuição armazenam um valor no objeto designado pelo operando à esquerda.  Há dois tipos de operações de atribuição: atribuição simples, na qual o valor do segundo operando é armazenado no objeto especificado pelo primeiro operando, e atribuição composta, na qual uma operação aritmética, de troca, ou bit a bit é executadas antes de armazenar o resultado.  Todos os operadores de atribuição na tabela a seguir, exceto o operador \=, são operadores de atribuição composta.  
  
### Operadores de atribuição  
  
|Operador|Significado|  
|--------------|-----------------|  
|**\=**|Armazena o valor do segundo operando no objeto especificado pelo primeiro operando \(atribuição simples\).|  
|**\*\=**|Multiplica o valor do primeiro operando pelo valor do segundo operando; armazena o resultado no objeto especificado pelo primeiro operando.|  
|`/=`|Divide o valor do primeiro operando pelo valor do segundo operando; armazena o resultado no objeto especificado pelo primeiro operando.|  
|`%=`|Obtém o módulo do primeiro operando especificado pelo valor do segundo operando; armazena o resultado no objeto especificado pelo primeiro operando.|  
|`+=`|Soma o valor do segundo operando ao valor do primeiro operando; armazena o resultado no objeto especificado pelo primeiro operando.|  
|**–\=**|Subtrai o valor do segundo operando do valor do primeiro operando; armazena o resultado no objeto especificado pelo primeiro operando.|  
|**\<\<\=**|Alterna o valor do primeiro operando à esquerda do número de bits especificado pelo valor do segundo operando; armazena o resultado no objeto especificado pelo primeiro operando.|  
|**\>\>\=**|Alterna o valor do primeiro operando à direita do número de bits especificado pelo valor do segundo operando; armazena o resultado no objeto especificado pelo primeiro operando.|  
|**&\=**|Obtém o bit a bit AND do primeiro e do segundo operandos; armazena o resultado no objeto especificado pelo primeiro operando.|  
|`^=`|Obtém o bit a bit exclusivo OR do primeiro e do segundo operandos; armazena o resultado no objeto especificado pelo primeiro operando.|  
|`&#124;=`|Obtém o bit a bit inclusivo OR do primeiro e do segundo operandos; armazena o resultado no objeto especificado pelo primeiro operando.|  
  
 **Palavras\-chave do operador**  
  
 Três dos operadores de atribuição composta têm equivalentes de texto.  Elas são:  
  
|Operador|Equivalente|  
|--------------|-----------------|  
|**&\=**|`and_eq`|  
|`&#124;=`|`or_eq`|  
|`^=`|`xor_eq`|  
  
 Há duas maneiras de acessar essas palavras\-chave do operador em seus programas: inclua o arquivo de cabeçalho `iso646.h`, ou compile com a opção de compilador [\/Za](../build/reference/za-ze-disable-language-extensions.md) \(Desabilitar extensões de linguagem\).  
  
## Exemplo  
  
```  
// expre_Assignment_Operators.cpp  
// compile with: /EHsc  
// Demonstrate assignment operators  
#include <iostream>  
using namespace std;  
int main() {  
   int a = 3, b = 6, c = 10, d = 0xAAAA, e = 0x5555;  
  
   a += b;      // a is 9  
   b %= a;      // b is 6  
   c >>= 1;      // c is 5  
   d |= e;      // Bitwise--d is 0xFFFF   
  
   cout  << "a = 3, b = 6, c = 10, d = 0xAAAA, e = 0x5555" << endl  
         << "a += b yields " << a << endl  
         << "b %= a yields " << b << endl  
         << "c >>= 1 yields " << c << endl  
         << "d |= e yields " << hex << d << endl;  
}  
```  
  
## Atribuição simples  
 O operador de atribuição simples \(\=\) faz com que o valor do segundo operando seja armazenado no objeto especificado pelo primeiro operando.  Se os dois objetos forem de tipos aritméticos, o operando da direita será convertido no tipo da esquerda, armazenamento o valor anteriormente.  
  
 Os objetos dos tipos const e volatile podem ser atribuídos aos l\-values dos tipos que são apenas volatile ou que não são const nem volatile.  
  
 A atribuição a objetos do tipo de classe \(tipos struct, union e class\) é executada por uma função chamada operator\=.  O comportamento padrão dessa função do operador é executar uma cópia bit a bit; no entanto, esse comportamento pode ser alterado usando operadores sobrecarregados.  \(Consulte [Operadores sobrecarregados](../cpp/operator-overloading.md) para obter mais informações.\)  
  
 Um objeto de qualquer classe derivada exclusiva de uma classe base pode ser atribuída a um objeto da classe base.  O contrário não é válido porque existe uma conversão implícita da classe derivada para a classe base, mas não da classe base para a classe derivada.  Por exemplo:  
  
```  
// expre_SimpleAssignment.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
class ABase  
{  
public:  
    ABase() { cout << "constructing ABase\n"; }  
};  
  
class ADerived : public ABase  
{  
public:  
    ADerived() { cout << "constructing ADerived\n"; }  
};  
  
int main()  
{  
    ABase aBase;  
    ADerived aDerived;  
  
    aBase = aDerived; // OK  
    aDerived = aBase; // C2679  
}  
```  
  
 As atribuições para tipos de referência se comportam como se uma atribuição foi feita ao objeto ao qual a referência aponta.  
  
 Para objetos de tipo classe, a atribuição é diferente de inicialização.  Para ilustrar como a atribuição e a inicialização podem ser diferentes, considere o código  
  
```  
UserType1 A;  
UserType2 B = A;  
```  
  
 O código anterior mostra um inicializador; ele chama o construtor de `UserType2` que usa um argumento do tipo `UserType1`.  Dado o código  
  
```  
UserType1 A;  
UserType2 B;  
  
B = A;  
```  
  
 a instrução de atribuição  
  
```  
B = A;   
```  
  
 pode ter um dos seguintes efeitos  
  
-   Chamada do operator\= da função para `UserType2`, desde que o operator\= seja fornecido com um argumento `UserType1`.  
  
-   Chama a função de conversão explícita `UserType1::operator UserType2`, se essa função existir.  
  
-   Chamar um construtor `UserType2::UserType2`, desde que essa construtor exista, que usa um argumento `UserType1` e copia o resultado.  
  
## Atribuição composta  
 Os operadores de atribuição compostos, mostrados na tabela em [Operadores de atribuição](../cpp/assignment-operators.md), são especificados no formato *e1* `op`\= *e2*, onde *e1* é um l\-value modificável que não é do tipo de const e *e2* é um destes:  
  
-   Um tipo aritmético  
  
-   Um ponteiro, se `op` for \+ ou \-  
  
 O formulário *e1* `op`\= *e2* se comporta como *e1* *\= e1* `op` *e2*, mas *e1* é avaliado somente uma vez.  
  
 A atribuição composta para um tipo enumerado gera uma mensagem de erro.  Se o operando esquerdo for de um tipo ponteiro, o operando direito deverá ser do tipo ponteiro ou ser uma expressão constante avaliada como 0.  Se o operando esquerdo for do tipo integral, o operando direito não deverá ser de um tipo ponteiro.  
  
## Resultado dos operadores de atribuição  
 Os operadores de atribuição retornam o valor do objeto especificado pelo operando esquerdo após a atribuição.  O tipo resultante é o tipo do operando esquerdo.  O resultado de uma expressão de atribuição é sempre um l\-value.  Esses operadores binários possuem associatividade da direita para a esquerda.  O operando esquerdo deve ser um l\-value modificável.  
  
 Em ANSI C, o resultado de uma expressão de atribuição não é um l\-value.  Portanto, a expressão C\+\+ válida `(a += b) += c` é inválida em C.  
  
## Consulte também  
 [Expressões com operadores binários](../cpp/expressions-with-binary-operators.md)   
 [Operadores C\+\+](../misc/cpp-operators.md)   
 [Operadores, precedência e associatividade C\+\+](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Operadores de atribuição C](../c-language/c-assignment-operators.md)