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
ms.openlocfilehash: 9b70824670b8f47a2346135cb31ad39bd55694d1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59300608"
---
# <a name="how-to-determine-the-active-mdi-child"></a><span data-ttu-id="90553-102">방법: 활성 MDI 자식 확인</span><span class="sxs-lookup"><span data-stu-id="90553-102">How to: Determine the Active MDI Child</span></span>
<span data-ttu-id="90553-103">경우에 따라 현재 활성 자식 폼에 포커스가 있는 컨트롤에서 작동 하는 명령을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="90553-103">On occasion, you will want to provide a command that operates on the control that has focus on the currently active child form.</span></span> <span data-ttu-id="90553-104">예를 들어 자식 폼의 텍스트 상자에서 선택한 텍스트를 클립보드로 복사 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="90553-104">For example, suppose you want to copy selected text from the child form's text box to the Clipboard.</span></span> <span data-ttu-id="90553-105">선택한 텍스트를 사용 하 여 클립보드에 복사 하는 프로시저를 만듭니다는 <xref:System.Windows.Forms.Control.Click> 표준 편집 메뉴에서 복사 메뉴 항목의 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="90553-105">You would create a procedure that copies selected text to the Clipboard using the <xref:System.Windows.Forms.Control.Click> event of the Copy menu item on the standard Edit menu.</span></span>  
  
 <span data-ttu-id="90553-106">MDI 응용 프로그램에서 동일한 자식 폼의 여러 인스턴스를 가질 수 있으므로 프로시저 사용할 폼을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90553-106">Because an MDI application can have many instances of the same child form, the procedure needs to know which form to use.</span></span> <span data-ttu-id="90553-107">올바른 형식을 지정 하려면 사용 된 <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> 포커스가 있는 또는 가장 최근에 활성화 된 자식 폼을 반환 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="90553-107">To specify the correct form, use the <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> property, which returns the child form that has the focus or that was most recently active.</span></span>  
  
 <span data-ttu-id="90553-108">양식의 여러 컨트롤에 있는 경우도 활성 컨트롤을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90553-108">When you have several controls on a form, you also need to specify which control is active.</span></span> <span data-ttu-id="90553-109">같은 합니다 <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> 속성인은 <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> 속성 활성 자식 폼에 포커스를 사용 하 여 컨트롤을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="90553-109">Like the <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> property, the <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> property returns the control with the focus on the active child form.</span></span> <span data-ttu-id="90553-110">아래 절차를 자식 폼 메뉴의 메뉴를 MDI 폼 또는 도구 모음 단추에서 호출할 수 있는 복사 절차를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="90553-110">The procedure below illustrates a copy procedure that can be called from a child form menu, a menu on the MDI form, or a toolbar button.</span></span>  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a><span data-ttu-id="90553-111">활성 MDI 자식 (해당 텍스트를 클립보드로 복사)를 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="90553-111">To determine the active MDI child (to copy its text to the Clipboard)</span></span>  
  
1. <span data-ttu-id="90553-112">인 메서드 내부의 활성 자식 폼의 활성 컨트롤의 텍스트를 클립보드에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="90553-112">Within a method, copy the text of the active control of the active child form to the Clipboard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="90553-113">이 예제에서는 가정 MDI 부모 폼 (`Form1`) 포함 된 하나 이상의 MDI 자식 창에 있는 <xref:System.Windows.Forms.RichTextBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="90553-113">This example assumes there is an MDI parent form (`Form1`) that has one or more MDI child windows containing a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="90553-114">자세한 내용은 [MDI 부모 폼 만들기](how-to-create-mdi-parent-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="90553-114">For more information, see [Creating MDI Parent Forms](how-to-create-mdi-parent-forms.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="90553-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="90553-115">See also</span></span>

- [<span data-ttu-id="90553-116">MDI(다중 문서 인터페이스) 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="90553-116">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="90553-117">방법: MDI 부모 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="90553-117">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="90553-118">방법: MDI 자식 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="90553-118">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="90553-119">방법: 활성 MDI 자식으로 데이터 전송</span><span class="sxs-lookup"><span data-stu-id="90553-119">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="90553-120">방법: MDI 자식 폼 정렬</span><span class="sxs-lookup"><span data-stu-id="90553-120">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
