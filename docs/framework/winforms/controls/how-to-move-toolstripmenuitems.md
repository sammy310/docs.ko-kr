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
ms.openlocfilehash: adf25973fde790937461007bd0106cca02dd83be
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039805"
---
# <a name="how-to-move-toolstripmenuitems"></a><span data-ttu-id="88c2c-102">방법: ToolStripMenuItems 이동</span><span class="sxs-lookup"><span data-stu-id="88c2c-102">How to: Move ToolStripMenuItems</span></span>
<span data-ttu-id="88c2c-103">디자인 타임에 전체 최상위 메뉴와 해당 메뉴 항목을의 다른 위치로 <xref:System.Windows.Forms.MenuStrip>이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88c2c-103">At design time, you can move entire top-level menus and their menu items to a different place on the <xref:System.Windows.Forms.MenuStrip>.</span></span> <span data-ttu-id="88c2c-104">최상위 메뉴 간에 개별 메뉴 항목을 이동 하거나 메뉴 내에서 메뉴 항목의 위치를 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88c2c-104">You can also move individual menu items between top-level menus or change the position of menu items within a menu.</span></span>

## <a name="to-move-a-top-level-menu-and-its-menu-items-to-another-top-level-location"></a><span data-ttu-id="88c2c-105">최상위 메뉴와 해당 메뉴 항목을 다른 최상위 위치로 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="88c2c-105">To move a top-level menu and its menu items to another top-level location</span></span>

1. <span data-ttu-id="88c2c-106">이동 하려는 메뉴에서 마우스 왼쪽 단추를 클릭 하 여 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88c2c-106">Click and hold down the left mouse button on the menu that you want to move.</span></span>

2. <span data-ttu-id="88c2c-107">원하는 새 위치 앞에 있는 최상위 메뉴로 삽입 지점을 끌고 왼쪽 마우스 단추를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="88c2c-107">Drag the insertion point to the top-level menu that is before the intended new location and release the left mouse button.</span></span>

     <span data-ttu-id="88c2c-108">선택한 메뉴가 삽입 지점의 오른쪽으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="88c2c-108">The selected menu moves to the right of the insertion point.</span></span>

## <a name="to-move-a-top-level-menu-and-its-menu-items-to-a-drop-down-location"></a><span data-ttu-id="88c2c-109">최상위 메뉴와 해당 메뉴 항목을 드롭다운 위치로 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="88c2c-109">To move a top-level menu and its menu items to a drop-down location</span></span>

1. <span data-ttu-id="88c2c-110">이동 하려는 메뉴를 마우스 왼쪽 단추로 클릭 하 고 CTRL + X를 누르거나, 메뉴를 마우스 오른쪽 단추로 클릭 하 고 바로 가기 메뉴에서 **잘라내기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="88c2c-110">Left-click the menu that you want to move and press CTRL+X, or right-click the menu and select **Cut** from the shortcut menu.</span></span>

2. <span data-ttu-id="88c2c-111">대상 최상위 메뉴에서 원하는 새 위치 위의 메뉴 항목을 마우스 왼쪽 단추로 클릭 하 고 CTRL + V를 누르거나, 원하는 새 위치 위에 있는 메뉴 항목을 마우스 오른쪽 단추로 클릭 하 고 바로 가기 메뉴에서 **붙여넣기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="88c2c-111">In the destination top-level menu, left-click the menu item above the intended new location and press CTRL+V, or right-click the menu item above the intended new location and select **Paste** from the shortcut menu.</span></span>

     <span data-ttu-id="88c2c-112">선택한 메뉴 항목 뒤에 잘린 메뉴가 삽입 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88c2c-112">The menu that you cut is inserted after the selected menu item.</span></span>

## <a name="to-move-a-menu-item-within-a-menu-using-the-items-collection-editor"></a><span data-ttu-id="88c2c-113">항목 컬렉션 편집기를 사용 하 여 메뉴에서 메뉴 항목을 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="88c2c-113">To move a menu item within a menu using the Items Collection Editor</span></span>

1. <span data-ttu-id="88c2c-114">이동 하려는 메뉴 항목이 포함 된 메뉴를 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="88c2c-114">Right-click the menu that contains the menu item you want to move.</span></span>

2. <span data-ttu-id="88c2c-115">바로 가기 메뉴에서 **DropDownItems 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="88c2c-115">From the shortcut menu, choose **Edit DropDownItems**.</span></span>

3. <span data-ttu-id="88c2c-116">**항목 컬렉션 편집기**에서 이동할 메뉴 항목을 마우스 왼쪽 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="88c2c-116">In the **Items Collection Editor**, left-click the menu item you want to move.</span></span>

4. <span data-ttu-id="88c2c-117">위쪽 및 아래쪽 화살표 키를 클릭 하 여 메뉴에서 메뉴 항목을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="88c2c-117">Click the UP and DOWN ARROW keys to move the menu item within the menu.</span></span>

5. <span data-ttu-id="88c2c-118">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="88c2c-118">Click **OK**.</span></span>

## <a name="to-move-a-menu-item-within-a-menu-using-the-keyboard"></a><span data-ttu-id="88c2c-119">키보드를 사용 하 여 메뉴에서 메뉴 항목을 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="88c2c-119">To move a menu item within a menu using the keyboard</span></span>

1. <span data-ttu-id="88c2c-120">ALT 키를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88c2c-120">Press and hold down the ALT key.</span></span>

2. <span data-ttu-id="88c2c-121">이동 하려는 메뉴 항목의 왼쪽 마우스 단추를 클릭 하 여 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="88c2c-121">Click and hold the left mouse button on the menu item that you want to move.</span></span>

3. <span data-ttu-id="88c2c-122">메뉴 항목을 새 위치로 끌고 왼쪽 마우스 단추를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="88c2c-122">Drag the menu item to the new location and release the left mouse button.</span></span>

## <a name="to-move-a-menu-item-to-another-menu"></a><span data-ttu-id="88c2c-123">메뉴 항목을 다른 메뉴로 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="88c2c-123">To move a menu item to another menu</span></span>

1. <span data-ttu-id="88c2c-124">이동 하려는 메뉴 항목을 마우스 왼쪽 단추로 클릭 하 고 CTRL + X를 누르거나, 메뉴 항목을 마우스 오른쪽 단추로 클릭 하 고 바로 가기 메뉴에서 **잘라내기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="88c2c-124">Left-click the menu item that you want to move and press CTRL+X, or right-click the menu item and choose **Cut** from the shortcut menu.</span></span>

2. <span data-ttu-id="88c2c-125">잘린 메뉴 항목이 포함 될 메뉴를 마우스 왼쪽 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="88c2c-125">Left-click the menu that will contain the menu item that you cut.</span></span>

3. <span data-ttu-id="88c2c-126">원하는 새 위치 앞에 있는 메뉴 항목을 마우스 왼쪽 단추로 클릭 하 고 CTRL + V를 누르거나, 원하는 새 위치 앞에 있는 메뉴 항목을 마우스 오른쪽 단추로 클릭 하 고 바로 가기 메뉴에서 **붙여넣기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="88c2c-126">Left-click the menu item that is before the intended new location and press CTRL+V, or right-click the menu item that is before the intended new location and select **Paste** from the shortcut menu.</span></span>

     <span data-ttu-id="88c2c-127">잘린 메뉴 항목이 선택한 메뉴 항목 뒤에 삽입 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88c2c-127">The menu item that you cut is inserted after the selected menu item.</span></span>

## <a name="see-also"></a><span data-ttu-id="88c2c-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="88c2c-128">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="88c2c-129">MenuStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="88c2c-129">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
