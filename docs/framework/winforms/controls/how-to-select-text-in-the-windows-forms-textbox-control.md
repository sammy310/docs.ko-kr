---
title: TextBox 컨트롤에서 텍스트 선택
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], selecting text programmatically
- text boxes [Windows Forms], selecting text programmatically
- text [Windows Forms], selecting in text boxes programmatically
ms.assetid: 8c591546-6a01-45c7-8e03-f78431f903b1
ms.openlocfilehash: 8a32e40f14ddae6f8ddcaa6d62337329df6fde26
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745307"
---
# <a name="how-to-select-text-in-the-windows-forms-textbox-control"></a>방법: Windows Forms TextBox 컨트롤에서 텍스트 선택
Windows Forms <xref:System.Windows.Forms.TextBox> 컨트롤에서 프로그래밍 방식으로 텍스트를 선택할 수 있습니다. 예를 들어 텍스트에서 특정 문자열을 검색 하는 함수를 만드는 경우 텍스트를 선택 하 여 발견 된 문자열의 위치를 판독기에 시각적으로 경고할 수 있습니다.  
  
### <a name="to-select-text-programmatically"></a>프로그래밍 방식으로 텍스트를 선택 하려면  
  
1. <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> 속성을 선택 하려는 텍스트의 시작 부분으로 설정 합니다.  
  
     <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> 속성은 텍스트 문자열 내에서 삽입 지점을 나타내는 숫자로, 0은 맨 왼쪽 위치입니다. <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> 속성이 텍스트 상자의 문자 수보다 크거나 같은 값으로 설정 된 경우 삽입 지점은 마지막 문자 뒤에 배치 됩니다.  
  
2. <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> 속성을 선택 하려는 텍스트의 길이로 설정 합니다.  
  
     <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> 속성은 삽입 지점의 너비를 설정 하는 숫자 값입니다. <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A>를 0 보다 큰 값으로 설정 하면 현재 삽입 지점부터 시작 하 여 문자 수가 선택 됩니다.  
  
3. 필드 <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> 속성을 사용 하 여 선택한 텍스트에 액세스 합니다.  
  
     아래 코드는 컨트롤의 <xref:System.Windows.Forms.Control.Enter> 이벤트가 발생할 때 텍스트 상자의 내용을 선택 합니다. 이 예에서는 텍스트 상자에 `null` 되지 않은 <xref:System.Windows.Forms.TextBox.Text%2A> 속성 값이 있는지 또는 빈 문자열이 있는지를 확인 합니다. 텍스트 상자에 포커스가 있으면 텍스트 상자의 현재 텍스트가 선택 됩니다. `TextBox1_Enter` 이벤트 처리기는 컨트롤에 바인딩되어야 합니다. 자세한 내용은 [방법: 런타임에 Windows Forms 이벤트 처리기 만들기](../how-to-create-event-handlers-at-run-time-for-windows-forms.md)를 참조 하세요.  
  
     이 예를 테스트 하려면 입력란에 포커스가 있을 때까지 Tab 키를 누릅니다. 텍스트 상자를 클릭 하면 텍스트가 선택 취소 됩니다.  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       If (Not String.IsNullOrEmpty(TextBox1.Text)) Then  
          TextBox1.SelectionStart = 0  
          TextBox1.SelectionLength = TextBox1.Text.Length  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_Enter(object sender, System.EventArgs e){  
       if (!String.IsNullOrEmpty(textBox1.Text))  
       {  
          textBox1.SelectionStart = 0;  
          textBox1.SelectionLength = textBox1.Text.Length;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^ sender,  
          System::EventArgs ^ e) {  
       if (!System::String::IsNullOrEmpty(textBox1->Text))  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = textBox1->Text->Length;  
       }  
    }  
    ```  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.TextBox>
- [TextBox 컨트롤 개요](textbox-control-overview-windows-forms.md)
- [방법: Windows Forms TextBox 컨트롤에서 삽입 지점 제어](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [방법: Windows Forms TextBox 컨트롤을 사용하여 암호 텍스트 상자 만들기](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [방법: 읽기 전용 텍스트 상자 만들기](how-to-create-a-read-only-text-box-windows-forms.md)
- [방법: 문자열에 인용 부호 넣기](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [방법: Windows Forms TextBox 컨트롤에 여러 줄 표시](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [TextBox 컨트롤](textbox-control-windows-forms.md)
