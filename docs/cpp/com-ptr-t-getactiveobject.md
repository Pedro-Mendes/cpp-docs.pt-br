---
title: _com_ptr_t::GetActiveObject | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_ptr_t::GetActiveObject
dev_langs: C++
helpviewer_keywords: GetActiveObject method [C++]
ms.assetid: 2fa94853-0410-4620-91f2-136dae923f9f
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 153f7ffce400fd09e46706a361eebc87bbe1e1c3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="comptrtgetactiveobject"></a>_com_ptr_t::GetActiveObject
**Seção específica da Microsoft**  
  
 Anexa a uma instância existente de um objeto, considerando um **CLSID** ou **ProgID**.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
      HRESULT GetActiveObject(  
   const CLSID& rclsid   
) throw( );  
HRESULT GetActiveObject(  
   LPCWSTR clsidString   
) throw( );  
HRESULT GetActiveObject(  
   LPCSTR clsidStringA   
) throw( );  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `rclsid`  
 O **CLSID** de um objeto.  
  
 `clsidString`  
 Uma cadeia de caracteres Unicode que contém a um **CLSID** (começando com "**{**") ou um **ProgID**.  
  
 `clsidStringA`  
 Uma cadeia de caracteres multibyte, usando a página de código ANSI, que contém o um **CLSID** (começando com "**{**") ou um **ProgID**.  
  
## <a name="remarks"></a>Comentários  
 Essas funções de membro chamam `GetActiveObject` para recuperar um ponteiro para um objeto em execução que foi registrado com OLE e depois consulta o tipo de interface desse ponteiro inteligente. O ponteiro resultante é encapsulado nesse objeto `_com_ptr_t`. **Versão** é chamado para diminuir a contagem de referência para o ponteiro anteriormente encapsulado. Essa rotina retorna `HRESULT` para indicar êxito ou falha.  
  
-   **GetActiveObject (**`rclsid`**)** anexa a uma instância existente de um objeto, considerando um **CLSID**.  
  
-   **GetActiveObject (**`clsidString`**)** anexa a uma instância existente de um objeto, considerando uma cadeia de caracteres Unicode que contém a um **CLSID** (começando com "**{**") ou um **ProgID**.  
  
-   **GetActiveObject (**`clsidStringA`**)** anexa a uma instância existente de um objeto, considerando uma cadeia de caracteres multibyte que mantém a um **CLSID** (começando com "**{**") ou um **ProgID**. Chamadas [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072), que assume que a cadeia de caracteres é a página de código ANSI em vez de uma página de código OEM.  
  
 **Fim da seção específica da Microsoft**  
  
## <a name="see-also"></a>Consulte também  
 [Classe _com_ptr_t](../cpp/com-ptr-t-class.md)