---
title: '방법: 클릭 한 TreeView 노드 확인 (Windows Forms)'
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
ms.openlocfilehash: ab93158daf987e2f19516b8fb3abf80bfe79a12c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967338"
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a><span data-ttu-id="f321b-102">방법: 클릭 한 TreeView 노드 확인 (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="f321b-102">How to: Determine Which TreeView Node Was Clicked (Windows Forms)</span></span>
<span data-ttu-id="f321b-103">Windows Forms <xref:System.Windows.Forms.TreeView> 컨트롤로 작업할 때 일반적인 작업은 클릭 한 노드를 확인 하 고 적절 하 게 응답 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f321b-103">When working with the Windows Forms <xref:System.Windows.Forms.TreeView> control, a common task is to determine which node was clicked, and respond appropriately.</span></span>  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a><span data-ttu-id="f321b-104">클릭 한 TreeView 노드를 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="f321b-104">To determine which TreeView node was clicked</span></span>  
  
1. <span data-ttu-id="f321b-105"><xref:System.EventArgs> 개체를 사용 하 여 클릭 한 노드 개체에 대 한 참조를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f321b-105">Use the <xref:System.EventArgs> object to return a reference to the clicked node object.</span></span>  
  
2. <span data-ttu-id="f321b-106">이벤트와 관련 된 데이터를 포함 하 <xref:System.Windows.Forms.TreeViewEventArgs> 는 클래스를 확인 하 여 클릭 한 노드를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f321b-106">Determine which node was clicked by checking the <xref:System.Windows.Forms.TreeViewEventArgs> class, which contains data related to the event.</span></span>  
  
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
    > <span data-ttu-id="f321b-107"><xref:System.Windows.Forms.MouseEventArgs> <xref:System.Drawing.Point.Y%2A> 또는또는이벤트의를<xref:System.Drawing.Point> 사용 하 여 클릭이 발생 한의 및좌표값을가져올수있습니다.<xref:System.Drawing.Point.X%2A> <xref:System.Windows.Forms.Control.MouseUp> <xref:System.Windows.Forms.Control.MouseDown></span><span class="sxs-lookup"><span data-stu-id="f321b-107">As an alternative, you can use the <xref:System.Windows.Forms.MouseEventArgs> of the <xref:System.Windows.Forms.Control.MouseDown> or <xref:System.Windows.Forms.Control.MouseUp> event to get the <xref:System.Drawing.Point.X%2A> and <xref:System.Drawing.Point.Y%2A> coordinate values of the <xref:System.Drawing.Point> where the click occurred.</span></span> <span data-ttu-id="f321b-108">그런 다음 <xref:System.Windows.Forms.TreeView> 컨트롤의 <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> 메서드를 사용 하 여 클릭 한 노드를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f321b-108">Then, use the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> method to determine which node was clicked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f321b-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="f321b-109">See also</span></span>

- [<span data-ttu-id="f321b-110">TreeView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f321b-110">TreeView Control</span></span>](treeview-control-windows-forms.md)
