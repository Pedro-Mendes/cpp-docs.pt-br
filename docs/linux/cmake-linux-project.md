---
title: Configurar um projeto do Linux CMake no Visual Studio | Microsoft Docs
description: Como configurar um projeto do Linux CMake no Visual Studio
ms.custom: ''
ms.date: 07/20/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-linux
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: f8707b32-f90d-494d-ae0b-1d44425fdc25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 88f5ef5379d597a81456dab7f3dd28a73a4df84b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46394914"
---
# <a name="configure-a-linux-cmake-project"></a>Configurar um projeto do Linux CMake

**Visual Studio 2017 versão 15.4 e posteriores.**<br/>
Quando você instala a carga de trabalho Linux C++ para Visual Studio, o suporte do CMake para o Linux é selecionado por padrão. Agora, isso permite que você trabalhe em sua base de código existente que usa CMake sem precisar convertê-la em um projeto do Visual Studio. Se sua base de código for de multiplaforma, você poderá direcioná-la ao Windows e ao Linux de dentro do Visual Studio.

Este tópico pressupõe que você tenha uma familiaridade básica com o suporte ao CMake no Visual Studio. Para saber mais, veja [Ferramentas do CMake no Visual C++](../ide/cmake-tools-for-visual-cpp.md). Para obter mais informações sobre o próprio CMake, consulte [Compilar, testar e empacotar seu software com o CMake](https://cmake.org/).

> [!NOTE]  
> O suporte ao CMake no Visual Studio requer o suporte do modo de servidor que foi apresentado no CMake 3.8. Para uma variante do CMake fornecida pela Microsoft compatível com o painel [Exibição de Destinos do CMake](https://blogs.msdn.microsoft.com/vcblog/2018/04/09/cmake-support-in-visual-studio-targets-view-single-file-compilation-and-cache-generation-settings/) no Visual Studio, baixe os binários pré-criados mais recentes em [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases). Se o gerenciador de pacotes fornecer uma versão mais antiga que o CMake 3.8, uma solução alternativa será [criar o CMake da fonte](#build-a-supported-cmake-release-from-source), usar o CMake padrão ou baixá-lo da [página de download do CMake](https://cmake.org/download/) oficial. 

## <a name="open-a-folder"></a>Abrir uma pasta

Para começar, escolha **Arquivo** > **Abrir** > **Pasta** no menu principal ou digite `devenv.exe <foldername>` na linha de comando. A pasta que você abrir deverá conter um arquivo CMakeLists.txt, junto com o código-fonte.
O exemplo a seguir mostra um arquivo CMakeLists.txt simples e o arquivo .cpp:

```cpp
// hello.cpp

#include <iostream>

int main(int argc, char* argv[])
{
    std::cout << "Hello from Linux CMake" << std::endl;
}
```

CMakeLists.txt:

```cmd
project (hello-cmake)
add_executable(hello-cmake hello.cpp)
```

## <a name="choose-a-linux-target"></a>Escolha um destino do Linux

Assim que você abre a pasta, o Visual Studio analisa o arquivo CMakeLists.txt e especifica um destino do Windows de **x86-Debug**. Para direcionar ao Linux, altere as configurações de projeto para **Linux-Debug** ou **Linux-Release**.

Por padrão, o Visual Studio escolhe o primeiro sistema remoto na lista em **Ferramentas** > **Opções** > **Plataforma Cruzada** > **Gerenciador de Conexões**. Se nenhuma conexão remota for encontrada, será solicitado que você crie uma.

Depois de especificar um destino de Linux, sua origem será copiada para o computador Linux. Em seguida, o CMake é executado no computador Linux para gerar o cache de CMake para o projeto.

![Gerar o cache de CMake no Linux](media/cmake-linux-1.png "Gerar o cache de CMake no Linux")

**Visual Studio 2017 versão 15.7 e posteriores:**<br/>
Para oferecer suporte ao IntelliSense para cabeçalhos remotos, o Visual Studio os copia automaticamente para um diretório no seu computador Windows local. Para obter mais informações, veja [IntelliSense para cabeçalhos remotos](configure-a-linux-project.md#remote_intellisense).

## <a name="debug-the-project"></a>Depurar o projeto

Para depurar seu código no sistema remoto, defina um ponto de interrupção, selecione o destino do CMake como o item de inicialização no menu da barra de ferramentas ao lado da configuração do projeto e escolha **&#x23f5; Iniciar** na barra de ferramentas ou pressione F5.

Para personalizar os argumentos de linha de comando do programa, clique com o botão direito do mouse no executável no **Gerenciador de Soluções** e selecione **Configurações de Depuração e de Inicialização**. Isso abre ou cria um arquivo de configuração launch.vs.json que contém as informações do seu programa. Para especificar argumentos adicionais, adicione-os na matriz JSON `args`. Para saber mais, veja [Projetos Abrir Pasta no Visual C++](https://docs.microsoft.com/en-us/cpp/ide/non-msbuild-projects).

## <a name="configure-cmake-settings-for-linux"></a>Definir as configurações do CMake para Linux

Para alterar as configurações de CMake padrão, escolha **CMake | Alterar as configurações de CMake | CMakeLists.txt** no menu principal ou clique com o botão direito do mouse em CMakeSettings.txt em **Gerenciador de Soluções** e escolha **Alterar as configurações de CMake**. Em seguida, o Visual Studio cria um novo arquivo na pasta chamada `CMakeSettings.json` que é populada com as configurações padrão que são listadas no item de menu de configurações do projeto. O exemplo a seguir mostra a configuração padrão para Linux-Debug com base no exemplo de código anterior:

```json
{
      "name": "Linux-Debug",
      "generator": "Unix Makefiles",
      "remoteMachineName": "${defaultRemoteMachineName}",
      "configurationType": "Debug",
      "remoteCMakeListsRoot": "/var/tmp/src/${workspaceHash}/${name}",
      "cmakeExecutable": "/usr/local/bin/cmake",
      "buildRoot": "${env.LOCALAPPDATA}\\CMakeBuilds\\${workspaceHash}\\build\\${name}",
      "installRoot": "${env.LOCALAPPDATA}\\CMakeBuilds\\${workspaceHash}\\install\\${name}",
      "remoteBuildRoot": "/var/tmp/build/${workspaceHash}/build/${name}",
      "remoteInstallRoot": "/var/tmp/build/${workspaceHash}/install/${name}",
      "remoteCopySources": true,
      "remoteCopySourcesOutputVerbosity": "Normal",
      "remoteCopySourcesConcurrentCopies": "10",
      "remoteCopySourcesMethod": "rsync",
      "remoteCopySourcesExclusionList": [".vs", ".git"],
      "rsyncCommandArgs" : "-t --delete --delete-excluded",
      "remoteCopyBuildOutput" : "false",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "",
      "ctestCommandArgs": "",
      "inheritEnvironments": [ "linux-x64" ]
}
```

O valor `name` pode ser o que você desejar. O valor `remoteMachineName` especifica qual sistema remoto deve ser o destino, caso você tenha mais de um. O IntelliSense está habilitado para este campo para ajudá-lo a selecionar o sistema certo. O campo `remoteCMakeListsRoot` especifica para onde as fontes do projeto serão copiadas no sistema remoto. O campo `remoteBuildRoot` é onde a saída de build será gerada no sistema remoto. Essa saída também é copiada localmente para o local especificado por `buildRoot`. Os campos `remoteInstallRoot` e `installRoot` são semelhantes a `remoteBuildRoot` e `buildRoot`, exceto que eles se aplicam quando uma instalação do cmake é realizada. A entrada `remoteCopySources` controla se suas fontes locais são copiadas para o computador remoto. Defina essa opção como false se houver vários arquivos e você já estiver sincronizando as fontes por conta própria. O valor de `remoteCopyOutputVerbosity` controla o nível de detalhes da etapa de cópia, caso seja necessário diagnosticar erros. A entrada `remoteCopySourcesConcurrentCopies` controla quantos processos são gerados para fazer a cópia. O valor de `remoteCopySourcesMethod` pode ser rsync ou sftp. O campo `remoteCopySourcesExclusionList` permite que você controle o que é copiado para o computador remoto. O valor de `rsyncCommandArgs` permite que você controle o método rsync de cópia. O campo `remoteCopyBuildOutput` controla se a saída do build remoto é copiada para a pasta de build local.

Também há algumas configurações opcionais que você pode usar para obter mais controle:

```json
{
      "remotePreBuildCommand": "",
      "remotePreGenerateCommand": "",
      "remotePostBuildCommand": "",
}
```

Essas opções permitem que você execute comandos na caixa remota antes e depois do build e antes da geração do CMake. Elas podem ser qualquer comando válido na caixa remota. A saída é canalizada para o Visual Studio.

## <a name="build-a-supported-cmake-release-from-source"></a>Compilar uma versão do CMake com suporte da origem

A versão mínima do CMake requerida no seu computador Linux é 3.8 e ele também deve dar suporte ao modo de servidor. Para verificar isso, execute este comando:

```cmd
cmake --version
```

Para verificar se o modo de servidor está habilitado, execute:

```cmd
cmake -E capabilities
```

Na saída, procure por **"serverMode":true**. Observe que mesmo ao compilar CMake da fonte conforme descrito abaixo, você deverá verificar os recursos quando terminar. Seu sistema Linux pode ter limitações que impedem que o modo de servidor seja habilitado.

Para começar a compilar o CMake da fonte no shell para seu sistema Linux, verifique se o gerenciador de pacotes está atualizado e se o git e o cmake estão disponíveis.

Primeiro, clone as fontes do CMake do [repositório Microsoft CMake](https://github.com/Microsoft/CMake), onde mantemos um fork para suporte de CMake do Visual Studio:

```cmd
sudo apt-get update
sudo apt-get install -y git cmake
git clone https://github.com/Microsoft/CMake.git
cd CMake
```

Em seguida, compile e instale a versão atual do CMake em /usr/local/bin executando estes comandos:

```cmd
mkdir out
cd out
cmake ../
make
sudo make install
```

Depois, execute este comando para verificar se a versão é igual ou superior à 3.8 e se esse modo de servidor está habilitado:

```cmd
/usr/local/bin/cmake –version
cmake -E capabilities
```

## <a name="see-also"></a>Consulte também

[Trabalhando com Propriedades do Projeto](../ide/working-with-project-properties.md)<br/>
[Ferramentas CMake para Visual C++](../ide/cmake-tools-for-visual-cpp.md)  
