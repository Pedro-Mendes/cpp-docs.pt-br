---
title: "Como usar propriedades em C++/CLI | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "propriedades [C++], simples"
  - "propriedades simples"
ms.assetid: f5d82547-e214-4f05-9e1b-ddb6d0dc5e4c
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Como usar propriedades em C++/CLI
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Este artigo mostra como usar as propriedades em C\+\+\/CLI.  
  
## Propriedades básicas  
 Para os com os atributos básicos que simplesmente e recuperam dados confidenciais membros não é necessário definir explicitamente as funções do acessador obter e de cluster como o compilador as fornece automaticamente quando é fornecido apenas o tipo de dados da propriedade.  Este código a seguir demonstra uma propriedade básica:  
  
```  
// SimpleProperties.cpp  
// compile with: /clr  
using namespace System;  
  
ref class C {  
public:  
   property int Size;  
};  
  
int main() {  
   C^ c = gcnew C;  
   c->Size = 111;  
   Console::WriteLine("c->Size = {0}", c->Size);  
}  
```  
  
 **Saída**  
  
  **2.0 C \-\>tamanho \= 111**   
## Propriedades estáticos  
 Este exemplo de código mostra como declarar e usar uma propriedade estática.  Uma propriedade estático pode acessar apenas membros estáticos da classe.  
  
```  
// mcppv2_property_3.cpp  
// compile with: /clr  
using namespace System;  
  
ref class StaticProperties {  
   static int MyInt;  
   static int MyInt2;  
  
public:  
   static property int Static_Data_Member_Property;  
  
   static property int Static_Block_Property {  
      int get() {  
         return MyInt;  
      }  
  
      void set(int value) {  
         MyInt = value;  
      }        
   }  
};  
  
int main() {  
   StaticProperties::Static_Data_Member_Property = 96;  
   Console::WriteLine(StaticProperties::Static_Data_Member_Property);  
  
   StaticProperties::Static_Block_Property = 47;  
   Console::WriteLine(StaticProperties::Static_Block_Property);  
}  
```  
  
 **Saída**  
  
  **96**  
**47**   
## Propriedades indexadas  
 Uma propriedade indexada normalmente expõe uma estrutura de dados que é acessada usando um operador subscrito.  
  
 Se você usar uma propriedade indexada padrão, você pode acessar a estrutura de dados apenas com referência ao nome da classe, mas se você usar uma propriedade indexada definida pelo usuário, você deve especificar o nome da propriedade para acessar a estrutura de dados.  
  
 Para obter informações sobre como acessar um indicador padrão usando o ponteiro de `this` , consulte [Semântica do ponteiro em tipos de referência e valor](../misc/semantics-of-the-this-pointer-in-value-and-reference-types.md).  
  
 Para obter informações sobre como consumir um indicador que é escrita em C\#, consulte [Como consumir um indexador C\#](../dotnet/how-to-consume-a-csharp-indexer-cpp-cli.md).  
  
 Este exemplo de código mostra como usar a opção e propriedades indexadas definidas pelo usuário:  
  
```  
// mcppv2_property_2.cpp  
// compile with: /clr  
using namespace System;  
public ref class C {  
   array<int>^ MyArr;  
  
public:  
   C() {  
      MyArr = gcnew array<int>(5);  
   }  
  
   // default indexer  
   property int default[int] {  
      int get(int index) {  
         return MyArr[index];  
      }  
      void set(int index, int value) {  
         MyArr[index] = value;  
      }  
   }  
  
   // user-defined indexer  
   property int indexer1[int] {  
      int get(int index) {  
         return MyArr[index];  
      }  
      void set(int index, int value) {  
         MyArr[index] = value;  
      }  
   }  
};  
  
int main() {  
   C ^ MyC = gcnew C();  
  
   // use the default indexer  
   Console::Write("[ ");  
   for (int i = 0 ; i < 5 ; i++) {  
      MyC[i] = i;  
      Console::Write("{0} ", MyC[i]);  
   }  
  
   Console::WriteLine("]");  
  
   // use the user-defined indexer  
   Console::Write("[ ");  
   for (int i = 0 ; i < 5 ; i++) {  
      MyC->indexer1[i] = i * 2;  
      Console::Write("{0} ", MyC->indexer1[i]);  
   }  
  
   Console::WriteLine("]");  
}  
```  
  
 **Saída**  
  
  **\[ 0 1 2 3 4 \]**  
**\[ 0 2 4 6 8 \]** O exemplo a seguir mostra como chamar o indexador padrão usando o ponteiro de `this` .  
  
```  
// call_default_indexer_through_this_pointer.cpp  
// compile with: /clr /c  
value class Position {  
public:  
   Position(int x, int y) : position(gcnew array<int, 2>(100, 100)) {  
      this->default[x, y] = 1;  
   }  
  
   property int default[int, int] {  
      int get(int x, int y) {  
         return position[x, y];  
      }  
  
      void set(int x, int y, int value) {}  
   }  
  
private:  
   array<int, 2> ^ position;  
};  
```  
  
 Este exemplo mostra como usar <xref:System.Reflection.DefaultMemberAttribute> para especificar o indexador padrão:  
  
```  
// specify_default_indexer.cpp  
// compile with: /LD /clr  
using namespace System;  
[Reflection::DefaultMember("XXX")]  
public ref struct Squares {  
   property Double XXX[Double] {  
      Double get(Double data) {  
         return data*data;  
      }  
   }  
};  
```  
  
 O exemplo a seguir consome os metadados que é criado no exemplo anterior.  
  
```  
// consume_default_indexer.cpp  
// compile with: /clr  
#using "specify_default_indexer.dll"  
int main() {  
   Squares ^ square = gcnew Squares();  
   System::Console::WriteLine("{0}", square[3]);  
}  
```  
  
 **Saída**  
  
 **9**   
## Propriedades virtuais  
 Este exemplo de código mostra como declarar e usar propriedades virtuais:  
  
```  
// mcppv2_property_4.cpp  
// compile with: /clr  
using namespace System;  
interface struct IEFace {  
public:  
   property int VirtualProperty1;  
   property int VirtualProperty2 {  
      int get();  
      void set(int i);  
   }  
};  
  
// implement virtual events  
ref class PropImpl : public IEFace {  
   int MyInt;  
public:  
   virtual property int VirtualProperty1;  
  
   virtual property int VirtualProperty2 {  
      int get() {  
         return MyInt;  
      }  
      void set(int i) {  
         MyInt = i;  
      }  
   }  
};  
  
int main() {  
   PropImpl ^ MyPI = gcnew PropImpl();  
   MyPI->VirtualProperty1 = 93;  
   Console::WriteLine(MyPI->VirtualProperty1);  
  
   MyPI->VirtualProperty2 = 43;  
   Console::WriteLine(MyPI->VirtualProperty2);  
}  
```  
  
 **Saída**  
  
  **93**  
**43**   
## Abstratos propriedades e seladas  
 Embora as palavras\-chave de [abstract](../windows/abstract-cpp-component-extensions.md) e de [sealed](../windows/sealed-cpp-component-extensions.md) foram especificados como válidos na especificação de ECMA C\+\+\/CLI, para o compilador do Visual C\+\+, você não pode especificá\-los em propriedades triviais, nem na declaração de propriedade de uma propriedade não trivial.  
  
 Para declarar uma propriedade selada ou abstrata, você deve definir uma propriedade não trivial e então especificar a palavra\-chave de `abstract` ou de `sealed` nas funções do acessador obter e de cluster.  
  
```  
// properties_abstract_sealed.cpp  
// compile with: /clr  
ref struct A {  
protected:  
   int m_i;  
  
public:  
   A() { m_i = 87; }  
  
   // define abstract property  
   property int Prop_1 {  
      virtual int get() abstract;  
      virtual void set(int i) abstract;  
   }  
};  
  
ref struct B : A {  
private:  
   int m_i;  
  
public:  
   B() { m_i = 86; }  
  
   // implement abstract property  
   property int Prop_1 {  
      virtual int get() override { return m_i; }  
      virtual void set(int i) override { m_i = i; }  
   }  
};  
  
ref struct C {  
private:  
   int m_i;  
  
public:  
   C() { m_i = 87; }  
  
   // define sealed property  
   property int Prop_2 {  
      virtual int get() sealed { return m_i; }  
      virtual void set(int i) sealed { m_i = i; };  
   }  
};  
  
int main() {  
   B b1;  
   // call implementation of abstract property  
   System::Console::WriteLine(b1.Prop_1);  
  
   C c1;  
   // call sealed property  
   System::Console::WriteLine(c1.Prop_2);  
}  
```  
  
 **Saída**  
  
  **86**  
**87**   
## Propriedades multidimensionais  
 Você pode usar propriedades multidimensionais para definir os métodos de acessador da propriedade que têm um número não padrão de parâmetros.  
  
```  
// mcppv2_property_5.cpp  
// compile with: /clr  
ref class X {  
   double d;  
public:  
   X() : d(0) {}  
   property double MultiDimProp[int, int, int] {  
      double get(int, int, int) {  
         return d;  
      }  
      void set(int i, int j, int k, double l) {  
         // do something with those ints  
         d = l;  
      }  
   }  
  
   property double MultiDimProp2[int] {  
      double get(int) {  
         return d;  
      }  
      void set(int i, double l) {  
         // do something with those ints  
         d = l;  
      }  
   }  
  
};  
  
int main() {  
   X ^ MyX = gcnew X();  
   MyX->MultiDimProp[0,0,0] = 1.1;  
   System::Console::WriteLine(MyX->MultiDimProp[0, 0, 0]);  
}  
```  
  
 **Saída**  
  
  **1.1**   
## Sobrecarregando acessadores da propriedade  
 O exemplo a seguir mostra como sobrecarregar propriedades indexadas.  
  
```  
// mcppv2_property_6.cpp  
// compile with: /clr  
ref class X {  
   double d;  
public:  
   X() : d(0.0) {}  
   property double MyProp[int] {  
      double get(int i) {  
         return d;  
      }  
  
      double get(System::String ^ i) {  
         return 2*d;  
      }  
  
      void set(int i, double l) {  
         d = i * l;  
      }  
   }   // end MyProp definition  
};  
  
int main() {  
   X ^ MyX = gcnew X();  
   MyX->MyProp[2] = 1.7;  
   System::Console::WriteLine(MyX->MyProp[1]);  
   System::Console::WriteLine(MyX->MyProp["test"]);  
}  
```  
  
 **Saída**  
  
  **3.4**  
**6.8**   
## Consulte também  
 [property](../windows/property-cpp-component-extensions.md)