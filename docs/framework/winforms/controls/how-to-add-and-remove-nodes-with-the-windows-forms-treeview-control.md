---
title: TreeView 컨트롤을 통해 노드 추가 및 제거
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
ms.openlocfilehash: f1e74e6d2f827167c32a6955b3010b59cb2f85b8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142214"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control"></a><span data-ttu-id="6e468-102">방법: Windows Forms TreeView 컨트롤을 사용하여 노드 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="6e468-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>
<span data-ttu-id="6e468-103">Windows Forms <xref:System.Windows.Forms.TreeView> 컨트롤은 <xref:System.Windows.Forms.TreeView.Nodes%2A> 컬렉션에 최상위 노드를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="6e468-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control stores the top-level nodes in its <xref:System.Windows.Forms.TreeView.Nodes%2A> collection.</span></span> <span data-ttu-id="6e468-104">각각에는 <xref:System.Windows.Forms.TreeNode> 자식 <xref:System.Windows.Forms.TreeNode.Nodes%2A> 노드를 저장하는 자체 컬렉션도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e468-104">Each <xref:System.Windows.Forms.TreeNode> also has its own <xref:System.Windows.Forms.TreeNode.Nodes%2A> collection to store its child nodes.</span></span> <span data-ttu-id="6e468-105">두 컬렉션 속성은 <xref:System.Windows.Forms.TreeNodeCollection>모두 노드 계층구조의 단일 수준에서 노드를 추가, 제거 및 재정렬할 수 있는 표준 컬렉션 멤버를 제공하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6e468-105">Both collection properties are of type <xref:System.Windows.Forms.TreeNodeCollection>, which provides standard collection members that enable you to add, remove, and rearrange the nodes at a single level of the node hierarchy.</span></span>  
  
### <a name="to-add-nodes-programmatically"></a><span data-ttu-id="6e468-106">프로그래밍 방식으로 노드를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="6e468-106">To add nodes programmatically</span></span>  
  
1. <span data-ttu-id="6e468-107">트리 <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> 뷰의 속성 의 <xref:System.Windows.Forms.TreeView.Nodes%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6e468-107">Use the <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>  
  
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
  
### <a name="to-remove-nodes-programmatically"></a><span data-ttu-id="6e468-108">프로그래밍 방식으로 노드를 제거하려면</span><span class="sxs-lookup"><span data-stu-id="6e468-108">To remove nodes programmatically</span></span>  
  
1. <span data-ttu-id="6e468-109">트리 <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> 뷰의 <xref:System.Windows.Forms.TreeView.Nodes%2A> 속성 메서드를 사용하여 단일 노드를 제거하거나 메서드를 <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> 사용하여 모든 노드를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="6e468-109">Use the <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property to remove a single node, or the <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> method to clear all nodes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6e468-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e468-110">See also</span></span>

- [<span data-ttu-id="6e468-111">TreeView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="6e468-111">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="6e468-112">TreeView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="6e468-112">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="6e468-113">방법: Windows Forms TreeView 컨트롤의 아이콘 설정</span><span class="sxs-lookup"><span data-stu-id="6e468-113">How to: Set Icons for the Windows Forms TreeView Control</span></span>](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="6e468-114">방법: Windows Forms TreeView 컨트롤의 노드 전체 반복</span><span class="sxs-lookup"><span data-stu-id="6e468-114">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="6e468-115">방법: 클릭한 TreeView 노드 확인</span><span class="sxs-lookup"><span data-stu-id="6e468-115">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="6e468-116">방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="6e468-116">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
