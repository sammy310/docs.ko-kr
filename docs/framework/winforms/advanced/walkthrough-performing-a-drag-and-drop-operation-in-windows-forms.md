---
title: '연습: Windows Forms에서 끌어서 놓기 작업 수행'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
ms.openlocfilehash: f7551f28d07c9517865f60af99954eb40e57daa2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59340726"
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a>연습: Windows Forms에서 끌어서 놓기 작업 수행
Windows 기반 응용 프로그램 내에서 끌어서 놓기 작업을 수행 하는 일련의 이벤트를 가장 주목할 만한 처리 해야 합니다 <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, 및 <xref:System.Windows.Forms.Control.DragDrop> 이벤트입니다. 이러한 이벤트의 이벤트 인수에서 제공하는 정보를 사용하면 끌어서 놓기 작업을 쉽게 구현할 수 있습니다.  
  
## <a name="dragging-data"></a>데이터 끌기  
 모든 끌어서 놓기 작업은 끌기에서 시작됩니다. 끌기를 시작할 때 수집할 데이터를 사용 하도록 설정 하는 기능에서 구현 되는 <xref:System.Windows.Forms.Control.DoDragDrop%2A> 메서드.  
  
 다음 예제에서는 <xref:System.Windows.Forms.Control.MouseDown> 이벤트 가장 직관적 이기 때문에 끌기 작업을 시작 하는 데 사용 됩니다 (대부분의 끌어서 놓기 작업을 누른 마우스 단추를 사용 하 여 시작)입니다. 그러나 모든 이벤트는 끌어서 놓기 프로시저를 시작할 수 있습니다.  
  
> [!NOTE]
>  특정 컨트롤에는 사용자 지정 끌기 관련 이벤트가 있습니다. <xref:System.Windows.Forms.ListView> 하 고 <xref:System.Windows.Forms.TreeView> 컨트롤, 예를 들어 있는 <xref:System.Windows.Forms.TreeView.ItemDrag> 이벤트.  
  
#### <a name="to-start-a-drag-operation"></a>끌기 작업을 시작하려면  
  
1. 에 <xref:System.Windows.Forms.Control.MouseDown> 끌기를 시작할를 사용 하 여 컨트롤에 대 한 이벤트를 `DoDragDrop` 끌 수 데이터를 설정 하는 방법 및 끌기 효과 허용된 해야 합니다. 자세한 내용은 <xref:System.Windows.Forms.DragEventArgs.Data%2A> 및 <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>를 참조하세요.  
  
     다음 예제에서는 끌기 작업을 시작하는 방법을 보여 줍니다. 끌기 시작 되는 컨트롤은는 <xref:System.Windows.Forms.Button> 컨트롤을 끌고 있는 데이터를 나타내는 문자열이 <xref:System.Windows.Forms.Control.Text%2A> 의 속성은 <xref:System.Windows.Forms.Button> 제어 및 허용 되는 효과 복사 또는 이동 합니다.  
  
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
    >  모든 데이터를 매개 변수로 사용할 수는 `DoDragDrop` 메서드 위의 예에서 <xref:System.Windows.Forms.Control.Text%2A> 의 속성은 <xref:System.Windows.Forms.Button> 컨트롤 (하드 코딩 된 값 또는 데이터 집합에서 데이터 검색) 하는 대신 사용한 속성이 관련이 있으므로 끌어오는 위치 (의 <xref:System.Windows.Forms.Button> 컨트롤). 끌어서 놓기 작업을 Windows 기반 애플리케이션에 통합할 때 이 점을 명심해 주세요.  
  
 끌기 작업을 적용 하는 동안 처리할 수는 <xref:System.Windows.Forms.Control.QueryContinueDrag> "권한을 요청" 하는 이벤트의 끌기 작업을 계속 하려면 시스템. 이 메서드를 처리할 때 이기도 끌기 작업 확장에 영향을 줄 수 있는 메서드를 호출할 수에 대 한 적절 한 지점을 <xref:System.Windows.Forms.TreeNode> 에 <xref:System.Windows.Forms.TreeView> 그 위로 커서를 이동할 때 제어 합니다.  
  
## <a name="dropping-data"></a>데이터 놓기  
 Windows Form 또는 컨트롤의 위치에서 데이터를 끌기 시작하면 당연히 다른 위치에 놓으려고 할 것입니다. 데이터를 놓도록 올바르게 구성된 양식이나 컨트롤의 영역 위에서 움직이면 커서가 변경됩니다. Windows 폼 또는 컨트롤 내의 모든 영역을 설정 하 여 끌어 놓은 데이터를 적용할 수 있습니다 합니다 <xref:System.Windows.Forms.Control.AllowDrop%2A> 속성 및 처리 합니다 <xref:System.Windows.Forms.Control.DragEnter> 및 <xref:System.Windows.Forms.Control.DragDrop> 이벤트입니다.  
  
#### <a name="to-perform-a-drop"></a>놓기 작업을 수행하려면  
  
1. 설정 된 <xref:System.Windows.Forms.Control.AllowDrop%2A> 속성을 true로 합니다.  
  
2. 에 `DragEnter` 놓기 작업이 발생 하는 컨트롤에 대 한 이벤트 끌고 있는 데이터 형식이 적합 한지 확인 (이 예제의 경우 <xref:System.Windows.Forms.Control.Text%2A>). 코드에 설정한 값으로 발생 하는 효과 <xref:System.Windows.Forms.DragDropEffects> 열거형입니다. 자세한 내용은 <xref:System.Windows.Forms.DragEventArgs.Effect%2A>을 참조하세요.  
  
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
    >  사용자 고유의 정의할 수 있습니다 <xref:System.Windows.Forms.DataFormats> 으로 고유한 개체를 지정 하 여는 <xref:System.Object> 의 매개 변수는 <xref:System.Windows.Forms.DataObject.SetData%2A> 메서드. 이 작업을 수행할 때 지정된 개체는 직렬화(serialize)할 수 있어야 합니다. 자세한 내용은 <xref:System.Runtime.Serialization.ISerializable>을 참조하세요.  
  
3. 에 <xref:System.Windows.Forms.Control.DragDrop> 놓기 작업이 발생 하는 여기서 사용 하 여 컨트롤에 대 한 이벤트를 <xref:System.Windows.Forms.DataObject.GetData%2A> 끌고 있는 데이터를 검색 하는 방법입니다. 자세한 내용은 <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>을 참조하세요.  
  
     아래 예제에서는 <xref:System.Windows.Forms.TextBox> 컨트롤은 컨트롤 (놓기 작업이 발생 하는 위치) 위치로 끌 합니다. 코드 집합을 <xref:System.Windows.Forms.Control.Text%2A> 속성의는 <xref:System.Windows.Forms.TextBox> 끌고 있는 데이터 컨트롤입니다.  
  
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
    >  또한 작업할 수 있습니다는 <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> 속성인을 끌어서 놓기 작업 중에 누른 키에 따라 특정 효과가 발생 (예를 들어, 것이 표준 CTRL 키를 누를 때 끌어온된 데이터를 복사 하려면).  
  
## <a name="see-also"></a>참고자료

- [방법: 클립보드에 데이터 추가](how-to-add-data-to-the-clipboard.md)
- [방법: 클립보드에서 데이터 검색](how-to-retrieve-data-from-the-clipboard.md)
- [끌어서 놓기 작업 및 클립보드 지원](drag-and-drop-operations-and-clipboard-support.md)
