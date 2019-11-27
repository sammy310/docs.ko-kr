---
title: Slider 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Slider
- states [WPF], Slider
- Slider [WPF], styles and templates
- styles [WPF], Slider
- templates [WPF], Slider
- ControlTemplate [WPF], Slider
ms.assetid: d89aa97b-075a-4752-9c41-9679df65c491
ms.openlocfilehash: f533142d5ba202bd4aaf628487eaaa2a18a535d0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283383"
---
# <a name="slider-styles-and-templates"></a><span data-ttu-id="00666-102">Slider 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="00666-102">Slider Styles and Templates</span></span>
<span data-ttu-id="00666-103">이 항목에서는 <xref:System.Windows.Controls.Slider> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="00666-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Slider> control.</span></span> <span data-ttu-id="00666-104">기본 <xref:System.Windows.Controls.ControlTemplate>를 수정 하 여 컨트롤에 고유한 모양을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00666-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="00666-105">자세한 내용은 [컨트롤에 대 한 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="00666-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="slider-parts"></a><span data-ttu-id="00666-106">슬라이더 부분</span><span class="sxs-lookup"><span data-stu-id="00666-106">Slider Parts</span></span>  
 <span data-ttu-id="00666-107">다음 표에서는 <xref:System.Windows.Controls.Slider> 컨트롤의 명명 된 파트를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="00666-107">The following table lists the named parts for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="00666-108">부분</span><span class="sxs-lookup"><span data-stu-id="00666-108">Part</span></span>|<span data-ttu-id="00666-109">형식</span><span class="sxs-lookup"><span data-stu-id="00666-109">Type</span></span>|<span data-ttu-id="00666-110">설명</span><span class="sxs-lookup"><span data-stu-id="00666-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="00666-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="00666-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="00666-112"><xref:System.Windows.Controls.Slider>의 위치를 나타내는 요소에 대 한 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="00666-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Slider>.</span></span>|  
|<span data-ttu-id="00666-113">PART_SelectionRange</span><span class="sxs-lookup"><span data-stu-id="00666-113">PART_SelectionRange</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="00666-114"><xref:System.Windows.Controls.Slider>따라 선택 범위를 표시 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="00666-114">The element that displays a selection range along the <xref:System.Windows.Controls.Slider>.</span></span>  <span data-ttu-id="00666-115">선택 범위는 <xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A> 속성이 `true`되는 경우에만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00666-115">The selection range is visible only if the <xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A> property is `true`.</span></span>|  
  
## <a name="slider-states"></a><span data-ttu-id="00666-116">슬라이더 상태</span><span class="sxs-lookup"><span data-stu-id="00666-116">Slider States</span></span>  
 <span data-ttu-id="00666-117">다음 표에서는 <xref:System.Windows.Controls.Slider> 컨트롤의 시각적 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="00666-117">The following table lists the visual states for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="00666-118">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="00666-118">VisualState Name</span></span>|<span data-ttu-id="00666-119">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="00666-119">VisualStateGroup Name</span></span>|<span data-ttu-id="00666-120">설명</span><span class="sxs-lookup"><span data-stu-id="00666-120">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="00666-121">보통</span><span class="sxs-lookup"><span data-stu-id="00666-121">Normal</span></span>|<span data-ttu-id="00666-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="00666-122">CommonStates</span></span>|<span data-ttu-id="00666-123">기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="00666-123">The default state.</span></span>|  
|<span data-ttu-id="00666-124">MouseOver</span><span class="sxs-lookup"><span data-stu-id="00666-124">MouseOver</span></span>|<span data-ttu-id="00666-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="00666-125">CommonStates</span></span>|<span data-ttu-id="00666-126">마우스 포인터가 컨트롤 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00666-126">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="00666-127">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="00666-127">Disabled</span></span>|<span data-ttu-id="00666-128">CommonStates</span><span class="sxs-lookup"><span data-stu-id="00666-128">CommonStates</span></span>|<span data-ttu-id="00666-129">컨트롤이 비활성화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="00666-129">The control is disabled.</span></span>|  
|<span data-ttu-id="00666-130">포커스 있음</span><span class="sxs-lookup"><span data-stu-id="00666-130">Focused</span></span>|<span data-ttu-id="00666-131">FocusStates</span><span class="sxs-lookup"><span data-stu-id="00666-131">FocusStates</span></span>|<span data-ttu-id="00666-132">컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00666-132">The control has focus.</span></span>|  
|<span data-ttu-id="00666-133">포커스 없음</span><span class="sxs-lookup"><span data-stu-id="00666-133">Unfocused</span></span>|<span data-ttu-id="00666-134">FocusStates</span><span class="sxs-lookup"><span data-stu-id="00666-134">FocusStates</span></span>|<span data-ttu-id="00666-135">컨트롤에 포커스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00666-135">The control does not have focus.</span></span>|  
|<span data-ttu-id="00666-136">Valid</span><span class="sxs-lookup"><span data-stu-id="00666-136">Valid</span></span>|<span data-ttu-id="00666-137">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="00666-137">ValidationStates</span></span>|<span data-ttu-id="00666-138">컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="00666-138">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="00666-139">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="00666-139">InvalidFocused</span></span>|<span data-ttu-id="00666-140">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="00666-140">ValidationStates</span></span>|<span data-ttu-id="00666-141">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00666-141">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="00666-142">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="00666-142">InvalidUnfocused</span></span>|<span data-ttu-id="00666-143">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="00666-143">ValidationStates</span></span>|<span data-ttu-id="00666-144">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="00666-144">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="slider-controltemplate-example"></a><span data-ttu-id="00666-145">Slider ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="00666-145">Slider ControlTemplate Example</span></span>  
 <span data-ttu-id="00666-146">다음 예제에서는 <xref:System.Windows.Controls.Slider> 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="00666-146">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Slider](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#slider)]  
  
 <span data-ttu-id="00666-147">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="00666-147">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="00666-148">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00666-148">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00666-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="00666-149">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="00666-150">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="00666-150">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="00666-151">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="00666-151">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="00666-152">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="00666-152">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="00666-153">컨트롤에 대 한 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="00666-153">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
