---
title: 컨트롤 고정
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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 7c307d8c5b3bc32e15e6de048c434854ef1bbc65
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747188"
---
# <a name="how-to-anchor-controls-on-windows-forms"></a><span data-ttu-id="f2ba6-102">방법: Windows Forms에서 컨트롤 고정</span><span class="sxs-lookup"><span data-stu-id="f2ba6-102">How to: Anchor controls on Windows Forms</span></span>

<span data-ttu-id="f2ba6-103">런타임에 사용자가 크기를 조정할 수 있는 폼을 디자인 하는 경우 폼의 컨트롤 크기를 조정 하 고 적절 하 게 위치를 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba6-103">If you're designing a form that the user can resize at run time, the controls on your form should resize and reposition properly.</span></span> <span data-ttu-id="f2ba6-104">폼을 사용 하 여 동적으로 컨트롤의 크기를 조정 하려면 Windows Forms 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba6-104">To resize controls dynamically with the form, you can use the <xref:System.Windows.Forms.Control.Anchor%2A> property of Windows Forms controls.</span></span> <span data-ttu-id="f2ba6-105"><xref:System.Windows.Forms.Control.Anchor%2A> 속성은 컨트롤의 앵커 위치를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba6-105">The <xref:System.Windows.Forms.Control.Anchor%2A> property defines an anchor position for the control.</span></span> <span data-ttu-id="f2ba6-106">컨트롤이 폼에 고정 되 고 폼의 크기가 조정 되 면 컨트롤은 컨트롤과 앵커 위치 간의 거리를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba6-106">When a control is anchored to a form and the form is resized, the control maintains the distance between the control and the anchor positions.</span></span> <span data-ttu-id="f2ba6-107">예를 들어 폼의 왼쪽, 오른쪽 및 아래쪽 가장자리에 고정 된 <xref:System.Windows.Forms.TextBox> 컨트롤이 있는 경우 폼의 크기가 조정 될 때 <xref:System.Windows.Forms.TextBox> 컨트롤은 폼의 오른쪽과 왼쪽에서 같은 거리를 유지 하도록 가로 크기를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba6-107">For example, if you have a <xref:System.Windows.Forms.TextBox> control that is anchored to the left, right, and bottom edges of the form, as the form is resized, the <xref:System.Windows.Forms.TextBox> control resizes horizontally so that it maintains the same distance from the right and left sides of the form.</span></span> <span data-ttu-id="f2ba6-108">또한 컨트롤은 위치가 항상 폼의 아래쪽 가장자리와 동일한 거리를 갖도록 세로로 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba6-108">In addition, the control positions itself vertically so that its location is always the same distance from the bottom edge of the form.</span></span> <span data-ttu-id="f2ba6-109">컨트롤이 고정 되어 있지 않고 폼의 크기가 조정 되 면 폼의 가장자리를 기준으로 하는 컨트롤의 위치가 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba6-109">If a control is not anchored and the form is resized, the position of the control relative to the edges of the form is changed.</span></span>

<span data-ttu-id="f2ba6-110">합니다 <xref:System.Windows.Forms.Control.Anchor%2A> 상호 작용 하는 속성을 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba6-110">The <xref:System.Windows.Forms.Control.Anchor%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="f2ba6-111">자세한 내용은 [AutoSize 속성 개요](autosize-property-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f2ba6-111">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>

## <a name="anchor-a-control-on-a-form"></a><span data-ttu-id="f2ba6-112">폼에 컨트롤 고정</span><span class="sxs-lookup"><span data-stu-id="f2ba6-112">Anchor a control on a form</span></span>

1. <span data-ttu-id="f2ba6-113">Visual Studio에서 고정 하려는 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba6-113">In Visual Studio, select the control you want to anchor.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f2ba6-114">CTRL 키를 누른 채 각 컨트롤을 클릭 하 여 선택 하 고이 절차의 나머지 단계를 수행 하 여 여러 컨트롤을 동시에 고정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba6-114">You can anchor multiple controls simultaneously by pressing the CTRL key, clicking each control to select it, and then following the rest of this procedure.</span></span>

2. <span data-ttu-id="f2ba6-115">**속성** 창에서 <xref:System.Windows.Forms.Control.Anchor%2A> 속성의 오른쪽에 있는 화살표를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba6-115">In the **Properties** window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span>

     <span data-ttu-id="f2ba6-116">십자 표시를 보여 주는 편집기가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba6-116">An editor is displayed that shows a cross.</span></span>

3. <span data-ttu-id="f2ba6-117">앵커를 설정 하려면 십자의 위쪽, 왼쪽, 오른쪽 또는 아래쪽 섹션을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba6-117">To set an anchor, click the top, left, right, or bottom section of the cross.</span></span>

     <span data-ttu-id="f2ba6-118">컨트롤은 기본적으로 위쪽과 왼쪽에 고정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba6-118">Controls are anchored to the top and left by default.</span></span>

4. <span data-ttu-id="f2ba6-119">앵커 된 컨트롤의 측면을 지우려면 십자의 arm을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba6-119">To clear a side of the control that has been anchored, click that arm of the cross.</span></span>

5. <span data-ttu-id="f2ba6-120"><xref:System.Windows.Forms.Control.Anchor%2A> 속성 편집기를 닫으려면 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 이름을 다시 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba6-120">To close the <xref:System.Windows.Forms.Control.Anchor%2A> property editor, click the <xref:System.Windows.Forms.Control.Anchor%2A> property name again.</span></span>

<span data-ttu-id="f2ba6-121">런타임에 폼이 표시 되 면 컨트롤의 크기가 폼의 가장자리와 같은 거리에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba6-121">When your form is displayed at run time, the control resizes to remain positioned at the same distance from the edge of the form.</span></span> <span data-ttu-id="f2ba6-122">고정 가장자리 로부터의 거리는 항상 컨트롤이 Windows Forms 디자이너 배치 될 때 정의 된 거리와 동일 하 게 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba6-122">The distance from the anchored edge always remains the same as the distance defined when the control is positioned in the Windows Forms Designer.</span></span>

> [!NOTE]
> <span data-ttu-id="f2ba6-123"><xref:System.Windows.Forms.ComboBox> 컨트롤과 같은 특정 컨트롤의 높이는 제한 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba6-123">Certain controls, such as the <xref:System.Windows.Forms.ComboBox> control, have a limit to their height.</span></span> <span data-ttu-id="f2ba6-124">컨트롤을 폼 이나 컨테이너의 아래쪽에 고정 하면 컨트롤이 높이 제한을 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba6-124">Anchoring the control to the bottom of its form or container cannot force the control to exceed its height limit.</span></span>

<span data-ttu-id="f2ba6-125">상속 될 수 있으려면 상속 된 컨트롤을 `Protected` 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba6-125">Inherited controls must be `Protected` to be able to be anchored.</span></span> <span data-ttu-id="f2ba6-126">컨트롤의 액세스 수준을 변경 하려면 **속성** 창에서 해당 `Modifiers` 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba6-126">To change the access level of a control, set its `Modifiers` property in the **Properties** window.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2ba6-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f2ba6-127">See also</span></span>

- [<span data-ttu-id="f2ba6-128">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f2ba6-128">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="f2ba6-129">AutoSize 속성 개요</span><span class="sxs-lookup"><span data-stu-id="f2ba6-129">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="f2ba6-130">방법: Windows Forms에서 컨트롤 고정</span><span class="sxs-lookup"><span data-stu-id="f2ba6-130">How to: Dock Controls on Windows Forms</span></span>](how-to-dock-controls-on-windows-forms.md)
- [<span data-ttu-id="f2ba6-131">연습: FlowLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="f2ba6-131">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="f2ba6-132">연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="f2ba6-132">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="f2ba6-133">연습: Padding, Margins 및 AutoSize 속성을 사용하여 Windows Forms 컨트롤 레이아웃</span><span class="sxs-lookup"><span data-stu-id="f2ba6-133">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](windows-forms-controls-padding-autosize.md)
