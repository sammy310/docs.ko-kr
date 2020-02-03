---
title: TextBox 컨트롤에서 삽입 지점 제어
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
ms.openlocfilehash: fd4803820921f0c922a4ce885f809abee8fd4c6c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742210"
---
# <a name="how-to-control-the-insertion-point-in-a-windows-forms-textbox-control"></a><span data-ttu-id="a566b-102">방법: Windows Forms TextBox 컨트롤에서 삽입 지점 제어</span><span class="sxs-lookup"><span data-stu-id="a566b-102">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>
<span data-ttu-id="a566b-103">Windows Forms <xref:System.Windows.Forms.TextBox> 컨트롤에서 먼저 포커스를 받을 때 텍스트 상자에 있는 기본 삽입은 기존 텍스트의 왼쪽에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a566b-103">When a Windows Forms <xref:System.Windows.Forms.TextBox> control first receives the focus, the default insertion within the text box is to the left of any existing text.</span></span> <span data-ttu-id="a566b-104">사용자는 키보드 또는 마우스를 사용 하 여 삽입 지점을 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a566b-104">The user can move the insertion point with the keyboard or the mouse.</span></span> <span data-ttu-id="a566b-105">텍스트 상자가 손실 된 다음 포커스를 다시 얻으면 사용자가 마지막으로 배치 된 위치에 삽입 지점이 삽입 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a566b-105">If the text box loses and then regains the focus, the insertion point will be wherever the user last placed it.</span></span>  
  
 <span data-ttu-id="a566b-106">경우에 따라 사용자에 게이 동작을 disconcerting 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a566b-106">In some cases, this behavior can be disconcerting to the user.</span></span> <span data-ttu-id="a566b-107">워드 프로세싱 응용 프로그램에서 사용자는 기존 텍스트 뒤에 새 문자를 표시 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a566b-107">In a word processing application, the user might expect new characters to appear after any existing text.</span></span> <span data-ttu-id="a566b-108">데이터 입력 응용 프로그램에서 사용자는 기존 항목을 대체할 새 문자를 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a566b-108">In a data entry application, the user might expect new characters to replace any existing entry.</span></span> <span data-ttu-id="a566b-109"><xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> 및 <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> 속성을 사용 하면 용도에 맞게 동작을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a566b-109">The <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> and <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> properties enable you to modify the behavior to suit your purpose.</span></span>  
  
### <a name="to-control-the-insertion-point-in-a-textbox-control"></a><span data-ttu-id="a566b-110">TextBox 컨트롤에서 삽입 지점을 제어 하려면</span><span class="sxs-lookup"><span data-stu-id="a566b-110">To control the insertion point in a TextBox control</span></span>  
  
1. <span data-ttu-id="a566b-111"><xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> 속성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a566b-111">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property to an appropriate value.</span></span> <span data-ttu-id="a566b-112">0은 삽입 지점을 첫 번째 문자 바로 왼쪽에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a566b-112">Zero places the insertion point immediately to the left of the first character.</span></span>  
  
2. <span data-ttu-id="a566b-113">필드 <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> 속성을 선택 하려는 텍스트의 길이로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a566b-113">(Optional) Set the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property to the length of the text you want to select.</span></span>  
  
     <span data-ttu-id="a566b-114">아래 코드는 항상 삽입 지점을 0으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a566b-114">The code below always returns the insertion point to 0.</span></span> <span data-ttu-id="a566b-115">`TextBox1_Enter` 이벤트 처리기는 컨트롤에 바인딩되어야 합니다. 자세한 내용은 [Windows Forms에서 이벤트 처리기 만들기](../creating-event-handlers-in-windows-forms.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a566b-115">The `TextBox1_Enter` event handler must be bound to the control; for more information, see [Creating Event Handlers in Windows Forms](../creating-event-handlers-in-windows-forms.md).</span></span>  
  
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
  
## <a name="making-the-insertion-point-visible-by-default"></a><span data-ttu-id="a566b-116">삽입 지점이 기본적으로 표시 되도록 설정</span><span class="sxs-lookup"><span data-stu-id="a566b-116">Making the Insertion Point Visible by Default</span></span>  
 <span data-ttu-id="a566b-117"><xref:System.Windows.Forms.TextBox> 삽입 지점은 <xref:System.Windows.Forms.TextBox> 컨트롤이 탭 순서에서 첫 번째 인 경우에만 기본적으로 새 폼에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a566b-117">The <xref:System.Windows.Forms.TextBox> insertion point is visible by default in a new form only if the <xref:System.Windows.Forms.TextBox> control is first in the tab order.</span></span> <span data-ttu-id="a566b-118">그렇지 않으면 키보드 또는 마우스를 사용 하 여 <xref:System.Windows.Forms.TextBox> 포커스를 제공 하는 경우에만 삽입 지점이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a566b-118">Otherwise, the insertion point appears only if you give the <xref:System.Windows.Forms.TextBox> the focus with either the keyboard or the mouse.</span></span>  
  
#### <a name="to-make-the-text-box-insertion-point-visible-by-default-on-a-new-form"></a><span data-ttu-id="a566b-119">텍스트 상자 삽입 지점이 기본적으로 새 폼에 표시 되도록 하려면</span><span class="sxs-lookup"><span data-stu-id="a566b-119">To make the text box insertion point visible by default on a new form</span></span>  
  
- <span data-ttu-id="a566b-120"><xref:System.Windows.Forms.TextBox> 컨트롤의 <xref:System.Windows.Forms.Control.TabIndex%2A> 속성을 `0`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a566b-120">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.Control.TabIndex%2A> property to `0`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a566b-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a566b-121">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="a566b-122">TextBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="a566b-122">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="a566b-123">방법: Windows Forms TextBox 컨트롤을 사용하여 암호 텍스트 상자 만들기</span><span class="sxs-lookup"><span data-stu-id="a566b-123">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="a566b-124">방법: 읽기 전용 텍스트 상자 만들기</span><span class="sxs-lookup"><span data-stu-id="a566b-124">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="a566b-125">방법: 문자열에 인용 부호 넣기</span><span class="sxs-lookup"><span data-stu-id="a566b-125">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="a566b-126">방법: Windows Forms TextBox 컨트롤에서 텍스트 선택</span><span class="sxs-lookup"><span data-stu-id="a566b-126">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="a566b-127">방법: Windows Forms TextBox 컨트롤에 여러 줄 표시</span><span class="sxs-lookup"><span data-stu-id="a566b-127">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="a566b-128">TextBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="a566b-128">TextBox Control</span></span>](textbox-control-windows-forms.md)
