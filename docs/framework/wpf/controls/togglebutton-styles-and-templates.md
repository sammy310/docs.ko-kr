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
ms.openlocfilehash: a4c449a561017659db7f54fd3cdb8964742650de
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283670"
---
# <a name="togglebutton-styles-and-templates"></a><span data-ttu-id="3cf65-102">ToggleButton 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="3cf65-102">ToggleButton Styles and Templates</span></span>

<span data-ttu-id="3cf65-103">이 항목에서는 <xref:System.Windows.Controls.Primitives.ToggleButton> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf65-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span> <span data-ttu-id="3cf65-104">기본 <xref:System.Windows.Controls.ControlTemplate>를 수정 하 여 컨트롤에 고유한 모양을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf65-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="3cf65-105">자세한 내용은 [컨트롤에 대 한 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3cf65-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>

## <a name="togglebutton-parts"></a><span data-ttu-id="3cf65-106">ToggleButton 파트</span><span class="sxs-lookup"><span data-stu-id="3cf65-106">ToggleButton Parts</span></span>

<span data-ttu-id="3cf65-107"><xref:System.Windows.Controls.Primitives.ToggleButton> 컨트롤에는 명명 된 파트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf65-107">The <xref:System.Windows.Controls.Primitives.ToggleButton> control does not have any named parts.</span></span>

## <a name="togglebutton-states"></a><span data-ttu-id="3cf65-108">ToggleButton 상태</span><span class="sxs-lookup"><span data-stu-id="3cf65-108">ToggleButton States</span></span>

<span data-ttu-id="3cf65-109">다음 표에서는 <xref:System.Windows.Controls.Primitives.ToggleButton> 컨트롤의 시각적 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3cf65-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

|<span data-ttu-id="3cf65-110">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="3cf65-110">VisualState Name</span></span>|<span data-ttu-id="3cf65-111">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="3cf65-111">VisualStateGroup Name</span></span>|<span data-ttu-id="3cf65-112">설명</span><span class="sxs-lookup"><span data-stu-id="3cf65-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="3cf65-113">보통</span><span class="sxs-lookup"><span data-stu-id="3cf65-113">Normal</span></span>|<span data-ttu-id="3cf65-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="3cf65-114">CommonStates</span></span>|<span data-ttu-id="3cf65-115">기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="3cf65-115">The default state.</span></span>|
|<span data-ttu-id="3cf65-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="3cf65-116">MouseOver</span></span>|<span data-ttu-id="3cf65-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="3cf65-117">CommonStates</span></span>|<span data-ttu-id="3cf65-118">마우스 포인터가 컨트롤 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf65-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="3cf65-119">누름</span><span class="sxs-lookup"><span data-stu-id="3cf65-119">Pressed</span></span>|<span data-ttu-id="3cf65-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="3cf65-120">CommonStates</span></span>|<span data-ttu-id="3cf65-121">컨트롤을 눌렀습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf65-121">The control is pressed.</span></span>|
|<span data-ttu-id="3cf65-122">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="3cf65-122">Disabled</span></span>|<span data-ttu-id="3cf65-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="3cf65-123">CommonStates</span></span>|<span data-ttu-id="3cf65-124">컨트롤이 비활성화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf65-124">The control is disabled.</span></span>|
|<span data-ttu-id="3cf65-125">포커스 있음</span><span class="sxs-lookup"><span data-stu-id="3cf65-125">Focused</span></span>|<span data-ttu-id="3cf65-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="3cf65-126">FocusStates</span></span>|<span data-ttu-id="3cf65-127">컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf65-127">The control has focus.</span></span>|
|<span data-ttu-id="3cf65-128">포커스 없음</span><span class="sxs-lookup"><span data-stu-id="3cf65-128">Unfocused</span></span>|<span data-ttu-id="3cf65-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="3cf65-129">FocusStates</span></span>|<span data-ttu-id="3cf65-130">컨트롤에 포커스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf65-130">The control does not have focus.</span></span>|
|<span data-ttu-id="3cf65-131">선택한 상태</span><span class="sxs-lookup"><span data-stu-id="3cf65-131">Checked</span></span>|<span data-ttu-id="3cf65-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="3cf65-132">CheckStates</span></span>|<span data-ttu-id="3cf65-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>가 `true`인 경우</span><span class="sxs-lookup"><span data-stu-id="3cf65-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|
|<span data-ttu-id="3cf65-134">선택 취소 되어 있음</span><span class="sxs-lookup"><span data-stu-id="3cf65-134">Unchecked</span></span>|<span data-ttu-id="3cf65-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="3cf65-135">CheckStates</span></span>|<span data-ttu-id="3cf65-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>가 `false`인 경우</span><span class="sxs-lookup"><span data-stu-id="3cf65-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|
|<span data-ttu-id="3cf65-137">비활성화</span><span class="sxs-lookup"><span data-stu-id="3cf65-137">Indeterminate</span></span>|<span data-ttu-id="3cf65-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="3cf65-138">CheckStates</span></span>|<span data-ttu-id="3cf65-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A>가 `true`이고 <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>이 `null`인 경우</span><span class="sxs-lookup"><span data-stu-id="3cf65-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|
|<span data-ttu-id="3cf65-140">유효</span><span class="sxs-lookup"><span data-stu-id="3cf65-140">Valid</span></span>|<span data-ttu-id="3cf65-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3cf65-141">ValidationStates</span></span>|<span data-ttu-id="3cf65-142">컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cf65-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="3cf65-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="3cf65-143">InvalidFocused</span></span>|<span data-ttu-id="3cf65-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3cf65-144">ValidationStates</span></span>|<span data-ttu-id="3cf65-145">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf65-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="3cf65-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="3cf65-146">InvalidUnfocused</span></span>|<span data-ttu-id="3cf65-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3cf65-147">ValidationStates</span></span>|<span data-ttu-id="3cf65-148">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="3cf65-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

> [!NOTE]
> <span data-ttu-id="3cf65-149">컨트롤 템플릿에 확정 되지 않은 시각적 상태가 없으면 선택 되지 않은 시각적 상태가 기본 시각적 상태로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cf65-149">If the Indeterminate visual state does not exist in your control template, then the Unchecked visual state will be used as default visual state.</span></span>

## <a name="togglebutton-controltemplate-example"></a><span data-ttu-id="3cf65-150">ToggleButton ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="3cf65-150">ToggleButton ControlTemplate Example</span></span>

<span data-ttu-id="3cf65-151">다음 예제에서는 <xref:System.Windows.Controls.Primitives.ToggleButton> 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3cf65-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#ToggleButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]

<span data-ttu-id="3cf65-152">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf65-152">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="3cf65-153">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3cf65-153">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="3cf65-154">참고자료</span><span class="sxs-lookup"><span data-stu-id="3cf65-154">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="3cf65-155">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="3cf65-155">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="3cf65-156">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="3cf65-156">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="3cf65-157">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="3cf65-157">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="3cf65-158">컨트롤에 대 한 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="3cf65-158">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
