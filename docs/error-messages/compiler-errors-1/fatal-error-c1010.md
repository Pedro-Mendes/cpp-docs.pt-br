---
title: Erro fatal C1010 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1010
dev_langs:
- C++
helpviewer_keywords:
- C1010
ms.assetid: dfd035f1-a7a2-40bc-bc92-dc4d7f456767
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5ae762c15c96ed7c12a20d2070d22cdc556667ac
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46064081"
---
# <a name="fatal-error-c1010"></a>Erro fatal C1010

fim de arquivo inesperado durante a procura de cabeçalho pré-compilado. Você esqueceu de adicionar ' #include nome ' à sua fonte?

Um arquivo de inclusão especificado com [/Yu](../../build/reference/yu-use-precompiled-header-file.md) não estiver listado no arquivo de origem.  Essa opção é habilitada por padrão na maioria dos tipos de projeto do Visual C++ e "Stdafx. h" é o padrão incluem o arquivo especificado por essa opção.

No ambiente do Visual Studio, use um dos seguintes métodos para resolver esse erro:

- Se você não usar cabeçalhos pré-compilados em seu projeto, defina as **criar/usar de cabeçalho pré-compilado** propriedade dos arquivos de origem **não cabeçalhos pré-compilados usando**. Para definir essa opção do compilador, siga estas etapas:

   1. No painel Gerenciador de soluções do projeto, clique com botão direito no nome do projeto e, em seguida, clique em **propriedades**.

   1. No painel esquerdo, clique no **C/C++** pasta.

   1. Clique o **cabeçalhos pré-compilados** nó.

   1. No painel direito, clique em **criar/usar cabeçalho de pré-compilado**e, em seguida, clique em **não usando cabeçalhos pré-compilados**.

- Certifique-se de excluído, renomeado ou removido do arquivo de cabeçalho inadvertidamente (por padrão, Stdafx. h) do projeto atual. Esse arquivo também deve ser incluído antes de qualquer outro código em seus arquivos de origem usando **#include "Stdafx. h"**. (Esse arquivo de cabeçalho é especificado como **criar/usar PCH através de arquivo** propriedade do projeto)