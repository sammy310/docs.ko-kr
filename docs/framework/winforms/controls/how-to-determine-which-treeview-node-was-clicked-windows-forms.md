---
title: '방법: (Windows Forms) 클릭 한 TreeView 노드 확인'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TreeNode
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- tree nodes in TreeView control [Windows Forms], determining node clicked
- TreeView control [Windows Forms], determining node clicked
ms.assetid: 06a4a191-d918-42af-9f49-956c93eff261
ms.openlocfilehash: 71f13c7b160822c92475d4d03e923b40d4f0454d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771048"
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a><span data-ttu-id="62664-102">방법: (Windows Forms) 클릭 한 TreeView 노드 확인</span><span class="sxs-lookup"><span data-stu-id="62664-102">How to: Determine Which TreeView Node Was Clicked (Windows Forms)</span></span>
<span data-ttu-id="62664-103">Windows Forms를 사용 하 여 작업할 때 <xref:System.Windows.Forms.TreeView> 컨트롤 일반적인 작업을 결정 하는 것 노드 클릭 되었는지 및 적절 하 게 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="62664-103">When working with the Windows Forms <xref:System.Windows.Forms.TreeView> control, a common task is to determine which node was clicked, and respond appropriately.</span></span>  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a><span data-ttu-id="62664-104">클릭 한 TreeView 노드 확인</span><span class="sxs-lookup"><span data-stu-id="62664-104">To determine which TreeView node was clicked</span></span>  
  
1. <span data-ttu-id="62664-105">사용 된 <xref:System.EventArgs> 클릭 한 노드 개체에 대 한 참조를 반환할 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="62664-105">Use the <xref:System.EventArgs> object to return a reference to the clicked node object.</span></span>  
  
2. <span data-ttu-id="62664-106">노드를 확인 하 여 클릭 했는지 확인 합니다 <xref:System.Windows.Forms.TreeViewEventArgs> 이벤트와 관련 된 데이터를 포함 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="62664-106">Determine which node was clicked by checking the <xref:System.Windows.Forms.TreeViewEventArgs> class, which contains data related to the event.</span></span>  
  
    ```vb  
    Private Sub TreeView1_AfterSelect(ByVal sender As System.Object, _  
    ByVal e As System.Windows.Forms.TreeViewEventArgs) Handles TreeView1.AfterSelect  
       ' Determine by checking the Node property of the TreeViewEventArgs.  
       MessageBox.Show(e.Node.Text)  
    End Sub  
    ```  
  
    ```csharp  
    protected void treeView1_AfterSelect (object sender,   
    System.Windows.Forms.TreeViewEventArgs e)  
    {  
       // Determine by checking the Text property.  
       MessageBox.Show(e.Node.Text);  
    }  
    ```  
  
    ```cpp  
    private:  
       void treeView1_AfterSelect(System::Object ^  sender,  
          System::Windows::Forms::TreeViewEventArgs ^  e)  
       {  
          // Determine by checking the Text property.  
          MessageBox::Show(e->Node->Text);  
       }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="62664-107">사용할 수 있습니다는 <xref:System.Windows.Forms.MouseEventArgs> 의 <xref:System.Windows.Forms.Control.MouseDown> 또는 <xref:System.Windows.Forms.Control.MouseUp> 가져올 이벤트를 <xref:System.Drawing.Point.X%2A> 및 <xref:System.Drawing.Point.Y%2A> 좌표 값을 <xref:System.Drawing.Point> 클릭이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="62664-107">As an alternative, you can use the <xref:System.Windows.Forms.MouseEventArgs> of the <xref:System.Windows.Forms.Control.MouseDown> or <xref:System.Windows.Forms.Control.MouseUp> event to get the <xref:System.Drawing.Point.X%2A> and <xref:System.Drawing.Point.Y%2A> coordinate values of the <xref:System.Drawing.Point> where the click occurred.</span></span> <span data-ttu-id="62664-108">그런 다음 사용 합니다 <xref:System.Windows.Forms.TreeView> 컨트롤의 <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> 노드를 클릭 했는지 확인 하는 방법.</span><span class="sxs-lookup"><span data-stu-id="62664-108">Then, use the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> method to determine which node was clicked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62664-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="62664-109">See also</span></span>

- [<span data-ttu-id="62664-110">TreeView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="62664-110">TreeView Control</span></span>](treeview-control-windows-forms.md)
