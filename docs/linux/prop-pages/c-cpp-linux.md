---
title: Propriedades do C/C++ (Linux C++) | Microsoft Docs
ms.custom: 
ms.date: 9/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4bb8894b-c874-4a68-935e-b127d54e484f
author: mikeblome
ms.author: mblome
manager: ghogen
f1_keywords:
- VC.Project.VCClangCompilerTool.AdditionalIncludeDirectories
- VC.Project.VCClangCompilerTool.DebugInformationFormat
- VC.Project.VCClangCompilerTool.ObjectFile
- VC.Project.VCClangCompilerTool.WarningLevel
- VC.Project.VCClangCompilerTool.WarnAsError
- VC.Project.VCClangCompilerTool.AdditionalWarning
- VC.Project.VCClangCompilerTool.Verbose
- VC.Project.VCConfiguration.BuildLogFile
- VC.Project.VCClangCompilerTool.Optimization
- VC.Project.VCClangCompilerTool.StrictAliasing
- VC.Project.VCClangCompilerTool.UnrollLoops
- VC.Project.VCClangCompilerTool.LinkTimeOptimization
- VC.Project.VCClangCompilerTool.OmitFramePointers
- VC.Project.VCClangCompilerTool.NoCommonBlocks
- VC.Project.VCClangCompilerTool.PIC
- VC.Project.VCClangCompilerTool.ThreadSafeStatics
- VC.Project.VCClangCompilerTool.RelaxIEEE
- VC.Project.VCClangCompilerTool.HideInlineMethods
- VC.Project.VCClangCompilerTool.SymbolsHiddenByDefault
- VC.Project.VCClangCompilerTool.ExceptionHandling
- VC.Project.VCClangCompilerTool.RuntimeTypeInfo
- VC.Project.VCClangCompilerTool.CLanguageStandard
- VC.Project.VCClangCompilerTool.CppLanguageStandard
- VC.Project.VCClangCompilerTool.PreprocessorDefinitions
- VC.Project.VCClangCompilerTool.UndefinePreprocessorDefinitions
- VC.Project.VCClangCompilerTool.UndefineAllPreprocessorDefinitions
- VC.Project.VCClangCompilerTool.ShowIncludes
- VC.Project.VCClangCompilerTool.CompileAs
- VC.Project.VCClangCompilerTool.ForcedIncludeFiles
- vc.project.AdditionalOptionsPage
ms.openlocfilehash: 94a22843c15e537a7af8e1e44827f8c1ab365165
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2017
---
# <a name="cc-properties-linux-c"></a>Propriedades do C/C++ (Linux C++)

## <a name="general"></a>Geral
Propriedade | Descrição | Opções
--- | ---| ---
Diretórios de Inclusão Adicionais | Especifica um ou mais diretórios a serem adicionados ao caminho de inclusão, separados por ponto e vírgula (se houver mais de um). (-I[path]).
Formato das informações de depuração | Especifica o tipo de informações de depuração geradas pelo compilador. | **Nenhum** – não produz nenhuma informação de depuração, portanto, a compilação pode ser mais rápida.<br>**Mínimo de informações de depuração** – gerar o mínimo de informações de depuração.<br>**Informações de depuração completas (DWARF2)** – gerar informações de depuração DWARF2.<br>
Nome do arquivo-objeto | Especifica um nome para substituir o nome do arquivo-objeto padrão. Pode ser um nome de arquivo ou de diretório. (-o [name]).
Nível de aviso | Selecione o rigor que você deseja que o compilador aplique aos erros de código.  Outros sinalizadores devem ser adicionados diretamente às Opções Adicionais. (/w, /Weverything). | **Desligar todos os avisos** – desabilita todos os avisos do compilador.<br>**EnableAllWarnings** – habilita todos os avisos, incluindo os que são desabilitados por padrão.<br>
Tratar avisos como erros | Trata todos os avisos do compilador como erros. Para um novo projeto, talvez seja melhor usar /Werror em todas as compilações. Resolver todos os avisos assegurará o menor número possível de defeitos de código difíceis de localizar.
Avisos adicionais do C | Define um conjunto adicional de mensagens de aviso.
Avisos adicionais do C++ | Define um conjunto adicional de mensagens de aviso.
Habilitar modo detalhado | Quando o modo detalhado é habilitado, essa ferramenta imprime mais informações para diagnosticar o build.
Compilador C | Especifica o programa a ser invocado durante a compilação de arquivos de origem C ou o caminho para o compilador C no sistema remoto.
Compilador C++ | Especifica o programa a ser invocado durante a compilação de arquivos de origem C++ ou o caminho para o compilador C++ no sistema remoto.
Tempo limite de compilação | Tempo limite de compilação remota, em milissegundos.
Copiar arquivos-objetos | Especifica se é necessário copiar os arquivos-objetos compilados do sistema remoto para o computador local.

## <a name="optimization"></a>Otimização
Propriedade | Descrição | Opções
--- | ---| ---
Otimização | Especifica o nível de otimização para o aplicativo. | **Personalizar** – otimização personalizada.<br>**Desabilitado** – desabilitar a otimização.<br>**Minimizar Tamanho** – otimizar o tamanho.<br>**Maximizar velocidade** – otimizar a velocidade.<br>**Otimização total** – otimizações de alto custo.<br>
Alias estrito | Considere as regras de alias mais rígidas.  Um objeto de um tipo nunca será considerado como residente do mesmo endereço que um objeto de um tipo diferente.
Desenrolar loops | Desenrole loops para deixar o aplicativo mais rápido reduzindo o número de branches executados às custas do aumento do tamanho do código.
Otimização de tempo de vinculação | Habilite otimizações entre procedimentos permitindo que o otimizador consulte arquivos-objetos em seu aplicativo.
Omitir ponteiro de quadro | Inibe a criação de ponteiros de quadros na pilha de chamadas.
Não há blocos comuns | Alocar até mesmo variáveis globais não inicializadas na seção de dados do arquivo-objeto, em vez de gerá-las como blocos comuns

## <a name="preprocessor"></a>Pré-processador
Propriedade | Descrição | Opções
--- | ---| ---
Definições do Pré-processador | Defina símbolos de pré-processamento para seu arquivo de origem. (-D)
Excluir definições do pré-processador | Especifica uma ou mais exclusões de definição do pré-processador.  (-U [macro])
Excluir todas as definições do pré-processador | Exclua as definições de todos os valores do pré-processador definidos anteriormente.  (-undef)
Mostrar inclusões | Gera uma lista de arquivos de inclusão com a saída do compilador.  (-H)

## <a name="code-generation"></a>Geração de código
Propriedade | Descrição | Opções
--- | ---| ---
Código independente da posição | Gere um código independente da posição (PIC) para ser usado em uma biblioteca compartilhada.
Estáticos são thread-safe | Emita um código extra para usar as rotinas especificadas no ABI C++ para inicialização thread-safe de estáticos locais. | **Não** – desabilitar estáticos thread-safe.<br>**Sim** – habilitar estáticos thread-safe.<br>
Otimização de ponto flutuante | Habilita otimizações de ponto flutuante relaxando a conformidade com o IEEE-754.
Métodos embutidos ocultados | Quando habilitado, as cópias fora de linha de métodos embutidos são declaradas como 'private extern'.
Símbolos ocultos por padrão | Todos os símbolos são declarados como 'private extern', a menos que sejam marcados explicitamente para serem exportados usando a macro '__attribute'.
Habilitar exceções do C++ | Especifica o modelo de tratamento de exceções a ser utilizado pelo compilador. | **Não** – desabilitar o tratamento de exceções.<br>**Sim** – habilitar tratamento de exceções.<br>

## <a name="language"></a>Linguagem
Propriedade | Descrição | Opções
--- | ---| ---
Habilitar informações de tipo de tempo de execução | Adiciona um código para verificar os tipos de objeto C++ no tempo de execução (informações de tipo de tempo de execução).     (frtti, fno-rtti)
Padrão de linguagem C | Determina o padrão de linguagem C. | **Padrão**<br>**C89** – padrão de linguagem C89.<br>**C99** – padrão de linguagem C99.<br>**C11** – padrão de linguagem C11.<br>**C99 (dialeto GNU )** – padrão de linguagem C99 (dialeto GNU).<br>**C11 (dialeto GNU )** – padrão de linguagem C11 (dialeto GNU).<br>
Padrão de linguagem C++ | Determina o padrão de linguagem C++. | **Padrão**<br>**C++03** – padrão de linguagem C++03.<br>**C++11** – padrão de linguagem C++11.<br>**C++14** – padrão de linguagem C++14.<br>**C++03 (dialeto GNU )** – padrão de linguagem C++03 (dialeto GNU).<br>**C++11 (dialeto GNU )** – padrão de linguagem C++11 (dialeto GNU).<br>**C++14 (dialeto GNU )** – padrão de linguagem C++14 (dialeto GNU).<br>

## <a name="advanced"></a>Avançado
Propriedade | Descrição | Opções
--- | ---| ---
Compilar como | Selecione a opção de linguagem de compilação para arquivos .c e .cpp.  'Padrão' detectará com base na extensão .c ou .cpp. (-x c, -x c++) | **Padrão** – padrão.<br>**Compilar como código C** – compilar como código C.<br>**Compilar como código C++** – compilar como código C++.<br>
Arquivos de inclusão forçados | Um ou mais arquivos de inclusão forçados (-include [name])

## <a name="additional-options"></a>Opções Adicionais 