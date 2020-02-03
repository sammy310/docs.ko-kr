---
title: 컨트롤의 탭 순서 설정
ms.date: 03/30/2017
f1_keywords:
- TabStop
- TabIndex
helpviewer_keywords:
- tab order [Windows Forms], controls on Windows forms
- Windows Forms controls, setting tab order
- controls [Windows Forms], setting tab order
- Windows Forms, setting tab order
ms.assetid: 71fa8e76-0472-414b-ad3c-0f90166e0ad7
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 5d53e411bda0279271e4f73e1842c52fd6d9b3a9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746834"
---
# <a name="how-to-set-the-tab-order-on-windows-forms"></a><span data-ttu-id="bdf73-102">방법: Windows Forms에서 탭 순서 설정</span><span class="sxs-lookup"><span data-stu-id="bdf73-102">How to: Set the tab order on Windows Forms</span></span>

<span data-ttu-id="bdf73-103">탭 순서는 Tab 키를 눌러 사용자가 한 컨트롤에서 다른 컨트롤로 포커스를 이동 하는 순서입니다.</span><span class="sxs-lookup"><span data-stu-id="bdf73-103">The tab order is the order in which a user moves focus from one control to another by pressing the Tab key.</span></span> <span data-ttu-id="bdf73-104">각 양식에는 자체 탭 순서가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdf73-104">Each form has its own tab order.</span></span> <span data-ttu-id="bdf73-105">기본적으로 탭 순서는 컨트롤을 만든 순서와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdf73-105">By default, the tab order is the same as the order in which you created the controls.</span></span> <span data-ttu-id="bdf73-106">탭 순서 번호는 0부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdf73-106">Tab-order numbering begins with zero.</span></span>

## <a name="to-set-the-tab-order-of-a-control"></a><span data-ttu-id="bdf73-107">컨트롤의 탭 순서를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="bdf73-107">To set the tab order of a control</span></span>

1. <span data-ttu-id="bdf73-108">Visual Studio의 **보기** 메뉴에서 **탭 순서**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdf73-108">In Visual Studio, on the **View** menu, select **Tab Order**.</span></span>

   <span data-ttu-id="bdf73-109">이렇게 하면 폼에서 탭 순서 선택 모드가 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdf73-109">This activates the tab-order selection mode on the form.</span></span> <span data-ttu-id="bdf73-110"><xref:System.Windows.Forms.Control.TabIndex%2A> 속성을 나타내는 숫자가 각 컨트롤의 왼쪽 위 모퉁이에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdf73-110">A number (representing the <xref:System.Windows.Forms.Control.TabIndex%2A> property) appears in the upper-left corner of each control.</span></span>

2. <span data-ttu-id="bdf73-111">원하는 탭 순서를 설정 하려면 컨트롤을 순서 대로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdf73-111">Click the controls sequentially to establish the tab order you want.</span></span>

   > [!NOTE]
   > <span data-ttu-id="bdf73-112">탭 순서에서 컨트롤의 자리를 0 보다 크거나 같은 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdf73-112">A control's place within the tab order can be set to any value greater than or equal to 0.</span></span> <span data-ttu-id="bdf73-113">중복이 발생 하면 두 컨트롤의 z 순서가 평가 되 고 맨 위에 있는 컨트롤이 먼저 탭으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdf73-113">When duplicates occur, the z-order of the two controls is evaluated and the control on top is tabbed to first.</span></span> <span data-ttu-id="bdf73-114">Z 축은 폼의 z 축 [depth]를 따라 폼에 있는 컨트롤의 시각적 계층화입니다.</span><span class="sxs-lookup"><span data-stu-id="bdf73-114">(The z-order is the visual layering of controls on a form along the form's z-axis [depth].</span></span> <span data-ttu-id="bdf73-115">Z 순서에 따라 다른 컨트롤 앞에 있는 컨트롤이 결정 됩니다. Z 순서에 대 한 자세한 내용은 [Windows Forms에서 개체 계층화](how-to-layer-objects-on-windows-forms.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bdf73-115">The z-order determines which controls are in front of other controls.) For more information on z-order, see [Layering Objects on Windows Forms](how-to-layer-objects-on-windows-forms.md).</span></span>

3. <span data-ttu-id="bdf73-116">완료 되 면 **보기** 메뉴에서 **탭 순서** 를 다시 선택 하 여 탭 순서 모드를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdf73-116">When you have finished, select **Tab Order** on the **View** menu again to leave tab order mode.</span></span>

   > [!NOTE]
   > <span data-ttu-id="bdf73-117">포커스를 가져올 수 없는 컨트롤, 비활성화 된 컨트롤 및 보이지 않는 컨트롤은 <xref:System.Windows.Forms.Control.TabIndex%2A> 속성이 없으며 탭 순서에 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bdf73-117">Controls that cannot get the focus, as well as disabled and invisible controls, do not have a <xref:System.Windows.Forms.Control.TabIndex%2A> property and are not included in the tab order.</span></span> <span data-ttu-id="bdf73-118">사용자가 Tab 키를 누를 때 이러한 컨트롤을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="bdf73-118">As a user presses the Tab key, these controls are skipped.</span></span>

<span data-ttu-id="bdf73-119">또는 <xref:System.Windows.Forms.Control.TabIndex%2A> 속성을 사용 하 여 속성 창에서 탭 순서를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdf73-119">Alternatively, tab order can be set in the Properties window using the <xref:System.Windows.Forms.Control.TabIndex%2A> property.</span></span> <span data-ttu-id="bdf73-120">컨트롤의 <xref:System.Windows.Forms.Control.TabIndex%2A> 속성은 탭 순서에서 위치가 지정 되는 위치를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdf73-120">The <xref:System.Windows.Forms.Control.TabIndex%2A> property of a control determines where it is positioned in the tab order.</span></span> <span data-ttu-id="bdf73-121">기본적으로 그려진 첫 번째 컨트롤의 <xref:System.Windows.Forms.Control.TabIndex%2A> 값은 0이 고, 두 번째 컨트롤의 <xref:System.Windows.Forms.Control.TabIndex%2A>은 1입니다.</span><span class="sxs-lookup"><span data-stu-id="bdf73-121">By default, the first control drawn has a <xref:System.Windows.Forms.Control.TabIndex%2A> value of 0, the second has a <xref:System.Windows.Forms.Control.TabIndex%2A> of 1, and so on.</span></span>

<span data-ttu-id="bdf73-122">또한 기본적으로 <xref:System.Windows.Forms.GroupBox> 컨트롤에는 정수 <xref:System.Windows.Forms.Control.TabIndex%2A> 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdf73-122">Additionally, by default, a <xref:System.Windows.Forms.GroupBox> control has its own <xref:System.Windows.Forms.Control.TabIndex%2A> value, which is a whole number.</span></span> <span data-ttu-id="bdf73-123">런타임에는 <xref:System.Windows.Forms.GroupBox> 컨트롤 자체에 포커스를 둘 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bdf73-123">A <xref:System.Windows.Forms.GroupBox> control itself cannot have focus at run time.</span></span> <span data-ttu-id="bdf73-124">따라서 <xref:System.Windows.Forms.GroupBox> 내의 각 컨트롤에는 0부터 시작 하는 고유한 10 진수 <xref:System.Windows.Forms.Control.TabIndex%2A> 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdf73-124">Thus, each control within a <xref:System.Windows.Forms.GroupBox> has its own decimal <xref:System.Windows.Forms.Control.TabIndex%2A> value, beginning with .0.</span></span> <span data-ttu-id="bdf73-125">기본적으로 <xref:System.Windows.Forms.GroupBox> 컨트롤의 <xref:System.Windows.Forms.Control.TabIndex%2A> 증가 하면 그 안에 포함 된 컨트롤이 그에 따라 증가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdf73-125">Naturally, as the <xref:System.Windows.Forms.Control.TabIndex%2A> of a <xref:System.Windows.Forms.GroupBox> control is incremented, the controls within it will be incremented accordingly.</span></span> <span data-ttu-id="bdf73-126"><xref:System.Windows.Forms.Control.TabIndex%2A> 값을 5에서 6으로 변경한 경우 해당 그룹에 있는 첫 번째 컨트롤의 <xref:System.Windows.Forms.Control.TabIndex%2A> 값이 자동으로 6.0로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdf73-126">If you changed a <xref:System.Windows.Forms.Control.TabIndex%2A> value from 5 to 6, the <xref:System.Windows.Forms.Control.TabIndex%2A> value of the first control in its group automatically changes to 6.0, and so on.</span></span>

<span data-ttu-id="bdf73-127">마지막으로, 폼의 많은 컨트롤은 탭 순서에서 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdf73-127">Finally, any control of the many on your form can be skipped in the tab order.</span></span> <span data-ttu-id="bdf73-128">일반적으로 런타임에 Tab 키를 누르면 탭 순서의 각 컨트롤이 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdf73-128">Usually, pressing Tab successively at run time selects each control in the tab order.</span></span> <span data-ttu-id="bdf73-129"><xref:System.Windows.Forms.Control.TabStop%2A> 속성을 끄면 폼의 탭 순서에서 컨트롤을 전달 하도록 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdf73-129">By turning off the <xref:System.Windows.Forms.Control.TabStop%2A> property, you can make a control be passed over in the tab order of the form.</span></span>

## <a name="to-remove-a-control-from-the-tab-order"></a><span data-ttu-id="bdf73-130">탭 순서에서 컨트롤을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="bdf73-130">To remove a control from the tab order</span></span>

<span data-ttu-id="bdf73-131">**속성** 창에서 컨트롤의 <xref:System.Windows.Forms.Control.TabStop%2A> 속성을 **false** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdf73-131">Set the control's <xref:System.Windows.Forms.Control.TabStop%2A> property to **false** in the **Properties** window.</span></span>

<span data-ttu-id="bdf73-132">Tab 키를 사용 하 여 컨트롤을 순환할 때 컨트롤이 생략 되는 경우에도 <xref:System.Windows.Forms.Control.TabStop%2A> 속성이 `false`로 설정 된 컨트롤은 탭 순서에서 해당 위치를 계속 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdf73-132">A control whose <xref:System.Windows.Forms.Control.TabStop%2A> property has been set to `false` still maintains its position in the tab order, even though the control is skipped when you cycle through the controls with the Tab key.</span></span>

> [!NOTE]
> <span data-ttu-id="bdf73-133">라디오 단추 그룹은 런타임에 단일 탭 정지를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="bdf73-133">A radio button group has a single tab stop at run time.</span></span> <span data-ttu-id="bdf73-134">선택 된 단추 (즉, <xref:System.Windows.Forms.RadioButton.Checked%2A> 속성이 `true`로 설정 된 단추의 <xref:System.Windows.Forms.Control.TabStop%2A> 속성은 자동으로 `true`로 설정 되 고 다른 단추의 <xref:System.Windows.Forms.Control.TabStop%2A> 속성은 `false`로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdf73-134">The selected button (that is, the button with its <xref:System.Windows.Forms.RadioButton.Checked%2A> property set to `true`) has its <xref:System.Windows.Forms.Control.TabStop%2A> property automatically set to `true`, while the other buttons have their <xref:System.Windows.Forms.Control.TabStop%2A> property set to `false`.</span></span> <span data-ttu-id="bdf73-135"><xref:System.Windows.Forms.RadioButton> 컨트롤을 그룹화 하는 방법에 대 한 자세한 내용은 [그룹화 Windows Forms RadioButton 컨트롤이 집합으로 작동 하는 방법](how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bdf73-135">For more information about grouping <xref:System.Windows.Forms.RadioButton> controls, see [Grouping Windows Forms RadioButton Controls to Function as a Set](how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bdf73-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bdf73-136">See also</span></span>

- [<span data-ttu-id="bdf73-137">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="bdf73-137">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="bdf73-138">Windows Forms에서 사용할 컨트롤</span><span class="sxs-lookup"><span data-stu-id="bdf73-138">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="bdf73-139">기능별 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="bdf73-139">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
