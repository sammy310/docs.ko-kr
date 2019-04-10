---
title: '방법: ToolStripMenuItems 이동'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], moving
- menus [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], dragging and dropping
- menu items [Windows Forms], moving
- menu items [Windows Forms], cutting and pasting
- menu items [Windows Forms], dragging and dropping
- MenuStrip control [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], cutting and pasting
ms.assetid: cab9e03e-4edd-4c25-b3e3-bd1edc602bd9
ms.openlocfilehash: 70387a4c43b78f93a46f601eb35b7dca2083b01f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168339"
---
# <a name="how-to-move-toolstripmenuitems"></a>방법: ToolStripMenuItems 이동
디자인 타임으로 이동할 수 있습니다 최상위 메뉴 전체와 해당 메뉴 항목을 다른 위치로 <xref:System.Windows.Forms.MenuStrip>합니다. 최상위 메뉴 간에 개별 메뉴 항목을 이동 하거나 메뉴에서 메뉴 항목의 위치를 변경할 수도 있습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-another-top-level-location"></a>최상위 메뉴와 메뉴 항목을 다른 최상위 위치로 이동 하려면  
  
1.  클릭 하 고 이동 하려는 메뉴에서 마우스 왼쪽된 단추를 길게 누른 키를 누릅니다.  
  
2.  원하는 새 위치 앞에 있는 최상위 메뉴에 삽입 포인터를 끌어서 왼쪽된 마우스 단추를 놓습니다.  
  
     선택한 메뉴 삽입 지점의 오른쪽으로 이동합니다.  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-a-drop-down-location"></a>최상위 메뉴와 메뉴 항목을 드롭다운 위치에 이동 하려면  
  
1.  이동 및 CTRL + x를 또는 메뉴를 마우스 오른쪽 단추로 클릭 하 고 선택 하려는 메뉴를 마우스 왼쪽 단추로 클릭 **잘라내기** 바로 가기 메뉴에서.  
  
2.  대상 최상위 메뉴에서 원하는 새 위치 위에 있는 메뉴 항목을 마우스 왼쪽 단추로 클릭 하 고 CTRL + v를 또는 원하는 새 위치 위에 있는 메뉴 항목을 마우스 오른쪽 단추로 클릭 하 고 선택 **붙여넣기** 바로 가기 메뉴에서.  
  
     잘라낸 메뉴는 선택한 메뉴 항목 뒤에 삽입 됩니다.  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-items-collection-editor"></a>항목 컬렉션 편집기를 사용 하 여 메뉴에서 메뉴 항목을 이동 하려면  
  
1.  이동 하려는 메뉴 항목을 포함 하는 메뉴를 마우스 오른쪽 단추로 클릭 합니다.  
  
2.  바로 가기 메뉴에서 선택 **DropDownItems 편집**합니다.  
  
3.  에 **항목 컬렉션 편집기**를 이동 하려는 메뉴 항목을 마우스 왼쪽 단추로 클릭 합니다.  
  
4.  메뉴 내의 메뉴 항목을 이동 하려면 위쪽 및 아래쪽 화살표 키를 클릭 합니다.  
  
5.  **확인**을 클릭합니다.  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-keyboard"></a>키보드를 사용 하 여 메뉴에서 메뉴 항목을 이동 하려면  
  
1.  누른 ALT 키를 보유 합니다.  
  
2.  클릭 하 고 마우스 왼쪽된 단추를 이동 하려는 메뉴 항목에 저장 합니다.  
  
3.  메뉴 항목을 새 위치로 끌어서 왼쪽된 마우스 단추를 놓습니다.  
  
### <a name="to-move-a-menu-item-to-another-menu"></a>다른 메뉴에 메뉴 항목을 이동 하려면  
  
1.  이동 하 고 CTRL + x를 또는 메뉴 항목을 마우스 오른쪽 단추로 클릭 하 고 선택 하려는 메뉴 항목을 마우스 왼쪽 단추로 클릭 **잘라내기** 바로 가기 메뉴에서.  
  
2.  잘라낸 메뉴 항목을 포함 하는 메뉴를 마우스 왼쪽 단추로 클릭 합니다.  
  
3.  원하는 새 위치 앞에 있는 메뉴 항목을 마우스 왼쪽 단추로 클릭 하 고 CTRL + V를 누르거나 선택한 원하는 새 위치 앞에 있는 메뉴 항목을 마우스 오른쪽 단추로 클릭 **붙여넣기** 바로 가기 메뉴에서.  
  
     잘라낸 메뉴 항목이 선택한 메뉴 항목 뒤에 삽입 됩니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [MenuStrip 컨트롤 개요](menustrip-control-overview-windows-forms.md)
