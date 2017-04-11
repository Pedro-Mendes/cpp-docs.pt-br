---
title: "auto_handle::operator auto_handle | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "msclr.auto_handle.operator auto_handle"
  - "operator auto_handle"
  - "msclr::auto_handle::operator auto_handle"
  - "auto_handle.operator auto_handle"
  - "auto_handle::operator auto_handle"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator auto_handle"
ms.assetid: 2f8b35d1-2783-4d91-b6fb-eae551270fb8
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# auto_handle::operator auto_handle
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Operador de conversão de tipos entre `auto_handle` e tipos compatíveis.  
  
## Sintaxe  
  
```  
template<typename _other_type>  
operator auto_handle<_other_type>();  
```  
  
## Valor de retorno  
 `auto_handle` atual convertido em `auto_handle<_other_type>`.  
  
## Exemplo  
  
```  
// msl_auto_handle_op_auto_handle.cpp  
// compile with: /clr  
#include <msclr\auto_handle.h>  
  
using namespace System;  
using namespace msclr;  
  
ref class ClassA {  
protected:     
   String^ m_s;  
public:  
   ClassA( String^ s ) : m_s( s ) {}  
  
   virtual void PrintHello() {  
      Console::WriteLine( "Hello from {0} A!", m_s );  
   }  
};  
  
ref class ClassB : ClassA {  
public:  
   ClassB( String ^ s) : ClassA( s ) {}  
   virtual void PrintHello() new {  
      Console::WriteLine( "Hello from {0} B!", m_s );  
   }  
};  
  
int main() {  
   auto_handle<ClassB> b = gcnew ClassB("first");  
   b->PrintHello();  
   auto_handle<ClassA> a = (auto_handle<ClassA>)b;  
   a->PrintHello();  
}  
```  
  
  **Hello world de primeiro B\!**  
**Hello world primeiro de\!**   
## Requisitos  
 msclr \<de**Arquivo de cabeçalho** \\ auto\_handle.h\>  
  
 msclr de**Namespace**  
  
## Consulte também  
 [Membros auto\_handle](../dotnet/auto-handle-members.md)