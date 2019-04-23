---
title: '방법: TreeView 노드에 바로 가기 메뉴 연결'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- shortcut menus [Windows Forms], adding to TreeView controls
- TreeView control [Windows Forms], adding shortcut menus
- tree nodes in TreeView control [Windows Forms], shortcut menus
ms.assetid: a23c6752-fd8f-44ad-b781-bab37962fc7c
ms.openlocfilehash: f818cccb3103866af993f1aff527a9c1a7c82109
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59294175"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treeview-node"></a><span data-ttu-id="7ba21-102">방법: TreeView 노드에 바로 가기 메뉴 연결</span><span class="sxs-lookup"><span data-stu-id="7ba21-102">How to: Attach a ShortCut Menu to a TreeView Node</span></span>
<span data-ttu-id="7ba21-103">Windows Forms <xref:System.Windows.Forms.TreeView> 제어 파일 및 폴더 Windows 탐색기의 왼쪽된 창에 표시 된 비슷한 노드 계층 구조를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ba21-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control displays a hierarchy of nodes, similar to the files and folders displayed in the left pane of Windows Explorer.</span></span> <span data-ttu-id="7ba21-104">설정 하 여 합니다 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 속성을 제공할 수 있습니다 상황에 맞는 작업 사용자에 게는 마우스 오른쪽 단추로 클릭는 <xref:System.Windows.Forms.TreeView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ba21-104">By setting the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property, you can provide context-sensitive operations to the user when they right-click the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="7ba21-105">연결 하 여는 <xref:System.Windows.Forms.ContextMenuStrip> 구성 요소를 개별 <xref:System.Windows.Forms.TreeNode> 항목을 사용자 지정된 된 바로 가기 메뉴 기능 수준을 추가할 수 있습니다 프로그램 <xref:System.Windows.Forms.TreeView> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="7ba21-105">By associating a <xref:System.Windows.Forms.ContextMenuStrip> component with individual <xref:System.Windows.Forms.TreeNode> items, you can add a customized level of shortcut menu functionality to your <xref:System.Windows.Forms.TreeView> controls.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-programmatically"></a><span data-ttu-id="7ba21-106">트리 노드를 사용 하 여 바로 가기 메뉴를 프로그래밍 방식으로 연결 하려면</span><span class="sxs-lookup"><span data-stu-id="7ba21-106">To associate a shortcut menu with a TreeNode programmatically</span></span>  
  
1. <span data-ttu-id="7ba21-107">인스턴스화하는 <xref:System.Windows.Forms.TreeView> 적절 한 속성 설정을 사용 하 여 컨트롤을 루트를 만들 <xref:System.Windows.Forms.TreeNode>, 다음 하위 노드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ba21-107">Instantiate a <xref:System.Windows.Forms.TreeView> control with the appropriate property settings, create a root <xref:System.Windows.Forms.TreeNode>, and then add subnodes.</span></span>  
  
2. <span data-ttu-id="7ba21-108">인스턴스화하는 <xref:System.Windows.Forms.ContextMenuStrip> 구성 요소를 추가한 다음을 <xref:System.Windows.Forms.ToolStripMenuItem> 런타임에 사용할 수 있도록 하려는 각 작업에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ba21-108">Instantiate a <xref:System.Windows.Forms.ContextMenuStrip> component, and then add a <xref:System.Windows.Forms.ToolStripMenuItem> for each operation you want to make available at run time.</span></span>  
  
3. <span data-ttu-id="7ba21-109">설정 된 <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> 적절 한 속성 <xref:System.Windows.Forms.TreeNode> 만든 바로 가기 메뉴.</span><span class="sxs-lookup"><span data-stu-id="7ba21-109">Set the <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> property of the appropriate <xref:System.Windows.Forms.TreeNode> to the shortcut menu you create.</span></span>  
  
4. <span data-ttu-id="7ba21-110">이 속성을 설정 하는 경우 바로 가기 메뉴에서 노드를 마우스 오른쪽 단추로 클릭할 때 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ba21-110">When this property is set, the shortcut menu will be displayed when you right-click the node.</span></span>  
  
 <span data-ttu-id="7ba21-111">다음 코드 예제에서는 기본 <xref:System.Windows.Forms.TreeView> 하 고 <xref:System.Windows.Forms.ContextMenuStrip> 루트와 연결 된 <xref:System.Windows.Forms.TreeNode> 의 <xref:System.Windows.Forms.TreeView>합니다.</span><span class="sxs-lookup"><span data-stu-id="7ba21-111">The following code example creates a basic <xref:System.Windows.Forms.TreeView> and <xref:System.Windows.Forms.ContextMenuStrip> associated with the root <xref:System.Windows.Forms.TreeNode> of the <xref:System.Windows.Forms.TreeView>.</span></span> <span data-ttu-id="7ba21-112">맞게 메뉴 선택 항목을 사용자 지정 해야 합니다는 <xref:System.Windows.Forms.TreeView> 개발 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ba21-112">You will need to customize the menu choices to those that fit the <xref:System.Windows.Forms.TreeView> you are developing.</span></span> <span data-ttu-id="7ba21-113">처리할 코드를 작성 하려고 또한는 <xref:System.Windows.Forms.ToolStripItem.Click> 이러한 메뉴 항목에 대 한 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="7ba21-113">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.ToolStripItem.Click> events for these menu items.</span></span>  
  
 [!code-cpp[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/cpp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7ba21-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="7ba21-114">See also</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip>
- [<span data-ttu-id="7ba21-115">TreeView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="7ba21-115">TreeView Control</span></span>](treeview-control-windows-forms.md)
