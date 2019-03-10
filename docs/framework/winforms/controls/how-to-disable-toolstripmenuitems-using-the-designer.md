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
# <a name="how-to-disable-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="3ff85-102">방법: 디자이너를 사용 하 여 ToolStripMenuItems를 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="3ff85-102">How to: Disable ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="3ff85-103">제한 하거나 설정 및 사용자 활동에 대 한 응답에서 메뉴 항목을 사용 하지 않도록 설정 하 여 사용자가 수행 하는 명령을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ff85-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="3ff85-104">메뉴 항목은 생성 하지만이 통해 조정할 수 있습니다 때 기본적으로 활성화 된 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="3ff85-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="3ff85-105">디자인 타임에이 속성을 조작할 수 있습니다 합니다 **속성** 창 또는 코드에서 설정 하 여 프로그래밍 방식으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ff85-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span> <span data-ttu-id="3ff85-106">자세한 내용은 [방법: ToolStripMenuItems 사용 안 함](how-to-disable-toolstripmenuitems.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3ff85-106">For more information, see [How to: Disable ToolStripMenuItems](how-to-disable-toolstripmenuitems.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ff85-107">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ff85-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="3ff85-108">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3ff85-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="3ff85-109">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3ff85-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-disable-a-menu-item-at-design-time"></a><span data-ttu-id="3ff85-110">디자인 타임에 메뉴 항목을 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="3ff85-110">To disable a menu item at design time</span></span>  
  
1.  <span data-ttu-id="3ff85-111">폼에서 선택한 메뉴 항목을 설정 합니다 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 속성을 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="3ff85-111">With the menu item selected on the form, set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="3ff85-112">메뉴의 첫 번째 또는 최상위 메뉴 항목을 사용 하지 않도록 설정 메뉴 내에 포함 된 모든 메뉴 항목이 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ff85-112">Disabling the first or top-level menu item in a menu disables all the menu items contained within the menu.</span></span> <span data-ttu-id="3ff85-113">마찬가지로, 하위 메뉴 항목이 포함 된 메뉴 항목을 사용 하지 않도록 하위 메뉴 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="3ff85-113">Likewise, disabling a menu item that has submenu items disables the submenu items.</span></span> <span data-ttu-id="3ff85-114">지정 된 메뉴에서 모든 명령, 사용자에 게 사용할 수 없으면이 정리 사용자 인터페이스를 제공 하는 대로 숨기고 [전체] 메뉴를 사용 하지 않도록 설정 하는 바람직한 프로그래밍 관행을 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ff85-114">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="3ff85-115">숨기기와 숨기는 것 만으로도 바로 가기 키를 통해 메뉴 명령에 액세스 해도 대로 메뉴를 사용 하지 않도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ff85-115">You should both hide and disable the menu, as hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="3ff85-116">설정 된 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 최상위 메뉴 항목의 속성 `false` 전체 메뉴를 숨기려면 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ff85-116">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ff85-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="3ff85-117">See also</span></span>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="3ff85-118">방법: ToolStripMenuItems 숨기기</span><span class="sxs-lookup"><span data-stu-id="3ff85-118">How to: Hide ToolStripMenuItems</span></span>](how-to-hide-toolstripmenuitems.md)
- [<span data-ttu-id="3ff85-119">MenuStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="3ff85-119">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
