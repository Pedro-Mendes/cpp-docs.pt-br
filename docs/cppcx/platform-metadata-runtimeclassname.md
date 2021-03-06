---
title: Platform::Metadata::RuntimeClassName | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Metadata::RuntimeClassName
helpviewer_keywords:
- RuntimeClassName
- Platform::Metadata::RuntimeClassName
ms.assetid: fdef8f85-ab94-4edd-ba50-ee0da9358ff6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f7f81397be93de0080f2d6e8668d3cd5880ecc38
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44104048"
---
# <a name="platformmetadataruntimeclassname"></a>Platform::Metadata::RuntimeClassName

Quando aplicado a uma definição de classe, garante que uma classe privada retorne um nome válido da função GetRuntimeClassName.

## <a name="syntax"></a>Sintaxe

```cpp
[Platform::Metadata::RuntimeClassName] name
```

#### <a name="parameters"></a>Parâmetros

*name*<br/>
O nome de um tipo público existente que ainda é visível no Tempo de Execução do Windows.

### <a name="remarks"></a>Comentários

Use esse atributo em classes ref privadas para especificar um nome de tipo de tempo de execução personalizado e/ou quando o nome existente não atendem aos requisitos. Especifique como nome uma interface pública que a classe implementará.

### <a name="example"></a>Exemplo

O exemplo a seguir mostra como usar o atributo. Neste exemplo, o nome do tipo de tempo de execução de HellowWorldImpl é Test::Native::MyComponent::IHelloWorld

```cpp
namespace Test
{
    namespace Native
    {
        namespace MyComponent
        {
            public interface class IHelloWorld
            {
                Platform::String^ SayHello();
            };

            private ref class HelloWorldImpl sealed :[Platform::Metadata::RuntimeClassName] IHelloWorld
            {
            public:
                HelloWorldImpl();
                virtual Platform::String^ SayHello();
            };

            Platform::String^ HelloWorldImpl::SayHello()
            {
                return L"Hello World!";
            }
        }
    }
}
```

## <a name="see-also"></a>Consulte também

[Namespace Platform::Metadata](../cppcx/platform-metadata-namespace.md)