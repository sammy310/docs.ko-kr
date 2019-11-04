---
title: PasswordBox 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], PasswordBox
- templates [WPF], PasswordBox
- ControlTemplate [WPF], PasswordBox
- states [WPF], PasswordBox
- PasswordBox [WPF], styles and templates
- parts [WPF], PasswordBox
ms.assetid: deb52107-959f-4a60-b303-d21a0a933060
ms.openlocfilehash: 227ccbda8d570868258508935a5d95f0f40663ab
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458832"
---
# <a name="passwordbox-styles-and-templates"></a><span data-ttu-id="a118e-102">PasswordBox 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="a118e-102">PasswordBox Styles and Templates</span></span>

<span data-ttu-id="a118e-103">이 항목에서는 <xref:System.Windows.Controls.PasswordBox> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a118e-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.PasswordBox> control.</span></span> <span data-ttu-id="a118e-104">기본 <xref:System.Windows.Controls.ControlTemplate>를 수정 하 여 컨트롤에 고유한 모양을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a118e-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="a118e-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a118e-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>

## <a name="passwordbox-parts"></a><span data-ttu-id="a118e-106">PasswordBox 파트</span><span class="sxs-lookup"><span data-stu-id="a118e-106">PasswordBox Parts</span></span>

<span data-ttu-id="a118e-107">다음 표에서는 <xref:System.Windows.Controls.PasswordBox> 컨트롤의 명명 된 파트를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="a118e-107">The following table lists the named parts for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

|<span data-ttu-id="a118e-108">파트</span><span class="sxs-lookup"><span data-stu-id="a118e-108">Part</span></span>|<span data-ttu-id="a118e-109">Type</span><span class="sxs-lookup"><span data-stu-id="a118e-109">Type</span></span>|<span data-ttu-id="a118e-110">설명</span><span class="sxs-lookup"><span data-stu-id="a118e-110">Description</span></span>|
|-|-|-|
|<span data-ttu-id="a118e-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="a118e-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="a118e-112"><xref:System.Windows.FrameworkElement>포함할 수 있는 시각적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a118e-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="a118e-113"><xref:System.Windows.Controls.PasswordBox> 텍스트가이 요소에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a118e-113">The text of the <xref:System.Windows.Controls.PasswordBox> is displayed in this element.</span></span>|

## <a name="passwordbox-states"></a><span data-ttu-id="a118e-114">PasswordBox 상태</span><span class="sxs-lookup"><span data-stu-id="a118e-114">PasswordBox States</span></span>

<span data-ttu-id="a118e-115">다음 표에서는 <xref:System.Windows.Controls.PasswordBox> 컨트롤의 시각적 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a118e-115">The following table lists the visual states for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

|<span data-ttu-id="a118e-116">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="a118e-116">VisualState Name</span></span>|<span data-ttu-id="a118e-117">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="a118e-117">VisualStateGroup Name</span></span>|<span data-ttu-id="a118e-118">설명</span><span class="sxs-lookup"><span data-stu-id="a118e-118">Description</span></span>|
|-|-|-|
|<span data-ttu-id="a118e-119">보통</span><span class="sxs-lookup"><span data-stu-id="a118e-119">Normal</span></span>|<span data-ttu-id="a118e-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a118e-120">CommonStates</span></span>|<span data-ttu-id="a118e-121">기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="a118e-121">The default state.</span></span>|
|<span data-ttu-id="a118e-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="a118e-122">MouseOver</span></span>|<span data-ttu-id="a118e-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a118e-123">CommonStates</span></span>|<span data-ttu-id="a118e-124">마우스 포인터가 컨트롤 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a118e-124">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="a118e-125">Disabled</span><span class="sxs-lookup"><span data-stu-id="a118e-125">Disabled</span></span>|<span data-ttu-id="a118e-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a118e-126">CommonStates</span></span>|<span data-ttu-id="a118e-127">컨트롤이 비활성화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a118e-127">The control is disabled.</span></span>|
|<span data-ttu-id="a118e-128">포커스 있음</span><span class="sxs-lookup"><span data-stu-id="a118e-128">Focused</span></span>|<span data-ttu-id="a118e-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="a118e-129">FocusStates</span></span>|<span data-ttu-id="a118e-130">컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a118e-130">The control has focus.</span></span>|
|<span data-ttu-id="a118e-131">포커스 없음</span><span class="sxs-lookup"><span data-stu-id="a118e-131">Unfocused</span></span>|<span data-ttu-id="a118e-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="a118e-132">FocusStates</span></span>|<span data-ttu-id="a118e-133">컨트롤에 포커스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a118e-133">The control does not have focus.</span></span>|
|<span data-ttu-id="a118e-134">유효</span><span class="sxs-lookup"><span data-stu-id="a118e-134">Valid</span></span>|<span data-ttu-id="a118e-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a118e-135">ValidationStates</span></span>|<span data-ttu-id="a118e-136">컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="a118e-136">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="a118e-137">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a118e-137">InvalidFocused</span></span>|<span data-ttu-id="a118e-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a118e-138">ValidationStates</span></span>|<span data-ttu-id="a118e-139">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a118e-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="a118e-140">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a118e-140">InvalidUnfocused</span></span>|<span data-ttu-id="a118e-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a118e-141">ValidationStates</span></span>|<span data-ttu-id="a118e-142">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="a118e-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="passwordbox-controltemplate-example"></a><span data-ttu-id="a118e-143">PasswordBox ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="a118e-143">PasswordBox ControlTemplate Example</span></span>

<span data-ttu-id="a118e-144">다음 예제에서는 <xref:System.Windows.Controls.PasswordBox> 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a118e-144">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

[!code-xaml[ControlTemplateExamples#PasswordBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#passwordbox)]

<span data-ttu-id="a118e-145">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a118e-145">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="a118e-146">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a118e-146">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="a118e-147">참조</span><span class="sxs-lookup"><span data-stu-id="a118e-147">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="a118e-148">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="a118e-148">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="a118e-149">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="a118e-149">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="a118e-150">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="a118e-150">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="a118e-151">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="a118e-151">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
