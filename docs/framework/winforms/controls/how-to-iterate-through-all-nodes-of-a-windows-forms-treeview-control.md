---
title: TreeView 컨트롤의 모든 노드를 반복 합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], iterating through nodes
- tree nodes in TreeView control [Windows Forms], iterating through
ms.assetid: 427f8928-ebcf-4beb-887f-695b905d5134
ms.openlocfilehash: 010932fa3fdfaa907325b9934682dcbf889265c1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736372"
---
# <a name="how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control"></a><span data-ttu-id="3e8b4-102">방법: Windows Forms TreeView 컨트롤의 노드 전체 반복</span><span class="sxs-lookup"><span data-stu-id="3e8b4-102">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>
<span data-ttu-id="3e8b4-103">경우에 따라 노드 값에 대해 계산을 수행 하기 위해 Windows Forms <xref:System.Windows.Forms.TreeView> 컨트롤의 모든 노드를 검사 하는 것이 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e8b4-103">It is sometimes useful to examine every node in a Windows Forms <xref:System.Windows.Forms.TreeView> control in order to perform some calculation on the node values.</span></span> <span data-ttu-id="3e8b4-104">트리의 각 컬렉션의 각 노드를 반복하는 재귀 프로시저(C# 및 C++의 재귀 메서드)를 사용하여 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e8b4-104">This operation can be done using a recursive procedure (recursive method in C# and C++) that iterates through each node in each collection of the tree.</span></span>  
  
 <span data-ttu-id="3e8b4-105">트리 뷰의 각 <xref:System.Windows.Forms.TreeNode> 개체에는 <xref:System.Windows.Forms.TreeNode.FirstNode%2A>, <xref:System.Windows.Forms.TreeNode.LastNode%2A>, <xref:System.Windows.Forms.TreeNode.NextNode%2A>, <xref:System.Windows.Forms.TreeNode.PrevNode%2A>및 <xref:System.Windows.Forms.TreeNode.Parent%2A>트리 뷰를 탐색 하는 데 사용할 수 있는 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e8b4-105">Each <xref:System.Windows.Forms.TreeNode> object in a tree view has properties that you can use to navigate the tree view: <xref:System.Windows.Forms.TreeNode.FirstNode%2A>, <xref:System.Windows.Forms.TreeNode.LastNode%2A>, <xref:System.Windows.Forms.TreeNode.NextNode%2A>, <xref:System.Windows.Forms.TreeNode.PrevNode%2A>, and <xref:System.Windows.Forms.TreeNode.Parent%2A>.</span></span> <span data-ttu-id="3e8b4-106"><xref:System.Windows.Forms.TreeNode.Parent%2A> 속성의 값은 현재 노드의 부모 노드입니다.</span><span class="sxs-lookup"><span data-stu-id="3e8b4-106">The value of the <xref:System.Windows.Forms.TreeNode.Parent%2A> property is the parent node of the current node.</span></span> <span data-ttu-id="3e8b4-107">현재 노드의 자식 노드 (있는 경우)는 해당 <xref:System.Windows.Forms.TreeNode.Nodes%2A> 속성에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e8b4-107">The child nodes of the current node, if there are any, are listed in its <xref:System.Windows.Forms.TreeNode.Nodes%2A> property.</span></span> <span data-ttu-id="3e8b4-108"><xref:System.Windows.Forms.TreeView> 컨트롤 자체에는 전체 트리 뷰의 루트 노드인 <xref:System.Windows.Forms.TreeView.TopNode%2A> 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e8b4-108">The <xref:System.Windows.Forms.TreeView> control itself has the <xref:System.Windows.Forms.TreeView.TopNode%2A> property, which is the root node of the entire tree view.</span></span>  
  
### <a name="to-iterate-through-all-nodes-of-the-treeview-control"></a><span data-ttu-id="3e8b4-109">TreeView 컨트롤의 노드 전체를 반복하려면</span><span class="sxs-lookup"><span data-stu-id="3e8b4-109">To iterate through all nodes of the TreeView control</span></span>  
  
1. <span data-ttu-id="3e8b4-110">각 노드를 테스트하는 재귀 프로시저(C# 및 C++의 재귀 메서드)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3e8b4-110">Create a recursive procedure (recursive method in C# and C++) that tests each node.</span></span>  
  
2. <span data-ttu-id="3e8b4-111">프로시저를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="3e8b4-111">Call the procedure.</span></span>  
  
     <span data-ttu-id="3e8b4-112">다음 예제에서는 각 <xref:System.Windows.Forms.TreeNode> 개체의 <xref:System.Windows.Forms.TreeNode.Text%2A> 속성을 인쇄 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3e8b4-112">The following example shows how to print each <xref:System.Windows.Forms.TreeNode> object's <xref:System.Windows.Forms.TreeNode.Text%2A> property:</span></span>  
  
    ```vb  
    Private Sub PrintRecursive(ByVal n As TreeNode)  
       System.Diagnostics.Debug.WriteLine(n.Text)  
       MessageBox.Show(n.Text)  
       Dim aNode As TreeNode  
       For Each aNode In n.Nodes  
          PrintRecursive(aNode)  
       Next  
    End Sub  
  
    ' Call the procedure using the top nodes of the treeview.  
    Private Sub CallRecursive(ByVal aTreeView As TreeView)  
       Dim n As TreeNode  
       For Each n In aTreeView.Nodes  
          PrintRecursive(n)  
       Next  
    End Sub  
    ```  
  
    ```csharp  
    private void PrintRecursive(TreeNode treeNode)  
    {  
       // Print the node.  
       System.Diagnostics.Debug.WriteLine(treeNode.Text);  
       MessageBox.Show(treeNode.Text);  
       // Print each node recursively.  
       foreach (TreeNode tn in treeNode.Nodes)  
       {  
          PrintRecursive(tn);  
       }  
    }  
  
    // Call the procedure using the TreeView.  
    private void CallRecursive(TreeView treeView)  
    {  
       // Print each node recursively.  
       TreeNodeCollection nodes = treeView.Nodes;  
       foreach (TreeNode n in nodes)  
       {  
          PrintRecursive(n);  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void PrintRecursive( TreeNode^ treeNode )  
       {  
          // Print the node.  
          System::Diagnostics::Debug::WriteLine( treeNode->Text );  
          MessageBox::Show( treeNode->Text );  
  
          // Print each node recursively.  
          System::Collections::IEnumerator^ myNodes = (safe_cast<System::Collections::IEnumerable^>(treeNode->Nodes))->GetEnumerator();  
          try  
          {  
             while ( myNodes->MoveNext() )  
             {  
                TreeNode^ tn = safe_cast<TreeNode^>(myNodes->Current);  
                PrintRecursive( tn );  
             }  
          }  
          finally  
          {  
             IDisposable^ disposable = dynamic_cast<System::IDisposable^>(myNodes);  
             if ( disposable != nullptr )  
                      disposable->Dispose();  
          }  
       }  
  
       // Call the procedure using the TreeView.  
       void CallRecursive( TreeView^ treeView )  
       {  
          // Print each node recursively.  
          TreeNodeCollection^ nodes = treeView->Nodes;  
          System::Collections::IEnumerator^ myNodes = (safe_cast<System::Collections::IEnumerable^>(nodes))->GetEnumerator();  
          try  
          {  
             while ( myNodes->MoveNext() )  
             {  
                TreeNode^ n = safe_cast<TreeNode^>(myNodes->Current);  
                PrintRecursive( n );  
             }  
          }  
          finally  
          {  
             IDisposable^ disposable = dynamic_cast<System::IDisposable^>(myNodes);  
             if ( disposable != nullptr )  
                      disposable->Dispose();  
          }  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3e8b4-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3e8b4-113">See also</span></span>

- [<span data-ttu-id="3e8b4-114">TreeView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="3e8b4-114">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="3e8b4-115">재귀 프로시저</span><span class="sxs-lookup"><span data-stu-id="3e8b4-115">Recursive Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)
