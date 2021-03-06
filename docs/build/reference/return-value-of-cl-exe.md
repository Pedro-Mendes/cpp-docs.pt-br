---
title: Retornar o valor de cl.exe | Microsoft Docs
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, return value
ms.assetid: 7c2d7f33-ee0d-4199-8ef4-75fe2b007670
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4baca82dd9cf4581a5e20a7c426f4d79e383f3c
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43894659"
---
# <a name="return-value-of-clexe"></a>Valor de retorno de cl.exe

O cl.exe retorna zero para êxito (sem erros) e um número diferente de zero para outros casos.

O valor de retorno do cl.exe pode ser útil se você estiver compilando a partir de um arquivo de script, powershell, .cmd ou .bat. É recomendável capturar a saída do compilador caso haja erros ou avisos, para que você possa resolvê-los.

Há muitos possíveis códigos de saída de erro para o cl.exe listá-los. Você pode pesquisar um código de erro no Winerror. h ou Ntstatus arquivos incluídos no Windows Software Development Kit em % ProgramFiles (x86) %\Windows Kits\\<em>versão</em>\include\shared\. directory. Os códigos de erro retornados em decimal devem ser convertidos em hexadecimal para pesquisa. Por exemplo, um código de erro -1073741620 convertido em hexadecimal é 0xC00000CC. Esse erro é encontrado no ntstatus.h, onde a mensagem correspondente é "Não é possível localizar o nome de recurso compartilhado especificado no servidor remoto.” Para baixar a lista dos códigos de erro do Windows, consulte [ &#91;MS-ERREF&#93;: códigos de erro do Windows](https://msdn.microsoft.com/library/cc231196).

Você também pode usar o utilitário de pesquisa de erro no Visual Studio para descobrir o que uma mensagem de erro do compilador significa. Em um shell de comando do Visual Studio, insira **errlook.exe** para iniciar o utilitário; ou no IDE do Visual Studio, na barra de menus, escolha **ferramentas**, **pesquisa de erro**. Digite o valor do erro para encontrar o texto descritivo associado ao erro. Para obter mais informações, consulte [referência de ERRLOOK](../../build/reference/errlook-reference.md).

## <a name="remarks"></a>Comentários

Este é um arquivo .bat de exemplo que usa o valor de retorno do cl.exe.

```cmd
echo off
cl /W4 t.cpp
@if ERRORLEVEL == 0 (
   goto good
)

@if ERRORLEVEL != 0 (
   goto bad
)

:good
   echo "clean compile"
   echo %ERRORLEVEL%
   goto end

:bad
   echo "error or warning"
   echo %ERRORLEVEL%
   goto end

:end
```

## <a name="see-also"></a>Consulte também

[Sintaxe de linha de comando do compilador](../../build/reference/compiler-command-line-syntax.md)