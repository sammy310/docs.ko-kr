---
title: '방법: 디자이너를 사용하여 Windows Forms TreeView 컨트롤에서 노드 추가 및 제거'
ms.date: 03/30/2017
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
ms.openlocfilehash: ecf0b758a9c45a0354a68b6cbfecdb1c49ab390f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59322630"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a><span data-ttu-id="aa1f6-102">방법: 디자이너를 사용하여 Windows Forms TreeView 컨트롤에서 노드 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="aa1f6-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control Using the Designer</span></span>
<span data-ttu-id="aa1f6-103">Windows Forms 있으므로 <xref:System.Windows.Forms.TreeView> 해당 부모 노드를 주의 기울여야 하는 노드를 추가 하는 경우 컨트롤이 계층적 방식으로 노드를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa1f6-103">Because the Windows Forms <xref:System.Windows.Forms.TreeView> control displays nodes in a hierarchical manner, when adding a node you must pay attention to what its parent node is.</span></span>  
  
 <span data-ttu-id="aa1f6-104">다음 절차를 수행 하려면을 **Windows 응용 프로그램** 포함 하는 양식을 사용 하 여 프로젝트를 <xref:System.Windows.Forms.TreeView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa1f6-104">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="aa1f6-105">이러한 프로젝트 설정에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트를 만듭니다](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 고 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="aa1f6-105">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa1f6-106">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa1f6-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="aa1f6-107">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="aa1f6-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="aa1f6-108">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa1f6-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-or-remove-nodes-in-the-designer"></a><span data-ttu-id="aa1f6-109">추가 하거나 디자이너에서 노드를 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="aa1f6-109">To add or remove nodes in the designer</span></span>  
  
1. <span data-ttu-id="aa1f6-110"><xref:System.Windows.Forms.TreeView> 컨트롤을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="aa1f6-110">Select the <xref:System.Windows.Forms.TreeView> control.</span></span>  
  
2. <span data-ttu-id="aa1f6-111">에 **속성** 창에서 클릭 합니다 **줄임표** (![VisualStudioEllipsesButton 스크린 샷](../media/vbellipsesbutton.png "vbEllipsesButton")) 단추 옆에 <xref:System.Windows.Forms.TreeView.Nodes%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="aa1f6-111">In the **Properties** window, click the **Ellipsis** (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button next to the <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>  
  
     <span data-ttu-id="aa1f6-112">합니다 **트리 노드 편집기** 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="aa1f6-112">The **TreeNode Editor** appears.</span></span>  
  
3. <span data-ttu-id="aa1f6-113">노드를 추가 하려면 루트 노드가 있어야 합니다. 클릭 하 여 루트를 먼저 추가 해야 하나 존재 하지 않는 경우는 **루트 추가** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="aa1f6-113">To add nodes, a root node must exist; if one does not exist, you must first add a root by clicking the **Add Root** button.</span></span> <span data-ttu-id="aa1f6-114">루트 또는 다른 노드를 선택 하 고 클릭 한 다음 자식 노드를 추가할 수 있습니다 합니다 **자식 추가** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="aa1f6-114">You can then add child nodes by selecting the root or any other node and clicking the **Add Child** button.</span></span>  
  
4. <span data-ttu-id="aa1f6-115">노드를 삭제 하려면 삭제 한 다음 클릭 노드를 선택 합니다 **삭제** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="aa1f6-115">To delete nodes, select the node to delete and then click the **Delete** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa1f6-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="aa1f6-116">See also</span></span>

- [<span data-ttu-id="aa1f6-117">TreeView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="aa1f6-117">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="aa1f6-118">TreeView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="aa1f6-118">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="aa1f6-119">방법: Windows Forms TreeView 컨트롤에 대한 아이콘 설정</span><span class="sxs-lookup"><span data-stu-id="aa1f6-119">How to: Set Icons for the Windows Forms TreeView Control</span></span>](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="aa1f6-120">방법: Windows Forms TreeView 컨트롤의 모든 노드 반복</span><span class="sxs-lookup"><span data-stu-id="aa1f6-120">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="aa1f6-121">방법: 클릭한 TreeView 노드 확인</span><span class="sxs-lookup"><span data-stu-id="aa1f6-121">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="aa1f6-122">방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="aa1f6-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
