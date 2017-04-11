---
title: "Fun&#231;&#245;es com listas de argumentos vari&#225;veis (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "listas de argumentos [C++], número variável de"
  - "argumentos [C++], número variável de"
  - "declaradores, funções"
  - "declarando funções, variáveis"
  - "chamadas de função, número variável de argumentos"
  - "listas de argumentos variáveis"
ms.assetid: 27c2f83a-21dd-44c6-913c-2834cb944703
caps.latest.revision: 16
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fun&#231;&#245;es com listas de argumentos vari&#225;veis (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Declarações de função, o último membro é o reticências \(...\) pode levar a um número variável de argumentos.  Nesses casos, o C\+\+ fornece verificação de tipo apenas para os argumentos explicitamente declarados.  Você pode usar listas de argumentos variáveis quando precisar criar uma função tão geral que mesmo o número e os tipos de argumentos possam variar.  A família de funções é um exemplo de funções que usam listas de argumentos variáveis.`printf`*lista de declarações de argumento*  
  
## Funções com argumentos de variável  
 Para acessar argumentos após a declaração, use as macros contidos no arquivo de inclusão padrão STDARG. H conforme descrito abaixo.  
  
 **Específico da Microsoft**  
  
 O Microsoft C\+\+ permite que as reticências sejam especificadas como um argumento se as reticências forem o último argumento e se forem precedidas por uma vírgula.  Consequentemente, a declaração `int Func( int i, ... );` é válida, mas `int Func( int i ... );` não é.  
  
 **FIM de Específico da Microsoft**  
  
 A declaração de uma função que pega um número variável de argumentos que requer pelo menos um argumento de espaço reservado, mesmo se não for usado.  Se esse argumento de espaço reservado não for fornecido, não há como acessar os argumentos restantes.  
  
 Quando os argumentos do tipo `char` são passados como argumentos variáveis, são convertidos para o tipo `int`.  De maneira similar, quando os argumentos do tipo **float** são passados como argumentos variáveis, eles são convertidos para o tipo **double**.  Os argumentos de outros tipos estão sujeitos às promoções integral e de ponto flutuante comuns.  Consulte [Promoções integrais](../misc/integral-promotions.md) para obter mais informações.  
  
 Funções que exigem listas de variáveis são declaradas usando as reticências \(...\) na lista de argumentos.  Use os tipos e as macros que são descritos no arquivo de inclusão STDARG.H para acessar os argumentos que são passados por uma lista de variáveis.  Para obter mais informações sobre essas macros, consulte [va\_arg, va\_copy, va\_end, va\_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md).  na documentação da biblioteca de tempo de execução C.  
  
 O exemplo a seguir mostra como as macros funcionam em conjunto com o tipo \(declarado em STDARG. H\): `va_list` `va_end` `va_arg` `va_start`  
  
```  
// variable_argument_lists.cpp  
#include <stdio.h>  
#include <stdarg.h>  
  
//  Declaration, but not definition, of ShowVar.  
void ShowVar( char *szTypes, ... );  
int main() {  
   ShowVar( "fcsi", 32.4f, 'a', "Test string", 4 );  
}  
  
//  ShowVar takes a format string of the form  
//   "ifcs", where each character specifies the  
//   type of the argument in that position.  
//  
//  i = int  
//  f = float  
//  c = char  
//  s = string (char *)  
//  
//  Following the format specification is a variable   
//  list of arguments. Each argument corresponds to   
//  a format character in the format string to which   
// the szTypes parameter points   
void ShowVar( char *szTypes, ... ) {  
   va_list vl;  
   int i;  
  
   //  szTypes is the last argument specified; you must access   
   //  all others using the variable-argument macros.  
   va_start( vl, szTypes );  
  
   // Step through the list.  
   for( i = 0; szTypes[i] != '\0'; ++i ) {  
      union Printable_t {  
         int     i;  
         float   f;  
         char    c;  
         char   *s;  
      } Printable;  
  
      switch( szTypes[i] ) {   // Type to expect.  
         case 'i':  
            Printable.i = va_arg( vl, int );  
            printf_s( "%i\n", Printable.i );  
         break;  
  
         case 'f':  
             Printable.f = va_arg( vl, double );  
             printf_s( "%f\n", Printable.f );  
         break;  
  
         case 'c':  
             Printable.c = va_arg( vl, char );  
             printf_s( "%c\n", Printable.c );  
         break;  
  
         case 's':  
             Printable.s = va_arg( vl, char * );  
             printf_s( "%s\n", Printable.s );  
         break;  
  
         default:  
         break;  
      }  
   }  
   va_end( vl );  
}  
//Output:   
// 32.400002  
// a  
// Test string  
```  
  
 O exemplo anterior ilustra estes conceitos importantes:  
  
1.  Você deve estabelecer um marcador de lista como uma variável de tipo `va_list` antes que argumentos de variáveis sejam acessados.  No exemplo anterior, o marcador é chamado `vl`.  
  
2.  Os argumentos individuais são acessados usando a macro `va_arg`.  Você deve informar à macro `va_arg` o tipo de argumento a ser recuperado para que ela possa transferir o número de bytes correto da pilha.  Se você especificar um tipo incorreto de um tamanho diferente do fornecido pelo programa de chamada para `va_arg`, os resultados serão imprevisíveis.  
  
3.  É necessário converter explicitamente o resultado obtido usando a macro `va_arg` no tipo desejado.  
  
 Você deve chamar a macro para encerrar o processamento do argumento de variável.`va_end`