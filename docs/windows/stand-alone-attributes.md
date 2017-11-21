---
title: "Atributos autônomos | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- standalone attributes
- attributes [C++], standalone
ms.assetid: 0d72e84e-236c-43b3-ac9a-d9b91fcd6794
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 17009c1e9c1f7a771b717a96d1aadc4a680fe78f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="stand-alone-attributes"></a>Atributos autônomos
Um atributo autônomo não funcionam em uma palavra-chave C++, mas é mais parecida com uma linha de código. Declarações de atributo autônomo exigem um ponto e vírgula no final da linha.  
  
|Atributo|Descrição|  
|---------------|-----------------|  
|[cpp_quote](../windows/cpp-quote.md)|Emite a cadeia de caracteres especificada, sem o caractere de aspas, para o arquivo de cabeçalho gerado.|  
|[personalizado](../windows/custom-cpp.md)|Permite que você defina seu próprio atributo.|  
|[db_command](../windows/db-command.md)|Cria um comando OLE DB.|  
|[emitidl](../windows/emitidl.md)|Determina se todos os atributos IDL subsequentes serão processados e colocados no arquivo. idl gerado.|  
|[idl_module](../windows/idl-module.md)|Especifica um ponto de entrada em uma DLL.|  
|[idl_quote](../windows/idl-quote.md)|Permite que você use as construções de IDL não tem suporte na versão atual do Visual C++ e que eles passam para o arquivo. idl gerado.|  
|[import](../windows/import.md)|Especifica outro arquivo. idl, odl ou. h que contém as definições que você deseja fazer referência do arquivo. idl principal.|  
|[importidl](../windows/importidl.md)|Insere o arquivo. idl especificado no arquivo. idl gerado|  
|[importlib](../windows/importlib.md)|Torna os tipos que já foi compilados em outra biblioteca de tipo disponível para a biblioteca de tipos que está sendo criada.|  
|[include](../windows/include-cpp.md)|Especifica um ou mais arquivos de cabeçalho a ser incluído no arquivo. idl gerado.|  
|[includelib](../windows/includelib-cpp.md)|Faz com que um arquivo. IDL ou. h ser incluída no arquivo. idl gerado.|  
|[library_block](../windows/library-block.md)|Coloca uma construção dentro do bloco de biblioteca do arquivo. idl.|  
|[módulo](../windows/module-cpp.md)|Define o bloco de biblioteca no arquivo. idl.|  
|[no_injected_text](../windows/no-injected-text.md)|Impede que o compilador injeção de código como resultado do uso do atributo.|  
|[pragma](../windows/pragma.md)|Emite a cadeia de caracteres especificada, sem o caractere de aspas, no arquivo. idl gerado.|  
  
## <a name="see-also"></a>Consulte também  
 [Atributos por uso](../windows/attributes-by-usage.md)