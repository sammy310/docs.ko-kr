---
title: '방법: 디자이너를 사용 하 여 ToolStripMenuItems를 사용 하지 않도록 설정'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], disabling in designer
- MenuStrip control [Windows Forms], disabling menu items in designer
- menu items [Windows Forms], disabling
- menus [Windows Forms], disabling items
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
ms.openlocfilehash: a185fe4421b5b5d7846c7d8cacbfc1cae5f805eb
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57704437"
---
# <a name="how-to-disable-toolstripmenuitems-using-the-designer"></a>방법: 디자이너를 사용 하 여 ToolStripMenuItems를 사용 하지 않도록 설정
제한 하거나 설정 및 사용자 활동에 대 한 응답에서 메뉴 항목을 사용 하지 않도록 설정 하 여 사용자가 수행 하는 명령을 확장할 수 있습니다. 메뉴 항목은 생성 하지만이 통해 조정할 수 있습니다 때 기본적으로 활성화 된 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 속성입니다. 디자인 타임에이 속성을 조작할 수 있습니다 합니다 **속성** 창 또는 코드에서 설정 하 여 프로그래밍 방식으로 합니다. 자세한 내용은 [방법: ToolStripMenuItems 사용 안 함](how-to-disable-toolstripmenuitems.md)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-disable-a-menu-item-at-design-time"></a>디자인 타임에 메뉴 항목을 사용 하지 않도록 설정  
  
1.  폼에서 선택한 메뉴 항목을 설정 합니다 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 속성을 `false`입니다.  
  
    > [!TIP]
    >  메뉴의 첫 번째 또는 최상위 메뉴 항목을 사용 하지 않도록 설정 메뉴 내에 포함 된 모든 메뉴 항목이 사용 하지 않도록 설정 합니다. 마찬가지로, 하위 메뉴 항목이 포함 된 메뉴 항목을 사용 하지 않도록 하위 메뉴 항목입니다. 지정 된 메뉴에서 모든 명령, 사용자에 게 사용할 수 없으면이 정리 사용자 인터페이스를 제공 하는 대로 숨기고 [전체] 메뉴를 사용 하지 않도록 설정 하는 바람직한 프로그래밍 관행을 간주 됩니다. 숨기기와 숨기는 것 만으로도 바로 가기 키를 통해 메뉴 명령에 액세스 해도 대로 메뉴를 사용 하지 않도록 설정 해야 합니다. 설정 된 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 최상위 메뉴 항목의 속성 `false` 전체 메뉴를 숨기려면 합니다.  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [방법: ToolStripMenuItems 숨기기](how-to-hide-toolstripmenuitems.md)
- [MenuStrip 컨트롤 개요](menustrip-control-overview-windows-forms.md)
