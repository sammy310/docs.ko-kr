---
title: TextBox 컨트롤에서 삽입 지점 제어
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], insertion point
- insertion points [Windows Forms], TextBox controls
- text boxes [Windows Forms], controlling insertion point
ms.assetid: 5bee7d34-5121-429e-ab1f-d8ff67bc74c1
ms.openlocfilehash: fd4803820921f0c922a4ce885f809abee8fd4c6c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742210"
---
# <a name="how-to-control-the-insertion-point-in-a-windows-forms-textbox-control"></a>방법: Windows Forms TextBox 컨트롤에서 삽입 지점 제어
Windows Forms <xref:System.Windows.Forms.TextBox> 컨트롤에서 먼저 포커스를 받을 때 텍스트 상자에 있는 기본 삽입은 기존 텍스트의 왼쪽에 있습니다. 사용자는 키보드 또는 마우스를 사용 하 여 삽입 지점을 이동할 수 있습니다. 텍스트 상자가 손실 된 다음 포커스를 다시 얻으면 사용자가 마지막으로 배치 된 위치에 삽입 지점이 삽입 됩니다.  
  
 경우에 따라 사용자에 게이 동작을 disconcerting 수 있습니다. 워드 프로세싱 응용 프로그램에서 사용자는 기존 텍스트 뒤에 새 문자를 표시 하는 것이 좋습니다. 데이터 입력 응용 프로그램에서 사용자는 기존 항목을 대체할 새 문자를 예측할 수 있습니다. <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> 및 <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> 속성을 사용 하면 용도에 맞게 동작을 수정할 수 있습니다.  
  
### <a name="to-control-the-insertion-point-in-a-textbox-control"></a>TextBox 컨트롤에서 삽입 지점을 제어 하려면  
  
1. <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> 속성을 적절한 값으로 설정합니다. 0은 삽입 지점을 첫 번째 문자 바로 왼쪽에 배치 합니다.  
  
2. 필드 <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> 속성을 선택 하려는 텍스트의 길이로 설정 합니다.  
  
     아래 코드는 항상 삽입 지점을 0으로 반환 합니다. `TextBox1_Enter` 이벤트 처리기는 컨트롤에 바인딩되어야 합니다. 자세한 내용은 [Windows Forms에서 이벤트 처리기 만들기](../creating-event-handlers-in-windows-forms.md)를 참조 하세요.  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       TextBox1.SelectionStart = 0  
       TextBox1.SelectionLength = 0  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_Enter(Object sender, System.EventArgs e) {  
       textBox1.SelectionStart = 0;  
       textBox1.SelectionLength = 0;  
    }  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = 0;  
       }  
    ```  
  
## <a name="making-the-insertion-point-visible-by-default"></a>삽입 지점이 기본적으로 표시 되도록 설정  
 <xref:System.Windows.Forms.TextBox> 삽입 지점은 <xref:System.Windows.Forms.TextBox> 컨트롤이 탭 순서에서 첫 번째 인 경우에만 기본적으로 새 폼에 표시 됩니다. 그렇지 않으면 키보드 또는 마우스를 사용 하 여 <xref:System.Windows.Forms.TextBox> 포커스를 제공 하는 경우에만 삽입 지점이 표시 됩니다.  
  
#### <a name="to-make-the-text-box-insertion-point-visible-by-default-on-a-new-form"></a>텍스트 상자 삽입 지점이 기본적으로 새 폼에 표시 되도록 하려면  
  
- <xref:System.Windows.Forms.TextBox> 컨트롤의 <xref:System.Windows.Forms.Control.TabIndex%2A> 속성을 `0`로 설정 합니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.TextBox>
- [TextBox 컨트롤 개요](textbox-control-overview-windows-forms.md)
- [방법: Windows Forms TextBox 컨트롤을 사용하여 암호 텍스트 상자 만들기](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [방법: 읽기 전용 텍스트 상자 만들기](how-to-create-a-read-only-text-box-windows-forms.md)
- [방법: 문자열에 인용 부호 넣기](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [방법: Windows Forms TextBox 컨트롤에서 텍스트 선택](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [방법: Windows Forms TextBox 컨트롤에 여러 줄 표시](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [TextBox 컨트롤](textbox-control-windows-forms.md)
