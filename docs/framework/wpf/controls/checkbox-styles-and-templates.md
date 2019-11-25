---
title: CheckBox 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], CheckBox
- templates [WPF], CheckBox
- parts [WPF], CheckBox
- ControlTemplate [WPF], CheckBox
- CheckBox [WPF], styles and templates
- styles [WPF], CheckBox
ms.assetid: bfdaec96-d101-4d3d-864d-c27e6b621d03
ms.openlocfilehash: b9eee48c01f53e12bbe4a72f84c20eab68d5de23
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283813"
---
# <a name="checkbox-styles-and-templates"></a><span data-ttu-id="51a64-102">CheckBox 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="51a64-102">CheckBox Styles and Templates</span></span>
<span data-ttu-id="51a64-103">이 항목에서는 <xref:System.Windows.Controls.CheckBox> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="51a64-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.CheckBox> control.</span></span> <span data-ttu-id="51a64-104">기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51a64-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="51a64-105">자세한 내용은 [컨트롤에 대 한 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="51a64-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="checkbox-parts"></a><span data-ttu-id="51a64-106">CheckBox 파트</span><span class="sxs-lookup"><span data-stu-id="51a64-106">CheckBox Parts</span></span>  
 <span data-ttu-id="51a64-107"><xref:System.Windows.Controls.CheckBox> 컨트롤에는 명명 된 파트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="51a64-107">The <xref:System.Windows.Controls.CheckBox> control does not have any named parts.</span></span>  
  
## <a name="checkbox-states"></a><span data-ttu-id="51a64-108">CheckBox 상태</span><span class="sxs-lookup"><span data-stu-id="51a64-108">CheckBox States</span></span>  
 <span data-ttu-id="51a64-109">다음 표에서는 <xref:System.Windows.Controls.CheckBox> 컨트롤의 시각적 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="51a64-109">The following table lists the visual states for the <xref:System.Windows.Controls.CheckBox> control.</span></span>  
  
|<span data-ttu-id="51a64-110">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="51a64-110">VisualState Name</span></span>|<span data-ttu-id="51a64-111">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="51a64-111">VisualStateGroup Name</span></span>|<span data-ttu-id="51a64-112">설명</span><span class="sxs-lookup"><span data-stu-id="51a64-112">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="51a64-113">보통</span><span class="sxs-lookup"><span data-stu-id="51a64-113">Normal</span></span>|<span data-ttu-id="51a64-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="51a64-114">CommonStates</span></span>|<span data-ttu-id="51a64-115">기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="51a64-115">The default state.</span></span>|  
|<span data-ttu-id="51a64-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="51a64-116">MouseOver</span></span>|<span data-ttu-id="51a64-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="51a64-117">CommonStates</span></span>|<span data-ttu-id="51a64-118">마우스 포인터가 컨트롤 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51a64-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="51a64-119">누름</span><span class="sxs-lookup"><span data-stu-id="51a64-119">Pressed</span></span>|<span data-ttu-id="51a64-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="51a64-120">CommonStates</span></span>|<span data-ttu-id="51a64-121">컨트롤을 눌렀습니다.</span><span class="sxs-lookup"><span data-stu-id="51a64-121">The control is pressed.</span></span>|  
|<span data-ttu-id="51a64-122">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="51a64-122">Disabled</span></span>|<span data-ttu-id="51a64-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="51a64-123">CommonStates</span></span>|<span data-ttu-id="51a64-124">컨트롤이 비활성화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="51a64-124">The control is disabled.</span></span>|  
|<span data-ttu-id="51a64-125">포커스 있음</span><span class="sxs-lookup"><span data-stu-id="51a64-125">Focused</span></span>|<span data-ttu-id="51a64-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="51a64-126">FocusStates</span></span>|<span data-ttu-id="51a64-127">컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51a64-127">The control has focus.</span></span>|  
|<span data-ttu-id="51a64-128">포커스 없음</span><span class="sxs-lookup"><span data-stu-id="51a64-128">Unfocused</span></span>|<span data-ttu-id="51a64-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="51a64-129">FocusStates</span></span>|<span data-ttu-id="51a64-130">컨트롤에 포커스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="51a64-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="51a64-131">선택한 상태</span><span class="sxs-lookup"><span data-stu-id="51a64-131">Checked</span></span>|<span data-ttu-id="51a64-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="51a64-132">CheckStates</span></span>|<span data-ttu-id="51a64-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>가 `true`인 경우</span><span class="sxs-lookup"><span data-stu-id="51a64-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|  
|<span data-ttu-id="51a64-134">선택 취소 되어 있음</span><span class="sxs-lookup"><span data-stu-id="51a64-134">Unchecked</span></span>|<span data-ttu-id="51a64-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="51a64-135">CheckStates</span></span>|<span data-ttu-id="51a64-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>가 `false`인 경우</span><span class="sxs-lookup"><span data-stu-id="51a64-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|  
|<span data-ttu-id="51a64-137">비활성화</span><span class="sxs-lookup"><span data-stu-id="51a64-137">Indeterminate</span></span>|<span data-ttu-id="51a64-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="51a64-138">CheckStates</span></span>|<span data-ttu-id="51a64-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A>가 `true`이고 <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>이 `null`인 경우</span><span class="sxs-lookup"><span data-stu-id="51a64-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|  
|<span data-ttu-id="51a64-140">유효</span><span class="sxs-lookup"><span data-stu-id="51a64-140">Valid</span></span>|<span data-ttu-id="51a64-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="51a64-141">ValidationStates</span></span>|<span data-ttu-id="51a64-142">컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="51a64-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="51a64-143">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="51a64-143">InvalidUnfocused</span></span>|<span data-ttu-id="51a64-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="51a64-144">ValidationStates</span></span>|<span data-ttu-id="51a64-145">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51a64-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="51a64-146">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="51a64-146">InvalidFocused</span></span>|<span data-ttu-id="51a64-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="51a64-147">ValidationStates</span></span>|<span data-ttu-id="51a64-148">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="51a64-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="checkbox-controltemplate-example"></a><span data-ttu-id="51a64-149">CheckBox ControlTemplate 예</span><span class="sxs-lookup"><span data-stu-id="51a64-149">CheckBox ControlTemplate Example</span></span>  
 <span data-ttu-id="51a64-150">다음 예제에서는 <xref:System.Windows.Controls.CheckBox> 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="51a64-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.CheckBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#CheckBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/checkbox.xaml#checkbox)]  
  
 <span data-ttu-id="51a64-151">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="51a64-151">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="51a64-152">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51a64-152">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51a64-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="51a64-153">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="51a64-154">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="51a64-154">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="51a64-155">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="51a64-155">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="51a64-156">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="51a64-156">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="51a64-157">컨트롤에 대 한 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="51a64-157">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
