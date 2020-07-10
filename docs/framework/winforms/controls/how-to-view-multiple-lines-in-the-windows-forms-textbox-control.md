---
title: TextBox 컨트롤에서 여러 줄 보기
description: 여러 줄, WordWrap 및 ScrollBars 속성을 설정 하 여 Windows Forms TextBox 컨트롤에서 여러 줄을 보는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- newline
- end of line
- ScrollBars property [Windows Forms], in TextBox control
- CRLF
- MultiLine property in TextBox control
- line-feed
- TextBox control [Windows Forms], viewing multiple lines
- carriage return
ms.assetid: 43173201-0b74-4067-a472-605029ca5f35
ms.openlocfilehash: e40d720bcd56366f4f06bfe2e2d347aaf9aa9d6c
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174473"
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a><span data-ttu-id="cd165-103">방법: Windows Forms TextBox 컨트롤에서 여러 줄 표시</span><span class="sxs-lookup"><span data-stu-id="cd165-103">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>
<span data-ttu-id="cd165-104">기본적으로 Windows Forms 컨트롤은 <xref:System.Windows.Forms.TextBox> 한 줄의 텍스트를 표시 하 고 스크롤 막대를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd165-104">By default, the Windows Forms <xref:System.Windows.Forms.TextBox> control displays a single line of text and does not display scroll bars.</span></span> <span data-ttu-id="cd165-105">텍스트가 사용 가능한 공간 보다 길면 텍스트의 일부만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd165-105">If the text is longer than the available space, only part of the text is visible.</span></span> <span data-ttu-id="cd165-106"><xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 및 <xref:System.Windows.Forms.TextBox.ScrollBars%2A> 속성을 적절 한 값으로 설정 하 여이 기본 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd165-106">You can change this default behavior by setting the <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>, and <xref:System.Windows.Forms.TextBox.ScrollBars%2A> properties to appropriate values.</span></span>  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a><span data-ttu-id="cd165-107">TextBox 컨트롤에서 캐리지 리턴을 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="cd165-107">To display a carriage return in the TextBox control</span></span>  
  
- <span data-ttu-id="cd165-108">여러 줄에서 캐리지 리턴을 표시 하려면 <xref:System.Windows.Forms.TextBox> 속성을 사용 <xref:System.Environment.NewLine%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd165-108">To display a carriage return in a multi-line <xref:System.Windows.Forms.TextBox>, use the <xref:System.Environment.NewLine%2A> property.</span></span>  
  
     <span data-ttu-id="cd165-109">이스케이프 문자 ()의 해석은 \\ 언어 마다 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="cd165-109">Be aware that the interpretation of escape characters (\\) is language-specific.</span></span> <span data-ttu-id="cd165-110">Visual Basic는 `Chr$(13) & Chr$(10)` 캐리지 리턴 및 줄 바꿈 문자 조합에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd165-110">Visual Basic uses `Chr$(13) & Chr$(10)` for the carriage return and linefeed character combination.</span></span>  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a><span data-ttu-id="cd165-111">TextBox 컨트롤에서 여러 줄을 보려면</span><span class="sxs-lookup"><span data-stu-id="cd165-111">To view multiple lines in the TextBox control</span></span>  
  
1. <span data-ttu-id="cd165-112"><xref:System.Windows.Forms.TextBox.Multiline%2A> 속성을 `true`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cd165-112">Set the <xref:System.Windows.Forms.TextBox.Multiline%2A> property to `true`.</span></span> <span data-ttu-id="cd165-113"><xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>가 `true` (기본값) 이면 컨트롤의 텍스트가 하나 이상의 단락으로 표시 되 고, 그렇지 않으면 컨트롤의 가장자리에서 일부 줄이 잘릴 수 있는 목록으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd165-113">If <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> is `true` (the default), then the text in the control will appear as one or more paragraphs; otherwise it will appear as a list, in which some lines may be clipped at the edge of the control.</span></span>  
  
2. <span data-ttu-id="cd165-114"><xref:System.Windows.Forms.TextBox.ScrollBars%2A> 속성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cd165-114">Set the <xref:System.Windows.Forms.TextBox.ScrollBars%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="cd165-115">값</span><span class="sxs-lookup"><span data-stu-id="cd165-115">Value</span></span>|<span data-ttu-id="cd165-116">설명</span><span class="sxs-lookup"><span data-stu-id="cd165-116">Description</span></span>|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|<span data-ttu-id="cd165-117">텍스트가 거의 항상 컨트롤에 맞는 단락이 면이 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd165-117">Use this value if the text will be a paragraph that almost always fits the control.</span></span> <span data-ttu-id="cd165-118">텍스트가 너무 길어서 한 번에 표시할 수 없는 경우 사용자는 마우스 포인터를 사용 하 여 컨트롤 내에서 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd165-118">The user can use the mouse pointer to move around inside the control if the text is too long to display all at once.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|<span data-ttu-id="cd165-119">줄 목록을 표시 하 고, 일부는 컨트롤의 너비 보다 길 수 있는 경우이 값을 사용 <xref:System.Windows.Forms.TextBox> 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd165-119">Use this value if you want to display a list of lines, some of which may be longer than the width of the <xref:System.Windows.Forms.TextBox> control.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|<span data-ttu-id="cd165-120">목록이 컨트롤의 높이 보다 길면이 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd165-120">Use this value if the list may be longer than the height of the control.</span></span>|  
  
3. <span data-ttu-id="cd165-121"><xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 속성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cd165-121">Set the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="cd165-122">값</span><span class="sxs-lookup"><span data-stu-id="cd165-122">Value</span></span>|<span data-ttu-id="cd165-123">설명</span><span class="sxs-lookup"><span data-stu-id="cd165-123">Description</span></span>|  
    |-----------|-----------------|  
    |`false`|<span data-ttu-id="cd165-124">컨트롤의 텍스트는 자동으로 래핑되지 않으므로 줄 바꿈에 도달할 때까지 오른쪽으로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="cd165-124">Text in the control will not automatically be wrapped, so it will scroll to the right until a line break is reached.</span></span> <span data-ttu-id="cd165-125"><xref:System.Windows.Forms.ScrollBars.Horizontal>스크롤 막대 또는을 선택한 경우이 값 <xref:System.Windows.Forms.ScrollBars.Both> 을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd165-125">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Horizontal> scroll bars or <xref:System.Windows.Forms.ScrollBars.Both>, above.</span></span>|  
    |<span data-ttu-id="cd165-126">`true`(기본값)</span><span class="sxs-lookup"><span data-stu-id="cd165-126">`true` (default)</span></span>|<span data-ttu-id="cd165-127">가로 스크롤 막대는 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd165-127">The horizontal scrollbar will not appear.</span></span> <span data-ttu-id="cd165-128"><xref:System.Windows.Forms.ScrollBars.Vertical>스크롤 막대 또는 위를 선택 하 여 하나 이상의 단락을 표시 하는 경우이 값을 사용 <xref:System.Windows.Forms.ScrollBars.None> 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd165-128">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Vertical> scroll bars or <xref:System.Windows.Forms.ScrollBars.None>, above, to display one or more paragraphs.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cd165-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cd165-129">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="cd165-130">TextBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="cd165-130">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="cd165-131">방법: Windows Forms TextBox 컨트롤에서 삽입 지점 제어</span><span class="sxs-lookup"><span data-stu-id="cd165-131">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="cd165-132">방법: Windows Forms TextBox 컨트롤을 사용하여 암호 텍스트 상자 만들기</span><span class="sxs-lookup"><span data-stu-id="cd165-132">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="cd165-133">방법: 읽기 전용 텍스트 상자 만들기</span><span class="sxs-lookup"><span data-stu-id="cd165-133">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="cd165-134">방법: 문자열에 인용 부호 넣기</span><span class="sxs-lookup"><span data-stu-id="cd165-134">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="cd165-135">방법: Windows Forms TextBox 컨트롤에서 텍스트 선택</span><span class="sxs-lookup"><span data-stu-id="cd165-135">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="cd165-136">TextBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="cd165-136">TextBox Control</span></span>](textbox-control-windows-forms.md)
