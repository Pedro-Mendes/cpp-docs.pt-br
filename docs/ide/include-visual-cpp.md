---
title: '&lt;include&gt; (Visual C++) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- include
- <include>
dev_langs:
- C++
helpviewer_keywords:
- include C++ XML tag
- <include> C++ XML tag
ms.assetid: 392a3e61-0371-4617-8362-446650876ce3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 95a336319861ef44f65f0573389f09c3e9a45573
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425841"
---
# <a name="ltincludegt-visual-c"></a>&lt;include&gt; (Visual C++)

A marca \<include> permite consultar comentários em outro arquivo que descrevem os tipos e membros em seu código-fonte. Essa é uma alternativa para inserir comentários de documentação diretamente em seu arquivo de código-fonte.  Por exemplo, use \<include> para inserir comentários "clichê" padrão usados por toda a equipe ou empresa.

## <a name="syntax"></a>Sintaxe

```
<include file='filename' path='tagpath' />
```

#### <a name="parameters"></a>Parâmetros

*filename*<br/>
O nome do arquivo que contém a documentação. O nome do arquivo pode ser qualificado com um caminho.  Coloque o nome entre aspas simples ou duplas.  O compilador emite um aviso se não encontra `filename`.

*tagpath*<br/>
Uma expressão XPath válida que seleciona o conjunto de nós desejado contido no arquivo.

*name*<br/>
O especificador de nome na marca que precede os comentários; `name` terá um `id`.

*id*<br/>
A ID da marca que precede os comentários.  Coloque o nome entre aspas simples ou duplas.

## <a name="remarks"></a>Comentários

A marca \<include> usa a sintaxe XML XPath. Veja a documentação do XPath para descobrir outras formas de personalização usando \<include>.

Compile com [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) para processar comentários de documentação em um arquivo.

## <a name="example"></a>Exemplo

Este é um exemplo de vários arquivos. O primeiro arquivo, que usa \<include>, contém os seguintes comentários da documentação:

```cpp
// xml_include_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_include_tag.dll

/// <include file='xml_include_tag.doc' path='MyDocs/MyMembers[@name="test"]/*' />
public ref class Test {
   void TestMethod() {
   }
};

/// <include file='xml_include_tag.doc' path='MyDocs/MyMembers[@name="test2"]/*' />
public ref class Test2 {
   void Test() {
   }
};
```

O segundo arquivo, xml_include_tag.doc, contém os comentários de documentação a seguir:

```xml
<MyDocs>

<MyMembers name="test">
<summary>
The summary for this type.
</summary>
</MyMembers>

<MyMembers name="test2">
<summary>
The summary for this other type.
</summary>
</MyMembers>

</MyDocs>
```

## <a name="program-output"></a>Saída do Programa

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>t2</name>
    </assembly>
    <members>
        <member name="T:Test">
            <summary>
The summary for this type.
</summary>
        </member>
        <member name="T:Test2">
            <summary>
The summary for this other type.
</summary>
        </member>
    </members>
</doc>
```

## <a name="see-also"></a>Consulte também

[Documentação XML](../ide/xml-documentation-visual-cpp.md)