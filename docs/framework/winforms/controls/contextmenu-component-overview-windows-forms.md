---
title: ContextMenu 구성 요소 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ContextMenu
helpviewer_keywords:
- ContextMenu component [Windows Forms], about ContextMenu component
- context menus [Windows Forms], ContextMenu component
- shortcut menus [Windows Forms], ContextMenu component
ms.assetid: 49d6398f-d3c4-4679-84fa-1de07b68b05e
ms.openlocfilehash: 2acbcc9197a630a993471c22e572a4f3ed682c64
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956054"
---
# <a name="contextmenu-component-overview-windows-forms"></a>ContextMenu 구성 요소 개요(Windows Forms)
> [!IMPORTANT]
>  있지만 <xref:System.Windows.Forms.MenuStrip> 하 고 <xref:System.Windows.Forms.ContextMenuStrip> 바꾸고 기능을 추가 합니다 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu> 이전 버전의 컨트롤 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu> 선택 하면 이전 버전과 호환성 및 향후 사용을 위해 유지 됩니다.  
  
 Windows Forms를 사용 하 여 <xref:System.Windows.Forms.ContextMenu> 구성 요소, 선택한 개체와 연관 된 자주 사용 되는 명령의 쉽게 액세스할 수 있는 바로 가기 메뉴를 사용 하 여 사용자를 제공할 수 있습니다. 바로 가기 메뉴의 항목은 주로 응용 프로그램에서 다른 곳에 나타나는 기본 메뉴에서 항목의 하위 항목입니다. 일반적으로 사용자를 마우스 오른쪽 단추로 클릭 하 여 바로 가기 메뉴를 액세스할 수 있습니다. Windows Forms에서 바로 가기 메뉴 컨트롤에 연결 됩니다.  
  
## <a name="key-properties"></a>키 속성  
 컨트롤의 설정 하 여 컨트롤을 사용 하 여 바로 가기 메뉴를 연결할 수 있습니다 <xref:System.Windows.Forms.Control.ContextMenu%2A> 속성을는 <xref:System.Windows.Forms.ContextMenu> 구성 요소입니다. 단일 바로 가기 메뉴는 여러 개의 컨트롤을 사용 하 여 연결할 수 있지만 각 컨트롤 바로 가기 메뉴를 하나만 가질 수 있습니다.  
  
 키 속성을 <xref:System.Windows.Forms.ContextMenu> 구성 요소를 <xref:System.Windows.Forms.Menu.MenuItems%2A> 속성입니다. 프로그래밍 방식으로 작성 하 여 메뉴 항목을 추가할 수 있습니다 <xref:System.Windows.Forms.MenuItem> 개체에 추가 하 여 <xref:System.Windows.Forms.Menu.MenuItemCollection> 바로 가기 메뉴. 바로 가기 메뉴 항목에에서는 일반적으로 다른 메뉴에서 가져온 것, 때문에 가장 자주 항목을 추가한 바로 가기 메뉴에 복사 하 여 합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.ContextMenu>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
