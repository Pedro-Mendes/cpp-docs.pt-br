---
title: Determinando qual método usar exportação | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- __declspec(dllexport) keyword [C++]
- exporting DLLs [C++], method comparison
- def files [C++], exporting from DLLs
- .def files [C++], exporting from DLLs
ms.assetid: 66d773ed-935c-45c2-ad03-1a060874b34d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 07315ca7558c2e8b972e8e3aba741696b8097e8c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703567"
---
# <a name="determining-which-exporting-method-to-use"></a>Determinando qual método de exportação usar

Você pode exportar funções em qualquer uma das duas maneiras — um arquivo. def ou o `__declspec(dllexport)` palavra-chave. Para ajudá-lo a decidir qual modo é melhor para sua DLL, considere estas perguntas:

- Você planeja exportar mais funções mais tarde?

- É a sua DLL usado apenas por aplicativos que você pode recompilar ou ele é usado por aplicativos que não é possível recriar — por exemplo, os aplicativos que são criados por terceiros?

## <a name="pros-and-cons-of-using-def-files"></a>Prós e contras do uso de arquivos. def

Exportando funções em um. def arquivo lhe dá controle sobre os ordinais de exportação. Quando você adiciona uma função exportada a sua DLL, você pode atribuir um valor ordinal mais alto que qualquer outra função exportada. Quando você fizer isso, os aplicativos que usam a vinculação implícita é preciso vincular novamente com a biblioteca de importação que contém a nova função. Isso é muito conveniente se você estiver criando uma DLL para uso por vários aplicativos, pois você pode adicionar uma nova funcionalidade e também garantir que ele continue a funcionar corretamente com os aplicativos que dependem dele já. Por exemplo, as DLLs do MFC são criadas por meio de arquivos. def.

Outra vantagem de usar um arquivo. def é que você pode usar o `NONAME` atributo exportar uma função. Isso faz com que apenas o ordinal na tabela de exportações na DLL. Para DLLs que tenham um grande número de funções exportadas, usando o `NONAME` atributo pode reduzir o tamanho do arquivo DLL. Para obter informações sobre como escrever uma instrução de definição de módulo, consulte [regras para instruções de definição de módulo](../build/reference/rules-for-module-definition-statements.md). Para obter informações sobre exportação ordinal, consulte [exportar funções de uma DLL por Ordinal em vez de por nome](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md).

Uma desvantagem de usar um arquivo. def é que se você estiver exportando funções em um arquivo do C++, você terá que colocar os nomes decorados de. def de arquivo ou define as funções exportadas usando extern "C" para evitar a decoração de nome que é feito pelo compilador Visual C++.

Se você colocar os nomes decorados no arquivo. def, você pode obtê-los usando o [DUMPBIN](../build/reference/dumpbin-reference.md) ferramenta ou, usando o vinculador [/Map](../build/reference/map-generate-mapfile.md) opção. Os nomes decorados produzidos pelo compilador são específicos do compilador; Portanto, se você colocar os nomes decorados produzidos pelo compilador em um arquivo. def, os aplicativos que são vinculados ao DLL também deverão ser compilados usando a mesma versão do compilador para que os nomes decorados no aplicativo de chamada corresponderem exportado nomeia i n o arquivo. def da DLL.

## <a name="pros-and-cons-of-using-declspecdllexport"></a>Prós e contras do uso de dllexport

Usando `__declspec(dllexport)` é conveniente porque você não precisa se preocupar sobre como manter um arquivo. def e obter os nomes decorados das funções exportadas. No entanto, a utilidade dessa forma de exportação é limitada pelo número de aplicativos vinculados que você está disposto a recompilar. Se você recriar a DLL com novos exportações, você precisa recompilar os aplicativos, pois os nomes decorados para funções exportadas do C++ pode ser alterado se você usar uma versão diferente do compilador para recriá-lo.

### <a name="what-do-you-want-to-do"></a>O que você deseja fazer?

- [Exportar de uma DLL usando. Arquivos DEF](../build/exporting-from-a-dll-using-def-files.md)

- [Exportar de uma DLL usando dllexport](../build/exporting-from-a-dll-using-declspec-dllexport.md)

- [Exportar e importar usando AFX_EXT_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)

- [Exportar funções de C++ para uso em executáveis da linguagem C](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)

- [Exportar funções de C para uso em executáveis C ou da linguagem C++](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [Importar para um aplicativo usando __declspec(dllimport)](../build/importing-into-an-application-using-declspec-dllimport.md)

- [Inicialize um DLL](../build/run-time-library-behavior.md#initializing-a-dll)

### <a name="what-do-you-want-to-know-more-about"></a>Que mais você deseja saber?

- [Importando e exportando funções embutidas](../build/importing-and-exporting-inline-functions.md)

- [Importações mútuas](../build/mutual-imports.md)

- [Nomes decorados](../build/reference/decorated-names.md)

## <a name="see-also"></a>Consulte também

[Exportando de uma DLL](../build/exporting-from-a-dll.md)