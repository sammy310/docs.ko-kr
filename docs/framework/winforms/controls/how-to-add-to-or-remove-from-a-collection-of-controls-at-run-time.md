---
title: '방법: 런타임에 컨트롤 컬렉션에서 컨트롤 추가 또는 제거'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- run time [Windows Forms], removing controls
- controls [Windows Forms], adding using collections
- controls collections
- collections [Windows Forms], adding items
- run time [Windows Forms], adding controls
- controls [Windows Forms], removing using collections
ms.assetid: 771bf895-3d5f-469b-a324-3528f343657e
ms.openlocfilehash: 369946581847b4bdcf8bc658aeb94b14c529061c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182285"
---
# <a name="how-to-add-to-or-remove-from-a-collection-of-controls-at-run-time"></a>방법: 런타임에 컨트롤 컬렉션에서 컨트롤 추가 또는 제거
응용 프로그램 개발의 일반적인 작업은 폼의 모든 컨테이너 컨트롤(예: <xref:System.Windows.Forms.Panel> 또는 <xref:System.Windows.Forms.GroupBox> 컨트롤 또는 양식 자체)에 컨트롤을 추가하고 제거하는 것입니다. 디자인 타임에 컨트롤을 패널이나 그룹 상자로 직접 끌어 놓을 수 있습니다. 런타임 시 이러한 컨트롤은 `Controls` 컬렉션을 유지 관리하고 여기서 배치된 컨트롤을 추적합니다.  
  
> [!NOTE]
> 다음 코드 예제는 안에 있는 컨트롤의 컬렉션을 유지하는 모든 컨트롤에 적용됩니다.  
  
### <a name="to-add-a-control-to-a-collection-programmatically"></a>프로그래밍 방식으로 컬렉션에 컨트롤을 추가하려면  
  
1. 추가될 컨트롤의 인스턴스를 만듭니다.  
  
2. 새 컨트롤의 속성을 설정합니다.  
  
3. 부모 컨트롤의 `Controls` 컬렉션에 컨트롤을 추가합니다.  
  
     다음 코드 예제에서는 <xref:System.Windows.Forms.Button> 컨트롤의 인스턴스를 만드는 방법을 보여 주며 있습니다. <xref:System.Windows.Forms.Panel> 컨트롤이 있는 폼이 필요하며 단추를 만드는 `NewPanelButton_Click`이벤트 처리 메서드가 이미 있습니다.  
  
    ```vb  
    Public NewPanelButton As New Button()  
  
    Public Sub AddNewControl()  
       ' The Add method will accept as a parameter any object that derives  
       ' from the Control class. In this case, it is a Button control.  
       Panel1.Controls.Add(NewPanelButton)  
       ' The event handler indicated for the Click event in the code
       ' below is used as an example. Substite the appropriate event  
       ' handler for your application.  
       AddHandler NewPanelButton.Click, AddressOf NewPanelButton_Click  
    End Sub  
    ```  
  
    ```csharp  
    public Button newPanelButton = new Button();  
  
    public void addNewControl()  
    {
       // The Add method will accept as a parameter any object that derives  
       // from the Control class. In this case, it is a Button control.  
       panel1.Controls.Add(newPanelButton);  
       // The event handler indicated for the Click event in the code
       // below is used as an example. Substitute the appropriate event  
       // handler for your application.  
       this.newPanelButton.Click += new System.EventHandler(this. NewPanelButton_Click);  
    }  
    ```  
  
### <a name="to-remove-controls-from-a-collection-programmatically"></a>컬렉션에서 컨트롤을 프로그래밍 방식으로 제거하려면  
  
1. 이벤트에서 이벤트 처리기를 제거합니다. 시각적 기본에서 [RemoveHandler 문](../../../visual-basic/language-reference/statements/removehandler-statement.md) 키워드를 사용 합니다. C#에서 [-= 연산자](../../../csharp/language-reference/operators/subtraction-operator.md)를 사용합니다.  
  
2. `Remove` 메서드를 사용하여 패널의 `Controls` 컬렉션에서 원하는 컨트롤을 삭제합니다.  
  
3. 메서드를 <xref:System.Windows.Forms.Control.Dispose%2A> 호출하여 컨트롤에서 사용하는 모든 리소스를 해제합니다.  
  
    ```vb  
    Public Sub RemoveControl()  
    ' NOTE: The code below uses the instance of
    ' the button (NewPanelButton) from the previous example.  
       If Panel1.Controls.Contains(NewPanelButton) Then  
          RemoveHandler NewPanelButton.Click, AddressOf _
             NewPanelButton_Click  
          Panel1.Controls.Remove(NewPanelButton)  
          NewPanelButton.Dispose()  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void removeControl(object sender, System.EventArgs e)  
    {  
    // NOTE: The code below uses the instance of
    // the button (newPanelButton) from the previous example.  
       if(panel1.Controls.Contains(newPanelButton))  
       {  
          this.newPanelButton.Click -= new System.EventHandler(this.
             NewPanelButton_Click);  
          panel1.Controls.Remove(newPanelButton);  
          newPanelButton.Dispose();  
       }  
    }  
    ```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.Panel>
- [Panel 컨트롤](panel-control-windows-forms.md)
