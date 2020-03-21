---
title: RichTextBox 컨트롤에서 서식 지정 특성변경 시기 결정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], text boxes
- RichTextBox control [Windows Forms], determining font changes
- text boxes [Windows Forms], determining font changes
- SelChange event
ms.assetid: bdfed015-f77a-41e5-b38f-f8629b2fa166
ms.openlocfilehash: a190c3479b58464763e0eefdd32d14e88a1f05e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142266"
---
# <a name="how-to-determine-when-formatting-attributes-change-in-the-windows-forms-richtextbox-control"></a>방법: Windows Forms RichTextBox 컨트롤에서 서식 특성의 변경 시기 결정
Windows Forms <xref:System.Windows.Forms.RichTextBox> 컨트롤의 일반적인 용도는 글꼴 옵션 또는 단락 스타일과 같은 특성을 가진 텍스트 서식을 지정하는 것입니다. 많은 워드 프로세싱 응용 프로그램과 마찬가지로 도구 모음을 표시하기 위해 응용 프로그램에서 텍스트 서식변경 사항을 추적해야 할 수 있습니다.  
  
### <a name="to-respond-to-changes-in-formatting-attributes"></a>서식 특성의 변경 사항에 응답하려면  
  
1. 특성의 <xref:System.Windows.Forms.RichTextBox.SelectionChanged> 값에 따라 적절한 작업을 수행 하도록 이벤트 처리기에 코드를 작성 합니다. 다음 예제는 <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> 속성 값에 따라 도구 모음 단추의 모양을 변경합니다. 도구 모음 단추는 삽입 지점이 컨트롤에서 이동될 때만 업데이트됩니다.  
  
     아래 예제는 <xref:System.Windows.Forms.RichTextBox> 컨트롤이 있는 폼과 <xref:System.Windows.Forms.ToolBar> 도구 모음 단추를 포함하는 컨트롤을 가정합니다. 도구 모음 및 도구 모음 단추에 대한 자세한 내용은 [도구 모음 컨트롤에 단추를 추가하는 방법을 참조하세요.](how-to-add-buttons-to-a-toolbar-control.md)  
  
    ```vb  
    ' The following code assumes the existence of a toolbar control  
    ' with at least one toolbar button.  
    Private Sub RichTextBox1_SelectionChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles RichTextBox1.SelectionChanged  
       If RichTextBox1.SelectionBullet = True Then  
          ' Bullet button on toolbar should appear pressed  
          ToolBarButton1.Pushed = True  
       Else  
           ' Bullet button on toolbar should appear unpressed  
           ToolBarButton1.Pushed = False  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private void richTextBox1_SelectionChanged(object sender,  
    System.EventArgs e)  
    {  
       if (richTextBox1.SelectionBullet == true)
       {  
          // Bullet button on toolbar should appear pressed  
          toolBarButton1.Pushed = true;  
       }  
       else
       {  
          // Bullet button on toolbar should appear unpressed  
          toolBarButton1.Pushed = false;  
       }  
    }  
    ```  
  
    ```cpp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private:  
       System::Void richTextBox1_SelectionChanged(  
          System::Object ^  sender, System::EventArgs ^  e)  
       {  
          if (richTextBox1->SelectionBullet == true)  
          {  
             // Bullet button on toolbar should appear pressed  
             toolBarButton1->Pushed = true;  
          }  
          else  
          {  
             // Bullet button on toolbar should appear unpressed  
             toolBarButton1->Pushed = false;  
          }  
       }  
    ```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.RichTextBox.SelectionChanged>
- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox 컨트롤](richtextbox-control-windows-forms.md)
- [Windows Forms에 사용할 수 있는 컨트롤](controls-to-use-on-windows-forms.md)
