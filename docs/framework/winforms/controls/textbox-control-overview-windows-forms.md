---
title: TextBox 컨트롤 개요(Windows Forms)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TextBox
helpviewer_keywords:
- TextBox control [Windows Forms], about TextBox controls
- text boxes [Windows Forms], adding
ms.assetid: d1a9c7f5-fa53-480a-a75c-158f8649ea2f
ms.openlocfilehash: a91b67df1071c79707bb20a68efb4d5e6f083ae0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61932550"
---
# <a name="textbox-control-overview-windows-forms"></a><span data-ttu-id="41731-102">TextBox 컨트롤 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="41731-102">TextBox Control Overview (Windows Forms)</span></span>
<span data-ttu-id="41731-103">Windows Forms 텍스트 상자에는 사용자 로부터 입력 하거나 텍스트를 표시 하도록 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41731-103">Windows Forms text boxes are used to get input from the user or to display text.</span></span> <span data-ttu-id="41731-104"><xref:System.Windows.Forms.TextBox> 컨트롤은 일반적으로 편집 가능한 텍스트에 사용 하도 설정할 수 있지만 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="41731-104">The <xref:System.Windows.Forms.TextBox> control is generally used for editable text, although it can also be made read-only.</span></span> <span data-ttu-id="41731-105">입력란 수 여러 줄을 표시, 텍스트 컨트롤의 크기를 래핑하고 기본 서식을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="41731-105">Text boxes can display multiple lines, wrap text to the size of the control, and add basic formatting.</span></span> <span data-ttu-id="41731-106"><xref:System.Windows.Forms.TextBox> 컨트롤은 컨트롤에 표시 되거나 입력 텍스트에 대 한 단일 형식 스타일을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="41731-106">The <xref:System.Windows.Forms.TextBox> control provides a single format style for text displayed or entered into the control.</span></span> <span data-ttu-id="41731-107">여러 유형의 서식 있는 텍스트를 표시 하려면 사용 된 <xref:System.Windows.Forms.RichTextBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="41731-107">To display multiple types of formatted text, use the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="41731-108">자세한 내용은 [RichTextBox 컨트롤 개요](richtextbox-control-overview-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="41731-108">For more information, see [RichTextBox Control Overview](richtextbox-control-overview-windows-forms.md).</span></span>  
  
## <a name="working-with-the-textbox-control"></a><span data-ttu-id="41731-109">TextBox 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="41731-109">Working with the TextBox Control</span></span>  
 <span data-ttu-id="41731-110">컨트롤에서 표시 되는 텍스트에 포함 된 <xref:System.Windows.Forms.TextBox.Text%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="41731-110">The text displayed by the control is contained in the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span> <span data-ttu-id="41731-111">기본적으로 최대 2048 자의 텍스트 상자에 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41731-111">By default, you can enter up to 2048 characters in a text box.</span></span> <span data-ttu-id="41731-112">설정한 경우에 <xref:System.Windows.Forms.TextBox.Multiline%2A> 속성을 `true`, 최대 32KB의 텍스트를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41731-112">If you set the <xref:System.Windows.Forms.TextBox.Multiline%2A> property to `true`, you can enter up to 32 KB of text.</span></span> <span data-ttu-id="41731-113"><xref:System.Windows.Forms.TextBox.Text%2A> 런타임 시 사용자 입력에 따라 또는 코드에서 런타임에 속성 창을 사용 하 여 디자인 타임에 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41731-113">The <xref:System.Windows.Forms.TextBox.Text%2A> property can be set at design time with the Properties Window, at run time in code, or by user input at run time.</span></span> <span data-ttu-id="41731-114">입력란의 현재 내용을 참조 하 여 런타임 시 검색할 수 있습니다는 <xref:System.Windows.Forms.TextBox.Text%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="41731-114">The current contents of a text box can be retrieved at run time by reading the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>  
  
 <span data-ttu-id="41731-115">다음 코드 예제는 런타임 시 컨트롤의 텍스트를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="41731-115">The following code example sets text in the control at run time.</span></span> <span data-ttu-id="41731-116">`InitializeMyControl` 프로시저는 자동으로 실행 되지 않으면 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41731-116">The `InitializeMyControl` procedure will not execute automatically; it must be called.</span></span>  
  
```vb  
Private Sub InitializeMyControl()  
   ' Put some text into the control first.  
   TextBox1.Text = "This is a TextBox control."  
End Sub  
```  
  
```csharp  
private void InitializeMyControl() {  
   // Put some text into the control first.  
   textBox1.Text = "This is a TextBox control.";  
}  
```  
  
```cpp  
private:  
   void InitializeMyControl()  
   {  
      // Put some text into the control first.  
      textBox1->Text = "This is a TextBox control.";  
   }  
```  
  
## <a name="see-also"></a><span data-ttu-id="41731-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="41731-117">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="41731-118">방법: Windows Forms TextBox 컨트롤의 삽입 지점 제어</span><span class="sxs-lookup"><span data-stu-id="41731-118">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="41731-119">방법: Windows Forms TextBox 컨트롤을 사용 하 여 암호 텍스트 상자 만들기</span><span class="sxs-lookup"><span data-stu-id="41731-119">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="41731-120">방법: 읽기 전용 텍스트 상자 만들기</span><span class="sxs-lookup"><span data-stu-id="41731-120">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="41731-121">방법: 문자열에 인용 부호 넣기</span><span class="sxs-lookup"><span data-stu-id="41731-121">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="41731-122">방법: Windows Forms TextBox 컨트롤에서 텍스트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="41731-122">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="41731-123">방법: Windows Forms TextBox 컨트롤에서 여러 줄 보기</span><span class="sxs-lookup"><span data-stu-id="41731-123">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="41731-124">TextBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="41731-124">TextBox Control</span></span>](textbox-control-windows-forms.md)
