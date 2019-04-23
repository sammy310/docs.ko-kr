---
title: '방법: ToolStripMenuItems를 사용하지 않도록 설정'
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
ms.openlocfilehash: a480cd29eef1a79a69f702eed7cd02c28d7ea3de
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59082726"
---
# <a name="how-to-disable-toolstripmenuitems"></a><span data-ttu-id="d7c95-102">방법: ToolStripMenuItems를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="d7c95-102">How to: Disable ToolStripMenuItems</span></span>
<span data-ttu-id="d7c95-103">제한 하거나 설정 및 사용자 활동에 대 한 응답에서 메뉴 항목을 사용 하지 않도록 설정 하 여 사용자가 수행 하는 명령을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7c95-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="d7c95-104">메뉴 항목은 생성 하지만이 통해 조정할 수 있습니다 때 기본적으로 활성화 된 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d7c95-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="d7c95-105">디자인 타임에이 속성을 조작할 수 있습니다 합니다 **속성** 창 또는 코드에서 설정 하 여 프로그래밍 방식으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7c95-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span>  
  
### <a name="to-disable-a-menu-item-programmatically"></a><span data-ttu-id="d7c95-106">메뉴 항목을 프로그래밍 방식으로 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="d7c95-106">To disable a menu item programmatically</span></span>  
  
-   <span data-ttu-id="d7c95-107">메뉴 항목의 속성을 설정한 메서드 내에서 설정 하는 코드를 추가 합니다 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 속성을 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="d7c95-107">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
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
    >  <span data-ttu-id="d7c95-108">메뉴의 첫 번째 또는 최상위 메뉴 항목을 사용 하지 않도록 설정 메뉴에서 포함 된 모든 메뉴 항목 숨겨지지만 비활성화 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7c95-108">Disabling the first or top-level menu item in a menu hides all the menu items contained within the menu, but does not disable them.</span></span> <span data-ttu-id="d7c95-109">마찬가지로, 하위 메뉴 항목이 포함 된 메뉴 항목을 사용 하지 않도록 설정 하위 메뉴 항목을 숨기지만 비활성화 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7c95-109">Likewise, disabling a menu item that has submenu items hides the submenu items, but does not disable them.</span></span> <span data-ttu-id="d7c95-110">지정 된 메뉴에서 모든 명령, 사용자에 게 사용할 수 없으면이 정리 사용자 인터페이스를 제공 하는 대로 숨기고 [전체] 메뉴를 사용 하지 않도록 설정 하는 바람직한 프로그래밍 관행을 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7c95-110">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="d7c95-111">숨기기 및 메뉴를 사용 하지 않도록 설정 하 고 숨기기만 해도 사용자 바로 가기 키를 통해 메뉴 명령에 액세스 하기 때문에 모든 항목 및 메뉴에서 하위 메뉴 항목을 사용 하지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7c95-111">You should hide and disable the menu, and disable every item and submenu item in the menu, because hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="d7c95-112">설정 된 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 최상위 메뉴 항목의 속성 `false` 전체 메뉴를 숨기려면 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7c95-112">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7c95-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="d7c95-113">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="d7c95-114">방법: ToolStripMenuItems 숨기기</span><span class="sxs-lookup"><span data-stu-id="d7c95-114">How to: Hide ToolStripMenuItems</span></span>](how-to-hide-toolstripmenuitems.md)
- [<span data-ttu-id="d7c95-115">MenuStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="d7c95-115">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
