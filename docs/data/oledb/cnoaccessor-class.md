---
title: Classe CNoAccessor | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CNoAccessor
- CNoAccessor
- ATL.CNoAccessor
dev_langs:
- C++
helpviewer_keywords:
- CNoAccessor class
ms.assetid: eb669ae5-0a56-49a3-9646-c4ae6239da31
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f383b79c8130501773c56db47c08b9449b259a62
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111427"
---
# <a name="cnoaccessor-class"></a>Classe CNoAccessor

Pode ser usado como um argumento de modelo (`TAccessor`) para classes de modelo, como `CCommand` e `CTable`, que exigem um argumento de classe de acessador.  
  
## <a name="syntax"></a>Sintaxe

```cpp
class CNoAccessor  
```  
  
## <a name="remarks"></a>Comentários  

Use `CNoAccessor` como um argumento de modelo quando você não deseja que a classe para dar suporte a parâmetros ou colunas de saída.  
  
`CNoAccessor` implementa os seguintes métodos de stub, cada um dos quais correspondem aos outros métodos de classe de acessador:  
  
- `BindColumns` -Associa as colunas para acessadores.  
  
- `BindParameters` -Associa os parâmetros criados para colunas.  
  
- `Bind` -Cria associações.  
  
- `Close` -Fecha o acessador.  
  
- `ReleaseAccessors` -Libera os acessadores criados pela classe.  
  
- `FreeRecordMemory` -Libera quaisquer colunas no registro atual que precise ser liberada.  
  
- `GetColumnInfo` -Obtém informações de coluna do conjunto de linhas aberto.  
  
- `GetNumAccessors` -Recupera o número de acessadores criado pela classe.  
  
- `IsAutoAccessor` -Retorna true se os dados são recuperados do acessador automaticamente durante uma operação de movimentação.  
  
- `GetHAccessor` -Recupera o identificador do acessador de um acessador especificado.  
  
- `GetBuffer` -Recupera o ponteiro para o buffer de indicador.  
  
- `NoBindOnNullRowset` -Impede que a associação de dados em conjuntos de linhas vazios.  
  
## <a name="requirements"></a>Requisitos  

**Cabeçalho:** atldbcli.h  
  
## <a name="see-also"></a>Consulte também  

[Modelos de consumidor do OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Referência de modelos de consumidor do OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)