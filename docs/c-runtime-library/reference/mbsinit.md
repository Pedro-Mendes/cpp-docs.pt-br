---
title: mbsinit | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- mbsinit
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- mbsinit
dev_langs:
- C++
helpviewer_keywords:
- mbsinit function
ms.assetid: 4618555b-baaa-4d04-93fa-36abae411034
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 5ee8d0460a0d8b3bfa34de9c4ce7487cfd071d12
ms.lasthandoff: 02/25/2017

---
# <a name="mbsinit"></a>mbsinit
Controla o estado de uma conversão de caracteres de vários bytes.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
      int mbsinit(  
   const mbstate_t* ps  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `ps`  
 Um ponteiro para uma variável [mbstate_t](../../c-runtime-library/standard-types.md).  
  
## <a name="return-value"></a>Valor de retorno  
 Diferente de zero se `ps` for NULL ou se não estiver no meio de uma conversão.  
  
## <a name="remarks"></a>Comentários  
 Ao usar uma das funções ANSI que usa um ponteiro **mbstate_t**, passar o endereço do seu `mbstate_t` retornará informações sobre se o último byte no buffer foi convertido.  
  
 A página de código apropriada deve ser instalada para dar suporte aos caracteres multibyte.  
  
## <a name="example"></a>Exemplo  
  
```  
// crt_mbsinit.cpp  
#include <stdio.h>  
#include <mbctype.h>  
#include <string.h>  
#include <locale.h>  
#include <cwchar>  
#include <xlocinfo.h>  
  
#define   BUF_SIZE   0x40  
  
wchar_t      g_wcBuf[BUF_SIZE] = L"This a wc buffer that will be over written...";  
char      g_mbBuf[BUF_SIZE] = "AaBbCc\x9A\x8B\xE0\xEF\xF0xXyYzZ";  
int      g_nInit = strlen(g_mbBuf);  
  
int MbsinitSample(char* szIn, wchar_t* wcOut, int nMax)  
{  
   mbstate_t   state = {0};  
   size_t      nConvResult, nmbLen = 0, nwcLen = 0;  
   wchar_t*   wcCur = wcOut;  
   wchar_t*   wcEnd = wcCur + nMax;  
   const char*   mbCur = szIn;  
   const char*   mbEnd = mbCur + strlen(mbCur) + 1;  
   char*      szLocal = setlocale(LC_ALL, "japanese");  
  
   printf("Locale set to: \"%s\"\n", szLocal);  
  
   if   (_setmbcp(_MB_CP_LOCALE) != -1)  
   {  
      while   ((mbCur < mbEnd) && (wcCur < wcEnd))  
      {  
         nConvResult = mbrtowc(wcCur, mbCur, 1, &state);   
  
         switch   (nConvResult)  
         {  
            case 0:  
            {   // done  
               printf("Conversion succeeded!\nMB String: ");  
               printf(szIn);  
               printf("\nWC String: ");  
               wprintf(wcOut);  
               printf("\n");  
               mbCur = mbEnd;  
               break;  
            }  
  
            case -1:  
            {   // encoding error  
               printf("ERROR: The call to mbrtowc has detected an encoding error.\n");  
               mbCur = mbEnd;  
               break;  
            }  
  
            case -2:  
            {   // incomplete character  
               if   (!mbsinit(&state))  
               {  
                  printf("Currently in middle of mb conversion, state = %x\n", state);  
                  // state will contain data regarding lead byte of mb character  
               }  
  
               ++nmbLen;  
               ++mbCur;  
               break;  
            }  
  
            default:  
            {  
               if   (nConvResult > 2)   // Microsoft mb should never be larger than 2  
                  printf("ERROR: nConvResult = %d\n", nConvResult);  
  
               ++nmbLen;  
               ++nwcLen;  
               ++wcCur;  
               ++mbCur;  
               break;  
            }  
         }  
      }  
   }  
   else  
      printf("ERROR: _setmbcp(932) failed!");  
  
   return 0;  
}  
  
int main(int argc, char* argv[])  
{  
   return MbsinitSample(g_mbBuf, g_wcBuf, BUF_SIZE);  
}  
```  
  
## <a name="sample-output"></a>Saída de Exemplo  
  
```  
Locale set to: "Japanese_Japan.932"  
Currently in middle of mb conversion, state = 9a  
Currently in middle of mb conversion, state = e0  
Currently in middle of mb conversion, state = f0  
Conversion succeeded!  
MB String: AaBbCcxXyYzZ  
WC String: AaBbCcxXyYzZ  
```  
  
## <a name="see-also"></a>Consulte também  
 [Classificação de byte](../../c-runtime-library/byte-classification.md)