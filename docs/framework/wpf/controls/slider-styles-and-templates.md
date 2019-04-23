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
ms.openlocfilehash: 385a69ad2bd17ae4c51437245915109aad446bdf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103196"
---
# <a name="slider-styles-and-templates"></a><span data-ttu-id="9a02a-102">Slider 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="9a02a-102">Slider Styles and Templates</span></span>
<span data-ttu-id="9a02a-103">이 항목에서는 스타일 및 템플릿에 대해 설명 합니다 <xref:System.Windows.Controls.Slider> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a02a-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Slider> control.</span></span> <span data-ttu-id="9a02a-104">기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a02a-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="9a02a-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9a02a-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="slider-parts"></a><span data-ttu-id="9a02a-106">슬라이더 부분</span><span class="sxs-lookup"><span data-stu-id="9a02a-106">Slider Parts</span></span>  
 <span data-ttu-id="9a02a-107">다음 표에서 대 한 명명된 된 파트를 <xref:System.Windows.Controls.Slider> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a02a-107">The following table lists the named parts for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="9a02a-108">파트</span><span class="sxs-lookup"><span data-stu-id="9a02a-108">Part</span></span>|<span data-ttu-id="9a02a-109">형식</span><span class="sxs-lookup"><span data-stu-id="9a02a-109">Type</span></span>|<span data-ttu-id="9a02a-110">설명</span><span class="sxs-lookup"><span data-stu-id="9a02a-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="9a02a-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="9a02a-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="9a02a-112">위치를 나타내는 요소에 대 한 컨테이너를 <xref:System.Windows.Controls.Slider>입니다.</span><span class="sxs-lookup"><span data-stu-id="9a02a-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Slider>.</span></span>|  
|<span data-ttu-id="9a02a-113">PART_SelectionRange</span><span class="sxs-lookup"><span data-stu-id="9a02a-113">PART_SelectionRange</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="9a02a-114">따라 선택 범위를 표시 하는 요소는 <xref:System.Windows.Controls.Slider>합니다.</span><span class="sxs-lookup"><span data-stu-id="9a02a-114">The element that displays a selection range along the <xref:System.Windows.Controls.Slider>.</span></span>  <span data-ttu-id="9a02a-115">선택 범위의 표시 됩니다. 경우에만 합니다 <xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A> 속성은 `true`.</span><span class="sxs-lookup"><span data-stu-id="9a02a-115">The selection range is visible only if the <xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A> property is `true`.</span></span>|  
  
## <a name="slider-states"></a><span data-ttu-id="9a02a-116">슬라이더 상태</span><span class="sxs-lookup"><span data-stu-id="9a02a-116">Slider States</span></span>  
 <span data-ttu-id="9a02a-117">다음 표에서 대 한 시각적 상태를 <xref:System.Windows.Controls.Slider> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a02a-117">The following table lists the visual states for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="9a02a-118">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="9a02a-118">VisualState Name</span></span>|<span data-ttu-id="9a02a-119">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="9a02a-119">VisualStateGroup Name</span></span>|<span data-ttu-id="9a02a-120">설명</span><span class="sxs-lookup"><span data-stu-id="9a02a-120">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="9a02a-121">보통</span><span class="sxs-lookup"><span data-stu-id="9a02a-121">Normal</span></span>|<span data-ttu-id="9a02a-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="9a02a-122">CommonStates</span></span>|<span data-ttu-id="9a02a-123">기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="9a02a-123">The default state.</span></span>|  
|<span data-ttu-id="9a02a-124">MouseOver</span><span class="sxs-lookup"><span data-stu-id="9a02a-124">MouseOver</span></span>|<span data-ttu-id="9a02a-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="9a02a-125">CommonStates</span></span>|<span data-ttu-id="9a02a-126">마우스 포인터가 컨트롤 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a02a-126">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="9a02a-127">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="9a02a-127">Disabled</span></span>|<span data-ttu-id="9a02a-128">CommonStates</span><span class="sxs-lookup"><span data-stu-id="9a02a-128">CommonStates</span></span>|<span data-ttu-id="9a02a-129">컨트롤이 비활성화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9a02a-129">The control is disabled.</span></span>|  
|<span data-ttu-id="9a02a-130">포커스 있음</span><span class="sxs-lookup"><span data-stu-id="9a02a-130">Focused</span></span>|<span data-ttu-id="9a02a-131">FocusStates</span><span class="sxs-lookup"><span data-stu-id="9a02a-131">FocusStates</span></span>|<span data-ttu-id="9a02a-132">컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a02a-132">The control has focus.</span></span>|  
|<span data-ttu-id="9a02a-133">포커스 없음</span><span class="sxs-lookup"><span data-stu-id="9a02a-133">Unfocused</span></span>|<span data-ttu-id="9a02a-134">FocusStates</span><span class="sxs-lookup"><span data-stu-id="9a02a-134">FocusStates</span></span>|<span data-ttu-id="9a02a-135">컨트롤에 포커스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9a02a-135">The control does not have focus.</span></span>|  
|<span data-ttu-id="9a02a-136">유효</span><span class="sxs-lookup"><span data-stu-id="9a02a-136">Valid</span></span>|<span data-ttu-id="9a02a-137">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9a02a-137">ValidationStates</span></span>|<span data-ttu-id="9a02a-138">컨트롤에서 사용 된 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="9a02a-138">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="9a02a-139">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="9a02a-139">InvalidFocused</span></span>|<span data-ttu-id="9a02a-140">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9a02a-140">ValidationStates</span></span>|<span data-ttu-id="9a02a-141">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a02a-141">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="9a02a-142">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="9a02a-142">InvalidUnfocused</span></span>|<span data-ttu-id="9a02a-143">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9a02a-143">ValidationStates</span></span>|<span data-ttu-id="9a02a-144">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a02a-144">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="slider-controltemplate-example"></a><span data-ttu-id="9a02a-145">슬라이더 ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="9a02a-145">Slider ControlTemplate Example</span></span>  
 <span data-ttu-id="9a02a-146">다음 예제에서는 정의 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.Slider> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a02a-146">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Slider](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#slider)]  
  
 <span data-ttu-id="9a02a-147">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9a02a-147">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="9a02a-148">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9a02a-148">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a02a-149">참고자료</span><span class="sxs-lookup"><span data-stu-id="9a02a-149">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="9a02a-150">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="9a02a-150">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="9a02a-151">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="9a02a-151">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="9a02a-152">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="9a02a-152">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="9a02a-153">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="9a02a-153">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
