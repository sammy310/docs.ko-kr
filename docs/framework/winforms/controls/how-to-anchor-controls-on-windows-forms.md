---
title: '방법: Windows Forms에서 컨트롤 고정'
ms.date: 03/30/2017
helpviewer_keywords:
- Anchor property [Windows Forms], enabling resizable forms
- Windows Forms controls, screen resolutions
- resizing forms [Windows Forms]
- Windows Forms controls, size
- screen resolution and control display
- controls [Windows Forms], anchoring
- forms [Windows Forms], resizing
- Windows Forms, resizing
- controls [Windows Forms], positioning
ms.assetid: 59ea914f-fbd3-427a-80fe-decd02f7ae6d
ms.openlocfilehash: b48761bda2baad4f7d1e6db9b41d73d6d54bc081
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211270"
---
# <a name="how-to-anchor-controls-on-windows-forms"></a><span data-ttu-id="5d3cb-102">방법: Windows Forms에서 컨트롤 고정</span><span class="sxs-lookup"><span data-stu-id="5d3cb-102">How to: Anchor Controls on Windows Forms</span></span>

<span data-ttu-id="5d3cb-103">런타임 시를 조정할 수 있는 폼을 디자인 하는 경우 폼에서 컨트롤의 크기를 조정 하 고 위치가 적절 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3cb-103">If you're designing a form that the user can resize at run time, the controls on your form should resize and reposition properly.</span></span> <span data-ttu-id="5d3cb-104">폼을 사용 하 여 동적으로 컨트롤 크기 조정에 사용할 수는 <xref:System.Windows.Forms.Control.Anchor%2A> Windows Forms 컨트롤의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5d3cb-104">To resize controls dynamically with the form, you can use the <xref:System.Windows.Forms.Control.Anchor%2A> property of Windows Forms controls.</span></span> <span data-ttu-id="5d3cb-105"><xref:System.Windows.Forms.Control.Anchor%2A> 속성은 컨트롤에 대 한 앵커 위치를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3cb-105">The <xref:System.Windows.Forms.Control.Anchor%2A> property defines an anchor position for the control.</span></span> <span data-ttu-id="5d3cb-106">컨트롤을 폼에 고정 하 고 폼의 크기를 조정할 때 컨트롤 컨트롤 앵커 위치 사이의 거리를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3cb-106">When a control is anchored to a form and the form is resized, the control maintains the distance between the control and the anchor positions.</span></span> <span data-ttu-id="5d3cb-107">예를 들어 있는 경우는 <xref:System.Windows.Forms.TextBox> 폼 크기가 조정 됩니다, 왼쪽, 오른쪽 및 폼의 아래쪽 가장자리에 고정 되는 컨트롤을 <xref:System.Windows.Forms.TextBox> 컨트롤의 크기가 조정 가로로 폼의 오른쪽과 왼쪽된 로부터 같은 거리에 유지 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3cb-107">For example, if you have a <xref:System.Windows.Forms.TextBox> control that is anchored to the left, right, and bottom edges of the form, as the form is resized, the <xref:System.Windows.Forms.TextBox> control resizes horizontally so that it maintains the same distance from the right and left sides of the form.</span></span> <span data-ttu-id="5d3cb-108">또한 컨트롤 세로 위치가 조정 해당 위치는 항상 폼의 아래쪽 가장자리 로부터 같은 거리에 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3cb-108">In addition, the control positions itself vertically so that its location is always the same distance from the bottom edge of the form.</span></span> <span data-ttu-id="5d3cb-109">컨트롤을 고정 하지 않으면 폼의 크기를 조정 하 고 폼의 가장자리를 기준으로 컨트롤의 위치 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d3cb-109">If a control is not anchored and the form is resized, the position of the control relative to the edges of the form is changed.</span></span>

<span data-ttu-id="5d3cb-110">합니다 <xref:System.Windows.Forms.Control.Anchor%2A> 상호 작용 하는 속성을 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5d3cb-110">The <xref:System.Windows.Forms.Control.Anchor%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="5d3cb-111">자세한 내용은 [AutoSize 속성 개요](autosize-property-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3cb-111">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>

## <a name="anchor-a-control-on-a-form"></a><span data-ttu-id="5d3cb-112">폼에서 컨트롤 고정</span><span class="sxs-lookup"><span data-stu-id="5d3cb-112">Anchor a control on a form</span></span>

1. <span data-ttu-id="5d3cb-113">Visual Studio에서 고정 하려는 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3cb-113">In Visual Studio, select the control you want to anchor.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5d3cb-114">CTRL 키를 하 여 선택한 각 컨트롤을 클릭 하 고 다음이 절차의 나머지 부분에서 동시에 여러 컨트롤을 고정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d3cb-114">You can anchor multiple controls simultaneously by pressing the CTRL key, clicking each control to select it, and then following the rest of this procedure.</span></span>

2. <span data-ttu-id="5d3cb-115">에 **속성** 창 오른쪽의 화살표를 클릭 합니다 <xref:System.Windows.Forms.Control.Anchor%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5d3cb-115">In the **Properties** window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span>

     <span data-ttu-id="5d3cb-116">편집기는 크로스를 보여주는 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d3cb-116">An editor is displayed that shows a cross.</span></span>

3. <span data-ttu-id="5d3cb-117">앵커를 설정 하려면 위쪽, 왼쪽, 오른쪽 또는 아래쪽 교차 부분을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3cb-117">To set an anchor, click the top, left, right, or bottom section of the cross.</span></span>

     <span data-ttu-id="5d3cb-118">컨트롤 위쪽에 고정 되며 기본적으로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d3cb-118">Controls are anchored to the top and left by default.</span></span>

4. <span data-ttu-id="5d3cb-119">고정 된 컨트롤의 한 쪽을 지우려면 교차 해당 막대를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3cb-119">To clear a side of the control that has been anchored, click that arm of the cross.</span></span>

5. <span data-ttu-id="5d3cb-120">닫습니다 합니다 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 편집기를 클릭 합니다 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 이름을 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3cb-120">To close the <xref:System.Windows.Forms.Control.Anchor%2A> property editor, click the <xref:System.Windows.Forms.Control.Anchor%2A> property name again.</span></span>

<span data-ttu-id="5d3cb-121">런타임에 폼에 표시 되 면 컨트롤을 폼의 가장자리 로부터 같은 거리에 위치를 유지 하도록 크기가 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d3cb-121">When your form is displayed at run time, the control resizes to remain positioned at the same distance from the edge of the form.</span></span> <span data-ttu-id="5d3cb-122">고정 된 가장자리에서 항상 거리 Windows Forms 디자이너에서 컨트롤은 위치를 지정할 때 정의 된 대로 동일 하 게 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d3cb-122">The distance from the anchored edge always remains the same as the distance defined when the control is positioned in the Windows Forms Designer.</span></span>

> [!NOTE]
> <span data-ttu-id="5d3cb-123">와 같은 특정 컨트롤을 <xref:System.Windows.Forms.ComboBox> 해당 높이에 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d3cb-123">Certain controls, such as the <xref:System.Windows.Forms.ComboBox> control, have a limit to their height.</span></span> <span data-ttu-id="5d3cb-124">폼 이나 컨테이너의 맨 아래에 컨트롤을 고정 하면 컨트롤의 높이 제한을 초과할 강제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d3cb-124">Anchoring the control to the bottom of its form or container cannot force the control to exceed its height limit.</span></span>

<span data-ttu-id="5d3cb-125">상속 된 컨트롤 해야 `Protected` 고정 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d3cb-125">Inherited controls must be `Protected` to be able to be anchored.</span></span> <span data-ttu-id="5d3cb-126">컨트롤의 액세스 수준을 변경 하려면 해당 `Modifiers` 속성에는 **속성** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="5d3cb-126">To change the access level of a control, set its `Modifiers` property in the **Properties** window.</span></span>

## <a name="see-also"></a><span data-ttu-id="5d3cb-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="5d3cb-127">See also</span></span>

- [<span data-ttu-id="5d3cb-128">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="5d3cb-128">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="5d3cb-129">Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="5d3cb-129">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="5d3cb-130">AutoSize 속성 개요</span><span class="sxs-lookup"><span data-stu-id="5d3cb-130">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="5d3cb-131">방법: Windows Forms에 컨트롤 도킹</span><span class="sxs-lookup"><span data-stu-id="5d3cb-131">How to: Dock Controls on Windows Forms</span></span>](how-to-dock-controls-on-windows-forms.md)
- [<span data-ttu-id="5d3cb-132">연습: FlowLayoutPanel을 사용 하 여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="5d3cb-132">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="5d3cb-133">연습: TableLayoutPanel을 사용 하 여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="5d3cb-133">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="5d3cb-134">연습: Windows Forms 컨트롤 Padding, Margins 및 AutoSize 속성을 사용 하 여 레이아웃</span><span class="sxs-lookup"><span data-stu-id="5d3cb-134">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](windows-forms-controls-padding-autosize.md)
