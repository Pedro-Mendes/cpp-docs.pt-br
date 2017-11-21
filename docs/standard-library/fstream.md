---
title: '&lt;fstream&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: <fstream>
dev_langs: C++
helpviewer_keywords: fstream header
ms.assetid: 660de351-0489-41df-b239-40e0cdcab46b
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dc68979d4dc4b79a2b1e6e987f51bebc6d15aa3b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="ltfstreamgt"></a>&lt;fstream&gt;
Define várias classes que dão suporte a operações de iostreams em sequências armazenadas em arquivos externos.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
#include <fstream>  
  
```  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[filebuf](../standard-library/fstream-typedefs.md#filebuf)|Um tipo `basic_filebuf` especializado em parâmetros de modelo `char`.|  
|[fstream](../standard-library/fstream-typedefs.md#fstream)|Um tipo `basic_fstream` especializado em parâmetros de modelo `char`.|  
|[ifstream](../standard-library/fstream-typedefs.md#ifstream)|Um tipo `basic_ifstream` especializado em parâmetros de modelo `char`.|  
|[ofstream](../standard-library/fstream-typedefs.md#ofstream)|Um tipo `basic_ofstream` especializado em parâmetros de modelo `char`.|  
|[wfstream](../standard-library/fstream-typedefs.md#wfstream)|Um tipo `basic_fstream` especializado em parâmetros de modelo `wchar_t`.|  
|[wifstream](../standard-library/fstream-typedefs.md#wifstream)|Um tipo `basic_ifstream` especializado em parâmetros de modelo `wchar_t`.|  
|[wofstream](../standard-library/fstream-typedefs.md#wofstream)|Um tipo `basic_ofstream` especializado em parâmetros de modelo `wchar_t`.|  
|[wfilebuf](../standard-library/fstream-typedefs.md#wfilebuf)|Um tipo `basic_filebuf` especializado em parâmetros de modelo `wchar_t`.|  
  
### <a name="classes"></a>Classes  
  
|||  
|-|-|  
|[basic_filebuf](../standard-library/basic-filebuf-class.md)|A classe de modelo descreve um buffer de fluxo que controla a transmissão de elementos do tipo **Elem**, cujas características dos caracteres são determinadas pela classe **Tr**, para e de uma sequência de elementos armazenados em um arquivo externo.|  
|[basic_fstream](../standard-library/basic-fstream-class.md)|A classe de modelo descreve um objeto que controla a inserção e a extração de elementos e objetos codificados usando um buffer de fluxo da classe [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**>, com elementos do tipo **Elem** cujas características dos caracteres são determinadas pela classe **Tr**.|  
|[basic_ifstream](../standard-library/basic-ifstream-class.md)|A classe de modelo descreve um objeto que controla a extração de elementos e objetos codificados de um buffer de fluxo da classe [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**>, com elementos do tipo **Elem** cujas características dos caracteres são determinadas pela classe **Tr**.|  
|[basic_ofstream](../standard-library/basic-ofstream-class.md)|A classe de modelo descreve um objeto que controla a inserção de elementos e objetos codificados em um buffer de fluxo da classe [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**>, com elementos do tipo **Elem** cujas características dos caracteres são determinadas pela classe **Tr**.|  
  
## <a name="see-also"></a>Consulte também  
 [Referência de Arquivos de Cabeçalho](../standard-library/cpp-standard-library-header-files.md)   
 [Acesso Thread-Safe na Biblioteca Padrão C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Programação de iostream](../standard-library/iostream-programming.md)   
 [Convenções de iostreams](../standard-library/iostreams-conventions.md)


