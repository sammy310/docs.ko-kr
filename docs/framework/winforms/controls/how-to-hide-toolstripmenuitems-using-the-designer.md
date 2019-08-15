---
title: '방법: 디자이너를 사용하여 ToolStripMenuItems 숨기기'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
ms.openlocfilehash: 968d34a5f79d469ef62beaa8ac96742d73391b22
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039752"
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="9b8f8-102">방법: 디자이너를 사용하여 ToolStripMenuItems 숨기기</span><span class="sxs-lookup"><span data-stu-id="9b8f8-102">How to: Hide ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="9b8f8-103">메뉴 항목을 숨기면 응용 프로그램의 UI (사용자 인터페이스)를 제어 하 고 사용자 명령을 제한 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="9b8f8-103">Hiding menu items is a way to control the user interface (UI) of your application and restrict user commands.</span></span> <span data-ttu-id="9b8f8-104">대부분의 메뉴 항목을 사용할 수 없는 경우 전체 메뉴를 숨기는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9b8f8-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="9b8f8-105">이 경우 사용자에 게 혼란을 덜 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b8f8-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="9b8f8-106">또한 숨기 더라도 메뉴 또는 메뉴 항목을 숨기 거 나 사용 하지 않도록 설정 하는 것이 좋습니다 .이 경우에는 사용자가 바로 가기 키를 사용 하 여 메뉴 명령에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b8f8-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span> <span data-ttu-id="9b8f8-107">메뉴 항목을 [사용 하지 않도록 설정 하는 방법에 대 한 자세한 내용은 방법: 디자이너](how-to-disable-toolstripmenuitems-using-the-designer.md)를 사용 하 여 ToolStripMenuItems를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b8f8-107">For more information on disabling menu items, see [How to: Disable ToolStripMenuItems Using the Designer](how-to-disable-toolstripmenuitems-using-the-designer.md).</span></span>

## <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a><span data-ttu-id="9b8f8-108">최상위 메뉴와 해당 하위 메뉴 항목을 숨기려면</span><span class="sxs-lookup"><span data-stu-id="9b8f8-108">To hide a top-level menu and its submenu items</span></span>

1. <span data-ttu-id="9b8f8-109">최상위 메뉴 항목을 선택 하 고 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 또는 <xref:System.Windows.Forms.ToolStripItem.Available%2A> 속성을로 `false`설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b8f8-109">Select the top-level menu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> or <xref:System.Windows.Forms.ToolStripItem.Available%2A> property to `false`.</span></span>

     <span data-ttu-id="9b8f8-110">최상위 메뉴 항목을 숨기면 해당 메뉴의 모든 메뉴 항목도 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="9b8f8-110">When you hide the top-level menu item, all menu items within that menu are also hidden.</span></span> <span data-ttu-id="9b8f8-111">이후에를로 설정 <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 하 `false`는 경우 이외의 다른 위치를 클릭 하면 전체 최상위 메뉴 항목과 해당 하위 메뉴 항목이 폼에서 사라지고 작업의 런타임 효과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b8f8-111">If you click somewhere other than on the <xref:System.Windows.Forms.MenuStrip> after setting <xref:System.Windows.Forms.ToolStripItem.Visible%2A> to `false`, the entire top-level menu item and its submenu items disappear from your form, thus showing you the run-time effect of your action.</span></span> <span data-ttu-id="9b8f8-112">디자인 타임에 숨겨진 최상위 메뉴 항목을 표시 하려면 <xref:System.Windows.Forms.MenuStrip> **구성 요소 트레이**, **문서 개요**또는 속성 그리드 위쪽에서를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b8f8-112">To display the hidden top-level menu item at design time, click on the <xref:System.Windows.Forms.MenuStrip> in the **Component Tray**, in **Document Outline**, or at the top of the property grid.</span></span>

> [!NOTE]
>  <span data-ttu-id="9b8f8-113">병합 시나리오에서는 MDI (다중 문서 인터페이스) 자식 메뉴를 제외 하 고 전체 메뉴를 숨기는 것이 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b8f8-113">You will rarely hide an entire menu except for multiple document interface (MDI) child menus in a merging scenario.</span></span>

## <a name="to-hide-a-submenu-item"></a><span data-ttu-id="9b8f8-114">하위 메뉴 항목을 숨기려면</span><span class="sxs-lookup"><span data-stu-id="9b8f8-114">To hide a submenu item</span></span>

1. <span data-ttu-id="9b8f8-115">하위 메뉴 항목을 선택 하 고 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 속성을 `false`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b8f8-115">Select the submenu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>

     <span data-ttu-id="9b8f8-116">하위 메뉴 항목을 숨기면 디자인 타임에 폼에 계속 표시 되므로 추가 작업을 위해 쉽게 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b8f8-116">When you hide a submenu item, it remains visible on your form at design time so that you can easily select it for further work.</span></span> <span data-ttu-id="9b8f8-117">실제로는 런타임에 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="9b8f8-117">It will actually be hidden at run time.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b8f8-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="9b8f8-118">See also</span></span>

- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>
- <xref:System.Windows.Forms.ToolStripItem.Available%2A>
- <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>
- [<span data-ttu-id="9b8f8-119">MenuStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="9b8f8-119">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
- [<span data-ttu-id="9b8f8-120">방법: 디자이너를 사용 하 여 ToolStripMenuItems 비활성화</span><span class="sxs-lookup"><span data-stu-id="9b8f8-120">How to: Disable ToolStripMenuItems Using the Designer</span></span>](how-to-disable-toolstripmenuitems-using-the-designer.md)
