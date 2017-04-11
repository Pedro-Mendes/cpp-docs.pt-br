---
title: Classe CKeyboardManager | Documentos do Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager::CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager::CleanUp
- AFXKEYBOARDMANAGER/CKeyboardManager::FindDefaultAccelerator
- AFXKEYBOARDMANAGER/CKeyboardManager::IsKeyHandled
- AFXKEYBOARDMANAGER/CKeyboardManager::IsKeyPrintable
- AFXKEYBOARDMANAGER/CKeyboardManager::IsShowAllAccelerators
- AFXKEYBOARDMANAGER/CKeyboardManager::LoadState
- AFXKEYBOARDMANAGER/CKeyboardManager::ResetAll
- AFXKEYBOARDMANAGER/CKeyboardManager::SaveState
- AFXKEYBOARDMANAGER/CKeyboardManager::ShowAllAccelerators
- AFXKEYBOARDMANAGER/CKeyboardManager::TranslateCharToUpper
- AFXKEYBOARDMANAGER/CKeyboardManager::UpdateAccelTable
dev_langs:
- C++
helpviewer_keywords:
- CKeyboardManager class
ms.assetid: 4809ece6-89df-4479-8b53-9bf476ee107b
caps.latest.revision: 33
author: mikeblome
ms.author: mblome
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: bbe12d2bf4af0008233df25e09f09008c402ee7f
ms.lasthandoff: 02/25/2017

---
# <a name="ckeyboardmanager-class"></a>Classe CKeyboardManager
Gerencia as tabelas de chave de atalho para a janela do quadro principal e janelas de quadro filho.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
class CKeyboardManager : public CObject  
```  
  
## <a name="members"></a>Membros  
  
### <a name="public-constructors"></a>Construtores públicos  
  
|||  
|-|-|  
|Nome|Descrição|  
|[CKeyboardManager::CKeyboardManager](#ckeyboardmanager)|Constrói um objeto `CKeyboardManager`.|  
  
### <a name="public-methods"></a>Métodos Públicos  
  
|||  
|-|-|  
|Nome|Descrição|  
|[CKeyboardManager::CleanUp](#cleanup)|Limpa as tabelas de teclas de atalho.|  
|[CKeyboardManager::FindDefaultAccelerator](#finddefaultaccelerator)|Recupera a tecla de atalho para o comando especificado e a janela padrão.|  
|[CKeyboardManager::IsKeyHandled](#iskeyhandled)|Determina se uma chave é tratada pela tabela de aceleração.|  
|[CKeyboardManager::IsKeyPrintable](#iskeyprintable)|Indica se um caractere imprimível.|  
|[CKeyboardManager::IsShowAllAccelerators](#isshowallaccelerators)|Indica se os menus mostram todas as teclas de atalho para um comando ou a tecla de atalho padrão.|  
|[CKeyboardManager::LoadState](#loadstate)|Carrega as tabelas de teclas de atalho do registro do Windows.|  
|[CKeyboardManager::ResetAll](#resetall)|Recarrega as tabelas de chave de atalho do recurso do aplicativo.|  
|[CKeyboardManager::SaveState](#savestate)|Salva o atalho tabelas de chave no registro do Windows.|  
|[CKeyboardManager::ShowAllAccelerators](#showallaccelerators)|Especifica se o framework exibe todas as teclas de atalho para todos os comandos ou uma única tecla de atalho para cada comando. Esse método não afeta os comandos que têm apenas uma tecla de atalho associada.|  
|[CKeyboardManager::TranslateCharToUpper](#translatechartoupper)|Converte um caractere em seu registro superior.|  
|[CKeyboardManager::UpdateAccelTable](#updateacceltable)|Atualiza uma tabela de teclas de atalho com uma nova tabela de teclas de atalho.|  
  
## <a name="remarks"></a>Comentários  
 Os membros dessa classe permitem salvar e carregar tabelas de teclas de atalho no registro do Windows, use um modelo para atualizar as tabelas de teclas de atalho e localizar a tecla de atalho padrão para um comando em uma janela de quadro. Além disso, o `CKeyboardManager` objeto permite que você controle como teclas de atalho são exibidas ao usuário.  
  
 Você não deve criar um `CKeyboardManager` objeto manualmente. Ele será criado automaticamente pela estrutura do seu aplicativo. No entanto, você deve chamar [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager) durante o processo de inicialização do seu aplicativo. Para obter um ponteiro para o Gerenciador de teclado para o seu aplicativo, chame [CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager).  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir demonstra como recuperar um ponteiro para um `CKeyboardManager` de objeto um `CWinAppEx` classe e como exibir todas as teclas de atalho associadas com os comandos de menu. Este trecho de código é parte do [exemplo páginas personalizadas](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_CustomPages n º&5;](../../mfc/reference/codesnippet/cpp/ckeyboardmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hierarquia de herança  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** afxkeyboardmanager.h  
  
##  <a name="ckeyboardmanager"></a>CKeyboardManager::CKeyboardManager  
 Constrói um objeto `CKeyboardManager`.  
  
```  
CKeyboardManager();
```  
  
### <a name="remarks"></a>Comentários  
 Na maioria dos casos, você não precisa criar um `CKeyboardManager` diretamente. Por padrão, o framework cria uma para você. Para obter um ponteiro para o `CKeyboardManager`, chame [CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager). Se você criar uma manualmente, você deve inicializá-lo com o método [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager).  
  
##  <a name="cleanup"></a>CKeyboardManager::CleanUp  
 Libera o `CKeyboardManager` recursos e limpa todos os mapeamentos de teclas de atalho.  
  
```  
static void CleanUp();
```  
  
### <a name="remarks"></a>Comentários  
 Para obter mais informações sobre teclas de atalho, consulte [personalização de teclado e Mouse](../../mfc/keyboard-and-mouse-customization.md).  
  
 Você não precisa chamar esta função quando seu aplicativo for encerrado porque o framework chama automaticamente durante a saída do aplicativo.  
  
##  <a name="finddefaultaccelerator"></a>CKeyboardManager::FindDefaultAccelerator  
 Recupera a tecla de atalho para o comando especificado e a janela padrão.  
  
```  
static BOOL FindDefaultAccelerator(
    UINT uiCmd,  
    CString& str,  
    CFrameWnd* pWndFrame,  
    BOOL bIsDefaultFrame);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `uiCmd`  
 A ID do comando.  
  
 [out] `str`  
 Uma referência a um objeto `CString`.  
  
 [in] `pWndFrame`  
 Um ponteiro para uma janela de quadro.  
  
 [in] `bIsDefaultFrame`  
 Especifica se a janela do quadro da janela de quadro padrão.  
  
### <a name="return-value"></a>Valor de retorno  
 Diferente de zero se o atalho for encontrado; Caso contrário, 0.  
  
### <a name="remarks"></a>Comentários  
 Esse método procura o comando especificado por `uiCmd` e recupera a tecla de atalho do padrão. Em seguida, o método obtém a cadeia de caracteres associada a essa tecla de atalho e grava o valor para o `str` parâmetro.  
  
##  <a name="iskeyhandled"></a>CKeyboardManager::IsKeyHandled  
 Determina se a chave especificada é tratada pelo [CKeyboardManager classe](../../mfc/reference/ckeyboardmanager-class.md).  
  
```  
static BOOL __stdcall IsKeyHandled(
    WORD nKey,  
    BYTE fVirt,  
    CFrameWnd* pWndFrame,  
    BOOL bIsDefaultFrame);
```  
  
### <a name="parameters"></a>Parâmetros  
  
|||  
|-|-|  
|Parâmetro|Descrição|  
|[in] `nKey`|A tecla a ser verificada.|  
|[in] `fVirt`|Especifica o comportamento da tecla de atalho. Para obter uma lista dos valores possíveis, consulte [ACELERAÇÃO da estrutura](http://msdn.microsoft.com/library/windows/desktop/ms646340).|  
|[in] `pWndFrame`|Uma janela de quadro. Este método determina se uma tecla de atalho é tratada neste quadro.|  
|[in] `bIsDefaultFrame`|Um parâmetro booleano que indica se `pWndFrame` é a janela de quadro padrão.|  
  
### <a name="return-value"></a>Valor de retorno  
 `TRUE`Se a tecla de atalho é tratada. `FALSE`Se a chave não é tratada ou `pWndFrame` é `NULL`.  
  
### <a name="remarks"></a>Comentários  
 Os parâmetros de entrada devem corresponder à entrada accelerator tabela dois de `nKey` e `fVirt` para determinar se uma tecla de atalho é tratada em `pWndFrame`.  
  
##  <a name="iskeyprintable"></a>CKeyboardManager::IsKeyPrintable  
 Indica se um caractere imprimível.  
  
```  
static BOOL __stdcall IsKeyPrintable(const UINT nChar);
```  
  
### <a name="parameters"></a>Parâmetros  
  
|||  
|-|-|  
|Parâmetro|Descrição|  
|[in] `nChar`|O caractere que esse método verifica.|  
  
### <a name="return-value"></a>Valor de retorno  
 Diferente de zero se o caractere imprimível, zero se não for.  
  
### <a name="remarks"></a>Comentários  
 Este método falhará se uma chamada para [GetKeyboardState](http://msdn.microsoft.com/library/windows/desktop/ms646299) falhar.  
  
##  <a name="isshowallaccelerators"></a>CKeyboardManager::IsShowAllAccelerators  
 Indica se os menus mostram todas as teclas de atalho associadas com os comandos de menu ou as teclas de atalho padrão.  
  
```  
static BOOL IsShowAllAccelerators();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Diferente de zero se o aplicativo lista todas as teclas de atalho para comandos de menu. 0 se o aplicativo exibe somente as teclas de atalho padrão.  
  
### <a name="remarks"></a>Comentários  
 O aplicativo lista as teclas de atalho para comandos de menu na barra de menus. Use a função [CKeyboardManager::ShowAllAccelerators](#showallaccelerators) para controlar se o aplicativo lista todas as teclas de atalho ou apenas as teclas de atalho do padrão.  
  
##  <a name="loadstate"></a>CKeyboardManager::LoadState  
 Carrega as tabelas de teclas de atalho do registro do Windows.  
  
```  
BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    CFrameWnd* pDefaultFrame = NULL);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `lpszProfileName`  
 O caminho do registro onde `CKeyboardManager` os dados são salvos.  
  
 [in] `pDefaultFrame`  
 Um ponteiro para uma janela de quadro a ser usado como a janela padrão.  
  
### <a name="return-value"></a>Valor de retorno  
 Diferente de zero se o estado foi carregado com êxito ou 0, caso contrário.  
  
### <a name="remarks"></a>Comentários  
 Se o `lpszProfileName` parâmetro é `NULL`, esse método verifica o local do registro padrão `CKeyboardManager` dados. Local do registro padrão for especificado o [CWinAppEx classe](../../mfc/reference/cwinappex-class.md). Os dados devem ser gravados anteriormente com o método [CKeyboardManager::SaveState](#savestate).  
  
 Se você não especificar uma janela padrão, a janela do quadro principal do seu aplicativo será usada.  
  
##  <a name="resetall"></a>CKeyboardManager::ResetAll  
 Recarrega as tabelas de chave de atalho do recurso do aplicativo.  
  
```  
void ResetAll();
```  
  
### <a name="remarks"></a>Comentários  
 Essa função limpa os atalhos armazenados na `CKeyboardManager` instância. Em seguida, ele será recarregado o estado do Gerenciador de teclado do recurso do aplicativo.  
  
##  <a name="savestate"></a>CKeyboardManager::SaveState  
 Salva o atalho tabelas de chave no registro do Windows.  
  
```  
BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    CFrameWnd* pDefaultFrame = NULL);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `lpszProfileName`  
 O caminho do registro para salvar o `CKeyboardManager` estado.  
  
 [in] `pDefaultFrame`  
 Um ponteiro para uma janela de quadro que se torna a janela padrão.  
  
### <a name="return-value"></a>Valor de retorno  
 Diferente de zero se o estado do Gerenciador de teclado foi salvo com êxito, ou caso contrário, 0.  
  
### <a name="remarks"></a>Comentários  
 Se o `lpszProfileName` parâmetro é `NULL`, esse método irá escrever o `CKeyboardManager` estado para o local padrão especificado pelo [CWinAppEx classe](../../mfc/reference/cwinappex-class.md). Se você especificar um local, você pode carregar os dados posteriormente usando o método [CKeyboardManager::LoadState](#loadstate).  
  
 Se você não especificar uma janela padrão, a janela do quadro principal será usada como a janela padrão.  
  
##  <a name="showallaccelerators"></a>CKeyboardManager::ShowAllAccelerators  
 Mostra todas as teclas de atalho associadas com os comandos de menu.  
  
```  
static void ShowAllAccelerators(
    BOOL bShowAll = TRUE,  
    LPCTSTR lpszDelimiter = _afxDefaultAcceleratorDelimiter);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `bShowAll`  
 Se `true`, as teclas de atalho serão exibidas. Se `false`, somente a primeira tecla de atalho será exibida.  
  
 [in] `lpszDelimiter`  
 Uma cadeia de caracteres a ser inserido entre as teclas de atalho. Esse delimitador não tem nenhum efeito se apenas uma tecla de atalho é exibida.  
  
### <a name="remarks"></a>Comentários  
 Por padrão, se um comando tiver mais de uma tecla de atalho associada, somente a primeira tecla de atalho será mostrada. Essa função permite que você lista todas as teclas de atalho associadas a todos os comandos.  
  
 As teclas de atalho serão listadas ao lado do comando na barra de menus. Se todas as teclas de atalho são exibidas, a cadeia de caracteres fornecida pelo `lpszDelimiter` separará as teclas de atalho individuais.  
  
##  <a name="translatechartoupper"></a>CKeyboardManager::TranslateCharToUpper  
 Converte um caractere em seu registro superior.  
  
```  
static UINT TranslateCharToUpper(const UINT nChar);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `nChar`  
 O caractere a ser convertido.  
  
### <a name="return-value"></a>Valor de retorno  
 O caractere que é o registro superior de parâmetro de entrada.  
  
##  <a name="updateacceltable"></a>CKeyboardManager::UpdateAccelTable  
 Atualiza uma tabela de teclas de atalho com uma nova tabela de teclas de atalho.  
  
```  
BOOL UpdateAccelTable(
    CMultiDocTemplate* pTemplate,  
    LPACCEL lpAccel,  
    int nSize,  
    CFrameWnd* pDefaultFrame = NULL);

 
BOOL UpdateAccelTable(
    CMultiDocTemplate* pTemplate,  
    HACCEL hAccelNew,  
    CFrameWnd* pDefaultFrame = NULL);
```  
  
### <a name="parameters"></a>Parâmetros  
 [in] `pTemplate`  
 Um ponteiro para um modelo de documento.  
  
 [in] `lpAccel`  
 Um ponteiro para a nova tecla de atalho.  
  
 [in] `nSize`  
 O tamanho da nova tabela de atalho.  
  
 [in] `pDefaultFrame`  
 Um ponteiro para a janela do quadro padrão.  
  
 [in] `hAccelNew`  
 Um identificador para a nova tabela de atalho.  
  
### <a name="return-value"></a>Valor de retorno  
 Diferente de zero se o método for bem-sucedido; Caso contrário, 0.  
  
### <a name="remarks"></a>Comentários  
 Use esta função para substituir a tabela de atalho existente com novas teclas de atalho para vários objetos de janela de quadro. A função recebe um modelo de documento como um parâmetro para obter acesso a todos os objetos de janela de quadro conectado ao modelo de documento específico.  
  
## <a name="see-also"></a>Consulte também  
 [Gráfico de hierarquia](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [Classe de CWinAppEx](../../mfc/reference/cwinappex-class.md)   
 [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)   
 [Personalização de teclado e Mouse](../../mfc/keyboard-and-mouse-customization.md)



