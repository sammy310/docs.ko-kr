---
title: '방법: 디자이너를 사용하여 ToolStripMenuItems를 사용하지 않도록 설정'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], disabling in designer
- MenuStrip control [Windows Forms], disabling menu items in designer
- menu items [Windows Forms], disabling
- menus [Windows Forms], disabling items
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
ms.openlocfilehash: 692b6c11f6d58c52a0af29ed04ada45c48cae058
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046231"
---
# <a name="how-to-disable-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="ada4f-102">방법: 디자이너를 사용하여 ToolStripMenuItems를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="ada4f-102">How to: Disable ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="ada4f-103">사용자 활동에 대 한 응답으로 메뉴 항목을 사용 하거나 사용 하지 않도록 설정 하 여 사용자가 수행할 수 있는 명령을 제한 하거나 넓힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ada4f-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="ada4f-104">메뉴 항목은 만들어질 때 기본적으로 사용 하도록 설정 되지만 속성을 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 통해 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ada4f-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="ada4f-105">디자인 타임에 **속성** 창에서이 속성을 조작 하거나 코드에서이 속성을 설정 하 여 프로그래밍 방식으로 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ada4f-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span> <span data-ttu-id="ada4f-106">자세한 내용은 [방법: ToolStripMenuItems](how-to-disable-toolstripmenuitems.md)를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ada4f-106">For more information, see [How to: Disable ToolStripMenuItems](how-to-disable-toolstripmenuitems.md).</span></span>

## <a name="to-disable-a-menu-item-at-design-time"></a><span data-ttu-id="ada4f-107">디자인 타임에 메뉴 항목을 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="ada4f-107">To disable a menu item at design time</span></span>

1. <span data-ttu-id="ada4f-108">폼에서 선택한 메뉴 항목을 사용 하 여 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 속성을로 `false`설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ada4f-108">With the menu item selected on the form, set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>

    > [!TIP]
    > <span data-ttu-id="ada4f-109">메뉴의 첫 번째 또는 최상위 메뉴 항목을 사용 하지 않도록 설정 하면 메뉴 내에 포함 된 모든 메뉴 항목이 비활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ada4f-109">Disabling the first or top-level menu item in a menu disables all the menu items contained within the menu.</span></span> <span data-ttu-id="ada4f-110">마찬가지로 하위 메뉴 항목이 있는 메뉴 항목을 사용 하지 않도록 설정 하면 하위 메뉴 항목이 비활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ada4f-110">Likewise, disabling a menu item that has submenu items disables the submenu items.</span></span> <span data-ttu-id="ada4f-111">지정 된 메뉴의 모든 명령을 사용자가 사용할 수 없는 경우에는 완전 한 사용자 인터페이스를 제공 하므로 전체 메뉴를 숨기 거 나 사용 하지 않도록 설정 하는 것이 좋은 프로그래밍 습관 이라고 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ada4f-111">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="ada4f-112">메뉴를 숨기 거 나 사용 하지 않도록 설정 해야 합니다. 숨기 더라도 바로 가기 키를 통해 메뉴 명령에 대 한 액세스를 차단 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ada4f-112">You should both hide and disable the menu, as hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="ada4f-113">최상위 메뉴 항목의 `false` 속성을로설정하여전체메뉴를숨깁니다.<xref:System.Windows.Forms.ToolStripItem.Visible%2A></span><span class="sxs-lookup"><span data-stu-id="ada4f-113">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>

## <a name="see-also"></a><span data-ttu-id="ada4f-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="ada4f-114">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="ada4f-115">방법: ToolStripMenuItems 숨기기</span><span class="sxs-lookup"><span data-stu-id="ada4f-115">How to: Hide ToolStripMenuItems</span></span>](how-to-hide-toolstripmenuitems.md)
- [<span data-ttu-id="ada4f-116">MenuStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="ada4f-116">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
