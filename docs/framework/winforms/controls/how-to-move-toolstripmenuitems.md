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
ms.openlocfilehash: 50b5fd16780147ad7592035a901d993495dcb878
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708953"
---
# <a name="how-to-move-toolstripmenuitems"></a><span data-ttu-id="944bc-102">방법: ToolStripMenuItems 이동</span><span class="sxs-lookup"><span data-stu-id="944bc-102">How to: Move ToolStripMenuItems</span></span>
<span data-ttu-id="944bc-103">디자인 타임으로 이동할 수 있습니다 최상위 메뉴 전체와 해당 메뉴 항목을 다른 위치로 <xref:System.Windows.Forms.MenuStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="944bc-103">At design time, you can move entire top-level menus and their menu items to a different place on the <xref:System.Windows.Forms.MenuStrip>.</span></span> <span data-ttu-id="944bc-104">최상위 메뉴 간에 개별 메뉴 항목을 이동 하거나 메뉴에서 메뉴 항목의 위치를 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="944bc-104">You can also move individual menu items between top-level menus or change the position of menu items within a menu.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="944bc-105">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="944bc-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="944bc-106">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="944bc-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="944bc-107">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="944bc-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-another-top-level-location"></a><span data-ttu-id="944bc-108">최상위 메뉴와 메뉴 항목을 다른 최상위 위치로 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="944bc-108">To move a top-level menu and its menu items to another top-level location</span></span>  
  
1.  <span data-ttu-id="944bc-109">클릭 하 고 이동 하려는 메뉴에서 마우스 왼쪽된 단추를 길게 누른 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="944bc-109">Click and hold down the left mouse button on the menu that you want to move.</span></span>  
  
2.  <span data-ttu-id="944bc-110">원하는 새 위치 앞에 있는 최상위 메뉴에 삽입 포인터를 끌어서 왼쪽된 마우스 단추를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="944bc-110">Drag the insertion point to the top-level menu that is before the intended new location and release the left mouse button.</span></span>  
  
     <span data-ttu-id="944bc-111">선택한 메뉴 삽입 지점의 오른쪽으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="944bc-111">The selected menu moves to the right of the insertion point.</span></span>  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-a-drop-down-location"></a><span data-ttu-id="944bc-112">최상위 메뉴와 메뉴 항목을 드롭다운 위치에 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="944bc-112">To move a top-level menu and its menu items to a drop-down location</span></span>  
  
1.  <span data-ttu-id="944bc-113">이동 및 CTRL + x를 또는 메뉴를 마우스 오른쪽 단추로 클릭 하 고 선택 하려는 메뉴를 마우스 왼쪽 단추로 클릭 **잘라내기** 바로 가기 메뉴에서.</span><span class="sxs-lookup"><span data-stu-id="944bc-113">Left-click the menu that you want to move and press CTRL+X, or right-click the menu and select **Cut** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="944bc-114">대상 최상위 메뉴에서 원하는 새 위치 위에 있는 메뉴 항목을 마우스 왼쪽 단추로 클릭 하 고 CTRL + v를 또는 원하는 새 위치 위에 있는 메뉴 항목을 마우스 오른쪽 단추로 클릭 하 고 선택 **붙여넣기** 바로 가기 메뉴에서.</span><span class="sxs-lookup"><span data-stu-id="944bc-114">In the destination top-level menu, left-click the menu item above the intended new location and press CTRL+V, or right-click the menu item above the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="944bc-115">잘라낸 메뉴는 선택한 메뉴 항목 뒤에 삽입 됩니다.</span><span class="sxs-lookup"><span data-stu-id="944bc-115">The menu that you cut is inserted after the selected menu item.</span></span>  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-items-collection-editor"></a><span data-ttu-id="944bc-116">항목 컬렉션 편집기를 사용 하 여 메뉴에서 메뉴 항목을 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="944bc-116">To move a menu item within a menu using the Items Collection Editor</span></span>  
  
1.  <span data-ttu-id="944bc-117">이동 하려는 메뉴 항목을 포함 하는 메뉴를 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="944bc-117">Right-click the menu that contains the menu item you want to move.</span></span>  
  
2.  <span data-ttu-id="944bc-118">바로 가기 메뉴에서 선택 **DropDownItems 편집**합니다.</span><span class="sxs-lookup"><span data-stu-id="944bc-118">From the shortcut menu, choose **Edit DropDownItems**.</span></span>  
  
3.  <span data-ttu-id="944bc-119">에 **항목 컬렉션 편집기**를 이동 하려는 메뉴 항목을 마우스 왼쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="944bc-119">In the **Items Collection Editor**, left-click the menu item you want to move.</span></span>  
  
4.  <span data-ttu-id="944bc-120">메뉴 내의 메뉴 항목을 이동 하려면 위쪽 및 아래쪽 화살표 키를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="944bc-120">Click the UP and DOWN ARROW keys to move the menu item within the menu.</span></span>  
  
5.  <span data-ttu-id="944bc-121">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="944bc-121">Click **OK**.</span></span>  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-keyboard"></a><span data-ttu-id="944bc-122">키보드를 사용 하 여 메뉴에서 메뉴 항목을 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="944bc-122">To move a menu item within a menu using the keyboard</span></span>  
  
1.  <span data-ttu-id="944bc-123">누른 ALT 키를 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="944bc-123">Press and hold down the ALT key.</span></span>  
  
2.  <span data-ttu-id="944bc-124">클릭 하 고 마우스 왼쪽된 단추를 이동 하려는 메뉴 항목에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="944bc-124">Click and hold the left mouse button on the menu item that you want to move.</span></span>  
  
3.  <span data-ttu-id="944bc-125">메뉴 항목을 새 위치로 끌어서 왼쪽된 마우스 단추를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="944bc-125">Drag the menu item to the new location and release the left mouse button.</span></span>  
  
### <a name="to-move-a-menu-item-to-another-menu"></a><span data-ttu-id="944bc-126">다른 메뉴에 메뉴 항목을 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="944bc-126">To move a menu item to another menu</span></span>  
  
1.  <span data-ttu-id="944bc-127">이동 하 고 CTRL + x를 또는 메뉴 항목을 마우스 오른쪽 단추로 클릭 하 고 선택 하려는 메뉴 항목을 마우스 왼쪽 단추로 클릭 **잘라내기** 바로 가기 메뉴에서.</span><span class="sxs-lookup"><span data-stu-id="944bc-127">Left-click the menu item that you want to move and press CTRL+X, or right-click the menu item and choose **Cut** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="944bc-128">잘라낸 메뉴 항목을 포함 하는 메뉴를 마우스 왼쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="944bc-128">Left-click the menu that will contain the menu item that you cut.</span></span>  
  
3.  <span data-ttu-id="944bc-129">원하는 새 위치 앞에 있는 메뉴 항목을 마우스 왼쪽 단추로 클릭 하 고 CTRL + V를 누르거나 선택한 원하는 새 위치 앞에 있는 메뉴 항목을 마우스 오른쪽 단추로 클릭 **붙여넣기** 바로 가기 메뉴에서.</span><span class="sxs-lookup"><span data-stu-id="944bc-129">Left-click the menu item that is before the intended new location and press CTRL+V, or right-click the menu item that is before the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="944bc-130">잘라낸 메뉴 항목이 선택한 메뉴 항목 뒤에 삽입 됩니다.</span><span class="sxs-lookup"><span data-stu-id="944bc-130">The menu item that you cut is inserted after the selected menu item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="944bc-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="944bc-131">See also</span></span>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="944bc-132">MenuStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="944bc-132">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
