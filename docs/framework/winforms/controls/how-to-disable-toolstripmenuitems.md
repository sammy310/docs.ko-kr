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
ms.openlocfilehash: f86a2934e799e4604693491dacbecc517d44d810
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046221"
---
# <a name="how-to-disable-toolstripmenuitems"></a><span data-ttu-id="7ef44-102">방법: ToolStripMenuItems를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="7ef44-102">How to: Disable ToolStripMenuItems</span></span>
<span data-ttu-id="7ef44-103">사용자 활동에 대 한 응답으로 메뉴 항목을 사용 하거나 사용 하지 않도록 설정 하 여 사용자가 수행할 수 있는 명령을 제한 하거나 넓힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ef44-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="7ef44-104">메뉴 항목은 만들어질 때 기본적으로 사용 하도록 설정 되지만 속성을 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 통해 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ef44-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="7ef44-105">디자인 타임에 **속성** 창에서이 속성을 조작 하거나 코드에서이 속성을 설정 하 여 프로그래밍 방식으로 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ef44-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span>  
  
### <a name="to-disable-a-menu-item-programmatically"></a><span data-ttu-id="7ef44-106">프로그래밍 방식으로 메뉴 항목을 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="7ef44-106">To disable a menu item programmatically</span></span>  
  
- <span data-ttu-id="7ef44-107">메뉴 항목의 속성을 설정 하는 메서드 내에서 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> `false`속성을 설정 하는 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ef44-107">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
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
    > <span data-ttu-id="7ef44-108">메뉴의 첫 번째 또는 최상위 메뉴 항목을 사용 하지 않도록 설정 하면 메뉴에 포함 된 모든 메뉴 항목이 숨겨지고 비활성화 되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7ef44-108">Disabling the first or top-level menu item in a menu hides all the menu items contained within the menu, but does not disable them.</span></span> <span data-ttu-id="7ef44-109">마찬가지로 하위 메뉴 항목이 있는 메뉴 항목을 사용 하지 않도록 설정 하면 하위 메뉴 항목이 숨겨지고 비활성화 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7ef44-109">Likewise, disabling a menu item that has submenu items hides the submenu items, but does not disable them.</span></span> <span data-ttu-id="7ef44-110">지정 된 메뉴의 모든 명령을 사용자가 사용할 수 없는 경우에는 완전 한 사용자 인터페이스를 제공 하므로 전체 메뉴를 숨기 거 나 사용 하지 않도록 설정 하는 것이 좋은 프로그래밍 습관 이라고 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ef44-110">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="7ef44-111">메뉴를 숨기 거 나 사용 하지 않도록 설정 하 고 메뉴의 모든 항목 및 하위 메뉴 항목을 사용 하지 않도록 설정 해야 합니다. 숨기기만 하면 바로 가기 키를 통해 메뉴 명령에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ef44-111">You should hide and disable the menu, and disable every item and submenu item in the menu, because hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="7ef44-112">최상위 메뉴 항목의 `false` 속성을로설정하여전체메뉴를숨깁니다.<xref:System.Windows.Forms.ToolStripItem.Visible%2A></span><span class="sxs-lookup"><span data-stu-id="7ef44-112">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ef44-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="7ef44-113">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="7ef44-114">방법: ToolStripMenuItems 숨기기</span><span class="sxs-lookup"><span data-stu-id="7ef44-114">How to: Hide ToolStripMenuItems</span></span>](how-to-hide-toolstripmenuitems.md)
- [<span data-ttu-id="7ef44-115">MenuStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="7ef44-115">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
