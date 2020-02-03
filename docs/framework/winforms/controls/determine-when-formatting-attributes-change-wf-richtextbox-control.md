---
title: RichTextBox 컨트롤에서 서식 특성의 변경 시기 결정
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
ms.openlocfilehash: f9b2a1028f79059ec7d4d6bf3683100455bb5dea
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746042"
---
# <a name="how-to-determine-when-formatting-attributes-change-in-the-windows-forms-richtextbox-control"></a><span data-ttu-id="3cb3d-102">방법: Windows Forms RichTextBox 컨트롤에서 서식 특성의 변경 시기 결정</span><span class="sxs-lookup"><span data-stu-id="3cb3d-102">How to: Determine When Formatting Attributes Change in the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="3cb3d-103">Windows Forms <xref:System.Windows.Forms.RichTextBox> 컨트롤의 일반적인 용도는 글꼴 옵션이 나 단락 스타일과 같은 특성을 사용 하 여 텍스트의 서식을 지정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3cb3d-103">A common use of the Windows Forms <xref:System.Windows.Forms.RichTextBox> control is formatting text with attributes such as font options or paragraph styles.</span></span> <span data-ttu-id="3cb3d-104">응용 프로그램은 많은 단어 처리 응용 프로그램에서와 같이 도구 모음을 표시 하기 위해 텍스트 서식의 변경 내용을 추적 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cb3d-104">Your application may need to keep track of any changes in text formatting for the purpose of displaying a toolbar, as in many word-processing applications.</span></span>  
  
### <a name="to-respond-to-changes-in-formatting-attributes"></a><span data-ttu-id="3cb3d-105">서식 특성의 변경 내용에 응답 하려면</span><span class="sxs-lookup"><span data-stu-id="3cb3d-105">To respond to changes in formatting attributes</span></span>  
  
1. <span data-ttu-id="3cb3d-106"><xref:System.Windows.Forms.RichTextBox.SelectionChanged> 이벤트 처리기에서 코드를 작성 하 여 특성 값에 따라 적절 한 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cb3d-106">Write code in the <xref:System.Windows.Forms.RichTextBox.SelectionChanged> event handler to perform an appropriate action depending on the value of the attribute.</span></span> <span data-ttu-id="3cb3d-107">다음 예에서는 <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> 속성의 값에 따라 도구 모음 단추의 모양을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cb3d-107">The following example changes the appearance of a toolbar button depending on the value of the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property.</span></span> <span data-ttu-id="3cb3d-108">도구 모음 단추는 삽입 지점이 컨트롤에서 이동 될 때만 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cb3d-108">The toolbar button will only be updated when the insertion point is moved in the control.</span></span>  
  
     <span data-ttu-id="3cb3d-109">아래 예제에서는 <xref:System.Windows.Forms.RichTextBox> 컨트롤 및 도구 모음 단추가 포함 된 <xref:System.Windows.Forms.ToolBar> 컨트롤을 포함 하는 폼을 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cb3d-109">The example below assumes a form with a <xref:System.Windows.Forms.RichTextBox> control and a <xref:System.Windows.Forms.ToolBar> control that contains a toolbar button.</span></span> <span data-ttu-id="3cb3d-110">도구 모음 및 도구 모음 단추에 대 한 자세한 내용은 [방법: Toolbar 컨트롤에 단추 추가](how-to-add-buttons-to-a-toolbar-control.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3cb3d-110">For more information about toolbars and toolbar buttons, see [How to: Add Buttons to a ToolBar Control](how-to-add-buttons-to-a-toolbar-control.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3cb3d-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3cb3d-111">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox.SelectionChanged>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="3cb3d-112">RichTextBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="3cb3d-112">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="3cb3d-113">Windows Forms에서 사용할 컨트롤</span><span class="sxs-lookup"><span data-stu-id="3cb3d-113">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
