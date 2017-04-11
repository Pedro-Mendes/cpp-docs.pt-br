---
title: C2259 de erro do compilador | Documentos do Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2259
dev_langs:
- C++
helpviewer_keywords:
- C2259
ms.assetid: e458236f-bdea-4786-9aa6-a98d8bffa5f4
caps.latest.revision: 16
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
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 0837d8f5e48ccf0de0ba8630801667da2ddb6bfa
ms.lasthandoff: 02/25/2017

---
# <a name="compiler-error-c2259"></a>C2259 de erro do compilador
'class': não é possível instanciar a classe abstrata  
  
 Código declara uma instância de uma estrutura ou classe abstrata.  
  
 Você não pode instanciar uma classe ou estrutura com uma ou mais funções virtuais puras. Para instanciar objetos de uma classe derivada, a classe derivada deve substituir cada função virtual pura.  
  
 Para obter mais informações, consulte [classes implicitamente abstratas](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Implicitly_abstract_classes).  
  
 O exemplo a seguir gera C2259:  
  
```  
// C2259.cpp  
// compile with: /c  
class V {  
public:  
   void virtual func() = 0;  
};  
class A : public V {};  
class B : public V {  
public:  
   void func();  
};  
V v;  // C2259, V is an abstract class  
A a;  // C2259, A inherits func() as pure virtual  
B b;  // OK, B defines func()  
```  
  
 Sempre que deriva de uma interface e implementa os métodos de interface na classe derivada com permissões de acesso que não seja público, você pode receber C2259.  Isso ocorre porque o compilador espera que os métodos de interface implementados na classe derivada com acesso público. Quando você implementa as funções de membro de uma interface com permissões de acesso mais restritivos, o compilador não considera a ser implementações para os métodos de interface definidos na interface, que por sua vez faz a classe derivada de uma classe abstrata.  
  
 Há duas soluções possíveis para o problema:  
  
-   Verifique as permissões de acesso público para os métodos implementados.  
  
-   Use o operador de resolução de escopo para os métodos de interface implementados na classe derivada para qualificar o nome do método implementado com o nome da interface.  
  
 C2259 também pode ocorrer como resultado do trabalho de conformidade que foi feito no Visual C++ 2005, **/ZC:** está ativada por padrão. Nessa situação, C2599 pode ser resolvido ou por compilar com **/Zc:wchar_t-**, para obter o comportamento de versões anteriores ou, preferencialmente, atualizando seus tipos para que sejam compatíveis. Para obter mais informações, consulte [/Zc:wchar_t (wchar_t é o tipo nativo)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md).  
  
 O exemplo a seguir gera C2259:  
  
```  
// C2259b.cpp  
// compile with: /c  
#include <windows.h>   
  
class MyClass {  
public:  
   // WCHAR now typedef'ed to wchar_t  
   virtual void func(WCHAR*) = 0;  
};  
  
class MyClass2 : MyClass {  
public:  
   void func(unsigned short*);  
};  
  
MyClass2 x;   // C2259  
  
// OK  
class MyClass3 {  
public:  
   virtual void func(WCHAR*) = 0;  
   virtual void func2(wchar_t*) = 0;  
   virtual void func3(unsigned short*) = 0;  
};  
  
class MyClass4 : MyClass3 {  
public:  
   void func(WCHAR*) {}  
   void func2(wchar_t*) {}  
   void func3(unsigned short*) {}  
};  
  
MyClass4 y;  
```  
  
 O exemplo a seguir gera C2259:  
  
```  
// C2259c.cpp  
// compile with: /clr  
interface class MyInterface {  
   void MyMethod();  
};  
  
ref class MyDerivedClass: public MyInterface {  
private:  
   // Uncomment the following line to resolve.  
   // public:  
   void MyMethod(){}  
   // or the following line  
   // void MyInterface::MyMethod() {};  
};  
  
int main() {  
   MyDerivedClass^ instance = gcnew MyDerivedClass; // C2259  
}  
```  
