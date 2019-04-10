---
title: '방법: ToolStripMenuItems 복사'
ms.date: 03/30/2017
helpviewer_keywords:
- menu items [Windows Forms], copying and pasting
- MenuStrip control [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], copying and pasting
ms.assetid: 17ef4207-e92e-4db2-b648-27246e6517ad
ms.openlocfilehash: c59af175a6ee23395e19247efd8fa15e6d19ae66
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59334343"
---
# <a name="how-to-copy-toolstripmenuitems"></a><span data-ttu-id="381c9-102">방법: ToolStripMenuItems 복사</span><span class="sxs-lookup"><span data-stu-id="381c9-102">How to: Copy ToolStripMenuItems</span></span>
<span data-ttu-id="381c9-103">디자인 타임에 최상위 메뉴 전체와 해당 하위 메뉴 항목을 <xref:System.Windows.Forms.MenuStrip>의 다른 위치로 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="381c9-103">At design time, you can copy entire top-level menus and their submenu items to a different place on the <xref:System.Windows.Forms.MenuStrip>.</span></span> <span data-ttu-id="381c9-104">최상위 메뉴 간에 개별 메뉴 항목을 복사하거나 메뉴 내에서 메뉴 항목의 위치를 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="381c9-104">You can also copy individual menu items between top-level menus or change the position of menu items within a menu.</span></span>  
  
### <a name="to-copy-a-top-level-menu-and-its-submenu-items-to-another-top-level-location"></a><span data-ttu-id="381c9-105">최상위 메뉴와 해당 하위 메뉴 항목을 다른 최상위 위치로 복사하려면</span><span class="sxs-lookup"><span data-stu-id="381c9-105">To copy a top-level menu and its submenu items to another top-level location</span></span>  
  
1. <span data-ttu-id="381c9-106">복사하려는 메뉴를 마우스 왼쪽 단추로 클릭하고 Ctrl+C를 누르거나, 메뉴를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **복사** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="381c9-106">Left-click the menu that you want to copy and press CTRL+C, or right-click the menu and select **Copy** from the shortcut menu.</span></span>  
  
2. <span data-ttu-id="381c9-107">원하는 새 위치 뒤에 있는 최상위 메뉴를 마우스 왼쪽 단추로 클릭하고 Ctrl+V를 누르거나, 원하는 새 위치 앞에 있는 최상위 메뉴 항목을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **붙여넣기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="381c9-107">Left-click the top-level menu that is after the intended new location and press CTRL+V, or right-click the top-level menu item that is before the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="381c9-108">복사한 메뉴가 선택한 최상위 메뉴 앞에 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="381c9-108">The menu that you copied is inserted before the selected top-level menu.</span></span>  
  
### <a name="to-copy-a-top-level-menu-and-its-submenu-items-to-a-drop-down-location"></a><span data-ttu-id="381c9-109">최상위 메뉴와 해당 하위 메뉴 항목을 드롭다운 위치에 복사하려면</span><span class="sxs-lookup"><span data-stu-id="381c9-109">To copy a top-level menu and its submenu items to a drop-down location</span></span>  
  
1. <span data-ttu-id="381c9-110">이동하려는 메뉴를 마우스 왼쪽 단추로 클릭하고 Ctrl+C를 누르거나, 메뉴를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **복사** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="381c9-110">Left-click the menu that you want to move and press CTRL+C, or right-click the menu and select **Copy** from the shortcut menu.</span></span>  
  
2. <span data-ttu-id="381c9-111">대상 최상위 메뉴에서 원하는 새 위치 위에 있는 하위 메뉴 항목을 마우스 왼쪽 단추로 클릭하고 Ctrl+V를 누르거나, 원하는 새 위치 위에 있는 하위 메뉴 항목을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **붙여넣기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="381c9-111">In the destination top-level menu, left-click the submenu item that is above the intended new location and press CTRL+V, or right-click the submenu item that is above the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="381c9-112">복사한 메뉴가 선택한 하위 메뉴 항목 앞에 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="381c9-112">The menu that you copied is inserted before the selected submenu item.</span></span>  
  
### <a name="to-copy-a-submenu-item-to-another-menu"></a><span data-ttu-id="381c9-113">다른 메뉴에 하위 메뉴 항목을 복사하려면</span><span class="sxs-lookup"><span data-stu-id="381c9-113">To copy a submenu item to another menu</span></span>  
  
1. <span data-ttu-id="381c9-114">복사하려는 하위 메뉴 항목을 마우스 왼쪽 단추로 클릭하고 Ctrl+C를 누르거나, 하위 메뉴 항목을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **복사** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="381c9-114">Left-click the submenu item that you want to copy and press CTRL+C, or right-click the submenu item and choose **Copy** from the shortcut menu.</span></span>  
  
2. <span data-ttu-id="381c9-115">잘라낸 하위 메뉴 항목이 포함될 메뉴를 마우스 왼쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="381c9-115">Left-click the menu that will contain the submenu item that you cut.</span></span>  
  
3. <span data-ttu-id="381c9-116">원하는 새 위치 앞에 있는 하위 메뉴 항목을 마우스 왼쪽 단추로 클릭하고 Ctrl+V를 누르거나, 원하는 새 위치 앞에 있는 하위 메뉴 항목을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **붙여넣기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="381c9-116">Left-click the submenu item that is before the intended new location and press CTRL+V, or right-click the submenu item that is before the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="381c9-117">복사한 하위 메뉴 항목이 선택한 하위 메뉴 항목 앞에 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="381c9-117">The submenu item that you copied is inserted before the selected submenu item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="381c9-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="381c9-118">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="381c9-119">MenuStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="381c9-119">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
