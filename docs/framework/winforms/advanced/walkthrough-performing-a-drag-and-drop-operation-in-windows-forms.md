---
title: '연습: 끌어서 놓기 작업 수행'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
ms.openlocfilehash: b5e4bf753733cb9bd010672f40e8fbeb0cf036bf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182438"
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a>연습: Windows Forms에서 끌어서 놓기 작업 수행
Windows 기반 응용 프로그램 내에서 끌어서 놓기 작업을 수행하려면 일련의 이벤트(특히 <xref:System.Windows.Forms.Control.DragEnter> <xref:System.Windows.Forms.Control.DragLeave>는 <xref:System.Windows.Forms.Control.DragDrop> ? 및 이벤트)를 처리해야 합니다. 이러한 이벤트의 이벤트 인수에서 제공하는 정보를 사용하면 끌어서 놓기 작업을 쉽게 구현할 수 있습니다.  
  
## <a name="dragging-data"></a>데이터 끌기  
 모든 끌어서 놓기 작업은 끌기에서 시작됩니다. 드래그가 시작될 때 데이터를 수집할 수 있도록 <xref:System.Windows.Forms.Control.DoDragDrop%2A> 하는 기능이 메서드에서 구현됩니다.  
  
 다음 예제에서는 <xref:System.Windows.Forms.Control.MouseDown> 이벤트가 가장 직관적이기 때문에 드래그 작업을 시작하는 데 사용됩니다(대부분의 끌어서 놓기 작업은 마우스 단추를 누르는 것으로 시작됨). 그러나 모든 이벤트는 끌어서 놓기 프로시저를 시작할 수 있습니다.  
  
> [!NOTE]
> 특정 컨트롤에는 사용자 지정 끌기 관련 이벤트가 있습니다. 및 <xref:System.Windows.Forms.ListView> <xref:System.Windows.Forms.TreeView> 컨트롤에는 예를 들어 <xref:System.Windows.Forms.TreeView.ItemDrag> 이벤트가 있습니다.  
  
#### <a name="to-start-a-drag-operation"></a>끌기 작업을 시작하려면  
  
1. 드래그가 <xref:System.Windows.Forms.Control.MouseDown> 시작되는 컨트롤의 경우 메서드를 `DoDragDrop` 사용하여 데이터를 드래그할 수 있도록 설정하고 허용된 효과 끌기를 갖습니다. 자세한 내용은 <xref:System.Windows.Forms.DragEventArgs.Data%2A> 및 <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>를 참조하세요.  
  
     다음 예제에서는 끌기 작업을 시작하는 방법을 보여 줍니다. 끌기가 시작되는 컨트롤은 <xref:System.Windows.Forms.Button> 컨트롤이고, 드래그하는 데이터는 <xref:System.Windows.Forms.Control.Text%2A> <xref:System.Windows.Forms.Button> 컨트롤의 속성을 나타내는 문자열이며 허용된 효과는 복사 또는 이동중입니다.  
  
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
    > 모든 데이터는 메서드의 `DoDragDrop` 매개 변수로 사용할 수 있습니다. 위의 예에서 컨트롤의 속성은 속성이 <xref:System.Windows.Forms.Control.Text%2A> <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Button> (컨트롤)에서 드래그되는 위치와 관련이 있기 때문에 (값을 하드 코딩하거나 데이터 집합에서 데이터를 검색하는 대신) 사용되었습니다. 끌어서 놓기 작업을 Windows 기반 애플리케이션에 통합할 때 이 점을 명심해 주세요.  
  
 끌기 작업이 적용되는 동안 시스템의 "권한 <xref:System.Windows.Forms.Control.QueryContinueDrag> 요청"으로 드래그 작업을 계속하는 이벤트를 처리할 수 있습니다. 이 메서드를 처리할 때 커서가 위로 마우스를 가져간 경우 <xref:System.Windows.Forms.TreeNode> <xref:System.Windows.Forms.TreeView> 컨트롤에서 를 확장하는 등 드래그 작업에 영향을 주는 메서드를 호출하는 것이 적절한 지점이기도 합니다.  
  
## <a name="dropping-data"></a>데이터 놓기  
 Windows Form 또는 컨트롤의 위치에서 데이터를 끌기 시작하면 당연히 다른 위치에 놓으려고 할 것입니다. 데이터를 놓도록 올바르게 구성된 양식이나 컨트롤의 영역 위에서 움직이면 커서가 변경됩니다. Windows 양식 또는 컨트롤 내의 모든 영역은 <xref:System.Windows.Forms.Control.AllowDrop%2A> 속성을 설정하고 <xref:System.Windows.Forms.Control.DragEnter> 및 <xref:System.Windows.Forms.Control.DragDrop> 이벤트를 처리하여 삭제된 데이터를 수락하도록 할 수 있습니다.  
  
#### <a name="to-perform-a-drop"></a>놓기 작업을 수행하려면  
  
1. <xref:System.Windows.Forms.Control.AllowDrop%2A> 속성을 true로 설정합니다.  
  
2. 드롭이 `DragEnter` 발생하는 컨트롤의 경우 드래그되는 데이터가 허용 가능한 형식인지 확인합니다(이 <xref:System.Windows.Forms.Control.Text%2A>경우). 그런 다음 코드는 드롭이 <xref:System.Windows.Forms.DragDropEffects> 열거형의 값으로 발생할 때 발생하는 효과를 설정합니다. 자세한 내용은 <xref:System.Windows.Forms.DragEventArgs.Effect%2A>을 참조하세요.  
  
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
    > 사용자 고유의 <xref:System.Windows.Forms.DataFormats> 개체를 <xref:System.Windows.Forms.DataObject.SetData%2A> 메서드의 매개 <xref:System.Object> 변수로 지정하여 사용자 고유를 정의할 수 있습니다. 이 작업을 수행할 때 지정된 개체는 직렬화(serialize)할 수 있어야 합니다. 자세한 내용은 <xref:System.Runtime.Serialization.ISerializable>을 참조하세요.  
  
3. 드롭이 <xref:System.Windows.Forms.Control.DragDrop> 발생할 컨트롤의 경우 메서드를 <xref:System.Windows.Forms.DataObject.GetData%2A> 사용하여 드래그되는 데이터를 검색합니다. 자세한 내용은 <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>을 참조하세요.  
  
     아래 예제에서 <xref:System.Windows.Forms.TextBox> 컨트롤은 컨트롤을 드래그하는 것입니다(드롭이 발생하는 위치). 코드는 드래그되는 데이터와 <xref:System.Windows.Forms.TextBox> 동일한 컨트롤의 <xref:System.Windows.Forms.Control.Text%2A> 속성을 설정합니다.  
  
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
    > 또한 <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> 끌어서 놓기 작업 중에 누른 키에 따라 특정 효과가 발생하도록 속성으로 작업할 수 있습니다(예: CTRL 키를 누를 때 드래그된 데이터를 복사하는 것이 표준임).  
  
## <a name="see-also"></a>참고 항목

- [방법: 클립보드에 데이터 추가](how-to-add-data-to-the-clipboard.md)
- [방법: 클립보드에서 데이터 검색](how-to-retrieve-data-from-the-clipboard.md)
- [끌어서 놓기 작업 및 클립보드 지원](drag-and-drop-operations-and-clipboard-support.md)
