---
title: "Como realizar marshaling de um VARIANT para ADO.NET (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ADO.NET [C++], realizando marshaling em tipos VARIANT"
  - "VARIANT"
  - "VARIANT, marshaling"
ms.assetid: 67a180a7-5691-48ab-8d85-7f75a68dde91
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Como realizar marshaling de um VARIANT para ADO.NET (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Demonstra como adicionar `VARIANT` nativo para um base de dados e como o marshaling <xref:System.Object?displayProperty=fullName> de um base de dados a `VARIANT`nativo.  
  
## Exemplo  
 Neste exemplo, a classe DatabaseClass é criada para interagir com um objeto do ADO.NET <xref:System.Data.DataTable> .  Observe que essa classe é um `class` C\+\+ nativo \(em relação a `ref class` ou a `value class`\).  Isso é necessário porque nós desejamos para usar essa classe de código nativo, e você não pode usar gerenciado em código nativo.  Esta classe será criada para atingir CLR, como é indicado por `#pragma managed` diretivo precedendo a declaração da classe.  Para obter mais informações sobre essa política, consulte [gerenciado, não gerenciado](../preprocessor/managed-unmanaged.md).  
  
 Observe o membro particular da classe de DatabaseClass: `gcroot<DataTable ^> table`.  Como os tipos nativos não podem conter tipos gerenciados, a palavra\-chave de `gcroot` é necessário.  Para obter mais informações sobre `gcroot`, consulte: [Como declarar identificadores em tipos nativos](../dotnet/how-to-declare-handles-in-native-types.md).  
  
 O restante do código neste exemplo é código C\+\+ nativo, como é indicado por `#pragma unmanaged``main`acima diretivo.  Neste exemplo, estamos criando uma nova instância de DatabaseClass e estamos chamar os métodos para criar uma tabela e popular algumas linhas na tabela.  Observe que os tipos de `VARIANT` nativos estão sendo passados como valores para a coluna ObjectCol da base de dados.  Dentro de DatabaseClass, esses tipos de `VARIANT` marshaling para objetos gerenciados usando a funcionalidade marshaling localizada no namespace de <xref:System.Runtime.InteropServices?displayProperty=fullName> .  Especificamente, o método <xref:System.Runtime.InteropServices.Marshal.GetObjectForNativeVariant%2A> é usado ao marshaling `VARIANT` a <xref:System.Object>, e o método <xref:System.Runtime.InteropServices.Marshal.GetNativeVariantForObject%2A> é usado ao marshaling <xref:System.Object> a `VARIANT`.  
  
```  
// adonet_marshal_variant.cpp  
// compile with: /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll  
#include <comdef.h>  
#include <gcroot.h>  
#include <iostream>  
using namespace std;  
  
#using <System.Data.dll>  
using namespace System;  
using namespace System::Data;  
using namespace System::Runtime::InteropServices;  
  
#define MAXCOLS 100  
  
#pragma managed  
class DatabaseClass  
{  
public:  
    DatabaseClass() : table(nullptr) { }  
  
    void AddRow(VARIANT *objectColValue)  
    {  
        // Add a row to the table.  
        DataRow ^row = table->NewRow();  
        row["ObjectCol"] = Marshal::GetObjectForNativeVariant(  
            IntPtr(objectColValue));  
        table->Rows->Add(row);  
    }  
  
    void CreateAndPopulateTable()  
    {  
        // Create a simple DataTable.  
        table = gcnew DataTable("SampleTable");  
  
        // Add a column of type String to the table.  
        DataColumn ^column1 = gcnew DataColumn("ObjectCol",  
            Type::GetType("System.Object"));  
        table->Columns->Add(column1);  
    }  
  
    int GetValuesForColumn(wchar_t *dataColumn, VARIANT *values,  
        int valuesLength)  
    {  
        // Marshal the name of the column to a managed  
        // String.  
        String ^columnStr = Marshal::PtrToStringUni(  
                (IntPtr)dataColumn);  
  
        // Get all rows in the table.  
        array<DataRow ^> ^rows = table->Select();  
        int len = rows->Length;  
        len = (len > valuesLength) ? valuesLength : len;  
        for (int i = 0; i < len; i++)  
        {  
            // Marshal each column value from a managed object  
            // to a VARIANT.  
            Marshal::GetNativeVariantForObject(  
                rows[i][columnStr], IntPtr(&values[i]));  
        }  
  
        return len;  
    }  
  
private:  
    // Using gcroot, you can use a managed type in  
    // a native class.  
    gcroot<DataTable ^> table;  
};  
  
#pragma unmanaged  
int main()  
{  
    // Create a table and add a few rows to it.  
    DatabaseClass *db = new DatabaseClass();  
    db->CreateAndPopulateTable();  
  
    BSTR bstr1 = SysAllocString(L"This is a BSTR in a VARIANT.");  
    VARIANT v1;  
    v1.vt = VT_BSTR;  
    v1.bstrVal = bstr1;  
    db->AddRow(&v1);  
  
    int i = 42;  
    VARIANT v2;  
    v2.vt = VT_I4;  
    v2.lVal = i;  
    db->AddRow(&v2);  
  
    // Now retrieve the rows and display their contents.  
    VARIANT values[MAXCOLS];  
    int len = db->GetValuesForColumn(  
        L"ObjectCol", values, MAXCOLS);  
    for (int i = 0; i < len; i++)  
    {  
        switch (values[i].vt)  
        {  
            case VT_BSTR:  
                wcout << L"ObjectCol: " << values[i].bstrVal << endl;  
                break;  
            case VT_I4:  
                cout << "ObjectCol: " << values[i].lVal << endl;  
                break;  
            default:  
                break;  
        }  
  
    }  
  
    SysFreeString(bstr1);  
    delete db;  
  
    return 0;  
}  
```  
  
  **ObjectCol: Este é um BSTR em uma VARIANT.**  
**ObjectCol: 42**   
## Compilando o código  
  
-   Para compilar o código de linha de comando, salve o exemplo de código em um arquivo chamado adonet\_marshal\_variant.cpp e digite a seguinte instrução:  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_variant.cpp  
    ```  
  
## Segurança do .NET Framework  
 Para obter informações sobre problemas de segurança que envolvem o ADO.NET, consulte [Protegendo aplicativos ADO.NET](../Topic/Securing%20ADO.NET%20Applications.md).  
  
## Consulte também  
 <xref:System.Runtime.InteropServices>   
 [Acesso a dados](../dotnet/data-access-using-adonet-cpp-cli.md)   
 [ADO.NET](../Topic/ADO.NET.md)   
 [Interoperability](http://msdn.microsoft.com/pt-br/afcc2e7d-3f32-48d2-8141-1c42acf29084)   
 [Nativo e interoperabilidade .NET](../Topic/Native%20and%20.NET%20Interoperability.md)