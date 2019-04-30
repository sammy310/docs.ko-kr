---
title: RepeatButton 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatButton [WPF], styles and templates
- styles [WPF], RepeatButton
- templates [WPF], RepeatButton
- parts [WPF], RepeatButton
- ControlTemplate [WPF], RepeatButton
- states [WPF], RepeatButton
ms.assetid: fd340743-f44f-4990-9077-085301469670
ms.openlocfilehash: 86f212326bc707e4b07b8cab8d9a95d4f6ef8920
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053317"
---
# <a name="repeatbutton-styles-and-templates"></a><span data-ttu-id="df401-102">RepeatButton 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="df401-102">RepeatButton Styles and Templates</span></span>

<span data-ttu-id="df401-103">이 항목에서는 스타일 및 템플릿에 대해 설명 합니다 <xref:System.Windows.Controls.Primitives.RepeatButton> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="df401-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span> <span data-ttu-id="df401-104">기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df401-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="df401-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df401-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>

## <a name="repeatbutton-parts"></a><span data-ttu-id="df401-106">RepeatButton 파트</span><span class="sxs-lookup"><span data-stu-id="df401-106">RepeatButton Parts</span></span>

<span data-ttu-id="df401-107"><xref:System.Windows.Controls.Primitives.RepeatButton> 컨트롤에 명명된 된 파트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df401-107">The <xref:System.Windows.Controls.Primitives.RepeatButton> control does not have any named parts.</span></span>

## <a name="repeatbutton-states"></a><span data-ttu-id="df401-108">RepeatButton 상태</span><span class="sxs-lookup"><span data-stu-id="df401-108">RepeatButton States</span></span>

<span data-ttu-id="df401-109">다음 표에서 대 한 시각적 상태를 <xref:System.Windows.Controls.Primitives.RepeatButton> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="df401-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

|<span data-ttu-id="df401-110">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="df401-110">VisualState Name</span></span>|<span data-ttu-id="df401-111">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="df401-111">VisualStateGroup Name</span></span>|<span data-ttu-id="df401-112">설명</span><span class="sxs-lookup"><span data-stu-id="df401-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="df401-113">보통</span><span class="sxs-lookup"><span data-stu-id="df401-113">Normal</span></span>|<span data-ttu-id="df401-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="df401-114">CommonStates</span></span>|<span data-ttu-id="df401-115">기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="df401-115">The default state.</span></span>|
|<span data-ttu-id="df401-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="df401-116">MouseOver</span></span>|<span data-ttu-id="df401-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="df401-117">CommonStates</span></span>|<span data-ttu-id="df401-118">마우스 포인터가 컨트롤 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df401-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="df401-119">누름</span><span class="sxs-lookup"><span data-stu-id="df401-119">Pressed</span></span>|<span data-ttu-id="df401-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="df401-120">CommonStates</span></span>|<span data-ttu-id="df401-121">컨트롤을 눌렀습니다.</span><span class="sxs-lookup"><span data-stu-id="df401-121">The control is pressed.</span></span>|
|<span data-ttu-id="df401-122">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="df401-122">Disabled</span></span>|<span data-ttu-id="df401-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="df401-123">CommonStates</span></span>|<span data-ttu-id="df401-124">컨트롤이 비활성화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="df401-124">The control is disabled.</span></span>|
|<span data-ttu-id="df401-125">포커스 있음</span><span class="sxs-lookup"><span data-stu-id="df401-125">Focused</span></span>|<span data-ttu-id="df401-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="df401-126">FocusStates</span></span>|<span data-ttu-id="df401-127">컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df401-127">The control has focus.</span></span>|
|<span data-ttu-id="df401-128">포커스 없음</span><span class="sxs-lookup"><span data-stu-id="df401-128">Unfocused</span></span>|<span data-ttu-id="df401-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="df401-129">FocusStates</span></span>|<span data-ttu-id="df401-130">컨트롤에 포커스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df401-130">The control does not have focus.</span></span>|
|<span data-ttu-id="df401-131">유효</span><span class="sxs-lookup"><span data-stu-id="df401-131">Valid</span></span>|<span data-ttu-id="df401-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="df401-132">ValidationStates</span></span>|<span data-ttu-id="df401-133">컨트롤에서 사용 된 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="df401-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="df401-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="df401-134">InvalidFocused</span></span>|<span data-ttu-id="df401-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="df401-135">ValidationStates</span></span>|<span data-ttu-id="df401-136">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df401-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="df401-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="df401-137">InvalidUnfocused</span></span>|<span data-ttu-id="df401-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="df401-138">ValidationStates</span></span>|<span data-ttu-id="df401-139">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="df401-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="repeatbutton-controltemplate-example"></a><span data-ttu-id="df401-140">RepeatButton ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="df401-140">RepeatButton ControlTemplate Example</span></span>

<span data-ttu-id="df401-141">다음 예제에서는 정의 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.Primitives.RepeatButton> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="df401-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#RepeatButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#repeatbutton)]

<span data-ttu-id="df401-142">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="df401-142">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="df401-143">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df401-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="df401-144">참고자료</span><span class="sxs-lookup"><span data-stu-id="df401-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="df401-145">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="df401-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="df401-146">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="df401-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="df401-147">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="df401-147">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="df401-148">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="df401-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
