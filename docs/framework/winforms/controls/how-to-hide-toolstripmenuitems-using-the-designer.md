---
title: '방법: 디자이너를 사용 하 여 ToolStripMenuItems 숨기기'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
ms.openlocfilehash: 2af9f31360f667662d4d640b5e449ff6ee8ce381
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57721543"
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="8f8ce-102">방법: 디자이너를 사용 하 여 ToolStripMenuItems 숨기기</span><span class="sxs-lookup"><span data-stu-id="8f8ce-102">How to: Hide ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="8f8ce-103">메뉴 항목 숨기기는 응용 프로그램의 사용자 인터페이스 (UI)를 제어 하 고 사용자 명령을 제한 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-103">Hiding menu items is a way to control the user interface (UI) of your application and restrict user commands.</span></span> <span data-ttu-id="8f8ce-104">종종 전체 메뉴에 메뉴 항목을 모두 사용할 수 없는 경우 숨기려면 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="8f8ce-105">이 사용자에 대해 더 적은 방해 요소를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="8f8ce-106">또한 하려는 숨기고 메뉴 또는 메뉴 항목을 사용 하지 않도록 설정으로 숨기는 것 만으로도 사용자 바로 가기 키를 사용 하 여 메뉴 명령에 액세스 하는 것을 금지 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span> <span data-ttu-id="8f8ce-107">메뉴 항목을 사용 하지 않도록 설정 하는 방법은 참조 하세요. [방법: 디자이너를 사용 하 여 ToolStripMenuItems를 사용 하지 않도록 설정](how-to-disable-toolstripmenuitems-using-the-designer.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-107">For more information on disabling menu items, see [How to: Disable ToolStripMenuItems Using the Designer](how-to-disable-toolstripmenuitems-using-the-designer.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f8ce-108">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="8f8ce-109">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="8f8ce-110">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a><span data-ttu-id="8f8ce-111">최상위 메뉴와 해당 하위 메뉴 항목을 숨기려면</span><span class="sxs-lookup"><span data-stu-id="8f8ce-111">To hide a top-level menu and its submenu items</span></span>  
  
1.  <span data-ttu-id="8f8ce-112">최상위 메뉴 항목을 선택 하 고 설정 해당 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 나 <xref:System.Windows.Forms.ToolStripItem.Available%2A> 속성을 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-112">Select the top-level menu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> or <xref:System.Windows.Forms.ToolStripItem.Available%2A> property to `false`.</span></span>  
  
     <span data-ttu-id="8f8ce-113">최상위 메뉴 항목을 숨기려면 해당 메뉴에서 모든 메뉴 항목 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-113">When you hide the top-level menu item, all menu items within that menu are also hidden.</span></span> <span data-ttu-id="8f8ce-114">아닌 다른 위치를 클릭 하면 합니다 <xref:System.Windows.Forms.MenuStrip> 설정한 후 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 에 `false`, 전체 최상위 메뉴 항목 및 해당 하위 메뉴 항목 폼에 따라서 작업의 런타임 효과 보여주는에서 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-114">If you click somewhere other than on the <xref:System.Windows.Forms.MenuStrip> after setting <xref:System.Windows.Forms.ToolStripItem.Visible%2A> to `false`, the entire top-level menu item and its submenu items disappear from your form, thus showing you the run-time effect of your action.</span></span> <span data-ttu-id="8f8ce-115">디자인 타임에 숨겨진된 최상위 메뉴 항목을 표시 하려면 클릭 합니다 <xref:System.Windows.Forms.MenuStrip> 에 **구성 요소 트레이에**의 **문서 개요**, 또는 속성 표의 맨 위에 있는.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-115">To display the hidden top-level menu item at design time, click on the <xref:System.Windows.Forms.MenuStrip> in the **Component Tray**, in **Document Outline**, or at the top of the property grid.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f8ce-116">거의 전체 메뉴 병합 시나리오에서 여러 문서 MDI (인터페이스) 자식 메뉴를 제외 하 고 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-116">You will rarely hide an entire menu except for multiple document interface (MDI) child menus in a merging scenario.</span></span>  
  
### <a name="to-hide-a-submenu-item"></a><span data-ttu-id="8f8ce-117">하위 메뉴 항목을 숨기려면</span><span class="sxs-lookup"><span data-stu-id="8f8ce-117">To hide a submenu item</span></span>  
  
1.  <span data-ttu-id="8f8ce-118">하위 메뉴 항목을 선택 하 고 설정 해당 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 속성을 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-118">Select the submenu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>  
  
     <span data-ttu-id="8f8ce-119">하위 메뉴 항목을 숨길 때 추가 작업을 위해 쉽게 선택할 수 있도록 디자인 타임에 폼에 표시 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-119">When you hide a submenu item, it remains visible on your form at design time so that you can easily select it for further work.</span></span> <span data-ttu-id="8f8ce-120">이 런타임 시 실제로 표시 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8f8ce-120">It will actually be hidden at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f8ce-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="8f8ce-121">See also</span></span>
- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>
- <xref:System.Windows.Forms.ToolStripItem.Available%2A>
- <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>
- [<span data-ttu-id="8f8ce-122">MenuStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="8f8ce-122">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
- [<span data-ttu-id="8f8ce-123">방법: 디자이너를 사용 하 여 ToolStripMenuItems를 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="8f8ce-123">How to: Disable ToolStripMenuItems Using the Designer</span></span>](how-to-disable-toolstripmenuitems-using-the-designer.md)
