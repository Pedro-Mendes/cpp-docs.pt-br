---
title: Visual C++ no Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 08/22/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- unmanaged code, C++
- development environment, Visual C++
- unmanaged code
- Visual C++
- Visual C++, reference
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6116a1b27595c6400edfcb79daafb362fb7aec5f
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43684485"
---
# <a name="visual-c-in-visual-studio"></a>Visual C++ no Visual Studio

> [!NOTE]  
> Esta documentação para desenvolvedores aplica-se ao Visual Studio 2015 e ao Visual Studio 2017. 

> Se você estiver procurando um pacote redistribuível do Visual C++ para executar um programa, acesse o [Centro de Download da Microsoft](http://www.microsoft.com/en-us/download/) e insira **Visual C++** na caixa de pesquisa.  
  

Microsoft Visual C++, geralmente abreviado para Visual C++ ou MSVC, é o nome para as bibliotecas e ferramentas de desenvolvimento de linguagem de assembly, C e C++ disponíveis como parte do Visual Studio no Windows. Essas ferramentas e bibliotecas permitem que você crie aplicativos da UWP (Plataforma Universal do Windows), aplicativos de servidor e área de trabalho Windows nativos, bibliotecas e aplicativos multiplataforma que são executados no Windows, Linux, Android e iOS, bem como bibliotecas e aplicativos que usam o .NET Framework. Você pode usar o Visual C++ escrever qualquer coisa, desde aplicativos de console simples até os aplicativos mais sofisticados e complexos para área de trabalho do Windows, de drivers de dispositivo e componentes do sistema operacional até jogos multiplataforma para dispositivos móveis e dos menores dispositivos IoT até computação de alto desempenho multisservidor na nuvem do Azure.

## <a name="whats-new-and-conformance-history"></a>Histórico de novidades e de conformidade

[Novidades do C++ no Visual Studio 2017](what-s-new-for-visual-cpp-in-visual-studio.md)<br/>
Descubra as novidades do Visual Studio 2017.

[Novidades do C++ no Visual Studio 2003 até 2015](porting/visual-cpp-what-s-new-2003-through-2015.md)<br/>
Descubra quais foram as novidades do C++ para cada versão do Visual Studio, de 2003 até 2015.

[Aprimoramentos de conformidade do C++ no Visual Studio 2017](cpp-conformance-improvements-2017.md)<br/>
Saiba mais sobre as melhorias de conformidade do C++ no Visual Studio 2017.

[Conformidade com a linguagem Visual C++](visual-cpp-language-conformance.md)<br/>
Uma lista de status de conformidade por recurso no compilador C++ do MSVC.

[Histórico de alterações de 2003 a 2015 do Visual C++](porting/visual-cpp-change-history-2003-2015.md)<br/>
Saiba mais sobre as alterações significativas nas versões anteriores.

## <a name="install-visual-studio-and-upgrade-from-earlier-versions"></a>Instalar o Visual Studio e atualizar de versões anteriores

[Instalar o suporte ao C++ no Visual Studio](build/vscpp-step-0-installation.md)<br/>
Baixe o Visual Studio 2015 ou o Visual Studio 2017 e instale o conjunto de ferramentas do Visual C++.

[Guia de atualização e portabilidade do Visual C++](porting/visual-cpp-porting-and-upgrading-guide.md)<br/>
Diretrizes para portabilidade de código e atualização de projetos para o Visual Studio 2015 ou o Visual Studio 2017, incluindo a portabilidade de código C++ para o Windows 10 e a Plataforma Universal do Windows.

[Ferramentas e recursos do Visual C++ em edições do Visual Studio](ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)<br/>
Descubra as diferentes edições do Visual Studio.

[Plataformas com suporte](supported-platforms-visual-cpp.md)<br/>
Descubra quais plataformas têm suporte.

## <a name="learn-c"></a>Aprender sobre o C++

[Bem-vindo outra vez ao C++](cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
Saiba mais sobre as técnicas de programação modernas do C++ com base em C++11 e C++14 que permitem que você escreva código rápido e seguro e evite muitas das armadilhas do estilo de programação em C.

[C++ Padrão](http://isocpp.org/)<br/>
Saiba mais sobre o C++, obtenha uma visão geral do C++ Moderno e encontre links para livros, artigos, links e eventos

[Aprender sobre o Visual C++](build/vscpp-step-1-create.md)<br/>
Comece a conhecer o C++.

[Exemplos do Visual C++](visual-cpp-samples.md)<br/>
Informações sobre exemplos.

## <a name="c-development-tools"></a>Ferramentas de desenvolvimento do C++

[IDE e ferramentas de desenvolvimento](ide/ide-and-tools-for-visual-cpp-development.md).
Como usar o IDE do Visual Studio para criar projetos, trabalhar com arquivos de código-fonte, vincular a bibliotecas, compilar, depurar, criar testes de unidade, fazer análise estática, implantar e muito mais.

[Compiladores e ferramentas de build](build/building-c-cpp-programs.md) Opções de compilador e vinculador C++ da Microsoft, mensagens de erro, exemplos de linha de comando, configuração para diferentes plataformas e tópicos de referência de build. 

## <a name="write-applications-in-c"></a>Escrever aplicativos em C++

[Aplicativos universais do Windows](windows/universal-windows-apps-cpp.md)<br/>
Encontre guias e conteúdo de referência no Centro de Desenvolvedores do Windows. Para obter informações de como desenvolver aplicativos UWP, confira [Introdução à Plataforma Universal do Windows](/windows/uwp/get-started/universal-application-platform-guide) e [Criar um app "Hello world" em C++](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp).

[Aplicativos da área de trabalho (C++)](windows/desktop-applications-visual-cpp.md)<br/>
Saiba como criar aplicativos da área de trabalho tradicionais, nativos, em C++ para Windows.

[Programação no .NET com C++/CLI](dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md) Saiba como criar DLLs que permitem a interoperabilidade entre programas nativos em C++ e no .NET escritos em linguagens como C# ou Visual Basic.

[Programação para Linux](linux/index.md) Use o IDE do Visual Studio para codificar e implantar em um computador Linux remoto para compilação com GCC.

[DLLs no Visual C++](build/dlls-in-visual-cpp.md)<br/>
Descubra como usar o Win32, o ATL e o MFC para criar DLLs de área de trabalho do Windows e fornece informações sobre como compilar e registrar sua DLL.

[Programação paralela](parallel/parallel-programming-in-visual-cpp.md)<br/>
Saiba como usar a Biblioteca de Padrões Paralelos, C++ AMP, OpenMP e outros recursos que estão relacionados ao multithreading no Windows.

[Práticas Recomendadas de segurança](security/security-best-practices-for-cpp.md)<br/>
Saiba como proteger aplicativos contra código mal-intencionado e de uso não autorizado.

[Programação de Nuvem e da Web](cloud/cloud-and-web-programming-in-visual-cpp.md)<br/>
No C++ há várias opções para conectar-se com a Web e com a nuvem.

[Acesso a dados](data/data-access-in-cpp.md)<br/>
Conecte-se a bancos de dados usando ODBC e outras tecnologias de acesso de banco de dados.

[Texto e cadeias de caracteres](text/text-and-strings-in-visual-cpp.md)<br/>
Saiba mais sobre como trabalhar com formatos e codificações diferentes de texto e de cadeia de caracteres para desenvolvimento local e internacional.

## <a name="c-language-reference"></a>Referência da linguagem C++

Para obter mais informações sobre a linguagem C++, consulte [Referência da linguagem C++](cpp/cpp-language-reference.md).

Para obter informações sobre o pré-processador C++, consulte [Referência de pré-processador C/C++](preprocessor/c-cpp-preprocessor-reference.md).

## <a name="c-libraries-in-visual-studio"></a>Bibliotecas do C++ no Visual Studio

As seções a seguir fornecem informações sobre as diferentes bibliotecas do C e C++ que estão incluídas no Visual Studio.

[Referência da biblioteca em tempo de execução C](c-runtime-library/c-run-time-library-reference.md)<br/>
Inclui alternativas aprimoradas de segurança a funções que são conhecidas por impor problemas de segurança.

[Biblioteca Padrão do C++](standard-library/cpp-standard-library-reference.md)<br/>
A Biblioteca Padrão do C++.

[ATL (Active Template Library)](atl/atl-com-desktop-components.md)<br/>
Compatibilidade com aplicativos e componentes COM.

[Bibliotecas MFC (Microsoft Foundation Class)](mfc/mfc-desktop-applications.md)<br/>
Suporte para criação de aplicativos da área de trabalho com interfaces de usuário tradicionais ou no estilo Office.

[PPL (Biblioteca de Padrões Paralelos)](parallel/concrt/parallel-patterns-library-ppl.md)<br/>
Algoritmos assíncronos e paralelos que são executados na CPU.

[C++ AMP (C++ Accelerated Massive Parallelism)](parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
Algoritmos totalmente paralelos que são executados na GPU.

[WRL (Biblioteca de Modelos do Windows Runtime)](windows/windows-runtime-cpp-template-library-wrl.md)<br/>
Aplicativos UWP (Plataforma Universal do Windows) e componentes.

[Programação do .NET com C++/CLI](dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<br/>
Programação para o CLR (Common Language Runtime).

## <a name="third-party-open-source-c-libraries"></a>Bibliotecas C++ de software livre de terceiros

A ferramenta de linha de comando **vcpkg** multiplataforma simplifica bastante a descoberta e a instalação de mais de 900 bibliotecas C++ de software livre. Consulte [vcpkg: gerenciador de pacotes de C++ para Windows](vcpkg.md).

## <a name="feedback-and-community"></a>Comentários e comunidade

[Como relatar um problema com o Conjunto de Ferramentas do Visual C++](how-to-report-a-problem-with-the-visual-cpp-toolset.md)<br/>
Aprenda a criar relatórios de erro eficazes sobre o conjunto de ferramentas do Visual C++ (compilador, vinculador e outras ferramentas) e as maneiras de enviar o relatório.

[Blog da Equipe do Visual C++](http://blogs.msdn.com/b/vcblog/)<br/>
Saiba mais sobre os novos recursos e as informações mais recentes dos desenvolvedores do [!INCLUDE[vcprvc](build/includes/vcprvc_md.md)].

[Comunidade de Desenvolvedores do Visual Studio](https://developercommunity.visualstudio.com/)<br/>
Saiba como obter ajuda, arquivar bugs e fazer sugestões para o Visual Studio.

## <a name="see-also"></a>Consulte também

- [Referência da linguagem C](c-language/c-language-reference.md)
- [Referência da biblioteca em tempo de execução C](c-runtime-library/c-run-time-library-reference.md)
- [Intrínsecos do compilador e linguagem assembly](intrinsics/compiler-intrinsics-and-assembly-language.md)
