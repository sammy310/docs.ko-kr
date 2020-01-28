---
title: TreeView 컨트롤을 사용 하 여 노드 추가 및 제거
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
ms.openlocfilehash: 02b3a7286798c6f2a6426e09c8fc6c18b74a6bf0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731967"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control"></a>방법: Windows Forms TreeView 컨트롤을 사용하여 노드 추가 및 제거
Windows Forms <xref:System.Windows.Forms.TreeView> 컨트롤은 <xref:System.Windows.Forms.TreeView.Nodes%2A> 컬렉션에 최상위 노드를 저장 합니다. 각 <xref:System.Windows.Forms.TreeNode>에는 해당 자식 노드를 저장 하는 고유한 <xref:System.Windows.Forms.TreeNode.Nodes%2A> 컬렉션이 있습니다. 두 컬렉션 속성은 모두 노드 계층의 단일 수준에서 노드를 추가, 제거 및 다시 정렬할 수 있는 표준 컬렉션 멤버를 제공 하는 <xref:System.Windows.Forms.TreeNodeCollection>유형입니다.  
  
### <a name="to-add-nodes-programmatically"></a>프로그래밍 방식으로 노드를 추가 하려면  
  
1. 트리 뷰의 <xref:System.Windows.Forms.TreeView.Nodes%2A> 속성에 <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> 메서드를 사용 합니다.  
  
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
  
### <a name="to-remove-nodes-programmatically"></a>프로그래밍 방식으로 노드를 제거 하려면  
  
1. 트리 뷰의 <xref:System.Windows.Forms.TreeView.Nodes%2A> 속성의 <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> 메서드를 사용 하 여 단일 노드를 제거 하거나 <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> 메서드를 사용 하 여 모든 노드를 지웁니다.  
  
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
  
## <a name="see-also"></a>참조

- [TreeView 컨트롤](treeview-control-windows-forms.md)
- [TreeView 컨트롤 개요](treeview-control-overview-windows-forms.md)
- [방법: Windows Forms TreeView 컨트롤의 아이콘 설정](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [방법: Windows Forms TreeView 컨트롤의 노드 전체 반복](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [방법: 클릭한 TreeView 노드 확인](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
