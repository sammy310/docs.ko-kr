---
title: Button 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Button
- parts [WPF], Button
- styles [WPF], Button
- Button [WPF], styles and templates
- templates [WPF], Button
- ControlTemplate [WPF], Button
ms.assetid: e223c759-f8c4-4717-acfb-b1e40bdf5f3b
ms.openlocfilehash: ef9f85848ebdda9dc4ae15d0f54847eacd46e24d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283577"
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="d07c3-102">Button 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="d07c3-102">Button Styles and Templates</span></span>
<span data-ttu-id="d07c3-103">이 항목에서는 <xref:System.Windows.Controls.Button> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d07c3-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="d07c3-104">기본 <xref:System.Windows.Controls.ControlTemplate>를 수정 하 여 컨트롤에 고유한 모양을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d07c3-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="d07c3-105">자세한 내용은 [컨트롤에 대 한 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d07c3-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="d07c3-106">단추 파트</span><span class="sxs-lookup"><span data-stu-id="d07c3-106">Button Parts</span></span>  
 <span data-ttu-id="d07c3-107"><xref:System.Windows.Controls.Button> 컨트롤에는 명명 된 파트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d07c3-107">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="d07c3-108">단추 상태</span><span class="sxs-lookup"><span data-stu-id="d07c3-108">Button States</span></span>  
 <span data-ttu-id="d07c3-109">다음 표에서는 <xref:System.Windows.Controls.Button> 컨트롤의 시각적 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d07c3-109">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="d07c3-110">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="d07c3-110">VisualState Name</span></span>|<span data-ttu-id="d07c3-111">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="d07c3-111">VisualStateGroup Name</span></span>|<span data-ttu-id="d07c3-112">설명</span><span class="sxs-lookup"><span data-stu-id="d07c3-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="d07c3-113">보통</span><span class="sxs-lookup"><span data-stu-id="d07c3-113">Normal</span></span>|<span data-ttu-id="d07c3-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d07c3-114">CommonStates</span></span>|<span data-ttu-id="d07c3-115">기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="d07c3-115">The default state.</span></span>|  
|<span data-ttu-id="d07c3-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="d07c3-116">MouseOver</span></span>|<span data-ttu-id="d07c3-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d07c3-117">CommonStates</span></span>|<span data-ttu-id="d07c3-118">마우스 포인터가 컨트롤 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d07c3-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="d07c3-119">누름</span><span class="sxs-lookup"><span data-stu-id="d07c3-119">Pressed</span></span>|<span data-ttu-id="d07c3-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d07c3-120">CommonStates</span></span>|<span data-ttu-id="d07c3-121">컨트롤을 눌렀습니다.</span><span class="sxs-lookup"><span data-stu-id="d07c3-121">The control is pressed.</span></span>|  
|<span data-ttu-id="d07c3-122">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="d07c3-122">Disabled</span></span>|<span data-ttu-id="d07c3-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d07c3-123">CommonStates</span></span>|<span data-ttu-id="d07c3-124">컨트롤이 비활성화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d07c3-124">The control is disabled.</span></span>|  
|<span data-ttu-id="d07c3-125">포커스 있음</span><span class="sxs-lookup"><span data-stu-id="d07c3-125">Focused</span></span>|<span data-ttu-id="d07c3-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="d07c3-126">FocusStates</span></span>|<span data-ttu-id="d07c3-127">컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d07c3-127">The control has focus.</span></span>|  
|<span data-ttu-id="d07c3-128">포커스 없음</span><span class="sxs-lookup"><span data-stu-id="d07c3-128">Unfocused</span></span>|<span data-ttu-id="d07c3-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="d07c3-129">FocusStates</span></span>|<span data-ttu-id="d07c3-130">컨트롤에 포커스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d07c3-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="d07c3-131">Valid</span><span class="sxs-lookup"><span data-stu-id="d07c3-131">Valid</span></span>|<span data-ttu-id="d07c3-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d07c3-132">ValidationStates</span></span>|<span data-ttu-id="d07c3-133">컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="d07c3-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="d07c3-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="d07c3-134">InvalidFocused</span></span>|<span data-ttu-id="d07c3-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d07c3-135">ValidationStates</span></span>|<span data-ttu-id="d07c3-136">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 고 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d07c3-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="d07c3-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="d07c3-137">InvalidUnfocused</span></span>|<span data-ttu-id="d07c3-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d07c3-138">ValidationStates</span></span>|<span data-ttu-id="d07c3-139">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 고 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="d07c3-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="d07c3-140">Button ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="d07c3-140">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="d07c3-141">다음 예제에서는 <xref:System.Windows.Controls.Button> 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d07c3-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="d07c3-142">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d07c3-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="d07c3-143">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d07c3-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d07c3-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d07c3-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="d07c3-145">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="d07c3-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="d07c3-146">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="d07c3-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="d07c3-147">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="d07c3-147">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="d07c3-148">컨트롤에 대 한 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="d07c3-148">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
