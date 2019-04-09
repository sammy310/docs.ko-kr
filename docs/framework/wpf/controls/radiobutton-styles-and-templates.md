---
title: RadioButton 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], RadioButton
- RadioButton [WPF], styles and templates
- ControlTemplate [WPF], RadioButton
- states [WPF], RadioButton
- templates [WPF], RadioButton
- parts [WPF], RadioButton
ms.assetid: 9acf93f7-dd2f-4010-8ce0-1edd81c52ae2
ms.openlocfilehash: f11a8338c96d14c3c518713865061e4095ff23b1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078722"
---
# <a name="radiobutton-styles-and-templates"></a><span data-ttu-id="3ef15-102">RadioButton 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="3ef15-102">RadioButton Styles and Templates</span></span>
<span data-ttu-id="3ef15-103">이 항목에서는 스타일 및 템플릿에 대해 설명 합니다 <xref:System.Windows.Controls.RadioButton> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ef15-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.RadioButton> control.</span></span> <span data-ttu-id="3ef15-104">기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ef15-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="3ef15-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3ef15-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="radiobutton-parts"></a><span data-ttu-id="3ef15-106">RadioButton 파트</span><span class="sxs-lookup"><span data-stu-id="3ef15-106">RadioButton Parts</span></span>  
 <span data-ttu-id="3ef15-107"><xref:System.Windows.Controls.RadioButton> 컨트롤에 명명된 된 파트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ef15-107">The <xref:System.Windows.Controls.RadioButton> control does not have any named parts.</span></span>  
  
## <a name="radiobutton-states"></a><span data-ttu-id="3ef15-108">라디오 단추 상태</span><span class="sxs-lookup"><span data-stu-id="3ef15-108">RadioButton States</span></span>  
 <span data-ttu-id="3ef15-109">다음 표에서 대 한 시각적 상태를 <xref:System.Windows.Controls.RadioButton> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ef15-109">The following table lists the visual states for the <xref:System.Windows.Controls.RadioButton> control.</span></span>  
  
|<span data-ttu-id="3ef15-110">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="3ef15-110">VisualState Name</span></span>|<span data-ttu-id="3ef15-111">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="3ef15-111">VisualStateGroup Name</span></span>|<span data-ttu-id="3ef15-112">설명</span><span class="sxs-lookup"><span data-stu-id="3ef15-112">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="3ef15-113">보통</span><span class="sxs-lookup"><span data-stu-id="3ef15-113">Normal</span></span>|<span data-ttu-id="3ef15-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="3ef15-114">CommonStates</span></span>|<span data-ttu-id="3ef15-115">기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="3ef15-115">The default state.</span></span>|  
|<span data-ttu-id="3ef15-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="3ef15-116">MouseOver</span></span>|<span data-ttu-id="3ef15-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="3ef15-117">CommonStates</span></span>|<span data-ttu-id="3ef15-118">마우스 포인터가 컨트롤 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ef15-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="3ef15-119">누름</span><span class="sxs-lookup"><span data-stu-id="3ef15-119">Pressed</span></span>|<span data-ttu-id="3ef15-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="3ef15-120">CommonStates</span></span>|<span data-ttu-id="3ef15-121">컨트롤을 눌렀습니다.</span><span class="sxs-lookup"><span data-stu-id="3ef15-121">The control is pressed.</span></span>|  
|<span data-ttu-id="3ef15-122">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="3ef15-122">Disabled</span></span>|<span data-ttu-id="3ef15-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="3ef15-123">CommonStates</span></span>|<span data-ttu-id="3ef15-124">컨트롤이 비활성화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3ef15-124">The control is disabled.</span></span>|  
|<span data-ttu-id="3ef15-125">포커스 있음</span><span class="sxs-lookup"><span data-stu-id="3ef15-125">Focused</span></span>|<span data-ttu-id="3ef15-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="3ef15-126">FocusStates</span></span>|<span data-ttu-id="3ef15-127">컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ef15-127">The control has focus.</span></span>|  
|<span data-ttu-id="3ef15-128">포커스 없음</span><span class="sxs-lookup"><span data-stu-id="3ef15-128">Unfocused</span></span>|<span data-ttu-id="3ef15-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="3ef15-129">FocusStates</span></span>|<span data-ttu-id="3ef15-130">컨트롤에 포커스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ef15-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="3ef15-131">선택한 상태</span><span class="sxs-lookup"><span data-stu-id="3ef15-131">Checked</span></span>|<span data-ttu-id="3ef15-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="3ef15-132">CheckStates</span></span>|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> <span data-ttu-id="3ef15-133">`true`합니다.</span><span class="sxs-lookup"><span data-stu-id="3ef15-133">is `true`.</span></span>|  
|<span data-ttu-id="3ef15-134">선택 취소 되어 있음</span><span class="sxs-lookup"><span data-stu-id="3ef15-134">Unchecked</span></span>|<span data-ttu-id="3ef15-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="3ef15-135">CheckStates</span></span>|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> <span data-ttu-id="3ef15-136">`false`합니다.</span><span class="sxs-lookup"><span data-stu-id="3ef15-136">is `false`.</span></span>|  
|<span data-ttu-id="3ef15-137">비활성화</span><span class="sxs-lookup"><span data-stu-id="3ef15-137">Indeterminate</span></span>|<span data-ttu-id="3ef15-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="3ef15-138">CheckStates</span></span>|<xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> <span data-ttu-id="3ef15-139">됩니다 `true`, 및 <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 는 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="3ef15-139">is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|  
|<span data-ttu-id="3ef15-140">유효</span><span class="sxs-lookup"><span data-stu-id="3ef15-140">Valid</span></span>|<span data-ttu-id="3ef15-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3ef15-141">ValidationStates</span></span>|<span data-ttu-id="3ef15-142">컨트롤에서 사용 된 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="3ef15-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="3ef15-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="3ef15-143">InvalidFocused</span></span>|<span data-ttu-id="3ef15-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3ef15-144">ValidationStates</span></span>|<span data-ttu-id="3ef15-145">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ef15-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="3ef15-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="3ef15-146">InvalidUnfocused</span></span>|<span data-ttu-id="3ef15-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3ef15-147">ValidationStates</span></span>|<span data-ttu-id="3ef15-148">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ef15-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="radiobutton-controltemplate-example"></a><span data-ttu-id="3ef15-149">라디오 단추 ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="3ef15-149">RadioButton ControlTemplate Example</span></span>  
 <span data-ttu-id="3ef15-150">다음 예제에서는 정의 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.RadioButton> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ef15-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.RadioButton> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#RadioButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/radiobutton.xaml#radiobutton)]  
  
 <span data-ttu-id="3ef15-151">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3ef15-151">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="3ef15-152">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3ef15-152">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ef15-153">참고자료</span><span class="sxs-lookup"><span data-stu-id="3ef15-153">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="3ef15-154">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="3ef15-154">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="3ef15-155">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="3ef15-155">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="3ef15-156">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="3ef15-156">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="3ef15-157">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="3ef15-157">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
