---
title: Erro das LNK1302 das ferramentas de vinculador | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1302
dev_langs:
- C++
helpviewer_keywords:
- LNK1302
ms.assetid: aea3c753-c2c4-4249-bbc3-f2d4f0164b5e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3dc85b37d58e12602c02c2207c1f38bda9344e59
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045504"
---
# <a name="linker-tools-error-lnk1302"></a>Erro das Ferramentas de Vinculador LNK1302

apenas suporta vínculo seguro. netmodules; não foi possível vincular o. netmodule de arquivo

Um. netmodule (compilado com **/LN**) foi passado para o vinculador em uma tentativa de usuário para invocar a vinculação MSIL.  Um módulo do C++ é válido para se ele for compilado com a vinculação de MSIL **/CLR: safe**.

Para corrigir esse erro, compilar com **/CLR: safe** para habilitar a vinculação MSIL ou passe o **/clr** ou **/clr: pure** arquivo. obj para o vinculador, em vez do módulo.

Para saber mais, veja

- [/LN (criar módulo de MSIL)](../../build/reference/ln-create-msil-module.md)

- [Arquivos .netmodule como entrada do vinculador](../../build/reference/netmodule-files-as-linker-input.md)