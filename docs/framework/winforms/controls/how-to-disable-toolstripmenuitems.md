---
title: '방법: ToolStripMenuItems 사용 안 함'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], enabling
- ToolStripMenuItems [Windows Forms], disabling
- menu items [Windows Forms], disabling
- disabling menu items
- menu items [Windows Forms], enabling
- menus [Windows Forms], disabling menu items
ms.assetid: bcc1da84-50fd-41d2-8475-103b581d5654
ms.openlocfilehash: 3c18935239a4355d5416a0a79d0fa9f5c504cc7e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720214"
---
# <a name="how-to-disable-toolstripmenuitems"></a>방법: ToolStripMenuItems 사용 안 함
제한 하거나 설정 및 사용자 활동에 대 한 응답에서 메뉴 항목을 사용 하지 않도록 설정 하 여 사용자가 수행 하는 명령을 확장할 수 있습니다. 메뉴 항목은 생성 하지만이 통해 조정할 수 있습니다 때 기본적으로 활성화 된 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 속성입니다. 디자인 타임에이 속성을 조작할 수 있습니다 합니다 **속성** 창 또는 코드에서 설정 하 여 프로그래밍 방식으로 합니다.  
  
### <a name="to-disable-a-menu-item-programmatically"></a>메뉴 항목을 프로그래밍 방식으로 사용 하지 않도록 설정  
  
-   메뉴 항목의 속성을 설정한 메서드 내에서 설정 하는 코드를 추가 합니다 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 속성을 `false`입니다.  
  
    ```vb  
    MenuItem1.Enabled = False  
    ```  
  
    ```csharp  
    menuItem1.Enabled = false;  
    ```  
  
    ```cpp  
    menuItem1->Enabled = false;  
    ```  
  
    > [!TIP]
    >  메뉴의 첫 번째 또는 최상위 메뉴 항목을 사용 하지 않도록 설정 메뉴에서 포함 된 모든 메뉴 항목 숨겨지지만 비활성화 되지 않습니다. 마찬가지로, 하위 메뉴 항목이 포함 된 메뉴 항목을 사용 하지 않도록 설정 하위 메뉴 항목을 숨기지만 비활성화 되지 않습니다. 지정 된 메뉴에서 모든 명령, 사용자에 게 사용할 수 없으면이 정리 사용자 인터페이스를 제공 하는 대로 숨기고 [전체] 메뉴를 사용 하지 않도록 설정 하는 바람직한 프로그래밍 관행을 간주 됩니다. 숨기기 및 메뉴를 사용 하지 않도록 설정 하 고 숨기기만 해도 사용자 바로 가기 키를 통해 메뉴 명령에 액세스 하기 때문에 모든 항목 및 메뉴에서 하위 메뉴 항목을 사용 하지 않도록 해야 합니다. 설정 된 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 최상위 메뉴 항목의 속성 `false` 전체 메뉴를 숨기려면 합니다.  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [방법: ToolStripMenuItems 숨기기](how-to-hide-toolstripmenuitems.md)
- [MenuStrip 컨트롤 개요](menustrip-control-overview-windows-forms.md)
