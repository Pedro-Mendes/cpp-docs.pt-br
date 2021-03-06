---
title: Importando usando arquivos DEF | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- importing DLLs [C++], DEF files
- def files [C++], importing with
- .def files [C++], importing with
- dllimport attribute [C++], DEF files
- DLLs [C++], DEF files
ms.assetid: aefdbf50-f603-488a-b0d7-ed737bae311d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3e1562e14b20e4e1dd96764414978889d6205179
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45710535"
---
# <a name="importing-using-def-files"></a>Importando usando arquivos DEF

Se você optar por usar **__declspec(dllimport)** junto com um arquivo. def, você deve alterar o arquivo. def para usar dados no lugar de constante para reduzir a probabilidade de que a codificação incorreta fará com que um problema:

```
// project.def
LIBRARY project
EXPORTS
   ulDataInDll   DATA
```

A tabela a seguir mostra por que.

|Palavra-chave|Emite na biblioteca de importação|Exportações|
|-------------|---------------------------------|-------------|
|`CONSTANT`|`_imp_ulDataInDll`, `_ulDataInDll`|`_ulDataInDll`|
|`DATA`|`_imp_ulDataInDll`|`_ulDataInDll`|

Usando o **__declspec(dllimport)** e constante lista ambos os `imp` biblioteca que é criada para permitir que a vinculação explícita de importação de versão e o nome não decorado na DLL. lib. Usando o **__declspec(dllimport)** listas de dados e apenas o `imp` versão do nome.

Se você usar a constante, qualquer uma das construções de código a seguir pode ser usada para acessar `ulDataInDll`:

```
__declspec(dllimport) ULONG ulDataInDll; /*prototype*/
if (ulDataInDll == 0L)   /*sample code fragment*/
```

\-ou -

```
ULONG *ulDataInDll;      /*prototype*/
if (*ulDataInDll == 0L)  /*sample code fragment*/
```

No entanto, se você usar dados em seu arquivo. def, somente o código compilado com a seguinte definição pode acessar a variável `ulDataInDll`:

```
__declspec(dllimport) ULONG ulDataInDll;

if (ulDataInDll == 0L)   /*sample code fragment*/
```

Usando a constante é mais arriscado porque se você esquecer de usar o nível extra de indireção, você poderia potencialmente acessar ponteiro da tabela de endereço de importação para a variável — não a própria variável. Esse tipo de problema com frequência pode se manifestar como uma violação de acesso porque a tabela de endereços de importação é feita no momento, somente leitura pelo compilador e vinculador.

O vinculador atual do Visual C++ emite um aviso se perceber constante no arquivo. def para levar em conta para esse caso. O motivo real só para usar a constante é se você não é possível recompilar algum arquivo de objeto em que o arquivo de cabeçalho não listar **__declspec(dllimport)** no protótipo.

## <a name="see-also"></a>Consulte também

[Importando para um aplicativo](../build/importing-into-an-application.md)
