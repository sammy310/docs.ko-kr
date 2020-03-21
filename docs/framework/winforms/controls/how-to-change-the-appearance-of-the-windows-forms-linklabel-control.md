---
title: 링크 레이블 컨트롤의 모양 변경
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- LinkLabel properties
- LinkLabel control [Windows Forms], changing appearance of links
- links [Windows Forms], changing appearance
- examples [Windows Forms], LinkLabel control
- LinkLabel control [Windows Forms], examples
ms.assetid: fdc5854f-5162-4457-8cbe-1042feb2d132
ms.openlocfilehash: df66991289373a05fc7c27b7768a96643e3bbae0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142132"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a><span data-ttu-id="dadd4-102">방법: Windows Forms LinkLabel 컨트롤의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="dadd4-102">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>
<span data-ttu-id="dadd4-103"><xref:System.Windows.Forms.LinkLabel> 컨트롤에서 표시되는 텍스트를 다양한 용도에 맞게 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dadd4-103">You can change the text displayed by the <xref:System.Windows.Forms.LinkLabel> control to suit a variety of purposes.</span></span> <span data-ttu-id="dadd4-104">예를 들어 텍스트가 밑줄이 있는 특정 색상으로 표시되도록 설정하여 텍스트를 클릭할 수 있음을 사용자에게 표시하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="dadd4-104">For example, it is common practice to indicate to the user that text can be clicked by setting the text to appear in a specific color with an underline.</span></span> <span data-ttu-id="dadd4-105">사용자가 텍스트를 클릭하면 색상이 다른 색상으로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="dadd4-105">After the user clicks the text, the color changes to a different color.</span></span> <span data-ttu-id="dadd4-106">이 동작을 제어하려면 <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>의 다섯 가지 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>속성(" <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> 및 속성)을 <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dadd4-106">To control this behavior, you can set five different properties: the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, and <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> properties.</span></span>  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a><span data-ttu-id="dadd4-107">링크라벨 컨트롤의 모양을 변경하려면</span><span class="sxs-lookup"><span data-stu-id="dadd4-107">To change the appearance of a LinkLabel control</span></span>  
  
1. <span data-ttu-id="dadd4-108"><xref:System.Windows.Forms.LinkLabel.LinkColor%2A> 및 <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> 속성을 원하는 색상으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dadd4-108">Set the <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> and <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> properties to the colors you want.</span></span>  
  
     <span data-ttu-id="dadd4-109">이 작업은 프로그래매틱방식으로 또는 **속성** 창의 디자인 타임에 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dadd4-109">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    ' You can set the color using decimal values for red, green, and blue  
    LinkLabel1.LinkColor = Color.FromArgb(0, 0, 255)  
    ' Or you can set the color using defined constants  
    LinkLabel1.VisitedLinkColor = Color.Purple  
    ```  
  
    ```csharp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1.LinkColor = Color.FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1.VisitedLinkColor = Color.Purple;  
    ```  
  
    ```cpp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1->LinkColor = Color::FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1->VisitedLinkColor = Color::Purple;  
    ```  
  
2. <span data-ttu-id="dadd4-110"><xref:System.Windows.Forms.LinkLabel.Text%2A> 속성을 적절한 캡션으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dadd4-110">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>  
  
     <span data-ttu-id="dadd4-111">이 작업은 프로그래매틱방식으로 또는 **속성** 창의 디자인 타임에 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dadd4-111">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3. <span data-ttu-id="dadd4-112">캡션의 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 어느 부분이 링크로 표시될지 결정하기 위해 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dadd4-112">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span>  
  
     <span data-ttu-id="dadd4-113">이 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 값은 시작 <xref:System.Windows.Forms.LinkArea> 문자 위치와 문자 수라는 두 개의 숫자를 포함하는 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dadd4-113">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> value is represented with a <xref:System.Windows.Forms.LinkArea> containing two numbers, the starting character position and the number of characters.</span></span> <span data-ttu-id="dadd4-114">이 작업은 프로그래매틱방식으로 또는 **속성** 창의 디자인 타임에 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dadd4-114">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4. <span data-ttu-id="dadd4-115"><xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> 속성을 <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>로 <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>설정합니다. <xref:System.Windows.Forms.LinkBehavior.NeverUnderline></span><span class="sxs-lookup"><span data-stu-id="dadd4-115">Set the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> property to <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, or <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>.</span></span>  
  
     <span data-ttu-id="dadd4-116"><xref:System.Windows.Forms.LinkBehavior.HoverUnderline>로 설정된 경우 에 의해 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 결정된 캡션 부분은 포인터가 포인터에 놓일 때만 밑줄이 그어집니다.</span><span class="sxs-lookup"><span data-stu-id="dadd4-116">If it is set to <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, the part of the caption determined by <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> will only be underlined when the pointer rests on it.</span></span>  
  
5. <span data-ttu-id="dadd4-117"><xref:System.Windows.Forms.LinkLabel.LinkClicked> 이벤트 처리기에서 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dadd4-117">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, set the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="dadd4-118">링크를 방문한 경우 일반적으로 색상으로 모양을 변경하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="dadd4-118">When a link has been visited, it is common practice to change its appearance in some way, usually by color.</span></span> <span data-ttu-id="dadd4-119">텍스트는 <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> 속성에서 지정한 색상으로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="dadd4-119">The text will change to the color specified by the <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> property.</span></span>  
  
    ```vb  
    Protected Sub LinkLabel1_LinkClicked (ByVal sender As Object, _  
       ByVal e As EventArgs) Handles LinkLabel1.LinkClicked  
       ' Change the color of the link text  
       ' by setting LinkVisited to True.  
       LinkLabel1.LinkVisited = True  
       ' Then do whatever other action is appropriate  
    End Sub  
    ```  
  
    ```csharp  
    protected void LinkLabel1_LinkClicked(object sender, System.EventArgs e)  
    {  
       // Change the color of the link text by setting LinkVisited
       // to True.  
       linkLabel1.LinkVisited = true;  
       // Then do whatever other action is appropriate  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          // Change the color of the link text by setting LinkVisited
          // to True.  
          linkLabel1->LinkVisited = true;  
          // Then do whatever other action is appropriate  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="dadd4-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dadd4-120">See also</span></span>

- <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>
- [<span data-ttu-id="dadd4-121">LinkLabel 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="dadd4-121">LinkLabel Control Overview</span></span>](linklabel-control-overview-windows-forms.md)
- [<span data-ttu-id="dadd4-122">방법: Windows Forms LinkLabel 컨트롤을 사용하여 개체 또는 웹 페이지에 연결</span><span class="sxs-lookup"><span data-stu-id="dadd4-122">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [<span data-ttu-id="dadd4-123">LinkLabel 컨트롤</span><span class="sxs-lookup"><span data-stu-id="dadd4-123">LinkLabel Control</span></span>](linklabel-control-windows-forms.md)
