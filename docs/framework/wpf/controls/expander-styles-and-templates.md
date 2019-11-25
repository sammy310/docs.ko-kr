---
title: Expander 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], Expander
- ControlTemplate [WPF], Expander
- templates [WPF], Expander
- Expander [WPF], styles and templates
- states [WPF], Expander
- parts [WPF], Expander
ms.assetid: da2e5a1c-5230-4c21-98a5-59c7895facd7
ms.openlocfilehash: 39f81aacb24b0b68b550da622b1e3038eb9eac9b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283522"
---
# <a name="expander-styles-and-templates"></a><span data-ttu-id="7ac24-102">Expander 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="7ac24-102">Expander Styles and Templates</span></span>
<span data-ttu-id="7ac24-103">이 항목에서는 <xref:System.Windows.Controls.Expander> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac24-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Expander> control.</span></span> <span data-ttu-id="7ac24-104">기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ac24-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="7ac24-105">자세한 내용은 [컨트롤에 대 한 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7ac24-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="expander-parts"></a><span data-ttu-id="7ac24-106">확장기 파트</span><span class="sxs-lookup"><span data-stu-id="7ac24-106">Expander Parts</span></span>  
 <span data-ttu-id="7ac24-107"><xref:System.Windows.Controls.Expander> 컨트롤에는 명명 된 파트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7ac24-107">The <xref:System.Windows.Controls.Expander> control does not have any named parts.</span></span>  
  
## <a name="expander-states"></a><span data-ttu-id="7ac24-108">확장기 상태</span><span class="sxs-lookup"><span data-stu-id="7ac24-108">Expander States</span></span>  
 <span data-ttu-id="7ac24-109">다음 표에서는 <xref:System.Windows.Controls.Expander> 컨트롤의 시각적 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7ac24-109">The following table lists the visual states for the <xref:System.Windows.Controls.Expander> control.</span></span>  
  
|<span data-ttu-id="7ac24-110">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="7ac24-110">VisualState Name</span></span>|<span data-ttu-id="7ac24-111">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="7ac24-111">VisualStateGroup Name</span></span>|<span data-ttu-id="7ac24-112">설명</span><span class="sxs-lookup"><span data-stu-id="7ac24-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="7ac24-113">보통</span><span class="sxs-lookup"><span data-stu-id="7ac24-113">Normal</span></span>|<span data-ttu-id="7ac24-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="7ac24-114">CommonStates</span></span>|<span data-ttu-id="7ac24-115">기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="7ac24-115">The default state.</span></span>|  
|<span data-ttu-id="7ac24-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="7ac24-116">MouseOver</span></span>|<span data-ttu-id="7ac24-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="7ac24-117">CommonStates</span></span>|<span data-ttu-id="7ac24-118">마우스 포인터가 컨트롤 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ac24-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="7ac24-119">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="7ac24-119">Disabled</span></span>|<span data-ttu-id="7ac24-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="7ac24-120">CommonStates</span></span>|<span data-ttu-id="7ac24-121">컨트롤이 비활성화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7ac24-121">The control is disabled.</span></span>|  
|<span data-ttu-id="7ac24-122">포커스 있음</span><span class="sxs-lookup"><span data-stu-id="7ac24-122">Focused</span></span>|<span data-ttu-id="7ac24-123">FocusStates</span><span class="sxs-lookup"><span data-stu-id="7ac24-123">FocusStates</span></span>|<span data-ttu-id="7ac24-124">컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ac24-124">The control has focus.</span></span>|  
|<span data-ttu-id="7ac24-125">포커스 없음</span><span class="sxs-lookup"><span data-stu-id="7ac24-125">Unfocused</span></span>|<span data-ttu-id="7ac24-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="7ac24-126">FocusStates</span></span>|<span data-ttu-id="7ac24-127">컨트롤에 포커스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7ac24-127">The control does not have focus.</span></span>|  
|<span data-ttu-id="7ac24-128">넓게</span><span class="sxs-lookup"><span data-stu-id="7ac24-128">Expanded</span></span>|<span data-ttu-id="7ac24-129">ExpansionStates</span><span class="sxs-lookup"><span data-stu-id="7ac24-129">ExpansionStates</span></span>|<span data-ttu-id="7ac24-130">컨트롤이 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ac24-130">The control is expanded.</span></span>|  
|<span data-ttu-id="7ac24-131">Collapsed</span><span class="sxs-lookup"><span data-stu-id="7ac24-131">Collapsed</span></span>|<span data-ttu-id="7ac24-132">ExpansionStates</span><span class="sxs-lookup"><span data-stu-id="7ac24-132">ExpansionStates</span></span>|<span data-ttu-id="7ac24-133">컨트롤이 확장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7ac24-133">The control is not expanded.</span></span>|  
|<span data-ttu-id="7ac24-134">ExpandDown</span><span class="sxs-lookup"><span data-stu-id="7ac24-134">ExpandDown</span></span>|<span data-ttu-id="7ac24-135">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="7ac24-135">ExpandDirectionStates</span></span>|<span data-ttu-id="7ac24-136">컨트롤이 아래로 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ac24-136">The control expands down.</span></span>|  
|<span data-ttu-id="7ac24-137">ExpandUp</span><span class="sxs-lookup"><span data-stu-id="7ac24-137">ExpandUp</span></span>|<span data-ttu-id="7ac24-138">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="7ac24-138">ExpandDirectionStates</span></span>|<span data-ttu-id="7ac24-139">컨트롤이 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ac24-139">The control expands up.</span></span>|  
|<span data-ttu-id="7ac24-140">ExpandLeft</span><span class="sxs-lookup"><span data-stu-id="7ac24-140">ExpandLeft</span></span>|<span data-ttu-id="7ac24-141">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="7ac24-141">ExpandDirectionStates</span></span>|<span data-ttu-id="7ac24-142">컨트롤이 왼쪽으로 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ac24-142">The control expands left.</span></span>|  
|<span data-ttu-id="7ac24-143">ExpandRight</span><span class="sxs-lookup"><span data-stu-id="7ac24-143">ExpandRight</span></span>|<span data-ttu-id="7ac24-144">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="7ac24-144">ExpandDirectionStates</span></span>|<span data-ttu-id="7ac24-145">컨트롤이 오른쪽으로 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ac24-145">The control expands right.</span></span>|  
|<span data-ttu-id="7ac24-146">유효</span><span class="sxs-lookup"><span data-stu-id="7ac24-146">Valid</span></span>|<span data-ttu-id="7ac24-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7ac24-147">ValidationStates</span></span>|<span data-ttu-id="7ac24-148">컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ac24-148">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="7ac24-149">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="7ac24-149">InvalidFocused</span></span>|<span data-ttu-id="7ac24-150">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7ac24-150">ValidationStates</span></span>|<span data-ttu-id="7ac24-151">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ac24-151">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="7ac24-152">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="7ac24-152">InvalidUnfocused</span></span>|<span data-ttu-id="7ac24-153">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7ac24-153">ValidationStates</span></span>|<span data-ttu-id="7ac24-154">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="7ac24-154">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="expander-controltemplate-example"></a><span data-ttu-id="7ac24-155">확장기 ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="7ac24-155">Expander ControlTemplate Example</span></span>  
 <span data-ttu-id="7ac24-156">다음 예제에서는 <xref:System.Windows.Controls.Expander> 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7ac24-156">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Expander> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Expander](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/expander.xaml#expander)]  
  
 <span data-ttu-id="7ac24-157">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac24-157">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="7ac24-158">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7ac24-158">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ac24-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7ac24-159">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="7ac24-160">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="7ac24-160">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="7ac24-161">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="7ac24-161">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="7ac24-162">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="7ac24-162">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="7ac24-163">컨트롤에 대 한 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="7ac24-163">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
