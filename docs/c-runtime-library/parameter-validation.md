---
title: "Validação de parâmetro | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- parameters, validation
ms.assetid: 019dd5f0-dc61-4d2e-b4e9-b66409ddf1f2
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 749e734bc4657efff3f0dfaeb735a0ea69375d02

---
# <a name="parameter-validation"></a>Validação do parâmetro
A maioria das funções de CRT com segurança aprimorada e muitas das funções preexistentes validam seus parâmetros. Isso pode incluir verificar se há ponteiros nulos, verificar se os inteiros estão dentro de um dado alcance ou verificar se os valores de enumeração são válidos. Quando um parâmetro inválido é encontrado, o manipulador de parâmetro inválido é executado.  
  
## <a name="invalid-parameter-handler-routine"></a>Rotina do manipulador de parâmetro inválido  
 Quando uma função da Biblioteca de Tempo de Execução C detecta um parâmetro inválido, ela captura algumas informações sobre o erro e chama uma macro que encapsula uma função de expedição de manipulador de parâmetro inválido, um dentre [_invalid_parameter](../c-runtime-library/reference/invalid-parameter-functions.md), [_invalid_parameter_noinfo](../c-runtime-library/reference/invalid-parameter-functions.md) ou [_invalid_parameter_noinfo_noreturn](../c-runtime-library/reference/invalid-parameter-functions.md). A função de expedição chamada depende se o código é, respectivamente, um build de depuração, um build comercial ou se o erro não é considerado recuperável. 
 
 Em Builds de depuração, o macro de parâmetro inválido geralmente gera uma asserção com falha e um ponto de interrupção do depurador antes da função de expedição ser chamada. Quando o código é executado, a asserção pode ser relatada para o usuário em uma caixa de diálogo que contém “Cancelar”, “Repetir” e “Continuar” ou opções semelhantes, dependendo da versão da biblioteca de tempo de execução e do sistema operacional. Essas opções permitem ao usuário terminar imediatamente o programa, anexar um depurador ou permitir que o código existente continue em execução, o que chama a função de expedição. 
 
 A função de expedição do manipulador de parâmetro inválido por sua vez chama o manipulador de parâmetro inválido atribuído no momento. Por padrão, o parâmetro inválido chama `_invoke_watson`, fazendo com que o aplicativo “falhe”, ou seja, termine e gere um minidespejo. Se habilitada pelo sistema operacional, uma caixa de diálogo pergunta ao usuário se deseja carregar o despejo de memória para a Microsoft para análise.   
  
 Esse comportamento pode ser alterado usando as funções [_set_invalid_parameter_handler](../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) ou [_set_thread_local_invalid_parameter_handler](../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) para definir o manipulador de parâmetro inválido para a sua própria função. Se a função que você especificar não terminar o aplicativo, o controle será retornado para a função que recebeu os parâmetros inválidos. No CRT, essas funções normalmente interrompem a execução de funções, definem `errno` para um código de erro e retornam um código de erro. Em muitos casos, o valor `errno` e o valor retornado são ambos `EINVAL`, indicando um parâmetro inválido. Em alguns casos, um código de erro mais específico é retornado, tal como `EBADF` para um ponteiro de arquivo inválido passado como um parâmetro. Para obter mais informações sobre `errno`, consulte [errno, _doserrno, _sys_errlist e _sys_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="see-also"></a>Consulte também  
 [Recursos de segurança no CRT](../c-runtime-library/security-features-in-the-crt.md)   
 [Recursos da biblioteca CRT](../c-runtime-library/crt-library-features.md)


<!--HONumber=Feb17_HO4-->

