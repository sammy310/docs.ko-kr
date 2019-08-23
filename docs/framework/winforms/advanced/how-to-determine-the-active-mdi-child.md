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
ms.openlocfilehash: 91100b37e4cae9041479b209e40034efe376df5b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946215"
---
# <a name="how-to-determine-the-active-mdi-child"></a><span data-ttu-id="efa15-102">방법: 활성 MDI 자식 확인</span><span class="sxs-lookup"><span data-stu-id="efa15-102">How to: Determine the Active MDI Child</span></span>
<span data-ttu-id="efa15-103">경우에 따라 현재 활성화 된 자식 폼에 포커스가 있는 컨트롤에 대해 작동 하는 명령을 제공 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa15-103">On occasion, you will want to provide a command that operates on the control that has focus on the currently active child form.</span></span> <span data-ttu-id="efa15-104">예를 들어 선택한 텍스트를 자식 폼의 텍스트 상자에서 클립보드로 복사 하려는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="efa15-104">For example, suppose you want to copy selected text from the child form's text box to the Clipboard.</span></span> <span data-ttu-id="efa15-105">표준 편집 메뉴의 복사 메뉴 항목의 이벤트를 <xref:System.Windows.Forms.Control.Click> 사용 하 여 선택한 텍스트를 클립보드에 복사 하는 프로시저를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efa15-105">You would create a procedure that copies selected text to the Clipboard using the <xref:System.Windows.Forms.Control.Click> event of the Copy menu item on the standard Edit menu.</span></span>  
  
 <span data-ttu-id="efa15-106">MDI 응용 프로그램에는 동일한 자식 폼의 여러 인스턴스가 있을 수 있으므로 프로시저에서 사용할 폼을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa15-106">Because an MDI application can have many instances of the same child form, the procedure needs to know which form to use.</span></span> <span data-ttu-id="efa15-107">올바른 형식을 지정 하려면 포커스가 있거나 가장 최근에 <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> 활성화 된 자식 폼을 반환 하는 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa15-107">To specify the correct form, use the <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> property, which returns the child form that has the focus or that was most recently active.</span></span>  
  
 <span data-ttu-id="efa15-108">폼에 여러 컨트롤이 있는 경우에는 어떤 컨트롤이 활성화 되어 있는지도 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa15-108">When you have several controls on a form, you also need to specify which control is active.</span></span> <span data-ttu-id="efa15-109">속성과 마찬가지로 속성은 <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> 활성 자식 폼에 포커스가 있는 컨트롤을 반환 합니다. <xref:System.Windows.Forms.Form.ActiveMdiChild%2A></span><span class="sxs-lookup"><span data-stu-id="efa15-109">Like the <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> property, the <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> property returns the control with the focus on the active child form.</span></span> <span data-ttu-id="efa15-110">아래 절차에서는 자식 폼 메뉴, MDI 폼의 메뉴 또는 도구 모음 단추에서 호출할 수 있는 복사 프로시저를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="efa15-110">The procedure below illustrates a copy procedure that can be called from a child form menu, a menu on the MDI form, or a toolbar button.</span></span>  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a><span data-ttu-id="efa15-111">활성 MDI 자식 (텍스트를 클립보드에 복사)을 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="efa15-111">To determine the active MDI child (to copy its text to the Clipboard)</span></span>  
  
1. <span data-ttu-id="efa15-112">메서드 내에서 활성 자식 폼의 활성 컨트롤 텍스트를 클립보드에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa15-112">Within a method, copy the text of the active control of the active child form to the Clipboard.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="efa15-113">이 예제에서는 컨트롤을`Form1` <xref:System.Windows.Forms.RichTextBox> 포함 하는 mdi 자식 창이 하나 이상 있는 mdi 부모 폼 ()이 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa15-113">This example assumes there is an MDI parent form (`Form1`) that has one or more MDI child windows containing a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="efa15-114">자세한 내용은 [MDI 부모 폼 만들기](how-to-create-mdi-parent-forms.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="efa15-114">For more information, see [Creating MDI Parent Forms](how-to-create-mdi-parent-forms.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="efa15-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="efa15-115">See also</span></span>

- [<span data-ttu-id="efa15-116">MDI(다중 문서 인터페이스) 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="efa15-116">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="efa15-117">방법: MDI 부모 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="efa15-117">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="efa15-118">방법: MDI 자식 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="efa15-118">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="efa15-119">방법: 활성 MDI 자식으로 데이터 보내기</span><span class="sxs-lookup"><span data-stu-id="efa15-119">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="efa15-120">방법: MDI 자식 폼 정렬</span><span class="sxs-lookup"><span data-stu-id="efa15-120">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
