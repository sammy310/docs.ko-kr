---
title: '방법: 디자이너를 사용하여 Windows Forms TreeView 컨트롤에서 노드 추가 및 제거'
ms.date: 03/30/2017
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
ms.openlocfilehash: ef3a963b5621f0b972b02a007681f600fbdb1050
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2019
ms.locfileid: "69040068"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a><span data-ttu-id="d5873-102">방법: 디자이너를 사용하여 Windows Forms TreeView 컨트롤에서 노드 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="d5873-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control Using the Designer</span></span>

<span data-ttu-id="d5873-103">Windows Forms <xref:System.Windows.Forms.TreeView> 컨트롤은 노드를 계층적 방식으로 표시 하기 때문에 노드를 추가할 때 부모 노드가 무엇 인지 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5873-103">Because the Windows Forms <xref:System.Windows.Forms.TreeView> control displays nodes in a hierarchical manner, when adding a node you must pay attention to what its parent node is.</span></span>

<span data-ttu-id="d5873-104">다음 절차에는 <xref:System.Windows.Forms.TreeView> 컨트롤을 포함 하는 폼을 포함 하는 **Windows 응용 프로그램** 프로젝트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5873-104">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="d5873-105">이러한 프로젝트 [를 설정 하는 방법에 대 한 자세한 내용은 방법: Windows Forms 응용 프로그램 프로젝트](/visualstudio/ide/step-1-create-a-windows-forms-application-project) [를 만들고 방법: Windows Forms](how-to-add-controls-to-windows-forms.md)에 컨트롤을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5873-105">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-add-or-remove-nodes-in-the-designer"></a><span data-ttu-id="d5873-106">디자이너에서 노드를 추가 하거나 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="d5873-106">To add or remove nodes in the designer</span></span>

1. <span data-ttu-id="d5873-107"><xref:System.Windows.Forms.TreeView> 컨트롤을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5873-107">Select the <xref:System.Windows.Forms.TreeView> control.</span></span>

2. <span data-ttu-id="d5873-108">**속성 창에서** <xref:System.Windows.Forms.TreeView.Nodes%2A> 속성 옆에 있는 **줄임표** 단추![(...)를 클릭 하 여 속성 옆의 Visual Studio](./media/visual-studio-ellipsis-button.png)속성 창에서 줄임표 단추 (...)를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5873-108">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>

     <span data-ttu-id="d5873-109">**TreeNode 편집기** 가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d5873-109">The **TreeNode Editor** appears.</span></span>

3. <span data-ttu-id="d5873-110">노드를 추가 하려면 루트 노드가 있어야 합니다. 이 항목이 없으면 **루트 추가** 단추를 클릭 하 여 루트를 먼저 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5873-110">To add nodes, a root node must exist; if one does not exist, you must first add a root by clicking the **Add Root** button.</span></span> <span data-ttu-id="d5873-111">그런 다음 루트 또는 다른 노드를 선택 하 고 **자식 추가** 단추를 클릭 하 여 자식 노드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5873-111">You can then add child nodes by selecting the root or any other node and clicking the **Add Child** button.</span></span>

4. <span data-ttu-id="d5873-112">노드를 삭제 하려면 삭제할 노드를 선택 하 고 **삭제** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5873-112">To delete nodes, select the node to delete and then click the **Delete** button.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5873-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d5873-113">See also</span></span>

- [<span data-ttu-id="d5873-114">TreeView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="d5873-114">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="d5873-115">TreeView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="d5873-115">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="d5873-116">방법: Windows Forms TreeView 컨트롤의 아이콘 설정</span><span class="sxs-lookup"><span data-stu-id="d5873-116">How to: Set Icons for the Windows Forms TreeView Control</span></span>](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="d5873-117">방법: Windows Forms TreeView 컨트롤의 모든 노드를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5873-117">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="d5873-118">방법: 클릭 한 TreeView 노드 확인</span><span class="sxs-lookup"><span data-stu-id="d5873-118">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="d5873-119">방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가 (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="d5873-119">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
