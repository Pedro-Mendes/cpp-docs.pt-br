---
title: "APIs ANSI preteridas | Microsoft Docs"
ms.custom: ""
ms.date: "12/10/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC, Métodos preteridos ANSI"
ms.assetid: c7c5a6fd-95e4-4bee-b3d5-d3826c30947d
caps.latest.revision: 8
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# APIs ANSI preteridas
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\(MFC\) Da biblioteca de classes do Microsoft foundation estiver migrando para classes e métodos que são baseados no conjunto de caracteres Unicode.  Em virtude disso, as versões de ANSI de vários métodos de MFC são preteridas.  Use as versões Unicode desses métodos em seus aplicativos futuros.  
  
 Iniciando com o versão 6,1 dos controles comum do windows, que acompanha o [!INCLUDE[windowsver](../Token/windowsver_md.md)], os seguintes métodos de ANSI são substituídos.  
  
## Classe de CButton  
  
```  
AFX_ANSI_DEPRECATED BOOL GetIdealSize(LPSIZE psize) const;  
AFX_ANSI_DEPRECATED BOOL GetImageList(PBUTTON_IMAGELIST pbuttonImagelist) const;  
AFX_ANSI_DEPRECATED BOOL GetTextMargin(LPRECT pmargin) const;  
AFX_ANSI_DEPRECATED BOOL SetImageList(PBUTTON_IMAGELIST pbuttonImagelist);  
AFX_ANSI_DEPRECATED BOOL SetTextMargin(LPRECT pmargin);  
```  
  
## Classe de CComboBoxEx  
  
```  
AFX_ANSI_DEPRECATED HRESULT SetWindowTheme(LPCWSTR pszSubAppName);  
```  
  
## Classe de CEdit  
  
```  
AFX_ANSI_DEPRECATED BOOL GetCueBanner(LPWSTR lpszText, int cchText) const;  
AFX_ANSI_DEPRECATED BOOL SetCueBanner(LPCWSTR lpszText, BOOL fDrawIfFocused = FALSE);  
```  
  
## Classe de CLinkCtrl  
 A classe inteira é substituída.  
  
## Classe de CListCtrl  
  
```  
AFX_ANSI_DEPRECATED void CancelEditLabel();  
AFX_ANSI_DEPRECATED int EnableGroupView(BOOL fEnable);  
AFX_ANSI_DEPRECATED int GetGroupInfo(int iGroupId, PLVGROUP pgrp) const;  
AFX_ANSI_DEPRECATED void GetGroupMetrics(PLVGROUPMETRICS pGroupMetrics) const;  
AFX_ANSI_DEPRECATED BOOL GetInsertMark(LPLVINSERTMARK lvim) const;  
AFX_ANSI_DEPRECATED COLORREF GetInsertMarkColor() const;  
AFX_ANSI_DEPRECATED int GetInsertMarkRect(LPRECT pRect) const;  
AFX_ANSI_DEPRECATED COLORREF GetOutlineColor() const;  
AFX_ANSI_DEPRECATED UINT GetSelectedColumn() const;  
AFX_ANSI_DEPRECATED BOOL GetTileInfo(PLVTILEINFO pti) const;  
AFX_ANSI_DEPRECATED BOOL GetTileViewInfo(PLVTILEVIEWINFO ptvi) const;  
AFX_ANSI_DEPRECATED DWORD GetView() const;  
AFX_ANSI_DEPRECATED BOOL HasGroup(int iGroupId) const;  
AFX_ANSI_DEPRECATED int InsertGroup(int index, PLVGROUP pgrp);  
AFX_ANSI_DEPRECATED void InsertGroupSorted(PLVINSERTGROUPSORTED pStructInsert);  
AFX_ANSI_DEPRECATED int InsertMarkHitTest(LPPOINT pPoint, LPLVINSERTMARK lvim) const;  
AFX_ANSI_DEPRECATED BOOL IsGroupViewEnabled() const;  
AFX_ANSI_DEPRECATED void MoveGroup(int iGroupId, int toIndex);  
AFX_ANSI_DEPRECATED void MoveItemToGroup(int idItemFrom, int idGroupTo);  
AFX_ANSI_DEPRECATED void RemoveAllGroups();  
AFX_ANSI_DEPRECATED int RemoveGroup(int iGroupId);  
AFX_ANSI_DEPRECATED BOOL SetGroupInfo(int iGroupId, PLVGROUP pGroup);  
AFX_ANSI_DEPRECATED void SetGroupMetrics(PLVGROUPMETRICS pGroupMetrics);  
AFX_ANSI_DEPRECATED BOOL SetInfoTip(PLVSETINFOTIP plvInfoTip);  
AFX_ANSI_DEPRECATED BOOL SetInsertMark(LPLVINSERTMARK lvim);  
AFX_ANSI_DEPRECATED COLORREF SetInsertMarkColor(COLORREF color);  
AFX_ANSI_DEPRECATED COLORREF SetOutlineColor(COLORREF color);  
AFX_ANSI_DEPRECATED void SetSelectedColumn(int iCol);  
AFX_ANSI_DEPRECATED BOOL SetTileInfo(PLVTILEINFO pti);  
AFX_ANSI_DEPRECATED BOOL SetTileViewInfo(PLVTILEVIEWINFO ptvi);  
AFX_ANSI_DEPRECATED DWORD SetView(int iView);  
AFX_ANSI_DEPRECATED BOOL SortGroups(PFNLVGROUPCOMPARE _pfnGroupCompare, LPVOID _plv);  
```  
  
## Classe de CReBarCtrl  
  
```  
AFX_ANSI_DEPRECATED void GetBandMargins(PMARGINS pMargins) const;  
AFX_ANSI_DEPRECATED HRESULT SetWindowTheme(LPCWSTR pszSubAppName);  
```  
  
## Classe de CToolBarCtrl  
  
```  
AFX_ANSI_DEPRECATED void GetMetrics(LPTBMETRICS ptbm) const;  
AFX_ANSI_DEPRECATED void SetMetrics(LPTBMETRICS ptbm);  
AFX_ANSI_DEPRECATED HRESULT SetWindowTheme(LPCWSTR pszSubAppName);  
```  
  
## Classe de CToolTipCtrl  
  
```  
AFX_ANSI_DEPRECATED HRESULT SetWindowTheme(LPCWSTR pszSubAppName);  
```  
  
## Consulte também  
 [Requisitos de compilação para controles comuns do Windows Vista](../mfc/build-requirements-for-windows-vista-common-controls.md)