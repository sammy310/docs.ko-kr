---
title: ToggleButton 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToggleButton
- ToggleButton [WPF], styles and templates
- ControlTemplate [WPF], ToggleButton
- styles [WPF], ToggleButton
- templates [WPF], ToggleButton
- parts [WPF], ToggleButton
ms.assetid: 54f23f30-4bcb-4f09-8ce4-376a13a255a1
ms.openlocfilehash: e055dcbd557f9b90eb2fe99ad15a05b6f229fd28
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805915"
---
# <a name="togglebutton-styles-and-templates"></a><span data-ttu-id="0e4c3-102">ToggleButton 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="0e4c3-102">ToggleButton Styles and Templates</span></span>

<span data-ttu-id="0e4c3-103">이 항목에서는 <xref:System.Windows.Controls.Primitives.ToggleButton> 컨트롤의 스타일과 템플릿에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span> <span data-ttu-id="0e4c3-104">기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="0e4c3-105">자세한 내용은 [컨트롤에 대한 템플릿 만들기를](../../../desktop-wpf/themes/how-to-create-apply-template.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>

## <a name="togglebutton-parts"></a><span data-ttu-id="0e4c3-106">토글 버튼 부품</span><span class="sxs-lookup"><span data-stu-id="0e4c3-106">ToggleButton Parts</span></span>

<span data-ttu-id="0e4c3-107">컨트롤에는 <xref:System.Windows.Controls.Primitives.ToggleButton> 명명된 부품이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-107">The <xref:System.Windows.Controls.Primitives.ToggleButton> control does not have any named parts.</span></span>

## <a name="togglebutton-states"></a><span data-ttu-id="0e4c3-108">토글버튼 상태</span><span class="sxs-lookup"><span data-stu-id="0e4c3-108">ToggleButton States</span></span>

<span data-ttu-id="0e4c3-109">다음 표에는 컨트롤의 시각적 <xref:System.Windows.Controls.Primitives.ToggleButton> 상태가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

|<span data-ttu-id="0e4c3-110">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="0e4c3-110">VisualState Name</span></span>|<span data-ttu-id="0e4c3-111">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="0e4c3-111">VisualStateGroup Name</span></span>|<span data-ttu-id="0e4c3-112">Description</span><span class="sxs-lookup"><span data-stu-id="0e4c3-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="0e4c3-113">정상</span><span class="sxs-lookup"><span data-stu-id="0e4c3-113">Normal</span></span>|<span data-ttu-id="0e4c3-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0e4c3-114">CommonStates</span></span>|<span data-ttu-id="0e4c3-115">기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-115">The default state.</span></span>|
|<span data-ttu-id="0e4c3-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="0e4c3-116">MouseOver</span></span>|<span data-ttu-id="0e4c3-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0e4c3-117">CommonStates</span></span>|<span data-ttu-id="0e4c3-118">마우스 포인터가 컨트롤 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="0e4c3-119">누름</span><span class="sxs-lookup"><span data-stu-id="0e4c3-119">Pressed</span></span>|<span data-ttu-id="0e4c3-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0e4c3-120">CommonStates</span></span>|<span data-ttu-id="0e4c3-121">컨트롤을 눌렀습니다.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-121">The control is pressed.</span></span>|
|<span data-ttu-id="0e4c3-122">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="0e4c3-122">Disabled</span></span>|<span data-ttu-id="0e4c3-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0e4c3-123">CommonStates</span></span>|<span data-ttu-id="0e4c3-124">컨트롤이 비활성화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-124">The control is disabled.</span></span>|
|<span data-ttu-id="0e4c3-125">포커스 있음</span><span class="sxs-lookup"><span data-stu-id="0e4c3-125">Focused</span></span>|<span data-ttu-id="0e4c3-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="0e4c3-126">FocusStates</span></span>|<span data-ttu-id="0e4c3-127">컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-127">The control has focus.</span></span>|
|<span data-ttu-id="0e4c3-128">포커스 없음</span><span class="sxs-lookup"><span data-stu-id="0e4c3-128">Unfocused</span></span>|<span data-ttu-id="0e4c3-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="0e4c3-129">FocusStates</span></span>|<span data-ttu-id="0e4c3-130">컨트롤에 포커스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-130">The control does not have focus.</span></span>|
|<span data-ttu-id="0e4c3-131">선택</span><span class="sxs-lookup"><span data-stu-id="0e4c3-131">Checked</span></span>|<span data-ttu-id="0e4c3-132">체크스테이트</span><span class="sxs-lookup"><span data-stu-id="0e4c3-132">CheckStates</span></span>|<span data-ttu-id="0e4c3-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|
|<span data-ttu-id="0e4c3-134">선택 취소됨</span><span class="sxs-lookup"><span data-stu-id="0e4c3-134">Unchecked</span></span>|<span data-ttu-id="0e4c3-135">체크스테이트</span><span class="sxs-lookup"><span data-stu-id="0e4c3-135">CheckStates</span></span>|<span data-ttu-id="0e4c3-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|
|<span data-ttu-id="0e4c3-137">확정 되지 않은</span><span class="sxs-lookup"><span data-stu-id="0e4c3-137">Indeterminate</span></span>|<span data-ttu-id="0e4c3-138">체크스테이트</span><span class="sxs-lookup"><span data-stu-id="0e4c3-138">CheckStates</span></span>|<span data-ttu-id="0e4c3-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A>가 `true`이고 <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>이 `null`인 경우</span><span class="sxs-lookup"><span data-stu-id="0e4c3-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|
|<span data-ttu-id="0e4c3-140">Valid</span><span class="sxs-lookup"><span data-stu-id="0e4c3-140">Valid</span></span>|<span data-ttu-id="0e4c3-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0e4c3-141">ValidationStates</span></span>|<span data-ttu-id="0e4c3-142">컨트롤은 클래스를 <xref:System.Windows.Controls.Validation> 사용하고 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결된 `false`속성은 입니다.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="0e4c3-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="0e4c3-143">InvalidFocused</span></span>|<span data-ttu-id="0e4c3-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0e4c3-144">ValidationStates</span></span>|<span data-ttu-id="0e4c3-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결된 속성은 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|
|<span data-ttu-id="0e4c3-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="0e4c3-146">InvalidUnfocused</span></span>|<span data-ttu-id="0e4c3-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0e4c3-147">ValidationStates</span></span>|<span data-ttu-id="0e4c3-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결된 속성이며 `true` 컨트롤에 포커스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|

> [!NOTE]
> <span data-ttu-id="0e4c3-149">컨트롤 템플릿에 확정되지 않은 시각적 상태가 없으면 선택되지 않은 시각적 상태가 기본 시각적 상태로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-149">If the Indeterminate visual state does not exist in your control template, then the Unchecked visual state will be used as default visual state.</span></span>

## <a name="togglebutton-controltemplate-example"></a><span data-ttu-id="0e4c3-150">토글 버튼 제어템플릿 예제</span><span class="sxs-lookup"><span data-stu-id="0e4c3-150">ToggleButton ControlTemplate Example</span></span>

<span data-ttu-id="0e4c3-151">다음 예제에서는 컨트롤에 <xref:System.Windows.Controls.ControlTemplate> 대한 <xref:System.Windows.Controls.Primitives.ToggleButton> a를 정의하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#ToggleButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]

<span data-ttu-id="0e4c3-152">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-152">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="0e4c3-153">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-153">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="0e4c3-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0e4c3-154">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="0e4c3-155">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="0e4c3-155">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="0e4c3-156">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="0e4c3-156">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="0e4c3-157">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="0e4c3-157">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="0e4c3-158">컨트롤용 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="0e4c3-158">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
