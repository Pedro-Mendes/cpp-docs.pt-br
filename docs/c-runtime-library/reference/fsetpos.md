---
title: "fsetpos | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fsetpos"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "fsetpos"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "streams, setting position indicators"
  - "fsetpos function"
ms.assetid: 6d19ff48-1a2b-47b3-9f23-ed0a47b5a46e
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# <a name="fsetpos"></a>fsetpos
Define o indicador de posição do fluxo.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
int fsetpos(   
   FILE *stream,  
   const fpos_t *pos   
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `stream`  
 Ponteiro para a estrutura `FILE`.  
  
 `pos`  
 Armazenamento do indicador de posição.  
  
## <a name="return-value"></a>Valor de retorno  
 Se tiver êxito, `fsetpos` retornará 0. Em caso de falha, a função retorna um valor diferente de zero e define `errno` para uma das seguintes constantes de manifesto (definidas em ERRNO.H): `EBADF`, o que significa que o arquivo não está acessível ou o objeto para o qual `stream` aponta não é uma estrutura de arquivo válido; ou `EINVAL`, que significa que foi passado um valor inválido para `stream` ou `pos`. Se um parâmetro inválido for passado, essas funções invocarão o manipulador de parâmetro inválido, conforme descrito em [Validação de parâmetro](../../c-runtime-library/parameter-validation.md).  
  
 Consulte [_doserrno, errno, _sys_errlist e _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) para obter mais informações sobre esses e outros códigos de retorno.  
  
## <a name="remarks"></a>Comentários  
 A função `fsetpos` define o indicador de posição do arquivo para `stream` como o valor de `pos`*,* que é obtido em uma chamada anterior a `fgetpos` para `stream` *.* A função limpa o indicador de fim do arquivo e desfaz os efeitos de [ungetc](../../c-runtime-library/reference/ungetc-ungetwc.md) em `stream`*.* Depois de chamar `fsetpos`, a operação seguinte em `stream` pode ser de entrada ou saída.  
  
## <a name="requirements"></a>Requisitos  
  
|Função|Cabeçalho necessário|  
|--------------|---------------------|  
|`fsetpos`|\<stdio.h>|  
  
 Para obter mais informações sobre compatibilidade, consulte [Compatibilidade](../../c-runtime-library/compatibility.md) na Introdução.  
  
## <a name="example"></a>Exemplo  
 Veja o exemplo de [fgetpos](../../c-runtime-library/reference/fgetpos.md).  
  
## <a name="net-framework-equivalent"></a>Equivalente ao .NET Framework  
 [System::IO::FileStream::Position](https://msdn.microsoft.com/en-us/library/system.io.filestream.position.aspx)  
  
## <a name="see-also"></a>Consulte também  
 [E/S de fluxo](../../c-runtime-library/stream-i-o.md)   
 [fgetpos](../../c-runtime-library/reference/fgetpos.md)