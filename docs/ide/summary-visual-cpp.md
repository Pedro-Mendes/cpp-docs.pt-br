---
title: '&lt;summary&gt; (Visual C++) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- <summary>
- summary
dev_langs:
- C++
helpviewer_keywords:
- <summary> C++ XML tag
- summary C++ XML tag
ms.assetid: cdeeefbb-1339-45d6-9002-10042a9a2726
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f1a81bc910ca9d1682fa5093b4d3027b8090f585
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46397345"
---
# <a name="ltsummarygt-visual-c"></a>&lt;summary&gt; (Visual C++)

A marca \<summary> deve ser usada para descrever um tipo ou um membro de tipo. Use [\<remarks>](../ide/remarks-visual-cpp.md) para adicionar mais informações a uma descrição de tipo.

## <a name="syntax"></a>Sintaxe

```
<summary>description</summary>
```

#### <a name="parameters"></a>Parâmetros

*description*<br/>
Um resumo do objeto.

## <a name="remarks"></a>Comentários

O texto da marcação \<summary> é a única fonte de informações sobre o tipo no IntelliSense e também é exibido no [Pesquisador de Objetos](/visualstudio/ide/viewing-the-structure-of-code) e no relatório Web de comentários sobre código.

Compile com [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) para processar comentários de documentação em um arquivo.

## <a name="example"></a>Exemplo

```
// xml_summary_tag.cpp
// compile with: /LD /clr /doc
// post-build command: xdcmake xml_summary_tag.dll

/// Text for class MyClass.
public ref class MyClass {
public:
   /// <summary>MyMethod is a method in the MyClass class.
   /// <para>Here's how you could make a second paragraph in a description. <see cref="System::Console::WriteLine"/> for information about output statements.</para>
   /// <seealso cref="MyClass::MyMethod2"/>
   /// </summary>
   void MyMethod(int Int1) {}

   /// text
   void MyMethod2() {}
};
```

## <a name="see-also"></a>Consulte também

[Documentação XML](../ide/xml-documentation-visual-cpp.md)