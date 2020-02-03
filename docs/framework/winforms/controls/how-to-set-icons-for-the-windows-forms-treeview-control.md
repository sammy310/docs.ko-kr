---
title: TreeView 컨트롤의 아이콘 설정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], node icons
- ImageList component [Windows Forms], adding images
- icons [Windows Forms], setting for TreeView control
- tree nodes in TreeView control [Windows Forms], icons
ms.assetid: c14ddcc0-e5a6-4c21-a2d5-6799fd491781
ms.openlocfilehash: e3d7fc35c6d9f70822cdd0b69dd12f3d469f4ffa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737271"
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a><span data-ttu-id="2efb8-102">방법: Windows Forms TreeView 컨트롤의 아이콘 설정</span><span class="sxs-lookup"><span data-stu-id="2efb8-102">How to: Set Icons for the Windows Forms TreeView Control</span></span>
<span data-ttu-id="2efb8-103">Windows Forms <xref:System.Windows.Forms.TreeView> 컨트롤은 각 노드 옆에 아이콘을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2efb8-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control can display icons next to each node.</span></span> <span data-ttu-id="2efb8-104">아이콘은 노드 텍스트의 바로 왼쪽에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2efb8-104">The icons are positioned to the immediate left of the node text.</span></span> <span data-ttu-id="2efb8-105">이러한 아이콘을 표시 하려면 트리 뷰를 <xref:System.Windows.Forms.ImageList> 컨트롤과 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2efb8-105">To display these icons, you must associate the tree view with an <xref:System.Windows.Forms.ImageList> control.</span></span> <span data-ttu-id="2efb8-106">이미지 목록에 대 한 자세한 내용은 [Imagelist 구성 요소](imagelist-component-windows-forms.md) 및 [방법: Windows Forms imagelist 구성 요소를 사용 하 여 이미지 추가 또는 제거](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2efb8-106">For more information about image lists, see [ImageList Component](imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2efb8-107">Microsoft .NET Framework 버전 1.1의 버그로 인해 응용 프로그램에서 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>를 호출할 때 이미지가 <xref:System.Windows.Forms.TreeView> 노드에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2efb8-107">A bug in Microsoft .NET Framework version 1.1 prevents images from appearing on <xref:System.Windows.Forms.TreeView> nodes when your application calls <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2efb8-108">이 버그를 해결 하려면 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>를 호출한 직후 `Main` 메서드에서 <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType>를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="2efb8-108">To work around this bug, call <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> in your `Main` method immediately after calling <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.</span></span> <span data-ttu-id="2efb8-109">이 버그는 .NET Framework 2.0에서 수정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2efb8-109">This bug is fixed in .NET Framework 2.0.</span></span>  
  
### <a name="to-display-images-in-a-tree-view"></a><span data-ttu-id="2efb8-110">트리 뷰에서 이미지를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="2efb8-110">To display images in a tree view</span></span>  
  
1. <span data-ttu-id="2efb8-111"><xref:System.Windows.Forms.TreeView> 컨트롤의 <xref:System.Windows.Forms.TreeView.ImageList%2A> 속성을 사용 하려는 기존 <xref:System.Windows.Forms.ImageList> 컨트롤로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2efb8-111">Set the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.ImageList%2A> property to the existing <xref:System.Windows.Forms.ImageList> control you wish to use.</span></span>  
  
     <span data-ttu-id="2efb8-112">이러한 속성은 디자이너에서 속성 창 또는 코드를 사용 하 여 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2efb8-112">These properties can be set in the designer with the Properties window, or in code.</span></span>  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2. <span data-ttu-id="2efb8-113">노드의 <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> 및 <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2efb8-113">Set the node's <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> and <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> properties.</span></span> <span data-ttu-id="2efb8-114"><xref:System.Windows.Forms.TreeNode.ImageIndex%2A> 속성은 노드의 일반 및 확장 된 상태에 대해 표시 되는 이미지를 결정 하 고 <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> 속성은 노드의 선택 된 상태에 대해 표시 되는 이미지를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2efb8-114">The <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> property determines the image displayed for the node's normal and expanded states, and the <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> property determines the image displayed for the node's selected state.</span></span>  
  
     <span data-ttu-id="2efb8-115">이러한 속성은 코드 또는 TreeNode 편집기 내에서 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2efb8-115">These properties can be set in code, or within the TreeNode Editor.</span></span> <span data-ttu-id="2efb8-116">TreeNode 편집기를 열려면 속성 창의 <xref:System.Windows.Forms.TreeView.Nodes%2A> 속성 옆에 있는 줄임표 단추 (...)를 클릭 하 여](./media/visual-studio-ellipsis-button.png)의 속성 옆에 있는 줄임표 단추 (... 속성 창)를 ![합니다.</span><span class="sxs-lookup"><span data-stu-id="2efb8-116">To open the TreeNode Editor, click the ellipsis button ( ![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.TreeView.Nodes%2A> property on the Properties window.</span></span>  
  
    ```vb  
    ' (Assumes that ImageList1 contains at least two images and  
    ' the TreeView control contains a selected image.)  
    TreeView1.SelectedNode.ImageIndex = 0  
    TreeView1.SelectedNode.SelectedImageIndex = 1  
    ```  
  
    ```csharp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1.SelectedNode.ImageIndex = 0;  
    treeView1.SelectedNode.SelectedImageIndex = 1;  
    ```  
  
    ```cpp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1->SelectedNode->ImageIndex = 0;  
    treeView1->SelectedNode->SelectedImageIndex = 1;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2efb8-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2efb8-117">See also</span></span>

- [<span data-ttu-id="2efb8-118">TreeView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="2efb8-118">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="2efb8-119">방법: Windows Forms TreeView 컨트롤을 사용하여 노드 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="2efb8-119">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="2efb8-120">방법: Windows Forms TreeView 컨트롤의 노드 전체 반복</span><span class="sxs-lookup"><span data-stu-id="2efb8-120">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="2efb8-121">방법: 클릭한 TreeView 노드 확인</span><span class="sxs-lookup"><span data-stu-id="2efb8-121">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="2efb8-122">방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="2efb8-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
