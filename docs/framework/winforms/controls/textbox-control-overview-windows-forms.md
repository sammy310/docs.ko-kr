---
title: TextBox 컨트롤 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TextBox
helpviewer_keywords:
- TextBox control [Windows Forms], about TextBox controls
- text boxes [Windows Forms], adding
ms.assetid: d1a9c7f5-fa53-480a-a75c-158f8649ea2f
ms.openlocfilehash: 06ab460d720d17331881b5ba653263160eaf3cb3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742798"
---
# <a name="textbox-control-overview-windows-forms"></a>TextBox 컨트롤 개요(Windows Forms)
Windows Forms 텍스트 상자는 사용자의 입력을 가져오거나 텍스트를 표시 하는 데 사용 됩니다. <xref:System.Windows.Forms.TextBox> 컨트롤은 읽기 전용으로 만들 수도 있지만 편집 가능한 텍스트에 일반적으로 사용 됩니다. 텍스트 상자는 여러 줄을 표시 하 고 텍스트를 컨트롤의 크기로 래핑하고 기본 서식 지정을 추가할 수 있습니다. <xref:System.Windows.Forms.TextBox> 컨트롤은 컨트롤에 표시 되거나 입력 되는 텍스트에 대 한 단일 형식 스타일을 제공 합니다. 여러 형식의 서식이 지정 된 텍스트를 표시 하려면 <xref:System.Windows.Forms.RichTextBox> 컨트롤을 사용 합니다. 자세한 내용은 [RichTextBox 컨트롤 개요](richtextbox-control-overview-windows-forms.md)를 참조 하세요.  
  
## <a name="working-with-the-textbox-control"></a>TextBox 컨트롤 작업  
 컨트롤에 표시 되는 텍스트는 <xref:System.Windows.Forms.TextBox.Text%2A> 속성에 포함 되어 있습니다. 기본적으로 텍스트 상자에는 최대 2048 자까지 입력할 수 있습니다. <xref:System.Windows.Forms.TextBox.Multiline%2A> 속성을 `true`로 설정 하면 최대 32의 텍스트를 입력할 수 있습니다. 디자인 타임에 속성 창, 코드에서 런타임에 또는 런타임에 사용자 입력을 사용 하 여 <xref:System.Windows.Forms.TextBox.Text%2A> 속성을 설정할 수 있습니다. 런타임에 <xref:System.Windows.Forms.TextBox.Text%2A> 속성을 읽어 텍스트 상자의 현재 내용을 검색할 수 있습니다.  
  
 다음 코드 예제에서는 런타임에 컨트롤의 텍스트를 설정 합니다. `InitializeMyControl` 프로시저는 자동으로 실행 되지 않습니다. 호출 해야 합니다.  
  
```vb  
Private Sub InitializeMyControl()  
   ' Put some text into the control first.  
   TextBox1.Text = "This is a TextBox control."  
End Sub  
```  
  
```csharp  
private void InitializeMyControl() {  
   // Put some text into the control first.  
   textBox1.Text = "This is a TextBox control.";  
}  
```  
  
```cpp  
private:  
   void InitializeMyControl()  
   {  
      // Put some text into the control first.  
      textBox1->Text = "This is a TextBox control.";  
   }  
```  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.TextBox>
- [방법: Windows Forms TextBox 컨트롤에서 삽입 지점 제어](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [방법: Windows Forms TextBox 컨트롤을 사용하여 암호 텍스트 상자 만들기](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [방법: 읽기 전용 텍스트 상자 만들기](how-to-create-a-read-only-text-box-windows-forms.md)
- [방법: 문자열에 인용 부호 넣기](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [방법: Windows Forms TextBox 컨트롤에서 텍스트 선택](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [방법: Windows Forms TextBox 컨트롤에 여러 줄 표시](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [TextBox 컨트롤](textbox-control-windows-forms.md)
