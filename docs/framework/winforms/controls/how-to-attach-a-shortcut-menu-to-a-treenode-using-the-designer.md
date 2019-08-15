---
title: '방법: 디자이너를 사용하여 TreeNode에 바로 가기 메뉴 연결'
ms.date: 03/30/2017
helpviewer_keywords:
- shortcut menus [Windows Forms], attaching to TreeNodes
- TreeNode [Windows Forms], attaching a shortcut menu using Designer
ms.assetid: 8e45e184-1313-4f8f-90ff-2cd5789b2268
ms.openlocfilehash: eb3240d35309e03aa8ce949b9c5000f8581d2c2f
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040455"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treenode-using-the-designer"></a><span data-ttu-id="8169e-102">방법: 디자이너를 사용하여 TreeNode에 바로 가기 메뉴 연결</span><span class="sxs-lookup"><span data-stu-id="8169e-102">How to: Attach a Shortcut Menu to a TreeNode Using the Designer</span></span>
<span data-ttu-id="8169e-103">Windows Forms <xref:System.Windows.Forms.TreeView> 컨트롤은 windows 운영 체제에서 windows 탐색기 기능의 왼쪽 창에 표시 된 파일 및 폴더와 비슷한 노드 계층 구조를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8169e-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control displays a hierarchy of nodes, similar to the files and folders displayed in the left pane of the Windows Explorer feature in Windows operating systems.</span></span> <span data-ttu-id="8169e-104"><xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 속성을 설정 하 여 사용자가 <xref:System.Windows.Forms.TreeView> 컨트롤을 마우스 오른쪽 단추로 클릭 하면 상황에 맞는 작업을 사용자에 게 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8169e-104">By setting the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property, you can provide context-sensitive operations to the user when they right-click the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="8169e-105"><xref:System.Windows.Forms.ContextMenuStrip> 구성 요소를 개별 <xref:System.Windows.Forms.TreeNode> 항목과 연결 하면 <xref:System.Windows.Forms.TreeView> 컨트롤에 사용자 지정 수준의 바로 가기 메뉴 기능을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8169e-105">By associating a <xref:System.Windows.Forms.ContextMenuStrip> component with individual <xref:System.Windows.Forms.TreeNode> items, you can add a customized level of shortcut menu functionality to your <xref:System.Windows.Forms.TreeView> controls.</span></span>

## <a name="to-associate-a-shortcut-menu-with-a-treenode-at-design-time"></a><span data-ttu-id="8169e-106">디자인 타임에 바로 가기 메뉴를 TreeNode와 연결 하려면</span><span class="sxs-lookup"><span data-stu-id="8169e-106">To associate a shortcut menu with a TreeNode at design time</span></span>

1. <span data-ttu-id="8169e-107">폼에 <xref:System.Windows.Forms.TreeView> 컨트롤을 추가한 다음 필요에 따라에 노드를 추가 합니다. <xref:System.Windows.Forms.TreeView></span><span class="sxs-lookup"><span data-stu-id="8169e-107">Add a <xref:System.Windows.Forms.TreeView> control to your form, and then add nodes to the <xref:System.Windows.Forms.TreeView> as needed.</span></span> <span data-ttu-id="8169e-108">자세한 내용은 [방법: Windows Forms TreeView 컨트롤](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)을 사용 하 여 노드를 추가 및 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="8169e-108">For more information, see [How to: Add and Remove Nodes with the Windows Forms TreeView Control](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md).</span></span>

2. <span data-ttu-id="8169e-109">폼에 <xref:System.Windows.Forms.ContextMenuStrip> 구성 요소를 추가한 다음 런타임에 사용할 수 있도록 설정할 노드 수준 작업을 나타내는 바로 가기 메뉴에 메뉴 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8169e-109">Add a <xref:System.Windows.Forms.ContextMenuStrip> component to your form, and then add menu items to the shortcut menu that represent node-level operations you wish to make available at run time.</span></span> <span data-ttu-id="8169e-110">자세한 내용은 [방법: ContextMenuStrip](how-to-add-menu-items-to-a-contextmenustrip.md)에 메뉴 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8169e-110">For more information, see [How to: Add Menu Items to a ContextMenuStrip](how-to-add-menu-items-to-a-contextmenustrip.md).</span></span>

3. <span data-ttu-id="8169e-111">컨트롤에 대 한 <xref:System.Windows.Forms.ContextMenuStrip> <xref:System.Windows.Forms.TreeView> TreeNodeEditor 대화 상자를 다시 열고 편집할 노드를 선택 하 고 해당 속성을 추가한 바로 가기 메뉴로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8169e-111">Reopen the **TreeNodeEditor** dialog box for the <xref:System.Windows.Forms.TreeView> control, select the node to edit, and set its <xref:System.Windows.Forms.ContextMenuStrip> property to the shortcut menu that you added.</span></span>

4. <span data-ttu-id="8169e-112">이 속성이 설정 되 면 노드를 마우스 오른쪽 단추로 클릭 하면 바로 가기 메뉴가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8169e-112">When this property is set, the shortcut menu will be displayed when you right-click the node.</span></span>

     <span data-ttu-id="8169e-113">또한 이러한 메뉴 항목에 대 한 이벤트를 처리 하 <xref:System.Windows.Forms.ToolStripItem.Click> 는 코드를 작성 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8169e-113">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.ToolStripItem.Click> events for these menu items.</span></span>

## <a name="see-also"></a><span data-ttu-id="8169e-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="8169e-114">See also</span></span>

- [<span data-ttu-id="8169e-115">TreeView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="8169e-115">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="8169e-116">TreeView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="8169e-116">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="8169e-117">ContextMenuStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="8169e-117">ContextMenuStrip Control</span></span>](contextmenustrip-control.md)
