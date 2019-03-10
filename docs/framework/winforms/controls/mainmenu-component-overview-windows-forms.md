---
title: MainMenu 구성 요소 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
ms.openlocfilehash: 6c2c33c8c03751e87d71e65523b82d92b18f31c4
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709873"
---
# <a name="mainmenu-component-overview-windows-forms"></a>MainMenu 구성 요소 개요(Windows Forms)
> [!IMPORTANT]
>  있지만 <xref:System.Windows.Forms.MenuStrip> 하 고 <xref:System.Windows.Forms.ContextMenuStrip> 바꾸고 기능을 추가 합니다 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu> 이전 버전의 컨트롤 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu> 선택 하면 이전 버전과 호환성 및 향후 사용을 위해 유지 됩니다.  
  
 Windows Forms <xref:System.Windows.Forms.MainMenu> 구성 요소는 런타임에 메뉴를 표시 합니다. 주 메뉴 및 개별 항목의 모든 하위 메뉴는 <xref:System.Windows.Forms.MenuItem> 개체입니다.  
  
## <a name="key-properties"></a>키 속성  
 메뉴 항목을 설정 하 여 기본 항목으로 지정할 수 있습니다 합니다 <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> 속성을 `true`입니다. 기본 항목 메뉴를 클릭 하면 굵은 텍스트로 나타납니다. 메뉴 항목의 <xref:System.Windows.Forms.MenuItem.Checked%2A> 속성이 `true` 또는 `false`, 메뉴 항목이 선택 되어 있는지 여부를 나타냅니다. 메뉴 항목의 <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> 속성에는 선택한 항목의 모양을 사용자 지정: 경우 <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> 로 설정 된 `true`를 경우 항목 옆에 표시 되는 라디오 단추 <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> 로 설정 된 `false`, 항목 옆에 확인 표시가 나타납니다.  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [MenuStrip 컨트롤 개요](menustrip-control-overview-windows-forms.md)
