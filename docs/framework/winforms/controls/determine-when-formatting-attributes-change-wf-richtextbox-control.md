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
# <a name="how-to-determine-when-formatting-attributes-change-in-the-windows-forms-richtextbox-control"></a><span data-ttu-id="a43c6-102">방법: Windows Forms RichTextBox 컨트롤에서 서식 특성의 변경 시기 결정</span><span class="sxs-lookup"><span data-stu-id="a43c6-102">How to: Determine When Formatting Attributes Change in the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="a43c6-103">Windows Forms <xref:System.Windows.Forms.RichTextBox> 컨트롤의 일반적인 용도는 글꼴 옵션 또는 단락 스타일과 같은 특성을 가진 텍스트 서식을 지정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a43c6-103">A common use of the Windows Forms <xref:System.Windows.Forms.RichTextBox> control is formatting text with attributes such as font options or paragraph styles.</span></span> <span data-ttu-id="a43c6-104">많은 워드 프로세싱 응용 프로그램과 마찬가지로 도구 모음을 표시하기 위해 응용 프로그램에서 텍스트 서식변경 사항을 추적해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a43c6-104">Your application may need to keep track of any changes in text formatting for the purpose of displaying a toolbar, as in many word-processing applications.</span></span>  
  
### <a name="to-respond-to-changes-in-formatting-attributes"></a><span data-ttu-id="a43c6-105">서식 특성의 변경 사항에 응답하려면</span><span class="sxs-lookup"><span data-stu-id="a43c6-105">To respond to changes in formatting attributes</span></span>  
  
1. <span data-ttu-id="a43c6-106">특성의 <xref:System.Windows.Forms.RichTextBox.SelectionChanged> 값에 따라 적절한 작업을 수행 하도록 이벤트 처리기에 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a43c6-106">Write code in the <xref:System.Windows.Forms.RichTextBox.SelectionChanged> event handler to perform an appropriate action depending on the value of the attribute.</span></span> <span data-ttu-id="a43c6-107">다음 예제는 <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> 속성 값에 따라 도구 모음 단추의 모양을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a43c6-107">The following example changes the appearance of a toolbar button depending on the value of the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property.</span></span> <span data-ttu-id="a43c6-108">도구 모음 단추는 삽입 지점이 컨트롤에서 이동될 때만 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="a43c6-108">The toolbar button will only be updated when the insertion point is moved in the control.</span></span>  
  
     <span data-ttu-id="a43c6-109">아래 예제는 <xref:System.Windows.Forms.RichTextBox> 컨트롤이 있는 폼과 <xref:System.Windows.Forms.ToolBar> 도구 모음 단추를 포함하는 컨트롤을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="a43c6-109">The example below assumes a form with a <xref:System.Windows.Forms.RichTextBox> control and a <xref:System.Windows.Forms.ToolBar> control that contains a toolbar button.</span></span> <span data-ttu-id="a43c6-110">도구 모음 및 도구 모음 단추에 대한 자세한 내용은 [도구 모음 컨트롤에 단추를 추가하는 방법을 참조하세요.](how-to-add-buttons-to-a-toolbar-control.md)</span><span class="sxs-lookup"><span data-stu-id="a43c6-110">For more information about toolbars and toolbar buttons, see [How to: Add Buttons to a ToolBar Control](how-to-add-buttons-to-a-toolbar-control.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a43c6-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a43c6-111">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox.SelectionChanged>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="a43c6-112">RichTextBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="a43c6-112">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="a43c6-113">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="a43c6-113">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
