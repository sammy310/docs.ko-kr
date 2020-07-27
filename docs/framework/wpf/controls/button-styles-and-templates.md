---
title: Button 스타일 및 템플릿
description: Windows Presentation Foundation Button 컨트롤의 스타일 및 템플릿에 대해 알아봅니다. ControlTemplate를 수정 하 여 컨트롤에 고유한 모양을 제공 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Button
- parts [WPF], Button
- styles [WPF], Button
- Button [WPF], styles and templates
- templates [WPF], Button
- ControlTemplate [WPF], Button
ms.assetid: e223c759-f8c4-4717-acfb-b1e40bdf5f3b
ms.openlocfilehash: 11509adeef397f26eb040e6e98d0edb333b2515f
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166270"
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="20235-104">Button 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="20235-104">Button Styles and Templates</span></span>
<span data-ttu-id="20235-105">이 항목에서는 컨트롤의 스타일 및 템플릿에 대해 설명 합니다 <xref:System.Windows.Controls.Button> .</span><span class="sxs-lookup"><span data-stu-id="20235-105">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="20235-106">기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20235-106">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="20235-107">자세한 내용은 [컨트롤에 대 한 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="20235-107">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="20235-108">단추 파트</span><span class="sxs-lookup"><span data-stu-id="20235-108">Button Parts</span></span>  
 <span data-ttu-id="20235-109"><xref:System.Windows.Controls.Button>컨트롤에 명명 된 파트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="20235-109">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="20235-110">단추 상태</span><span class="sxs-lookup"><span data-stu-id="20235-110">Button States</span></span>  
 <span data-ttu-id="20235-111">다음 표에서는 컨트롤의 시각적 상태를 보여 줍니다 <xref:System.Windows.Controls.Button> .</span><span class="sxs-lookup"><span data-stu-id="20235-111">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="20235-112">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="20235-112">VisualState Name</span></span>|<span data-ttu-id="20235-113">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="20235-113">VisualStateGroup Name</span></span>|<span data-ttu-id="20235-114">설명</span><span class="sxs-lookup"><span data-stu-id="20235-114">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="20235-115">보통</span><span class="sxs-lookup"><span data-stu-id="20235-115">Normal</span></span>|<span data-ttu-id="20235-116">CommonStates</span><span class="sxs-lookup"><span data-stu-id="20235-116">CommonStates</span></span>|<span data-ttu-id="20235-117">기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="20235-117">The default state.</span></span>|  
|<span data-ttu-id="20235-118">MouseOver</span><span class="sxs-lookup"><span data-stu-id="20235-118">MouseOver</span></span>|<span data-ttu-id="20235-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="20235-119">CommonStates</span></span>|<span data-ttu-id="20235-120">마우스 포인터가 컨트롤 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20235-120">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="20235-121">누름</span><span class="sxs-lookup"><span data-stu-id="20235-121">Pressed</span></span>|<span data-ttu-id="20235-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="20235-122">CommonStates</span></span>|<span data-ttu-id="20235-123">컨트롤을 눌렀습니다.</span><span class="sxs-lookup"><span data-stu-id="20235-123">The control is pressed.</span></span>|  
|<span data-ttu-id="20235-124">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="20235-124">Disabled</span></span>|<span data-ttu-id="20235-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="20235-125">CommonStates</span></span>|<span data-ttu-id="20235-126">컨트롤이 비활성화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="20235-126">The control is disabled.</span></span>|  
|<span data-ttu-id="20235-127">포커스 있음</span><span class="sxs-lookup"><span data-stu-id="20235-127">Focused</span></span>|<span data-ttu-id="20235-128">FocusStates</span><span class="sxs-lookup"><span data-stu-id="20235-128">FocusStates</span></span>|<span data-ttu-id="20235-129">컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20235-129">The control has focus.</span></span>|  
|<span data-ttu-id="20235-130">포커스 없음</span><span class="sxs-lookup"><span data-stu-id="20235-130">Unfocused</span></span>|<span data-ttu-id="20235-131">FocusStates</span><span class="sxs-lookup"><span data-stu-id="20235-131">FocusStates</span></span>|<span data-ttu-id="20235-132">컨트롤에 포커스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="20235-132">The control does not have focus.</span></span>|  
|<span data-ttu-id="20235-133">Valid</span><span class="sxs-lookup"><span data-stu-id="20235-133">Valid</span></span>|<span data-ttu-id="20235-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="20235-134">ValidationStates</span></span>|<span data-ttu-id="20235-135">컨트롤은 클래스를 사용 하 <xref:System.Windows.Controls.Validation> 고 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="20235-135">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="20235-136">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="20235-136">InvalidFocused</span></span>|<span data-ttu-id="20235-137">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="20235-137">ValidationStates</span></span>|<span data-ttu-id="20235-138"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>연결 된 속성이이 `true` 고 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20235-138">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="20235-139">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="20235-139">InvalidUnfocused</span></span>|<span data-ttu-id="20235-140">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="20235-140">ValidationStates</span></span>|<span data-ttu-id="20235-141"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>연결 된 속성이이 `true` 고 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="20235-141">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="20235-142">Button ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="20235-142">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="20235-143">다음 예제에서는 <xref:System.Windows.Controls.ControlTemplate> 컨트롤에 대 한을 정의 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.Button> .</span><span class="sxs-lookup"><span data-stu-id="20235-143">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="20235-144">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="20235-144">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="20235-145">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="20235-145">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20235-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20235-146">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="20235-147">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="20235-147">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="20235-148">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="20235-148">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="20235-149">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="20235-149">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="20235-150">컨트롤의 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="20235-150">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
