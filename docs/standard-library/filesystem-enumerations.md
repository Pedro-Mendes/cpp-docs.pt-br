---
title: "Enumerações de &lt;filesystem&gt; | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- copy_options
- filesystem::copy_options
- std::filesystem::copy_options
- filesystem/std::filesystem::copy_options
- experimental::filesystem::copy_options
- std::experimental::filesystem::copy_options
- filesystem/std::experimental::filesystem::copy_options
- directory_options
- filesystem::directory_options
- std::filesystem::directory_options
- filesystem/std::filesystem::directory_options
- experimental::filesystem::directory_options
- std::experimental::filesystem::directory_options
- filesystem/std::experimental::filesystem::directory_options
- file_type
- filesystem::file_type
- std::filesystem::file_type
- filesystem/std::filesystem::file_type
- experimental::filesystem::file_type
- std::experimental::filesystem::file_type
- filesystem/std::experimental::filesystem::file_type
- perms
- filesystem::perms
- std::filesystem::perms
- filesystem/std::filesystem::perms
- experimental::filesystem::perms
- std::experimental::filesystem::perms
- filesystem/std::experimental::filesystem::perms
ms.assetid: 0096c046-d101-464c-8259-b878a48280b0
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 85c900f2263ae1c1089478badc85388e3b5e8548
ms.openlocfilehash: d9f3bbe8cddea347e1663d8963c4496bcf8d7319
ms.lasthandoff: 02/25/2017

---
# <a name="ltfilesystemgt-enumerations"></a>Enumerações de &lt;filesystem&gt;
Este tópico documenta as enumerações no cabeçalho filesystem.

## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** \<experimental/filesystem>  
  
 **Namespace:** std::experimental::filesystem  

##  <a name="a-namefilesystemcopyoptionsa--copyoptions"></a><a name="filesystem__copy_options"></a>  copy_options
Uma enumeração de valores de bitmask que é usada com as funções [copy](http://msdn.microsoft.com/en-us/4af7a9b0-8861-45ed-b84e-0307f0669d60) e [copy_file](http://msdn.microsoft.com/en-us/4af7a9b0-8861-45ed-b84e-0307f0669d60) para especificar o comportamento.  
  
### <a name="syntax"></a>Sintaxe  
```cpp  
enum class copy_options {      
   none = 0,  
   skip_existing = 1,  
   overwrite_existing = 2,  
   update_existing = 4,  
   recursive = 8,  
   copy_symlinks = 16,  
   skip_symlinks = 32,  
   directories_only = 64,  
   create_symlinks = 128,  
   create_hard_links = 256  
};  
```  
  
### <a name="values"></a>Valores  
  
|`Name`|Descrição|  
|------------|-----------------|  
|`none`|Executa o comportamento padrão da operação.|  
|`skip_existing`|Não copia se o arquivo já existir, não relata um erro.|  
|`overwrite_existing`|Substitui o arquivo se ele já existir.|  
|`update_existing`|Substitui o arquivo se ele já existir e for mais antigo que a substituição.|  
|`recursive`|Copia recursivamente subdiretórios e seus conteúdos.|  
|`copy_symlinks`|Copia links simbólicos como links simbólicos, em vez de copiar os arquivos para os quais eles apontam.|  
|`skip_symlinks`|Ignora links simbólicos.|  
|`directories_only`|Iterar somente diretórios, ignora arquivos.|  
|`create_symlinks`|Faz links simbólicos em vez de copiar arquivos. Um caminho absoluto deve ser usado como o caminho de origem, a menos que o destino seja o diretório atual.|  
|`create_hard_links`|Faz links físicos em vez de copiar arquivos.|  
  

##  <a name="a-namefilesystemdirectoryoptionsa-directoryoptions"></a><a name="filesystem__directory_options"></a> directory_options
Especifica se links simbólicos para diretórios devem ser seguidos ou ignorados.  
  
### <a name="syntax"></a>Sintaxe  
```cpp  
enum class directory_options {  
   none = 0,  
   follow_directory_symlink 
};  
```  
  
### <a name="values"></a>Valores  
  
|Nome|Descrição|  
|----------|-----------------|  
|`none`|Comportamento padrão: ignorar links simbólicos para diretórios. A permissão negada é um erro.|  
|`follow_directory_symlink`|Tratar links simbólicos para diretórios como diretórios reais.|  
  
##  <a name="a-namefilesystemfiletypea--filetype"></a><a name="filesystem__file_type"></a>  file_type
Uma enumeração de tipos de arquivo. Os valores com suporte são regular, directory, not_found e unknown.  
  
### <a name="syntax"></a>Sintaxe  
```cpp  
enum class file_type {
    not_found = -1, 
    none, 
    regular, 
    directory, 
    symlink,
    block, 
    character, 
    fifo, 
    socket, 
    unknown
};  
```  
  
### <a name="values"></a>Valores  
  
|Nome|Valor|Descrição|  
|----------|-----------|-----------------|  
|`not_found`|-1|Representa um arquivo que não existe.|  
|`none`|0|Representa um arquivo que não tem um atributo de tipo. (Sem suporte.)|  
|`regular`|1|Representa um arquivo de disco convencional.|  
|`directory`|2|Representa um diretório.|  
|`symlink`|3|Representa um link simbólico. (Sem suporte.)|  
|`block`|4|Representa um arquivo especial de bloco em sistemas baseados em UNIX. (Sem suporte.)|  
|`character`|5|Representa um arquivo especial de caractere em sistemas baseados em UNIX. (Sem suporte.)|  
|`fifo`|6|Representa um arquivo PEPS em sistemas baseados em UNIX. (Sem suporte.)|  
|`socket`|7|Representa um soquete em sistemas baseados em UNIX. (Sem suporte.)|  
|`unknown`|8|Representa um arquivo cujo status não pode ser determinado.|  
  
##  <a name="a-namefilesystempermsa--perms"></a><a name="filesystem__perms"></a>  perms
Sinalizadores de permissões de arquivo. Os valores com suporte são, essencialmente, "readonly". Para um arquivo somente leitura, nenhum dos bits *_write é definido. Caso contrário, o bit `all` (0x0777) é definido.  
  
### <a name="syntax"></a>Sintaxe  
```cpp  
enum class perms {// names for permissions
   none = 0,
   owner_read = 0400,  // S_IRUSR
   owner_write = 0200, // S_IWUSR
   owner_exec = 0100,  // S_IXUSR
   owner_all = 0700,   // S_IRWXU
   group_read = 040,   // S_IRGRP
   group_write = 020,  // S_IWGRP
   group_exec = 010,   // S_IXGRP
   group_all = 070,    // S_IRWXG
   others_read = 04,   // S_IROTH
   others_write = 02,  // S_IWOTH
   others_exec = 01,   // S_IXOTH
   others_all = 07,    // S_IRWXO
   all = 0777,
   set_uid = 04000,    // S_ISUID
   set_gid = 02000,    // S_ISGID
   sticky_bit = 01000, // S_ISVTX
   mask = 07777,
   unknown = 0xFFFF,
   add_perms = 0x10000,
   remove_perms = 0x20000,
   resolve_symlinks = 0x40000
};  
```  
  
## <a name="see-also"></a>Consulte também  
 [Referência de Arquivos de Cabeçalho](../standard-library/cpp-standard-library-header-files.md)   
 [\<filesystem>](../standard-library/filesystem.md)

