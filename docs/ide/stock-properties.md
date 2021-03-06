---
title: Propriedades de estoque | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- stock properties, about stock properties
- stock properties
ms.assetid: a89fc454-0b8e-447a-9033-4c8af46a24d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4a9b2aa4389d693cfc6734a29f3a744e955ca3ea
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43213787"
---
# <a name="stock-properties"></a>Propriedades de estoque
Caso esteja adicionando uma propriedade a uma dispinterface MFC usando o [Assistente de Adição de Propriedade](../ide/idl-attributes-add-property-wizard.md), escolha uma propriedade de estoque na lista **Nome da propriedade** da página [Nomes](../ide/names-add-property-wizard.md) do assistente. Estas são as seguintes propriedades:  
  
|Property name|Descrição|  
|-------------------|-----------------|  
|**Appearance**|Retorna ou define um valor que determina a aparência do controle. A propriedade **Appearance** do controle pode incluir ou omitir efeitos de exibição tridimensionais. Essa é uma propriedade de leitura/gravação de ambiente.|  
|`BackColor`|Retorna ou define a propriedade `BackColor` de ambiente do controle para uma cor da paleta (RGB) ou uma cor predefinida do sistema. Por padrão, seu valor corresponde à cor de primeiro plano do contêiner do controle. Essa é uma propriedade de leitura/gravação de ambiente.|  
|`BorderStyle`|Retorna ou define o estilo da borda de um controle. Essa é uma propriedade de leitura/gravação.|  
|**Caption**|Retorna ou define a propriedade **Caption** do controle. A legenda é o título da janela. **Caption** não tem nenhum tipo de implementação **Variável de membro**.|  
|**Habilitado**|Retorna ou define a propriedade **Enabled** do controle. Um controle habilitado pode responder aos eventos gerados pelo usuário.|  
|**Fonte**|Retorna ou define a fonte de ambiente do controle. Nulo se o controle não tem nenhuma fonte.|  
|`ForeColor`|Retorna ou define a propriedade `ForeColor` de ambiente do controle.|  
|**hWnd**|Retorna ou define a propriedade **hWnd** do controle. **hWnd** não tem nenhum tipo de implementação **Variável de membro**.|  
|**ReadyState**|Retorna ou define a propriedade **ReadyState** do controle. Um controle pode estar nos seguintes estados: inicialização cancelada, inicializado, carregando, interativo ou completo. Confira [READYSTATE](https://msdn.microsoft.com/library/aa768362.aspx) no *SDK da Internet* para obter mais informações.|  
|**Texto**|Retorna ou define o texto contido em um controle. **Text** não tem nenhum tipo de implementação **Variável de membro**.|  
  
## <a name="see-also"></a>Consulte também  
 [Adicionando uma propriedade](../ide/adding-a-property-visual-cpp.md)   
 [Atributos IDL, Assistente para Adicionar Propriedade](../ide/idl-attributes-add-property-wizard.md)