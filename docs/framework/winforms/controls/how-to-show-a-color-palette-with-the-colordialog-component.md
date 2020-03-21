---
title: '방법: ColorDialog 구성 요소를 사용하여 색상표 표시'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- palettes [Windows Forms], showing color
- color dialog box [Windows Forms], showing color palettes
- colors [Windows Forms], allowing users to select
- color palettes [Windows Forms], dialog box
- ColorDialog component [Windows Forms], showing color palettes
- color palettes [Windows Forms], showing in ColorDialog component
- colors [Windows Forms], showing palettes
ms.assetid: ee050f61-dbc8-4436-ba22-51360981ab48
ms.openlocfilehash: 0406ef7a32678bd149c0024348a7adf1f0b72926
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141785"
---
# <a name="how-to-show-a-color-palette-with-the-colordialog-component"></a>방법: ColorDialog 구성 요소를 사용하여 색상표 표시
[ColorDialog](colordialog-component-windows-forms.md) 구성 요소는 색상 팔레트를 표시하고 사용자가 선택한 색상을 포함하는 속성을 반환합니다.  
  
### <a name="to-choose-a-color-using-the-colordialog-component"></a>ColorDialog 구성 요소를 사용하여 색상을 선택하려면  
  
1. 메서드를 사용하여 대화 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 상자를 표시합니다.  
  
2. 속성을 <xref:System.Windows.Forms.DialogResult> 사용하여 대화 상자가 닫힌 방법을 확인합니다.  
  
3. <xref:System.Windows.Forms.ColorDialog> 구성 요소의 <xref:System.Windows.Forms.ColorDialog.Color%2A> 속성을 사용하여 선택한 색상을 설정합니다.  
  
     아래 예제에서는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기가 <xref:System.Windows.Forms.ColorDialog> 구성 요소를 엽니다. 색상을 선택하고 사용자가 **확인을**클릭하면 <xref:System.Windows.Forms.Button> 컨트롤의 배경색이 선택한 색상으로 설정됩니다. 이 예제는 양식에 <xref:System.Windows.Forms.Button> 컨트롤과 <xref:System.Windows.Forms.ColorDialog> 구성 요소가 있다고 가정합니다.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles Button1.Click  
       If ColorDialog1.ShowDialog() = DialogResult.OK Then  
          Button1.BackColor = ColorDialog1.Color  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(colorDialog1.ShowDialog() == DialogResult.OK)  
       {  
          button1.BackColor = colorDialog1.Color;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,
          System::EventArgs ^ e)  
       {  
          if(colorDialog1->ShowDialog() == DialogResult::OK)  
          {  
             button1->BackColor = colorDialog1->Color;  
          }  
       }  
    ```  
  
     (비주얼 C #, 비주얼 C++) 양식의 생성자에서 다음 코드를 배치하여 이벤트 처리기를 등록합니다.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.ColorDialog>
- [ColorDialog 구성 요소](colordialog-component-windows-forms.md)
