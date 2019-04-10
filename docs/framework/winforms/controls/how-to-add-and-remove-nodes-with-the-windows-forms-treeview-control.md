---
title: '방법: Windows Forms TreeView 컨트롤을 사용하여 노드 추가 및 제거'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: de1b82db-4905-449a-9f59-af271a6b6673
ms.openlocfilehash: 1849e3ae88b9805f74b2f792ad53b02aa87e6569
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59209517"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control"></a><span data-ttu-id="bc418-102">방법: Windows Forms TreeView 컨트롤을 사용하여 노드 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="bc418-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>
<span data-ttu-id="bc418-103">Windows Forms <xref:System.Windows.Forms.TreeView> 컨트롤의 최상위 노드를 저장 합니다. 해당 <xref:System.Windows.Forms.TreeView.Nodes%2A> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="bc418-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control stores the top-level nodes in its <xref:System.Windows.Forms.TreeView.Nodes%2A> collection.</span></span> <span data-ttu-id="bc418-104">각 <xref:System.Windows.Forms.TreeNode> 역시 자체 <xref:System.Windows.Forms.TreeNode.Nodes%2A> 해당 자식 노드를 저장 하는 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="bc418-104">Each <xref:System.Windows.Forms.TreeNode> also has its own <xref:System.Windows.Forms.TreeNode.Nodes%2A> collection to store its child nodes.</span></span> <span data-ttu-id="bc418-105">두 컬렉션 속성은 <xref:System.Windows.Forms.TreeNodeCollection>를 추가할 수 있도록 하는 표준 컬렉션 멤버를 제거 및 단일 노드 계층 구조 수준에서 노드를 다시 정렬 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc418-105">Both collection properties are of type <xref:System.Windows.Forms.TreeNodeCollection>, which provides standard collection members that enable you to add, remove, and rearrange the nodes at a single level of the node hierarchy.</span></span>  
  
### <a name="to-add-nodes-programmatically"></a><span data-ttu-id="bc418-106">프로그래밍 방식으로 노드를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="bc418-106">To add nodes programmatically</span></span>  
  
1.  <span data-ttu-id="bc418-107">사용 된 <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> 트리 뷰의 메서드의 <xref:System.Windows.Forms.TreeView.Nodes%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="bc418-107">Use the <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>  
  
    ```vb  
    ' Adds new node as a child node of the currently selected node.  
    Dim newNode As TreeNode = New TreeNode("Text for new node")  
    TreeView1.SelectedNode.Nodes.Add(newNode)  
    ```  
  
    ```csharp  
    // Adds new node as a child node of the currently selected node.  
    TreeNode newNode = new TreeNode("Text for new node");  
    treeView1.SelectedNode.Nodes.Add(newNode);  
    ```  
  
    ```cpp  
    // Adds new node as a child node of the currently selected node.  
    TreeNode ^ newNode = new TreeNode("Text for new node");  
    treeView1->SelectedNode->Nodes->Add(newNode);  
    ```  
  
### <a name="to-remove-nodes-programmatically"></a><span data-ttu-id="bc418-108">프로그래밍 방식으로 노드를 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="bc418-108">To remove nodes programmatically</span></span>  
  
1.  <span data-ttu-id="bc418-109">사용 된 <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> 트리 뷰의 메서드의 <xref:System.Windows.Forms.TreeView.Nodes%2A> 단일 노드를 제거 하려면 속성 또는 <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> 모든 노드를 선택 취소 하는 방법.</span><span class="sxs-lookup"><span data-stu-id="bc418-109">Use the <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property to remove a single node, or the <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> method to clear all nodes.</span></span>  
  
    ```vb  
    ' Removes currently selected node, or root if nothing is selected.  
    TreeView1.Nodes.Remove(TreeView1.SelectedNode)  
    ' Clears all nodes.  
    TreeView1.Nodes.Clear()  
    ```  
  
    ```csharp  
    // Removes currently selected node, or root if nothing   
    // is selected.  
    treeView1.Nodes.Remove(treeView1.SelectedNode);  
    // Clears all nodes.  
    TreeView1.Nodes.Clear();  
    ```  
  
    ```cpp  
    // Removes currently selected node, or root if nothing  
    // is selected.  
    treeView1->Nodes->Remove(treeView1->SelectedNode);  
    // Clears all nodes.  
    treeView1->Nodes->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="bc418-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="bc418-110">See also</span></span>

- [<span data-ttu-id="bc418-111">TreeView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="bc418-111">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="bc418-112">TreeView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="bc418-112">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="bc418-113">방법: Windows Forms TreeView 컨트롤에 대한 아이콘 설정</span><span class="sxs-lookup"><span data-stu-id="bc418-113">How to: Set Icons for the Windows Forms TreeView Control</span></span>](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="bc418-114">방법: Windows Forms TreeView 컨트롤의 모든 노드 반복</span><span class="sxs-lookup"><span data-stu-id="bc418-114">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="bc418-115">방법: 클릭한 TreeView 노드 확인</span><span class="sxs-lookup"><span data-stu-id="bc418-115">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="bc418-116">방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="bc418-116">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
