---
title: Importando para um aplicativo usando __declspec(dllimport) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- __declspec
- dllimport
dev_langs:
- C++
helpviewer_keywords:
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: edb4da4e-f83a-44cf-a668-9239d49dbe42
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 08a406c8884cdcb9d4b2ead2e61d416ac580fd73
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45704074"
---
# <a name="importing-into-an-application-using-declspecdllimport"></a>Importando para um aplicativo usando __declspec(dllimport)

Um programa que usa os símbolos públicos definidos por uma DLL é considerado para importá-los. Quando você cria arquivos de cabeçalho para aplicativos que usam suas DLLs para compilar, use **__declspec(dllimport)** sobre as declarações dos símbolos públicos. A palavra-chave **__declspec(dllimport)** funciona se você exportar arquivos. def ou com o **dllexport** palavra-chave.

Para tornar seu código mais legível, defina uma macro para **__declspec(dllimport)** e, em seguida, use a macro para declarar cada símbolo importado:

```
#define DllImport   __declspec( dllimport )

DllImport int  j;
DllImport void func();
```

Usando o **__declspec(dllimport)** é opcional em declarações de função, mas o compilador produz código mais eficiente se você usar essa palavra-chave. No entanto, você deve usar **__declspec(dllimport)** para o executável de importação acessar os símbolos de dados públicos e objetos da DLL. Observe que os usuários de sua DLL ainda precisam vincular com uma biblioteca de importação.

Você pode usar o mesmo arquivo de cabeçalho para a DLL e o aplicativo cliente. Para fazer isso, use um símbolo do pré-processador especial que indica se você estiver criando a DLL ou compilando o aplicativo cliente. Por exemplo:

```
#ifdef _EXPORTING
   #define CLASS_DECLSPEC    __declspec(dllexport)
#else
   #define CLASS_DECLSPEC    __declspec(dllimport)
#endif

class CLASS_DECLSPEC CExampleA : public CObject
{ ... class definition ... };
```

## <a name="what-do-you-want-to-do"></a>O que você deseja fazer?

- [Inicialize um DLL](../build/run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Que mais você deseja saber?

- [Importando e exportando funções embutidas](../build/importing-and-exporting-inline-functions.md)

- [Importações mútuas](../build/mutual-imports.md)

## <a name="see-also"></a>Consulte também

[Importando para um aplicativo](../build/importing-into-an-application.md)