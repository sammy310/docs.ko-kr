---
title: '방법: Windows Forms TextBox 컨트롤의 삽입 지점 제어'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], insertion point
- insertion points [Windows Forms], TextBox controls
- text boxes [Windows Forms], controlling insertion point
ms.assetid: 5bee7d34-5121-429e-ab1f-d8ff67bc74c1
ms.openlocfilehash: cb3e7e7a44391ec7ee34ad0659f4185bd2304d26
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714894"
---
# <a name="how-to-control-the-insertion-point-in-a-windows-forms-textbox-control"></a><span data-ttu-id="bbe7d-102">방법: Windows Forms TextBox 컨트롤의 삽입 지점 제어</span><span class="sxs-lookup"><span data-stu-id="bbe7d-102">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>
<span data-ttu-id="bbe7d-103">경우는 Windows Forms <xref:System.Windows.Forms.TextBox> 컨트롤의 포커스를 처음 받을, 기존 텍스트의 왼쪽에 텍스트 상자 내에서 기본 삽입 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7d-103">When a Windows Forms <xref:System.Windows.Forms.TextBox> control first receives the focus, the default insertion within the text box is to the left of any existing text.</span></span> <span data-ttu-id="bbe7d-104">키보드 또는 마우스를 사용 하 여 커서를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7d-104">The user can move the insertion point with the keyboard or the mouse.</span></span> <span data-ttu-id="bbe7d-105">텍스트 상자를 잃고 포커스를 다시 얻은 후, 하는 경우 아무 곳에 나 사용자 마지막으로 저장할 삽입 지점이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7d-105">If the text box loses and then regains the focus, the insertion point will be wherever the user last placed it.</span></span>  
  
 <span data-ttu-id="bbe7d-106">일부 경우에이 동작을 사용자에 게 혼란을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7d-106">In some cases, this behavior can be disconcerting to the user.</span></span> <span data-ttu-id="bbe7d-107">단어의 처리 응용 프로그램을 사용자 기존 텍스트 뒤에 새 문자를 예상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7d-107">In a word processing application, the user might expect new characters to appear after any existing text.</span></span> <span data-ttu-id="bbe7d-108">데이터 항목 응용 프로그램에서는 사용자 모든 기존 항목을 바꾸려면 새로운 문자 예상 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7d-108">In a data entry application, the user might expect new characters to replace any existing entry.</span></span> <span data-ttu-id="bbe7d-109">합니다 <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> 고 <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> 속성을 사용 하는 목적에 맞게 동작을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7d-109">The <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> and <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> properties enable you to modify the behavior to suit your purpose.</span></span>  
  
### <a name="to-control-the-insertion-point-in-a-textbox-control"></a><span data-ttu-id="bbe7d-110">TextBox 컨트롤의 삽입 지점 제어</span><span class="sxs-lookup"><span data-stu-id="bbe7d-110">To control the insertion point in a TextBox control</span></span>  
  
1.  <span data-ttu-id="bbe7d-111">
  <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> 속성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7d-111">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property to an appropriate value.</span></span> <span data-ttu-id="bbe7d-112">0에 바로 첫 번째 문자의 왼쪽에 삽입 지점을 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7d-112">Zero places the insertion point immediately to the left of the first character.</span></span>  
  
2.  <span data-ttu-id="bbe7d-113">(선택 사항) 설정 된 <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> 속성을 선택 하려는 텍스트의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7d-113">(Optional) Set the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property to the length of the text you want to select.</span></span>  
  
     <span data-ttu-id="bbe7d-114">아래 코드는 항상 0으로 삽입 포인터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7d-114">The code below always returns the insertion point to 0.</span></span> <span data-ttu-id="bbe7d-115">합니다 `TextBox1_Enter` 이벤트 처리기에 대 한 자세한 내용은 컨트롤에 바인딩할 수 해야을 참조 하십시오 [Windows Forms에서 이벤트 처리기 만들기](../creating-event-handlers-in-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7d-115">The `TextBox1_Enter` event handler must be bound to the control; for more information, see [Creating Event Handlers in Windows Forms](../creating-event-handlers-in-windows-forms.md).</span></span>  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       TextBox1.SelectionStart = 0  
       TextBox1.SelectionLength = 0  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_Enter(Object sender, System.EventArgs e) {  
       textBox1.SelectionStart = 0;  
       textBox1.SelectionLength = 0;  
    }  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = 0;  
       }  
    ```  
  
## <a name="making-the-insertion-point-visible-by-default"></a><span data-ttu-id="bbe7d-116">삽입 지점에 기본적으로 표시 하기</span><span class="sxs-lookup"><span data-stu-id="bbe7d-116">Making the Insertion Point Visible by Default</span></span>  
 <span data-ttu-id="bbe7d-117"><xref:System.Windows.Forms.TextBox> 삽입 지점이 새 양식만 경우에는 기본적으로 표시 되는 <xref:System.Windows.Forms.TextBox> 컨트롤은 탭 순서에서 첫 번째입니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7d-117">The <xref:System.Windows.Forms.TextBox> insertion point is visible by default in a new form only if the <xref:System.Windows.Forms.TextBox> control is first in the tab order.</span></span> <span data-ttu-id="bbe7d-118">삽입 지점을 제공 하는 경우에 표시 되는 고, 그렇지는 <xref:System.Windows.Forms.TextBox> 키보드 또는 마우스를 사용 하 여 포커스를 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7d-118">Otherwise, the insertion point appears only if you give the <xref:System.Windows.Forms.TextBox> the focus with either the keyboard or the mouse.</span></span>  
  
#### <a name="to-make-the-text-box-insertion-point-visible-by-default-on-a-new-form"></a><span data-ttu-id="bbe7d-119">새 폼에는 기본적으로 텍스트 상자 삽입 지점을 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="bbe7d-119">To make the text box insertion point visible by default on a new form</span></span>  
  
-   <span data-ttu-id="bbe7d-120">설정 된 <xref:System.Windows.Forms.TextBox> 컨트롤의 <xref:System.Windows.Forms.Control.TabIndex%2A> 속성을 `0`입니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7d-120">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.Control.TabIndex%2A> property to `0`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbe7d-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="bbe7d-121">See also</span></span>
- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="bbe7d-122">TextBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="bbe7d-122">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="bbe7d-123">방법: Windows Forms TextBox 컨트롤을 사용 하 여 암호 텍스트 상자 만들기</span><span class="sxs-lookup"><span data-stu-id="bbe7d-123">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="bbe7d-124">방법: 읽기 전용 텍스트 상자 만들기</span><span class="sxs-lookup"><span data-stu-id="bbe7d-124">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="bbe7d-125">방법: 문자열에 인용 부호 넣기</span><span class="sxs-lookup"><span data-stu-id="bbe7d-125">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="bbe7d-126">방법: Windows Forms TextBox 컨트롤에서 텍스트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbe7d-126">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="bbe7d-127">방법: Windows Forms TextBox 컨트롤에서 여러 줄 보기</span><span class="sxs-lookup"><span data-stu-id="bbe7d-127">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="bbe7d-128">TextBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="bbe7d-128">TextBox Control</span></span>](textbox-control-windows-forms.md)
