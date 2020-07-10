---
title: '방법: FlowLayoutPanel 컨트롤에서 자식 컨트롤 고정 및 도킹'
description: Windows Forms FlowLayoutPanel 컨트롤에서 프로그래밍 방식으로 자식 컨트롤을 고정 및 도킹 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms], child controls
- FlowLayoutPanel control [Windows Forms], child controls
- controls [Windows Forms], child
- child controls [Windows Forms], anchoring and docking
ms.assetid: a2bcdfca-9b63-45e6-9c0e-3411015cba98
ms.openlocfilehash: b4fb3bf6d148a526a75926bd67c1f967286332bf
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174538"
---
# <a name="how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control"></a><span data-ttu-id="c428d-103">방법: FlowLayoutPanel 컨트롤에서 자식 컨트롤 고정 및 도킹</span><span class="sxs-lookup"><span data-stu-id="c428d-103">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>

<span data-ttu-id="c428d-104"><xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤은 자식 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 및 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c428d-104">The <xref:System.Windows.Forms.FlowLayoutPanel> control supports the <xref:System.Windows.Forms.Control.Anchor%2A> and <xref:System.Windows.Forms.Control.Dock%2A> properties in its child controls.</span></span>

### <a name="to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control"></a><span data-ttu-id="c428d-105">FlowLayoutPanel 컨트롤의 자식 컨트롤을 고정 및 도킹하려면</span><span class="sxs-lookup"><span data-stu-id="c428d-105">To anchor and dock child controls in a FlowLayoutPanel control</span></span>

1. <span data-ttu-id="c428d-106">폼에 <xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c428d-106">Create a <xref:System.Windows.Forms.FlowLayoutPanel> control on your form.</span></span>

2. <span data-ttu-id="c428d-107"><xref:System.Windows.Forms.Control.Width%2A>컨트롤의를 <xref:System.Windows.Forms.FlowLayoutPanel> **300**로 설정 하 고 <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> 를로 설정 <xref:System.Windows.Forms.FlowDirection.TopDown> 합니다.</span><span class="sxs-lookup"><span data-stu-id="c428d-107">Set the <xref:System.Windows.Forms.Control.Width%2A> of the <xref:System.Windows.Forms.FlowLayoutPanel> control to **300**, and set its <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> to <xref:System.Windows.Forms.FlowDirection.TopDown>.</span></span>

3. <span data-ttu-id="c428d-108">두 개의 <xref:System.Windows.Forms.Button> 컨트롤을 만들어 <xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="c428d-108">Create two <xref:System.Windows.Forms.Button> controls, and place them in the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

4. <span data-ttu-id="c428d-109"><xref:System.Windows.Forms.Control.Width%2A>첫 번째 단추의를 **200**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c428d-109">Set the <xref:System.Windows.Forms.Control.Width%2A> of the first button to **200**.</span></span>

5. <span data-ttu-id="c428d-110">두 번째 단추의 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c428d-110">Set the <xref:System.Windows.Forms.Control.Dock%2A> property of the second button to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c428d-111">두 번째 단추는 첫 번째 단추와 동일한 너비를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c428d-111">The second button assumes the same width as the first button.</span></span> <span data-ttu-id="c428d-112"><xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤의 너비에 가로로 늘여지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c428d-112">It does not stretch across the width of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

6. <span data-ttu-id="c428d-113">두 번째 단추의 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 `None`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c428d-113">Set the <xref:System.Windows.Forms.Control.Dock%2A> property of the second button to `None`.</span></span> <span data-ttu-id="c428d-114">그러면 단추가 원래 너비를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c428d-114">This causes the button to assume its original width.</span></span>

7. <span data-ttu-id="c428d-115">두 번째 단추의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 `Left, Right`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c428d-115">Set the <xref:System.Windows.Forms.Control.Anchor%2A> property of the second button to `Left, Right`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c428d-116">두 번째 단추는 첫 번째 단추와 동일한 너비를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c428d-116">The second button assumes the same width as the first button.</span></span> <span data-ttu-id="c428d-117"><xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤의 너비에 가로로 늘여지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c428d-117">It does not stretch across the width of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span> <span data-ttu-id="c428d-118">이는 <xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤의 고정 및 도킹에 대한 일반적인 규칙입니다. 세로 흐름 방향에서는 <xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤이 폼에서 가장 넓은 자식 컨트롤의 암시된 열 너비를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="c428d-118">This is the general rule for anchoring and docking in the <xref:System.Windows.Forms.FlowLayoutPanel> control: for vertical flow directions, the <xref:System.Windows.Forms.FlowLayoutPanel> control calculates the width of an implied column from the widest child control in the column.</span></span> <span data-ttu-id="c428d-119">이 열에서 <xref:System.Windows.Forms.Control.Anchor%2A> 또는 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 가진 다른 모든 컨트롤은 이 암시된 열에 맞게 맞춰지거나 늘어납니다.</span><span class="sxs-lookup"><span data-stu-id="c428d-119">All other controls in this column with <xref:System.Windows.Forms.Control.Anchor%2A> or <xref:System.Windows.Forms.Control.Dock%2A> properties are aligned or stretched to fit this implied column.</span></span> <span data-ttu-id="c428d-120">이 동작은 가로 흐름 방향에서도 비슷하게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="c428d-120">The behavior works in a similar way for horizontal flow directions.</span></span> <span data-ttu-id="c428d-121"><xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤은 행에서 가장 높은 자식 컨트롤의 암시된 행 높이를 계산하고 이 행에서 도킹 또는 고정된 모든 자식 컨트롤이 암시된 행을 채우도록 맞춰지거나 크기가 조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c428d-121">The <xref:System.Windows.Forms.FlowLayoutPanel> control calculates the height of an implied row from the tallest child control in the row, and all docked or anchored child controls in this row are aligned or sized to fit the implied row.</span></span>

## <a name="example"></a><span data-ttu-id="c428d-122">예제</span><span class="sxs-lookup"><span data-stu-id="c428d-122">Example</span></span>

<span data-ttu-id="c428d-123">다음 그림에서는 <xref:System.Windows.Forms.FlowLayoutPanel>의 파란색 단추를 기준으로 고정 및 도킹된 단추 4개를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c428d-123">The following illustration shows four buttons that are anchored and docked relative to the blue button in a <xref:System.Windows.Forms.FlowLayoutPanel>.</span></span> <span data-ttu-id="c428d-124"><xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>은 <xref:System.Windows.Forms.FlowDirection.LeftToRight>입니다.</span><span class="sxs-lookup"><span data-stu-id="c428d-124">The <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> is <xref:System.Windows.Forms.FlowDirection.LeftToRight>.</span></span>

<span data-ttu-id="c428d-125">![FlowLayoutPanel 고정](./media/net-flpanchorexp.gif "NET_FLPanchorExp")</span><span class="sxs-lookup"><span data-stu-id="c428d-125">![FlowLayoutPanel anchoring](./media/net-flpanchorexp.gif "NET_FLPanchorExp")</span></span>

<span data-ttu-id="c428d-126">다음 그림에서는 <xref:System.Windows.Forms.FlowLayoutPanel>의 파란색 단추를 기준으로 고정 및 도킹된 단추 4개를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c428d-126">The following illustration shows four buttons that are anchored and docked relative to the blue button in a <xref:System.Windows.Forms.FlowLayoutPanel>.</span></span> <span data-ttu-id="c428d-127"><xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>은 <xref:System.Windows.Forms.FlowDirection.TopDown>입니다.</span><span class="sxs-lookup"><span data-stu-id="c428d-127">The <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> is <xref:System.Windows.Forms.FlowDirection.TopDown>.</span></span>

<span data-ttu-id="c428d-128">![FlowLayoutPanel 고정](./media/vs-flpanchor2.gif "VS_FLPanchor2")</span><span class="sxs-lookup"><span data-stu-id="c428d-128">![FlowLayoutPanel anchoring](./media/vs-flpanchor2.gif "VS_FLPanchor2")</span></span>

<span data-ttu-id="c428d-129">다음 코드 예제에서는 <xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤의 <xref:System.Windows.Forms.Button> 컨트롤에 대한 다양한 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c428d-129">The following code example demonstrates various <xref:System.Windows.Forms.Control.Anchor%2A> property values for a <xref:System.Windows.Forms.Button> control in a <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

[!code-csharp[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/CS/FlpAnchorExampleForm.cs#1)]
[!code-vb[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/VB/FlpAnchorExampleForm.vb#1)]

## <a name="compiling-the-code"></a><span data-ttu-id="c428d-130">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="c428d-130">Compiling the Code</span></span>

<span data-ttu-id="c428d-131">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c428d-131">This example requires:</span></span>

- <span data-ttu-id="c428d-132">System, System.Data, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="c428d-132">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="c428d-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c428d-133">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- [<span data-ttu-id="c428d-134">FlowLayoutPanel 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="c428d-134">FlowLayoutPanel Control Overview</span></span>](flowlayoutpanel-control-overview.md)
