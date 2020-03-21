---
title: '방법: 클릭한 TreeView 노드 확인'
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
ms.openlocfilehash: d960eaae2aa479e0be74e9a5e4fdbfec8ff411c1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182183"
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a>방법: 클릭한 TreeView 노드 확인(Windows Forms)
Windows Forms <xref:System.Windows.Forms.TreeView> 컨트롤을 사용하여 작업할 때 일반적인 작업은 클릭한 노드를 확인하고 적절하게 응답하는 것입니다.  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a>클릭한 TreeView 노드를 확인하려면  
  
1. 개체를 <xref:System.EventArgs> 사용하여 클릭한 노드 개체에 대한 참조를 반환합니다.  
  
2. 이벤트와 관련된 데이터가 포함된 <xref:System.Windows.Forms.TreeViewEventArgs> 클래스를 확인하여 클릭한 노드를 확인합니다.  
  
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
    > 또는 또는 또는 <xref:System.Windows.Forms.MouseEventArgs> 이벤트 <xref:System.Windows.Forms.Control.MouseDown> <xref:System.Windows.Forms.Control.MouseUp> 중 의 값을 사용하여 <xref:System.Drawing.Point.X%2A> <xref:System.Drawing.Point.Y%2A> 클릭이 발생한 <xref:System.Drawing.Point> 위치의 값을 및 좌표할 수 있습니다. 그런 다음 <xref:System.Windows.Forms.TreeView> 컨트롤의 <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> 메서드를 사용하여 클릭한 노드를 확인합니다.  
  
## <a name="see-also"></a>참고 항목

- [TreeView 컨트롤](treeview-control-windows-forms.md)
