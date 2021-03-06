---
title: Classe CFolderPickerDialog | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog::CFolderPickerDialog
dev_langs:
- C++
helpviewer_keywords:
- CFolderPickerDialog [MFC], CFolderPickerDialog
ms.assetid: 8db01684-dd1d-4e9c-989e-07a2318a8156
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d80839fca18d62c5fa9a9432296777c546268c5b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46411424"
---
# <a name="cfolderpickerdialog-class"></a>Classe CFolderPickerDialog

Classe CFolderPickerDialog implementa CFileDialog no modo de selecionador de pasta.

## <a name="syntax"></a>Sintaxe

```
class CFolderPickerDialog : public CFileDialog;
```

## <a name="members"></a>Membros

### <a name="public-constructors"></a>Construtores Públicos

|Nome|Descrição|
|----------|-----------------|
|[CFolderPickerDialog:: ~ CFolderPickerDialog](#cfolderpickerdialog__~cfolderpickerdialog)|Destruidor.|
|[CFolderPickerDialog::CFolderPickerDialog](#cfolderpickerdialog)|Construtor.|

## <a name="remarks"></a>Comentários

## <a name="inheritance-hierarchy"></a>Hierarquia de herança

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[CFileDialog](../../mfc/reference/cfiledialog-class.md)

`CFolderPickerDialog`

## <a name="requirements"></a>Requisitos

**Cabeçalho:** afxdlgs. h

##  <a name="cfolderpickerdialog"></a>  CFolderPickerDialog::CFolderPickerDialog

Construtor.

```
explicit CFolderPickerDialog(
    LPCTSTR lpszFolder = NULL,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL,
    DWORD dwSize = 0);
```

### <a name="parameters"></a>Parâmetros

*lpszFolder*<br/>
Pasta inicial.

*dwFlags*<br/>
Uma combinação de um ou mais sinalizadores que permitem que você personalize a caixa de diálogo.

*pParentWnd*<br/>
Um ponteiro para a janela do pai ou o proprietário do objeto de caixa de diálogo.

*dwSize*<br/>
O tamanho da estrutura OPENFILENAME.

### <a name="remarks"></a>Comentários

##  <a name="_dtorcfolderpickerdialog"></a>  CFolderPickerDialog:: ~ CFolderPickerDialog

Destruidor.

```
virtual ~CFolderPickerDialog();
```

### <a name="remarks"></a>Comentários

## <a name="see-also"></a>Consulte também

[Classes](../../mfc/reference/mfc-classes.md)
