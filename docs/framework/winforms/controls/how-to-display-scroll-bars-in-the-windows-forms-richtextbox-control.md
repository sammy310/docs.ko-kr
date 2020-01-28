---
title: RichTextBox 컨트롤에서 스크롤 막대 표시
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes [Windows Forms], displaying scroll bars
- scroll bars [Windows Forms], displaying in controls
- RichTextBox control [Windows Forms], displaying scroll bars
ms.assetid: cdeb42e1-86e8-410c-ba46-18aec264ef5f
ms.openlocfilehash: 2185b572ef20765043d3df3dbfd8bf5b21cfac28
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745555"
---
# <a name="how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control"></a><span data-ttu-id="ef258-102">방법: Windows Forms RichTextBox 컨트롤에서 스크롤 막대 표시</span><span class="sxs-lookup"><span data-stu-id="ef258-102">How to: Display Scroll Bars in the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="ef258-103">기본적으로 Windows Forms <xref:System.Windows.Forms.RichTextBox> 컨트롤은 필요한 경우 가로 및 세로 스크롤 막대를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef258-103">By default, the Windows Forms <xref:System.Windows.Forms.RichTextBox> control displays horizontal and vertical scroll bars as necessary.</span></span> <span data-ttu-id="ef258-104">아래 표에서 설명 하는 <xref:System.Windows.Forms.RichTextBox> 컨트롤의 <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> 속성에는 7 가지 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef258-104">There are seven possible values for the <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> property of the <xref:System.Windows.Forms.RichTextBox> control, which are described in the table below.</span></span>  
  
### <a name="to-display-scroll-bars-in-a-richtextbox-control"></a><span data-ttu-id="ef258-105">RichTextBox 컨트롤에서 스크롤 막대를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="ef258-105">To display scroll bars in a RichTextBox control</span></span>  
  
1. <span data-ttu-id="ef258-106"><xref:System.Windows.Forms.RichTextBox.Multiline%2A> 속성을 `true`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ef258-106">Set the <xref:System.Windows.Forms.RichTextBox.Multiline%2A> property to `true`.</span></span> <span data-ttu-id="ef258-107"><xref:System.Windows.Forms.RichTextBox.Multiline%2A> 속성이 `false`로 설정 되어 있으면 가로를 포함 하는 스크롤 막대의 형식이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef258-107">No type of scroll bar, including horizontal, will display if the <xref:System.Windows.Forms.RichTextBox.Multiline%2A> property is set to `false`.</span></span>  
  
2. <span data-ttu-id="ef258-108"><xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> 속성을 <xref:System.Windows.Forms.RichTextBoxScrollBars> 열거형의 적절 한 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef258-108">Set the <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> property to an appropriate value of the <xref:System.Windows.Forms.RichTextBoxScrollBars> enumeration.</span></span>  
  
    |<span data-ttu-id="ef258-109">값</span><span class="sxs-lookup"><span data-stu-id="ef258-109">Value</span></span>|<span data-ttu-id="ef258-110">설명</span><span class="sxs-lookup"><span data-stu-id="ef258-110">Description</span></span>|  
    |-----------|-----------------|  
    |<span data-ttu-id="ef258-111"><xref:System.Windows.Forms.RichTextBoxScrollBars.Both>(기본)</span><span class="sxs-lookup"><span data-stu-id="ef258-111"><xref:System.Windows.Forms.RichTextBoxScrollBars.Both> (default)</span></span>|<span data-ttu-id="ef258-112">텍스트가 컨트롤의 너비나 길이를 초과 하는 경우에만 가로 또는 세로 스크롤 막대를 표시 하거나 둘 다 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef258-112">Displays horizontal or vertical scroll bars, or both, only when text exceeds the width or length of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.None>|<span data-ttu-id="ef258-113">스크롤 막대의 유형을 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef258-113">Never displays any type of scroll bar.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Horizontal>|<span data-ttu-id="ef258-114">텍스트가 컨트롤의 너비를 초과 하는 경우에만 가로 스크롤 막대를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef258-114">Displays a horizontal scroll bar only when the text exceeds the width of the control.</span></span> <span data-ttu-id="ef258-115">이를 수행 하려면 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 속성을 `false`로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef258-115">(For this to occur, the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property must be set to `false`.)</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Vertical>|<span data-ttu-id="ef258-116">텍스트가 컨트롤의 높이를 초과할 때만 세로 스크롤 막대를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef258-116">Displays a vertical scroll bar only when the text exceeds the height of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedHorizontal>|<span data-ttu-id="ef258-117"><xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 속성이 `false`로 설정 된 경우 가로 스크롤 막대를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef258-117">Displays a horizontal scroll bar when the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property is set to `false`.</span></span> <span data-ttu-id="ef258-118">텍스트가 컨트롤의 너비를 초과 하지 않으면 스크롤 막대가 흐리게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef258-118">The scroll bar appears dimmed when text does not exceed the width of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedVertical>|<span data-ttu-id="ef258-119">항상 세로 스크롤 막대를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef258-119">Always displays a vertical scroll bar.</span></span> <span data-ttu-id="ef258-120">텍스트가 컨트롤의 길이를 초과 하지 않으면 스크롤 막대가 흐리게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef258-120">The scroll bar appears dimmed when text does not exceed the length of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedBoth>|<span data-ttu-id="ef258-121">항상 세로 스크롤 막대를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef258-121">Always displays a vertical scrollbar.</span></span> <span data-ttu-id="ef258-122"><xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 속성이 `false`로 설정 된 경우 가로 스크롤 막대를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef258-122">Displays a horizontal scroll bar when the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property is set to `false`.</span></span> <span data-ttu-id="ef258-123">텍스트가 컨트롤의 너비나 길이를 초과 하지 않는 경우 스크롤 막대가 회색으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef258-123">The scroll bars appear grayed when text does not exceed the width or length of the control.</span></span>|  
  
3. <span data-ttu-id="ef258-124"><xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 속성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ef258-124">Set the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="ef258-125">값</span><span class="sxs-lookup"><span data-stu-id="ef258-125">Value</span></span>|<span data-ttu-id="ef258-126">설명</span><span class="sxs-lookup"><span data-stu-id="ef258-126">Description</span></span>|  
    |-----------|-----------------|  
    |`false`|<span data-ttu-id="ef258-127">컨트롤의 텍스트는 컨트롤의 너비에 맞게 자동으로 조정 되지 않으므로 줄 바꿈에 도달할 때까지 오른쪽으로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="ef258-127">Text in the control is not automatically adjusted to fit the width of the control, so it will scroll to the right until a line break is reached.</span></span> <span data-ttu-id="ef258-128">위의 가로 스크롤 막대나 둘 다를 선택한 경우이 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef258-128">Use this value if you chose horizontal scroll bars or both, above.</span></span>|  
    |<span data-ttu-id="ef258-129">`true`(기본)</span><span class="sxs-lookup"><span data-stu-id="ef258-129">`true` (default)</span></span>|<span data-ttu-id="ef258-130">컨트롤의 텍스트는 컨트롤의 너비에 맞게 자동으로 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef258-130">Text in the control is automatically adjusted to fit the width of the control.</span></span> <span data-ttu-id="ef258-131">가로 스크롤 막대는 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef258-131">The horizontal scrollbar will not appear.</span></span> <span data-ttu-id="ef258-132">위쪽의 세로 스크롤 막대 또는 없음을 선택 하 여 하나 이상의 단락을 표시 하는 경우이 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef258-132">Use this value if you chose vertical scroll bars or none, above, to display one or more paragraphs.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ef258-133">참조</span><span class="sxs-lookup"><span data-stu-id="ef258-133">See also</span></span>

- <xref:System.Windows.Forms.RichTextBoxScrollBars>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="ef258-134">RichTextBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ef258-134">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="ef258-135">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ef258-135">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
