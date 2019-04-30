---
title: Windows Forms 및 컨트롤에서 국가별 글꼴
ms.date: 03/30/2017
helpviewer_keywords:
- fonts [Windows Forms], international
- international applications [Windows Forms], character display
- fonts [Windows Forms], globalization considerations
- localization [Windows Forms], fonts
- Windows Forms controls, labels
- font fallback in Windows Forms
- globalization [Windows Forms], character sets
dev_langs:
- csharp
- vb
ms.assetid: 2c3066df-9bac-479a-82b2-79e484b346a3
ms.openlocfilehash: 1f9afd575e2de04e0b11556ad34436839e13d968
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942898"
---
# <a name="international-fonts-in-windows-forms-and-controls"></a>Windows Forms 및 컨트롤에서 국가별 글꼴

국가별 응용 프로그램에서 글꼴을 선택 하는 권장된 방법은 가능한 글꼴 대체 (fallback)를 사용 하는 것입니다. 시스템 문자 스크립트 내용을 확인 하는 글꼴 대체 수단에 속합니다.

## <a name="using-font-fallback"></a>글꼴 대체 (fallback)를 사용 하 여

이 기능을 이용 하려면 설정 하지는 <xref:System.Drawing.Font> 폼 또는 다른 요소에 대 한 속성입니다. 응용 프로그램에는 다른 운영 체제의 지역화 된 언어에서 다른 기본 시스템 글꼴을 자동으로 사용 됩니다. 응용 프로그램을 실행 하면 시스템 운영 체제에서 선택한 문화권에 대 한 올바른 글꼴을 자동으로 제공 합니다.

글꼴 스타일을 변경 하는 것에 대 한 인 글꼴을 설정 하지 않는 규칙에 예외가 있습니다. 이는 사용자가 굵게 표시 된에서 텍스트 상자에 텍스트를 표시 하려면 단추를 클릭 하는 응용 프로그램에 대해 중요할 수 있습니다. 이렇게 하려면 하는 함수를 작성 굵게, 텍스트 상자의 글꼴 스타일을 변경 하려면 폼의 글꼴에 따라 합니다. 두 위치에서이 함수를 호출 하는 것이 반드시: 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기 및는 <xref:System.Windows.Forms.Control.FontChanged> 이벤트 처리기입니다. 에서만 함수를 호출 하는 경우는 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기 및 코드의 다른 일부 전체 폼의 글꼴 패밀리를 변경, 텍스트 상자 폼의 나머지 부분을 사용 하 여 변경 되지 않습니다.

```vb
Private Sub MakeBold()
   ' Change the TextBox to a bold version of the form font
   TextBox1.Font = New Font(Me.Font, FontStyle.Bold)
End Sub

Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click
   ' Clicking this button makes the TextBox bold
   MakeBold()
End Sub

Private Sub Form1_FontChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles MyBase.FontChanged
   ' If the TextBox is already bold and the form's font changes,
   ' change the TextBox to a bold version of the new form font
   If (TextBox1.Font.Style = FontStyle.Bold) Then
      MakeBold()
   End If
End Sub
```

```csharp
private void button1_Click(object sender, System.EventArgs e)
{
   // Clicking this button makes the TextBox bold
   MakeBold();
}

private void MakeBold()
{
   // Change the TextBox to a bold version of the form's font
   textBox1.Font = new Font(this.Font, FontStyle.Bold);
}

private void Form1_FontChanged(object sender, System.EventArgs e)
{
   // If the TextBox is already bold and the form's font changes,
   // change the TextBox to a bold version of the new form font
   if (textBox1.Font.Style == FontStyle.Bold)
   {
      MakeBold();
   }
}
```

그러나 응용 프로그램을 지역화할 때 굵게 표시할 수 있습니다 특정 잘못 언어. 중요 한 경우 일반 텍스트를 굵은 글꼴 전환 옵션이 지역화 해야 합니다. 하므로 지역화 담당자는 일반적으로 개발자가 아닌 및 소스 코드에 액세스할 수 없는, 리소스 파일에만이 옵션 해야 리소스 파일에서 설정 합니다. 이 위해 설정 된 <xref:System.Drawing.Font.Bold%2A> 속성을 `true`입니다. 따라서 지역화 담당자가 편집할 수 있는 리소스 파일에 작성 되 고 글꼴 설정 됩니다. 그런 다음 후 코드를 작성 하는 `InitializeComponent` 글꼴을 다시 설정 하는 방법에 따라 폼의 글꼴, 하지만 리소스 파일에 지정 된 글꼴 스타일을 사용 하 여 합니다.

```vb
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)
```

```csharp
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);
```
  
## <a name="see-also"></a>참고자료

- [Windows Forms 응용 프로그램 전역화](globalizing-windows-forms.md)
- [글꼴 및 텍스트 사용](using-fonts-and-text.md)
