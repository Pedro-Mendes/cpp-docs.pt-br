---
title: UUID (atributos C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.uuid
dev_langs:
- C++
helpviewer_keywords:
- uuid attribute
ms.assetid: 90562a94-5e28-451b-a4b0-cadda7f66efe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 37e5db99d97bc65f1f4a75e2e56e1f0e719dd9ab
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427167"
---
# <a name="uuid-c-attributes"></a>uuid (atributos C++)

Especifica a ID exclusiva para uma classe ou interface.

## <a name="syntax"></a>Sintaxe

```cpp
[ uuid(
   "uuid"
) ]
```

### <a name="parameters"></a>Parâmetros

*uuid*<br/>
Um identificador exclusivo, de 128 bits.

## <a name="remarks"></a>Comentários

Se a definição de uma interface ou classe não especifica o **uuid** atributo C++ e, em seguida, o compilador do Visual C++ fornece um. Quando você especifica um **uuid**, você deve incluir as aspas.

Se você não especificar **uuid**, em seguida, o compilador gerará o mesmo GUID para interfaces ou classes com o mesmo nome em projetos de atributo diferente em um computador.

Você pode usar Uuidgen.exe ou Guidgen.exe para gerar seus próprio IDs exclusivas. (Para executar qualquer uma dessas ferramentas, clique em **inicie** e clique em **executar** no menu. Em seguida, insira o nome da ferramenta necessária.)

Quando usado em um projeto que não usa ATL também, especificando o **uuid** atributo é o mesmo que especificar o [uuid](../cpp/uuid-cpp.md) **declspec** modificador. Para recuperar o **uuid** de uma classe, você pode usar [uuidof](../cpp/uuidof-operator.md)

## <a name="example"></a>Exemplo

Consulte a [associável](../windows/bindable.md) exemplo para uso do exemplo **uuid**.

## <a name="requirements"></a>Requisitos

### <a name="attribute-context"></a>Atributo de contexto

|||
|-|-|
|**Aplica-se a**|**classe**, **struct**, **interface**, **união**, **enum**|
|**Repetível**|Não|
|**Atributos obrigatórios**|Nenhum|
|**Atributos inválidos**|Nenhum|

Para obter mais informações sobre os contextos de atributo, consulte [contextos de atributo](../windows/attribute-contexts.md).

## <a name="see-also"></a>Consulte também

[Atributos de IDL](../windows/idl-attributes.md)<br/>
[Atributos de interface](../windows/interface-attributes.md)<br/>
[Atributos de classe](../windows/class-attributes.md)<br/>
[Atributos Typedef, Enum, Union e Struct](../windows/typedef-enum-union-and-struct-attributes.md)<br/>
[uuid](/windows/desktop/Midl/uuid)  