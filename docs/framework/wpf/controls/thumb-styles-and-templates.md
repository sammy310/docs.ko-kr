---
title: Thumb 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Thumb
- styles [WPF], Thumb
- templates [WPF], Thumb
- Thumb [WPF], styles and templates
- ControlTemplate [WPF], Thumb
- parts [WPF], Thumb
ms.assetid: 86a49235-62d9-414e-923e-53126e3f930a
ms.openlocfilehash: c2114a02016db96d898a394b6892b6d3042d81ff
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458243"
---
# <a name="thumb-styles-and-templates"></a><span data-ttu-id="72ccd-102">Thumb 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="72ccd-102">Thumb Styles and Templates</span></span>

<span data-ttu-id="72ccd-103">이 항목에서는 <xref:System.Windows.Controls.Primitives.Thumb> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="72ccd-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="72ccd-104">기본 <xref:System.Windows.Controls.ControlTemplate>를 수정 하 여 컨트롤에 고유한 모양을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72ccd-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="72ccd-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="72ccd-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>

## <a name="thumb-parts"></a><span data-ttu-id="72ccd-106">Thumb 요소</span><span class="sxs-lookup"><span data-stu-id="72ccd-106">Thumb Parts</span></span>

<span data-ttu-id="72ccd-107"><xref:System.Windows.Controls.Primitives.Thumb> 컨트롤에는 명명 된 파트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="72ccd-107">The <xref:System.Windows.Controls.Primitives.Thumb> control does not have any named parts.</span></span>

## <a name="thumb-states"></a><span data-ttu-id="72ccd-108">Thumb 상태</span><span class="sxs-lookup"><span data-stu-id="72ccd-108">Thumb States</span></span>

<span data-ttu-id="72ccd-109">다음 표에서는 <xref:System.Windows.Controls.Primitives.Thumb> 컨트롤의 시각적 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="72ccd-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>

|<span data-ttu-id="72ccd-110">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="72ccd-110">VisualState Name</span></span>|<span data-ttu-id="72ccd-111">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="72ccd-111">VisualStateGroup Name</span></span>|<span data-ttu-id="72ccd-112">설명</span><span class="sxs-lookup"><span data-stu-id="72ccd-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="72ccd-113">보통</span><span class="sxs-lookup"><span data-stu-id="72ccd-113">Normal</span></span>|<span data-ttu-id="72ccd-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="72ccd-114">CommonStates</span></span>|<span data-ttu-id="72ccd-115">기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="72ccd-115">The default state.</span></span>|
|<span data-ttu-id="72ccd-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="72ccd-116">MouseOver</span></span>|<span data-ttu-id="72ccd-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="72ccd-117">CommonStates</span></span>|<span data-ttu-id="72ccd-118">마우스 포인터가 컨트롤 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72ccd-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="72ccd-119">누름</span><span class="sxs-lookup"><span data-stu-id="72ccd-119">Pressed</span></span>|<span data-ttu-id="72ccd-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="72ccd-120">CommonStates</span></span>|<span data-ttu-id="72ccd-121">컨트롤을 눌렀습니다.</span><span class="sxs-lookup"><span data-stu-id="72ccd-121">The control is pressed.</span></span>|
|<span data-ttu-id="72ccd-122">Disabled</span><span class="sxs-lookup"><span data-stu-id="72ccd-122">Disabled</span></span>|<span data-ttu-id="72ccd-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="72ccd-123">CommonStates</span></span>|<span data-ttu-id="72ccd-124">컨트롤이 비활성화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="72ccd-124">The control is disabled.</span></span>|
|<span data-ttu-id="72ccd-125">포커스 있음</span><span class="sxs-lookup"><span data-stu-id="72ccd-125">Focused</span></span>|<span data-ttu-id="72ccd-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="72ccd-126">FocusStates</span></span>|<span data-ttu-id="72ccd-127">컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72ccd-127">The control has focus.</span></span>|
|<span data-ttu-id="72ccd-128">포커스 없음</span><span class="sxs-lookup"><span data-stu-id="72ccd-128">Unfocused</span></span>|<span data-ttu-id="72ccd-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="72ccd-129">FocusStates</span></span>|<span data-ttu-id="72ccd-130">컨트롤에 포커스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="72ccd-130">The control does not have focus.</span></span>|
|<span data-ttu-id="72ccd-131">유효</span><span class="sxs-lookup"><span data-stu-id="72ccd-131">Valid</span></span>|<span data-ttu-id="72ccd-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="72ccd-132">ValidationStates</span></span>|<span data-ttu-id="72ccd-133">컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="72ccd-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="72ccd-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="72ccd-134">InvalidFocused</span></span>|<span data-ttu-id="72ccd-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="72ccd-135">ValidationStates</span></span>|<span data-ttu-id="72ccd-136">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72ccd-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="72ccd-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="72ccd-137">InvalidUnfocused</span></span>|<span data-ttu-id="72ccd-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="72ccd-138">ValidationStates</span></span>|<span data-ttu-id="72ccd-139">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="72ccd-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="thumb-controltemplate-example"></a><span data-ttu-id="72ccd-140">Thumb ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="72ccd-140">Thumb ControlTemplate Example</span></span>

<span data-ttu-id="72ccd-141">다음 예제에서는 <xref:System.Windows.Controls.Primitives.Thumb> 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="72ccd-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>

[!code-xaml[ControlTemplateExamples#Thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#thumb)]

<span data-ttu-id="72ccd-142">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="72ccd-142">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="72ccd-143">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="72ccd-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="72ccd-144">참조</span><span class="sxs-lookup"><span data-stu-id="72ccd-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="72ccd-145">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="72ccd-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="72ccd-146">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="72ccd-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="72ccd-147">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="72ccd-147">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="72ccd-148">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="72ccd-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
