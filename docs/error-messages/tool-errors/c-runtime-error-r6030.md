---
title: C R6030 de erro de tempo de execução | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6030
dev_langs:
- C++
helpviewer_keywords:
- R6030
ms.assetid: 0238a6c3-a033-4046-8adc-f8f99d961153
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 63606624e1cbcc5ef2c5ea453ee6d346e3e686a8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46038120"
---
# <a name="c-runtime-error-r6030"></a>R6030 de erro de tempo de execução do C

CRT não inicializado

> [!NOTE]
>  Se você encontrar esta mensagem de erro durante a execução de um aplicativo, o aplicativo foi encerrado porque ele tem um problema interno. Esse problema é causado mais frequentemente por determinados programas de software de segurança ou raramente, por um bug no programa.
>
>  Você pode tentar corrigir esse erro com estas etapas:
>
>  -   Seu software de segurança pode ter instruções específicas para atenuar esse problema. Verifique o site do seu fornecedor software de segurança para obter detalhes. Como alternativa, verificar se há versões atualizadas do seu software de segurança ou experimente o software de segurança diferentes.
> -   Use o **aplicativos e recursos** ou **programas e recursos** página o **painel de controle** para reparar ou reinstalar o programa.
> -   Verifique **Windows Update** na **painel de controle** para atualizações de software.
> -   Verifique se há uma versão atualizada do aplicativo. Se o problema persistir, entre em contato com o fornecedor do aplicativo.

**Informações para programadores**

Esse erro ocorre se você estiver usando o tempo de execução C (CRT), mas o código de inicialização do CRT não foi executado. É possível receber esse erro se o vinculador alternar [/ENTRY](../../build/reference/entry-entry-point-symbol.md) é usada para substituir o padrão Iniciando endereço, geralmente **mainCRTStartup**, **wmainCRTStartup** para um EXE, do console **WinMainCRTStartup** ou **wWinMainCRTStartup** para um Windows. EXE, ou **dllmaincrtstartup** para uma DLL. A menos que uma das funções acima é chamada na inicialização, o tempo de execução C não será inicializado. Essas funções de inicialização normalmente são chamadas por padrão quando você vincular à biblioteca de tempo de execução do C e usa o vetor perpendicular **principal**, **wmain**, **WinMain**, ou  **DllMain** pontos de entrada.

Também é possível receber esse erro quando outro programa usa técnicas de injeção de código para interceptar determinadas chamadas de biblioteca DLL. Alguns programas de segurança intrusiva usam essa técnica. Nas versões do Visual C++ anteriores ao Visual Studio 2015, é possível usar uma biblioteca de CRT vinculadas estaticamente para resolver o problema, mas isso não é recomendado por motivos de atualizações de segurança e aplicativo. Corrigir esse problema pode exigir ação do usuário final.