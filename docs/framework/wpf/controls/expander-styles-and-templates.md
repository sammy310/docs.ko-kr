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
ms.openlocfilehash: 26989474f264161be12bcc14fed614fdc7f775b6
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460334"
---
# <a name="expander-styles-and-templates"></a><span data-ttu-id="da16c-102">Expander 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="da16c-102">Expander Styles and Templates</span></span>
<span data-ttu-id="da16c-103">이 항목에서는 <xref:System.Windows.Controls.Expander> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="da16c-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Expander> control.</span></span> <span data-ttu-id="da16c-104">기본 <xref:System.Windows.Controls.ControlTemplate>를 수정 하 여 컨트롤에 고유한 모양을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da16c-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="da16c-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="da16c-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="expander-parts"></a><span data-ttu-id="da16c-106">확장기 파트</span><span class="sxs-lookup"><span data-stu-id="da16c-106">Expander Parts</span></span>  
 <span data-ttu-id="da16c-107"><xref:System.Windows.Controls.Expander> 컨트롤에는 명명 된 파트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da16c-107">The <xref:System.Windows.Controls.Expander> control does not have any named parts.</span></span>  
  
## <a name="expander-states"></a><span data-ttu-id="da16c-108">확장기 상태</span><span class="sxs-lookup"><span data-stu-id="da16c-108">Expander States</span></span>  
 <span data-ttu-id="da16c-109">다음 표에서는 <xref:System.Windows.Controls.Expander> 컨트롤의 시각적 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="da16c-109">The following table lists the visual states for the <xref:System.Windows.Controls.Expander> control.</span></span>  
  
|<span data-ttu-id="da16c-110">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="da16c-110">VisualState Name</span></span>|<span data-ttu-id="da16c-111">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="da16c-111">VisualStateGroup Name</span></span>|<span data-ttu-id="da16c-112">설명</span><span class="sxs-lookup"><span data-stu-id="da16c-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="da16c-113">보통</span><span class="sxs-lookup"><span data-stu-id="da16c-113">Normal</span></span>|<span data-ttu-id="da16c-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="da16c-114">CommonStates</span></span>|<span data-ttu-id="da16c-115">기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="da16c-115">The default state.</span></span>|  
|<span data-ttu-id="da16c-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="da16c-116">MouseOver</span></span>|<span data-ttu-id="da16c-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="da16c-117">CommonStates</span></span>|<span data-ttu-id="da16c-118">마우스 포인터가 컨트롤 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da16c-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="da16c-119">Disabled</span><span class="sxs-lookup"><span data-stu-id="da16c-119">Disabled</span></span>|<span data-ttu-id="da16c-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="da16c-120">CommonStates</span></span>|<span data-ttu-id="da16c-121">컨트롤이 비활성화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="da16c-121">The control is disabled.</span></span>|  
|<span data-ttu-id="da16c-122">포커스 있음</span><span class="sxs-lookup"><span data-stu-id="da16c-122">Focused</span></span>|<span data-ttu-id="da16c-123">FocusStates</span><span class="sxs-lookup"><span data-stu-id="da16c-123">FocusStates</span></span>|<span data-ttu-id="da16c-124">컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da16c-124">The control has focus.</span></span>|  
|<span data-ttu-id="da16c-125">포커스 없음</span><span class="sxs-lookup"><span data-stu-id="da16c-125">Unfocused</span></span>|<span data-ttu-id="da16c-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="da16c-126">FocusStates</span></span>|<span data-ttu-id="da16c-127">컨트롤에 포커스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da16c-127">The control does not have focus.</span></span>|  
|<span data-ttu-id="da16c-128">넓게</span><span class="sxs-lookup"><span data-stu-id="da16c-128">Expanded</span></span>|<span data-ttu-id="da16c-129">ExpansionStates</span><span class="sxs-lookup"><span data-stu-id="da16c-129">ExpansionStates</span></span>|<span data-ttu-id="da16c-130">컨트롤이 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da16c-130">The control is expanded.</span></span>|  
|<span data-ttu-id="da16c-131">Collapsed</span><span class="sxs-lookup"><span data-stu-id="da16c-131">Collapsed</span></span>|<span data-ttu-id="da16c-132">ExpansionStates</span><span class="sxs-lookup"><span data-stu-id="da16c-132">ExpansionStates</span></span>|<span data-ttu-id="da16c-133">컨트롤이 확장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da16c-133">The control is not expanded.</span></span>|  
|<span data-ttu-id="da16c-134">ExpandDown</span><span class="sxs-lookup"><span data-stu-id="da16c-134">ExpandDown</span></span>|<span data-ttu-id="da16c-135">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="da16c-135">ExpandDirectionStates</span></span>|<span data-ttu-id="da16c-136">컨트롤이 아래로 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da16c-136">The control expands down.</span></span>|  
|<span data-ttu-id="da16c-137">ExpandUp</span><span class="sxs-lookup"><span data-stu-id="da16c-137">ExpandUp</span></span>|<span data-ttu-id="da16c-138">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="da16c-138">ExpandDirectionStates</span></span>|<span data-ttu-id="da16c-139">컨트롤이 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da16c-139">The control expands up.</span></span>|  
|<span data-ttu-id="da16c-140">ExpandLeft</span><span class="sxs-lookup"><span data-stu-id="da16c-140">ExpandLeft</span></span>|<span data-ttu-id="da16c-141">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="da16c-141">ExpandDirectionStates</span></span>|<span data-ttu-id="da16c-142">컨트롤이 왼쪽으로 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da16c-142">The control expands left.</span></span>|  
|<span data-ttu-id="da16c-143">ExpandRight</span><span class="sxs-lookup"><span data-stu-id="da16c-143">ExpandRight</span></span>|<span data-ttu-id="da16c-144">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="da16c-144">ExpandDirectionStates</span></span>|<span data-ttu-id="da16c-145">컨트롤이 오른쪽으로 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da16c-145">The control expands right.</span></span>|  
|<span data-ttu-id="da16c-146">유효</span><span class="sxs-lookup"><span data-stu-id="da16c-146">Valid</span></span>|<span data-ttu-id="da16c-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="da16c-147">ValidationStates</span></span>|<span data-ttu-id="da16c-148">컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="da16c-148">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="da16c-149">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="da16c-149">InvalidFocused</span></span>|<span data-ttu-id="da16c-150">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="da16c-150">ValidationStates</span></span>|<span data-ttu-id="da16c-151">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da16c-151">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="da16c-152">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="da16c-152">InvalidUnfocused</span></span>|<span data-ttu-id="da16c-153">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="da16c-153">ValidationStates</span></span>|<span data-ttu-id="da16c-154">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="da16c-154">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="expander-controltemplate-example"></a><span data-ttu-id="da16c-155">확장기 ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="da16c-155">Expander ControlTemplate Example</span></span>  
 <span data-ttu-id="da16c-156">다음 예제에서는 <xref:System.Windows.Controls.Expander> 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="da16c-156">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Expander> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Expander](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/expander.xaml#expander)]  
  
 <span data-ttu-id="da16c-157">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="da16c-157">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="da16c-158">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="da16c-158">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da16c-159">참조</span><span class="sxs-lookup"><span data-stu-id="da16c-159">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="da16c-160">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="da16c-160">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="da16c-161">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="da16c-161">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="da16c-162">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="da16c-162">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="da16c-163">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="da16c-163">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
