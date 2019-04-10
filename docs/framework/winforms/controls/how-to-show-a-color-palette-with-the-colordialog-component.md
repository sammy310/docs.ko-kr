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
ms.openlocfilehash: 587b2c3a502ec8a1cb2f4f7c0d981baa0f18ead6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59298021"
---
# <a name="how-to-show-a-color-palette-with-the-colordialog-component"></a><span data-ttu-id="f754f-102">방법: ColorDialog 구성 요소를 사용하여 색상표 표시</span><span class="sxs-lookup"><span data-stu-id="f754f-102">How to: Show a Color Palette with the ColorDialog Component</span></span>
<span data-ttu-id="f754f-103">합니다 [ColorDialog](colordialog-component-windows-forms.md) 색상표를 표시 하 고 사용자가 선택한 색을 포함 하는 속성을 반환 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f754f-103">The [ColorDialog](colordialog-component-windows-forms.md) component displays a palette of colors and returns a property containing the color the user has selected.</span></span>  
  
### <a name="to-choose-a-color-using-the-colordialog-component"></a><span data-ttu-id="f754f-104">ColorDialog 구성 요소를 사용 하 여 색을 선택 하려면</span><span class="sxs-lookup"><span data-stu-id="f754f-104">To choose a color using the ColorDialog component</span></span>  
  
1. <span data-ttu-id="f754f-105">사용 하 여 대화 상자를 표시 합니다 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="f754f-105">Display the dialog box using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
2. <span data-ttu-id="f754f-106">사용 된 <xref:System.Windows.Forms.DialogResult> 속성 대화 상자를 닫은 방법을 확인 하려면.</span><span class="sxs-lookup"><span data-stu-id="f754f-106">Use the <xref:System.Windows.Forms.DialogResult> property to determine how the dialog box was closed.</span></span>  
  
3. <span data-ttu-id="f754f-107">사용 하 여 합니다 <xref:System.Windows.Forms.ColorDialog.Color%2A> 의 속성을 <xref:System.Windows.Forms.ColorDialog> 선택한 색을 설정 하려면 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f754f-107">Use the <xref:System.Windows.Forms.ColorDialog.Color%2A> property of the <xref:System.Windows.Forms.ColorDialog> component to set the chosen color.</span></span>  
  
     <span data-ttu-id="f754f-108">아래 예제에서는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기가 열립니다는 <xref:System.Windows.Forms.ColorDialog> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f754f-108">In the example below, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens a <xref:System.Windows.Forms.ColorDialog> component.</span></span> <span data-ttu-id="f754f-109">색을 선택 하 고 사용자가 클릭할 **확인**, <xref:System.Windows.Forms.Button> 컨트롤의 배경 색 선택한 색으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f754f-109">When a color is chosen and the user clicks **OK**, the <xref:System.Windows.Forms.Button> control's background color is set to the chosen color.</span></span> <span data-ttu-id="f754f-110">이 예제에서는 폼에 가정를 <xref:System.Windows.Forms.Button> 컨트롤 및 <xref:System.Windows.Forms.ColorDialog> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f754f-110">The example assumes your form has a <xref:System.Windows.Forms.Button> control and a <xref:System.Windows.Forms.ColorDialog> component.</span></span>  
  
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
  
     <span data-ttu-id="f754f-111">(Visual C# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 이벤트 처리기를 등록 하려면 폼의 생성자에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f754f-111">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=   
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f754f-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="f754f-112">See also</span></span>

- <xref:System.Windows.Forms.ColorDialog>
- [<span data-ttu-id="f754f-113">ColorDialog 구성 요소</span><span class="sxs-lookup"><span data-stu-id="f754f-113">ColorDialog Component</span></span>](colordialog-component-windows-forms.md)
