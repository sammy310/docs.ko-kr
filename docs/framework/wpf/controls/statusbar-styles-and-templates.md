---
title: StatusBar 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], StatusBar
- styles [WPF], StatusBar
- templates [WPF], StatusBar
- states [WPF], StatusBar
- parts [WPF], StatusBar
- StatusBar [WPF], styles and templates
ms.assetid: 9f5e1c25-81eb-4756-a0ac-d9e1fbe33ee2
ms.openlocfilehash: 843c9003edbe94115719a63a968eda3833515a85
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283368"
---
# <a name="statusbar-styles-and-templates"></a><span data-ttu-id="735b0-102">StatusBar 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="735b0-102">StatusBar Styles and Templates</span></span>
<span data-ttu-id="735b0-103">이 항목에서는 <xref:System.Windows.Controls.Primitives.StatusBar> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="735b0-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span> <span data-ttu-id="735b0-104">기본 <xref:System.Windows.Controls.ControlTemplate>를 수정 하 여 컨트롤에 고유한 모양을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="735b0-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="735b0-105">자세한 내용은 [컨트롤에 대 한 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="735b0-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="statusbar-parts"></a><span data-ttu-id="735b0-106">StatusBar 파트</span><span class="sxs-lookup"><span data-stu-id="735b0-106">StatusBar Parts</span></span>  
 <span data-ttu-id="735b0-107"><xref:System.Windows.Controls.Primitives.StatusBar> 컨트롤에는 명명 된 파트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="735b0-107">The <xref:System.Windows.Controls.Primitives.StatusBar> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="735b0-108">상태 표시줄 상태</span><span class="sxs-lookup"><span data-stu-id="735b0-108">StatusBar States</span></span>  
 <span data-ttu-id="735b0-109">다음 표에서는 <xref:System.Windows.Controls.Primitives.StatusBar> 컨트롤의 시각적 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="735b0-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
|<span data-ttu-id="735b0-110">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="735b0-110">VisualState Name</span></span>|<span data-ttu-id="735b0-111">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="735b0-111">VisualStateGroup Name</span></span>|<span data-ttu-id="735b0-112">설명</span><span class="sxs-lookup"><span data-stu-id="735b0-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="735b0-113">유효</span><span class="sxs-lookup"><span data-stu-id="735b0-113">Valid</span></span>|<span data-ttu-id="735b0-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="735b0-114">ValidationStates</span></span>|<span data-ttu-id="735b0-115">컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="735b0-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="735b0-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="735b0-116">InvalidFocused</span></span>|<span data-ttu-id="735b0-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="735b0-117">ValidationStates</span></span>|<span data-ttu-id="735b0-118">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="735b0-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="735b0-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="735b0-119">InvalidUnfocused</span></span>|<span data-ttu-id="735b0-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="735b0-120">ValidationStates</span></span>|<span data-ttu-id="735b0-121">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="735b0-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbaritem-parts"></a><span data-ttu-id="735b0-122">StatusBarItem 파트</span><span class="sxs-lookup"><span data-stu-id="735b0-122">StatusBarItem Parts</span></span>  
 <span data-ttu-id="735b0-123"><xref:System.Windows.Controls.Primitives.StatusBarItem> 컨트롤에는 명명 된 파트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="735b0-123">The <xref:System.Windows.Controls.Primitives.StatusBarItem> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="735b0-124">상태 표시줄 상태</span><span class="sxs-lookup"><span data-stu-id="735b0-124">StatusBar States</span></span>  
 <span data-ttu-id="735b0-125">다음 표에서는 <xref:System.Windows.Controls.Primitives.StatusBarItem> 컨트롤의 시각적 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="735b0-125">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span></span>  
  
|<span data-ttu-id="735b0-126">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="735b0-126">VisualState Name</span></span>|<span data-ttu-id="735b0-127">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="735b0-127">VisualStateGroup Name</span></span>|<span data-ttu-id="735b0-128">설명</span><span class="sxs-lookup"><span data-stu-id="735b0-128">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="735b0-129">유효</span><span class="sxs-lookup"><span data-stu-id="735b0-129">Valid</span></span>|<span data-ttu-id="735b0-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="735b0-130">ValidationStates</span></span>|<span data-ttu-id="735b0-131">컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="735b0-131">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="735b0-132">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="735b0-132">InvalidFocused</span></span>|<span data-ttu-id="735b0-133">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="735b0-133">ValidationStates</span></span>|<span data-ttu-id="735b0-134">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="735b0-134">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="735b0-135">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="735b0-135">InvalidUnfocused</span></span>|<span data-ttu-id="735b0-136">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="735b0-136">ValidationStates</span></span>|<span data-ttu-id="735b0-137">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="735b0-137">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbar-controltemplate-example"></a><span data-ttu-id="735b0-138">StatusBar ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="735b0-138">StatusBar ControlTemplate Example</span></span>  
 <span data-ttu-id="735b0-139">다음 예제에서는 <xref:System.Windows.Controls.Primitives.StatusBar> 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="735b0-139">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#StatusBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/statusbar.xaml#statusbar)]  
  
 <span data-ttu-id="735b0-140"><xref:System.Windows.Controls.ControlTemplate>는 다음 리소스 중 하나 이상을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="735b0-140">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="735b0-141">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="735b0-141">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="735b0-142">참고자료</span><span class="sxs-lookup"><span data-stu-id="735b0-142">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="735b0-143">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="735b0-143">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="735b0-144">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="735b0-144">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="735b0-145">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="735b0-145">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="735b0-146">컨트롤에 대 한 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="735b0-146">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
