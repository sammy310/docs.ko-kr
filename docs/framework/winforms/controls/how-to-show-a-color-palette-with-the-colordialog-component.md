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
# <a name="how-to-show-a-color-palette-with-the-colordialog-component"></a><span data-ttu-id="fd831-102">방법: ColorDialog 구성 요소를 사용하여 색상표 표시</span><span class="sxs-lookup"><span data-stu-id="fd831-102">How to: Show a Color Palette with the ColorDialog Component</span></span>
<span data-ttu-id="fd831-103">[ColorDialog](colordialog-component-windows-forms.md) 구성 요소는 색상 팔레트를 표시하고 사용자가 선택한 색상을 포함하는 속성을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fd831-103">The [ColorDialog](colordialog-component-windows-forms.md) component displays a palette of colors and returns a property containing the color the user has selected.</span></span>  
  
### <a name="to-choose-a-color-using-the-colordialog-component"></a><span data-ttu-id="fd831-104">ColorDialog 구성 요소를 사용하여 색상을 선택하려면</span><span class="sxs-lookup"><span data-stu-id="fd831-104">To choose a color using the ColorDialog component</span></span>  
  
1. <span data-ttu-id="fd831-105">메서드를 사용하여 대화 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 상자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fd831-105">Display the dialog box using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
2. <span data-ttu-id="fd831-106">속성을 <xref:System.Windows.Forms.DialogResult> 사용하여 대화 상자가 닫힌 방법을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fd831-106">Use the <xref:System.Windows.Forms.DialogResult> property to determine how the dialog box was closed.</span></span>  
  
3. <span data-ttu-id="fd831-107"><xref:System.Windows.Forms.ColorDialog> 구성 요소의 <xref:System.Windows.Forms.ColorDialog.Color%2A> 속성을 사용하여 선택한 색상을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fd831-107">Use the <xref:System.Windows.Forms.ColorDialog.Color%2A> property of the <xref:System.Windows.Forms.ColorDialog> component to set the chosen color.</span></span>  
  
     <span data-ttu-id="fd831-108">아래 예제에서는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기가 <xref:System.Windows.Forms.ColorDialog> 구성 요소를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fd831-108">In the example below, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens a <xref:System.Windows.Forms.ColorDialog> component.</span></span> <span data-ttu-id="fd831-109">색상을 선택하고 사용자가 **확인을**클릭하면 <xref:System.Windows.Forms.Button> 컨트롤의 배경색이 선택한 색상으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd831-109">When a color is chosen and the user clicks **OK**, the <xref:System.Windows.Forms.Button> control's background color is set to the chosen color.</span></span> <span data-ttu-id="fd831-110">이 예제는 양식에 <xref:System.Windows.Forms.Button> 컨트롤과 <xref:System.Windows.Forms.ColorDialog> 구성 요소가 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="fd831-110">The example assumes your form has a <xref:System.Windows.Forms.Button> control and a <xref:System.Windows.Forms.ColorDialog> component.</span></span>  
  
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
  
     <span data-ttu-id="fd831-111">(비주얼 C #, 비주얼 C++) 양식의 생성자에서 다음 코드를 배치하여 이벤트 처리기를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="fd831-111">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="fd831-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fd831-112">See also</span></span>

- <xref:System.Windows.Forms.ColorDialog>
- [<span data-ttu-id="fd831-113">ColorDialog 구성 요소</span><span class="sxs-lookup"><span data-stu-id="fd831-113">ColorDialog Component</span></span>](colordialog-component-windows-forms.md)
