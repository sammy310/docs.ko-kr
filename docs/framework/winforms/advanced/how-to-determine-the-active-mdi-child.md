---
title: '방법: 활성 MDI 자식 확인'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- MDI [Windows Forms], child windows
- child forms
- MDI [Windows Forms], activating forms
- MDI [Windows Forms], locating focus
ms.assetid: 33880ec3-0207-4c2b-a616-ff140443cc0f
ms.openlocfilehash: 57491faa10c182630d41565ba236d65e393929b3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182541"
---
# <a name="how-to-determine-the-active-mdi-child"></a><span data-ttu-id="eea21-102">방법: 활성 MDI 자식 확인</span><span class="sxs-lookup"><span data-stu-id="eea21-102">How to: Determine the Active MDI Child</span></span>
<span data-ttu-id="eea21-103">경우에 따라 현재 활성 자식 양식에 중점을 둔 컨트롤에서 작동하는 명령을 제공하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="eea21-103">On occasion, you will want to provide a command that operates on the control that has focus on the currently active child form.</span></span> <span data-ttu-id="eea21-104">예를 들어 자식 양식의 텍스트 상자에서 선택한 텍스트를 클립보드에 복사한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="eea21-104">For example, suppose you want to copy selected text from the child form's text box to the Clipboard.</span></span> <span data-ttu-id="eea21-105">표준 편집 메뉴의 복사 메뉴 항목 <xref:System.Windows.Forms.Control.Click> 의 이벤트를 사용하여 선택한 텍스트를 클립보드에 복사하는 프로시저를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eea21-105">You would create a procedure that copies selected text to the Clipboard using the <xref:System.Windows.Forms.Control.Click> event of the Copy menu item on the standard Edit menu.</span></span>  
  
 <span data-ttu-id="eea21-106">MDI 응용 프로그램에는 동일한 자식 양식의 많은 인스턴스가 있을 수 있으므로 프로시저는 사용할 양식을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eea21-106">Because an MDI application can have many instances of the same child form, the procedure needs to know which form to use.</span></span> <span data-ttu-id="eea21-107">올바른 양식을 지정하려면 포커스가 <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> 있거나 가장 최근에 활성 상태인 자식 양식을 반환하는 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="eea21-107">To specify the correct form, use the <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> property, which returns the child form that has the focus or that was most recently active.</span></span>  
  
 <span data-ttu-id="eea21-108">양식에 여러 컨트롤이 있는 경우 활성 컨트롤을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eea21-108">When you have several controls on a form, you also need to specify which control is active.</span></span> <span data-ttu-id="eea21-109">속성과 <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> 마찬가지로 <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> 속성은 활성 자식 양식에 포커스를 두고 컨트롤을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="eea21-109">Like the <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> property, the <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> property returns the control with the focus on the active child form.</span></span> <span data-ttu-id="eea21-110">아래 절차에서는 자식 양식 메뉴, MDI 양식의 메뉴 또는 도구 모음 단추에서 호출할 수 있는 복사 절차를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eea21-110">The procedure below illustrates a copy procedure that can be called from a child form menu, a menu on the MDI form, or a toolbar button.</span></span>  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a><span data-ttu-id="eea21-111">활성 MDI 자식을 확인하려면(해당 텍스트를 클립보드에 복사)</span><span class="sxs-lookup"><span data-stu-id="eea21-111">To determine the active MDI child (to copy its text to the Clipboard)</span></span>  
  
1. <span data-ttu-id="eea21-112">메서드 내에서 활성 자식 양식의 활성 컨트롤의 텍스트를 클립보드에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="eea21-112">Within a method, copy the text of the active control of the active child form to the Clipboard.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="eea21-113">이 예제에서는 컨트롤을 포함하는 하나`Form1`이상의 MDI 자식 창이 있는 <xref:System.Windows.Forms.RichTextBox> MDI 상위 양식()이 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="eea21-113">This example assumes there is an MDI parent form (`Form1`) that has one or more MDI child windows containing a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="eea21-114">자세한 내용은 [MDI 상위 양식 만들기](how-to-create-mdi-parent-forms.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="eea21-114">For more information, see [Creating MDI Parent Forms](how-to-create-mdi-parent-forms.md).</span></span>  
  
    ```vb  
    Public Sub mniCopy_Click(ByVal sender As Object, _  
       ByVal e As System.EventArgs) Handles mniCopy.Click  
  
       ' Determine the active child form.  
       Dim activeChild As Form = Me.ActiveMDIChild  
  
       ' If there is an active child form, find the active control, which  
       ' in this example should be a RichTextBox.  
       If (Not activeChild Is Nothing) Then  
          Dim theBox As RichTextBox = _  
            TryCast(activeChild.ActiveControl, RichTextBox)  
  
          If (Not theBox Is Nothing) Then  
             'Put selected text on Clipboard.  
             Clipboard.SetDataObject(theBox.SelectedText)  
          Else  
             MessageBox.Show("You need to select a RichTextBox.")  
          End If  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void mniCopy_Click (object sender, System.EventArgs e)  
    {  
       // Determine the active child form.  
       Form activeChild = this.ActiveMdiChild;  
  
       // If there is an active child form, find the active control, which  
       // in this example should be a RichTextBox.  
       if (activeChild != null)  
       {
          try  
          {  
             RichTextBox theBox = (RichTextBox)activeChild.ActiveControl;  
             if (theBox != null)  
             {  
                // Put the selected text on the Clipboard.  
                Clipboard.SetDataObject(theBox.SelectedText);  
  
             }  
          }  
          catch  
          {  
             MessageBox.Show("You need to select a RichTextBox.");  
          }  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="eea21-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eea21-115">See also</span></span>

- [<span data-ttu-id="eea21-116">MDI(다중 문서 인터페이스) 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="eea21-116">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="eea21-117">방법: MDI 상위 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="eea21-117">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="eea21-118">방법: MDI 자식 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="eea21-118">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="eea21-119">방법: 활성 MDI 자식으로 데이터 전송</span><span class="sxs-lookup"><span data-stu-id="eea21-119">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="eea21-120">방법: MDI 자식 양식 정렬</span><span class="sxs-lookup"><span data-stu-id="eea21-120">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
