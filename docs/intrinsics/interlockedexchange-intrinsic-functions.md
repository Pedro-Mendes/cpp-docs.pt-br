---
title: "Fun&#231;&#245;es intr&#237;nsecas _InterlockedExchange | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_InterlockedExchange_rel"
  - "_InterlockedExchange8_nf"
  - "_InterlockedExchange_acq_cpp"
  - "_InterlockedExchange_nf"
  - "_InterlockedExchange64_nf"
  - "_InterlockedExchange_HLEAcquire"
  - "_InterlockedExchange_cpp"
  - "_InterlockedExchange64_acq_cpp"
  - "_InterlockedExchange64_acq"
  - "_InterlockedExchange64_HLERelease"
  - "_InterlockedExchange8_acq"
  - "_InterlockedExchange16_acq"
  - "_InterlockedExchange"
  - "_InterlockedExchange64_HLEAcquire"
  - "_InterlockedExchange8"
  - "_InterlockedExchange64_rel"
  - "_InterlockedExchange_acq"
  - "_InterlockedExchange16"
  - "_InterlockedExchange16_rel"
  - "_InterlockedExchange16_nf"
  - "_InterlockedExchange64"
  - "_InterlockedExchange_HLERelease"
  - "_InterlockedExchange64_cpp"
  - "_InterlockedExchange8_rel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_InterlockedExchange intrínseco"
  - "_InterlockedExchange_acq intrínseco"
  - "_InterlockedExchange16"
  - "_InterlockedExchange16_acq"
  - "_InterlockedExchange16_nf"
  - "_InterlockedExchange16_rel"
  - "_InterlockedExchange64 intrínseco"
  - "_InterlockedExchange64_acq intrínseco"
  - "_InterlockedExchange8"
  - "_InterlockedExchange8_acq"
  - "_InterlockedExchange8_nf"
  - "_InterlockedExchange8_rel"
  - "InterlockedExchange intrínseco"
  - "InterlockedExchange_acq intrínseco"
  - "InterlockedExchange64 intrínseco"
  - "InterlockedExchange64_acq intrínseco"
ms.assetid: be2f232a-6301-462a-a92b-fcdeb8b0f209
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Fun&#231;&#245;es intr&#237;nsecas _InterlockedExchange
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Específico da Microsoft**  
  
 Gera uma instrução atômica para definir um valor especificado.  
  
## Sintaxe  
  
```  
long _InterlockedExchange(  
   long volatile * Target,  
   long Value  
);  
long _InterlockedExchange_acq(  
   long volatile * Target,  
   long Value  
);  
long _InterlockedExchange_HLEAcquire(  
   long volatile * Target,  
   long Value  
);  
long _InterlockedExchange_HLERelease(  
   long volatile * Target,  
   long Value  
);  
long _InterlockedExchange_nf(  
   long volatile * Target,  
   long Value  
);  
long _InterlockedExchange_rel(  
   long volatile * Target,  
   long Value  
);  
char _InterlockedExchange8(  
   char volatile * Target,  
   char Value  
);  
char _InterlockedExchange8_acq(  
   char volatile * Target,  
   char Value  
);  
char _InterlockedExchange8_nf(  
   char volatile * Target,  
   char Value  
);  
char _InterlockedExchange8_rel(  
   char volatile * Target,  
   char Value  
);  
short _InterlockedExchange16(  
   short volatile * Target,  
   short Value  
);  
short _InterlockedExchange16_acq(  
   short volatile * Target,  
   short Value  
);  
short _InterlockedExchange16_nf(  
   short volatile * Target,  
   short Value  
);  
short _InterlockedExchange16_rel(  
   short volatile * Target,  
   short Value  
);  
__int64 _InterlockedExchange64(  
   __int64 volatile * Target,  
   __int64 Value  
);  
__int64 _InterlockedExchange64_acq(  
   __int64 volatile * Target,  
   __int64 Value  
);  
__int64 _InterlockedExchange64_HLEAcquire(  
   __int64 volatile * Target,  
   __int64 Value  
);  
__int64 _InterlockedExchange64_HLERelease(  
   __int64 volatile * Target,  
   __int64 Value  
);  
__int64 _InterlockedExchange64_nf(  
   __int64 volatile * Target,  
   __int64 Value  
);  
__int64 _InterlockedExchange64_rel(  
   __int64 volatile * Target,  
   __int64 Value  
);  
```  
  
#### Parâmetros  
 \[in, out\] `Target`  
 Ponteiro para o valor a ser trocado.  A função define essa variável como `Value` e retorna seu valor anterior.  
  
 \[in\] `Value`  
 Valor a ser trocado pelo valor apontado pelo `Target`.  
  
## Valor de retorno  
 Retorna o valor inicial apontado por `Target`.  
  
## Requisitos  
  
|Intrínseco|Arquitetura|Cabeçalho|  
|----------------|-----------------|---------------|  
|`_InterlockedExchange`, `_InterlockedExchange8`, `_InterlockedExchange16`, `_InterlockedExchange64`|x86, ARM, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\<intrin.h\>|  
|`_InterlockedExchange_acq`, `_InterlockedExchange_nf`, `_InterlockedExchange_rel`, `_InterlockedExchange8_acq`, `_InterlockedExchange8_nf`, `_InterlockedExchange8_rel`, `_InterlockedExchange16_acq`, `_InterlockedExchange16_nf`, `_InterlockedExchange16_rel`, `_InterlockedExchange64_acq`, `_InterlockedExchange64_nf`, `_InterlockedExchange64_rel`,|ARM|\<intrin.h\>|  
|`_InterlockedExchange_HLEAcquire`, `_InterlockedExchange_HLERelease`, `_InterlockedExchange64_HLEAcquire`, `_InterlockedExchange64_HLERelease`|x86, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\<immintrin.h\>|  
  
## Comentários  
 `_InterlockedExchange` fornece suporte intrínsecos do compilador para o Win32 [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] [InterlockedExchange](http://msdn.microsoft.com/library/ms683590.aspx) função.  
  
 Há diversas variações em `_InterlockedExchange` que têm base no tipo de dados que envolvem e se a semântica acquire ou release é usada.  
  
 Enquanto a função `_InterlockedExchange` opera em valores inteiros de 32 bits, `_InterlockedExchange8` opera em valores inteiros de 8 bits, `_InterlockedExchange16` opera em valores inteiros de 16 bits e `_InterlockedExchange64` opera em valores inteiros de 64 bits.  
  
 Em plataformas ARM, use intrínsecos com os sufixos `_acq` e `_rel` para semântica de aquisição e liberação, como no início e no final de uma seção crítica.  Os intrínsecos com um sufixo `_nf` \("no fence"\) não funcionam como uma barreira de memória.  
  
 Em plataformas Intel que suportam instruções HLE \(Elisão de Bloqueio de Hardware\), intrínsecos com os sufixos `_HLEAcquire` e `_HLERelease` incluem uma dica para o processador que pode acelerar o desempenho, eliminando uma etapa de gravação de bloqueio no hardware.  Se esses intrínsecos forem chamados em plataformas que não dão suporte a HLE, a dica será ignorada.  
  
 Essas rotinas somente estão disponíveis como intrínsecos.  
  
## Exemplo  
 Para obter um exemplo de como usar `_InterlockedExchange`, consulte [\_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md).  
  
## FIM de Específico da Microsoft  
  
## Consulte também  
 [Intrínsecos do compilador](../intrinsics/compiler-intrinsics.md)   
 [Palavras\-chave C\+\+](../cpp/keywords-cpp.md)   
 [Conflitos com o compilador x86](../Topic/Conflicts%20with%20the%20x86%20Compiler.md)