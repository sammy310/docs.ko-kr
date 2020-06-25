---
title: '연습: 끌어서 놓기 작업 수행'
description: System.windows.dragdrop.dragenter>, System.windows.dragdrop.dragleave> 및 DragDrop 이벤트를 비롯 한 일련의 이벤트를 처리 하 여 Windows Forms에서 끌어서 놓기 작업을 수행 하는 방법을 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
ms.openlocfilehash: 83bfda875e2fdec3981bbcb8f8f7be00db342440
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325815"
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a>연습: Windows Forms에서 끌어서 놓기 작업 수행
Windows 기반 응용 프로그램 내에서 끌어서 놓기 작업을 수행 하려면 일련의 이벤트, 특히 <xref:System.Windows.Forms.Control.DragEnter> , 및 이벤트를 처리 해야 합니다 <xref:System.Windows.Forms.Control.DragLeave> <xref:System.Windows.Forms.Control.DragDrop> . 이러한 이벤트의 이벤트 인수에서 제공하는 정보를 사용하면 끌어서 놓기 작업을 쉽게 구현할 수 있습니다.  
  
## <a name="dragging-data"></a>데이터 끌기  
 모든 끌어서 놓기 작업은 끌기에서 시작됩니다. 끌기를 시작할 때 데이터를 수집할 수 있도록 하는 기능을 메서드에서 구현할 수 <xref:System.Windows.Forms.Control.DoDragDrop%2A> 있습니다.  
  
 다음 예제에서는 <xref:System.Windows.Forms.Control.MouseDown> 가장 직관적 이기 때문에 끌기 작업을 시작 하는 데 사용 됩니다. 대부분의 끌어서 놓기 작업은 마우스 단추를 누른 상태로 시작 됩니다. 그러나 모든 이벤트는 끌어서 놓기 프로시저를 시작할 수 있습니다.  
  
> [!NOTE]
> 특정 컨트롤에는 사용자 지정 끌기 관련 이벤트가 있습니다. 예를 들어 <xref:System.Windows.Forms.ListView> 및 컨트롤에는 <xref:System.Windows.Forms.TreeView> <xref:System.Windows.Forms.TreeView.ItemDrag> 이벤트가 있습니다.  
  
#### <a name="to-start-a-drag-operation"></a>끌기 작업을 시작하려면  
  
1. <xref:System.Windows.Forms.Control.MouseDown>끌기가 시작 되는 컨트롤에 대 한 이벤트에서 메서드를 사용 `DoDragDrop` 하 여 끌어올 데이터를 설정 하 고 허용 되는 끌기 효과를 갖게 됩니다. 자세한 내용은 <xref:System.Windows.Forms.DragEventArgs.Data%2A> 및 <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>를 참조하세요.  
  
     다음 예제에서는 끌기 작업을 시작하는 방법을 보여 줍니다. 끌기가 시작 되는 컨트롤은 컨트롤이 고 <xref:System.Windows.Forms.Button> , 끌고 있는 데이터는 <xref:System.Windows.Forms.Control.Text%2A> 컨트롤의 속성을 나타내는 문자열이 <xref:System.Windows.Forms.Button> 고, 허용 되는 효과는 복사 또는 이동 중 하나입니다.  
  
    ```vb  
    Private Sub Button1_MouseDown(ByVal sender As Object, ByVal e As System.Windows.Forms.MouseEventArgs) Handles Button1.MouseDown  
       Button1.DoDragDrop(Button1.Text, DragDropEffects.Copy Or DragDropEffects.Move)  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_MouseDown(object sender,
    System.Windows.Forms.MouseEventArgs e)  
    {  
       button1.DoDragDrop(button1.Text, DragDropEffects.Copy |
          DragDropEffects.Move);  
    }  
    ```  
  
    > [!NOTE]
    > 모든 데이터를 메서드에서 매개 변수로 사용할 수 있습니다 `DoDragDrop` . 위의 예제에서 <xref:System.Windows.Forms.Control.Text%2A> <xref:System.Windows.Forms.Button> 속성은 컨트롤에서 끌고 있는 위치와 관련 되어 있으므로 값을 하드 코딩 하거나 데이터 집합에서 데이터를 검색 하는 대신 컨트롤의 속성을 사용 했습니다 <xref:System.Windows.Forms.Button> . 끌어서 놓기 작업을 Windows 기반 애플리케이션에 통합할 때 이 점을 명심해 주세요.  
  
 끌기 작업이 적용 되는 동안 <xref:System.Windows.Forms.Control.QueryContinueDrag> 시스템의 "권한 요청"을 통해 끌기 작업을 계속 하는 이벤트를 처리할 수 있습니다. 이 메서드를 처리할 때 <xref:System.Windows.Forms.TreeNode> <xref:System.Windows.Forms.TreeView> 커서를 커서를 가져갈 때 컨트롤의를 확장 하는 것과 같이 끌기 작업에 영향을 주는 메서드를 호출 하는 것도 적절 한 지점입니다.  
  
## <a name="dropping-data"></a>데이터 놓기  
 Windows Form 또는 컨트롤의 위치에서 데이터를 끌기 시작하면 당연히 다른 위치에 놓으려고 할 것입니다. 데이터를 놓도록 올바르게 구성된 양식이나 컨트롤의 영역 위에서 움직이면 커서가 변경됩니다. 속성을 설정 <xref:System.Windows.Forms.Control.AllowDrop%2A> 하 고 및 이벤트를 처리 하 여 삭제 된 데이터를 허용 하도록 Windows Form 또는 컨트롤 내에서 영역을 만들 수 있습니다 <xref:System.Windows.Forms.Control.DragEnter> <xref:System.Windows.Forms.Control.DragDrop> .  
  
#### <a name="to-perform-a-drop"></a>놓기 작업을 수행하려면  
  
1. 속성을 <xref:System.Windows.Forms.Control.AllowDrop%2A> true로 설정 합니다.  
  
2. `DragEnter`놓기 작업이 발생 하는 컨트롤에 대 한 이벤트에서 끌고 있는 데이터가 허용 되는 형식 (이 경우) 인지 확인 <xref:System.Windows.Forms.Control.Text%2A> 합니다. 그런 다음 코드에서 열거형의 값에 대 한 drop이 발생할 때 발생 하는 효과를 설정 합니다 <xref:System.Windows.Forms.DragDropEffects> . 자세한 내용은 <xref:System.Windows.Forms.DragEventArgs.Effect%2A>를 참조하세요.  
  
    ```vb  
    Private Sub TextBox1_DragEnter(ByVal sender As Object, ByVal e As System.Windows.Forms.DragEventArgs) Handles TextBox1.DragEnter  
       If (e.Data.GetDataPresent(DataFormats.Text)) Then  
         e.Effect = DragDropEffects.Copy  
       Else  
         e.Effect = DragDropEffects.None  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_DragEnter(object sender,
    System.Windows.Forms.DragEventArgs e)  
    {  
       if (e.Data.GetDataPresent(DataFormats.Text))
          e.Effect = DragDropEffects.Copy;  
       else  
          e.Effect = DragDropEffects.None;  
    }  
    ```  
  
    > [!NOTE]
    > 사용자 고유의 <xref:System.Windows.Forms.DataFormats> 개체를 <xref:System.Object> 메서드의 매개 변수로 지정 하 여 직접 정의할 수 있습니다 <xref:System.Windows.Forms.DataObject.SetData%2A> . 이 작업을 수행할 때 지정된 개체는 직렬화(serialize)할 수 있어야 합니다. 자세한 내용은 <xref:System.Runtime.Serialization.ISerializable>를 참조하세요.  
  
3. <xref:System.Windows.Forms.Control.DragDrop>놓기 작업이 발생 하는 컨트롤에 대 한 이벤트에서 메서드를 사용 <xref:System.Windows.Forms.DataObject.GetData%2A> 하 여 끌고 있는 데이터를 검색 합니다. 자세한 내용은 <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>를 참조하세요.  
  
     아래 예제에서 <xref:System.Windows.Forms.TextBox> 컨트롤은 놓기가 발생 하는 위치로 끌고 있는 컨트롤입니다. 이 코드는 <xref:System.Windows.Forms.Control.Text%2A> 컨트롤의 속성을 <xref:System.Windows.Forms.TextBox> 끌고 있는 데이터와 동일 하 게 설정 합니다.  
  
    ```vb  
    Private Sub TextBox1_DragDrop(ByVal sender As Object, ByVal e As System.Windows.Forms.DragEventArgs) Handles TextBox1.DragDrop  
       TextBox1.Text = e.Data.GetData(DataFormats.Text).ToString  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_DragDrop(object sender,
    System.Windows.Forms.DragEventArgs e)  
    {  
       textBox1.Text = e.Data.GetData(DataFormats.Text).ToString();  
    }  
    ```  
  
    > [!NOTE]
    > 또한 속성을 사용 하 여 작업을 수행할 수 있습니다 <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> . 이렇게 하면 끌어서 놓기 작업 중에 눌린 키에 따라 특정 효과가 발생 합니다. 예를 들어 CTRL 키를 누를 때 끌어온 데이터를 복사 하는 것이 표준입니다.  
  
## <a name="see-also"></a>참조

- [방법: 클립보드에 데이터 추가](how-to-add-data-to-the-clipboard.md)
- [방법: 클립보드에서 데이터 검색](how-to-retrieve-data-from-the-clipboard.md)
- [끌어서 놓기 작업 및 클립보드 지원](drag-and-drop-operations-and-clipboard-support.md)
