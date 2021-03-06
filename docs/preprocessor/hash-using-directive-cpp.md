---
title: '#Diretiva using (C + + / CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- friend_as_cpp
- '#using'
- friend_as
- '#using_cpp'
dev_langs:
- C++
helpviewer_keywords:
- using directive (#using)
- '#using directive'
- LIBPATH environment variable
- preprocessor, directives
ms.assetid: 870b15e5-f361-40a8-ba1c-c57d75c8809a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8a43946100146def9c0082f533c3657d7ab8ebac
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42541343"
---
# <a name="using-directive-ccli"></a># Diretiva using (C + + / CLI)
Importa metadados para um programa compilado com [/clr](../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="syntax"></a>Sintaxe  
  
```  
#using file [as_friend]  
```  
  
### <a name="parameters"></a>Parâmetros  
*file*  
Um MSIL .dll, .exe, .netmodule ou .obj. Por exemplo,  
  
`#using <MyComponent.dll>`  
  
*as_friend*  
Especifica que todos os tipos no *arquivo* estão acessíveis. Para obter mais informações, consulte [Assemblies de amigo (C++)](../dotnet/friend-assemblies-cpp.md).  
  
## <a name="remarks"></a>Comentários  
 
*arquivo* pode ser Microsoft intermediate language (MSIL) que você importa para seus dados gerenciados e construções gerenciadas. Se um arquivo. dll contém um manifesto do assembly, em seguida, todos os. DLLs referenciados no manifesto são importados e o assembly que você está criando listará *arquivo* nos metadados como uma referência de assembly.  
  
Se *arquivo* não contém um assembly (se *arquivo* é um módulo) e se você não pretende usar informações de tipo do módulo no aplicativo atual (assembly), você terá a opção apenas indicar que o módulo faz parte do assembly; Use [/ASSEMBLYMODULE](../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md). Então, os tipos no módulo estariam disponíveis para qualquer aplicativo que fizesse referência ao assembly.  
  
Uma alternativa para usar **#using** é o [/FU](../build/reference/fu-name-forced-hash-using-file.md) opção de compilador.  
  
assemblies .exe passado para **#using** deve ser compilado usando um dos compiladores do Visual Studio .NET (Visual Basic ou Visual c#, por exemplo).  Tentar importar metadados de um assembly .exe compilado com `/clr` resultará em uma exceção de carregamento de arquivo.  
  
> [!NOTE]
> Um componente que é referenciado com **#using** pode ser executado com uma versão diferente do arquivo importado no tempo de compilação, fazendo com que um aplicativo cliente para gerar resultados inesperados.  
  
Para que o compilador reconheça um tipo em um assembly (não um módulo), ele precisa ser forçado a resolver o tipo, que você pode fazer, por exemplo, definindo uma instância do tipo. Há outras maneiras de resolver nomes de tipo em um assembly para o compilador, por exemplo, se você herda de um tipo em um assembly, o nome do tipo se tornará, então, conhecido do compilador.  
  
Ao importar metadados criados a partir do código-fonte que usada [__declspec(thread)](../cpp/thread.md), a semântica de thread não persiste nos metadados. Por exemplo, uma variável declarada com **__declspec(thread)**, compilada em um programa que é criado para o .NET Framework common language runtime e, em seguida, importado por meio **#using**, deixará de ter **__declspec(thread)** semântica na variável.  
  
Todos os tipos (gerenciados e nativos) em um arquivo referenciado pelo importados **#using** estão disponíveis, mas o compilador trata tipos nativos como declarações e não as definições.  
  
mscorlib.dll é referenciado automaticamente durante a compilação com `/clr`.  
  
A variável de ambiente LIBPATH Especifica os diretórios que serão pesquisados quando o compilador tenta resolver nomes de arquivo passado para **#using**.  
  
O compilador pesquisará referências ao longo do seguinte caminho:  
  
- Um caminho especificado na **#using** instrução.  
  
- O diretório atual.  
  
- O diretório do sistema do .NET Framework.  
  
- Diretórios adicionados com o [/AI](../build/reference/ai-specify-metadata-directories.md) opção de compilador.  
  
- Diretórios na variável de ambiente LIBPATH.  
  
## <a name="example"></a>Exemplo  
 
Se você criar um assembly (C) e fizer referência a um assembly (B) que faz referência a outro assembly (A), não terá que fazer referência explicitamente ao assembly A, a menos que use explicitamente um dos tipos de A em C.  
  
```cpp  
// using_assembly_A.cpp  
// compile with: /clr /LD  
public ref class A {};  
```  
  
## <a name="example"></a>Exemplo  
  
```cpp  
// using_assembly_B.cpp  
// compile with: /clr /LD  
#using "using_assembly_A.dll"  
public ref class B {  
public:  
   void Test(A a) {}  
   void Test() {}  
};    
```  
  
## <a name="example"></a>Exemplo  
 
No exemplo a seguir, não há erros do compilador por não fazer referência usando _assembly_A.dll, pois o programa não usa nenhum dos tipos definidos no uso de _assembly_A.cpp.  
  
```cpp  
// using_assembly_C.cpp  
// compile with: /clr  
#using "using_assembly_B.dll"  
int main() {  
   B b;  
   b.Test();  
}  
```  
  
## <a name="see-also"></a>Consulte também 

[Diretivas do pré-processador](../preprocessor/preprocessor-directives.md)