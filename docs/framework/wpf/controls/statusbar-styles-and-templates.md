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
ms.openlocfilehash: b1dd575d58571b845fc849ca432ad440d1ce3ec4
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458267"
---
# <a name="statusbar-styles-and-templates"></a><span data-ttu-id="40de2-102">StatusBar 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="40de2-102">StatusBar Styles and Templates</span></span>
<span data-ttu-id="40de2-103">이 항목에서는 <xref:System.Windows.Controls.Primitives.StatusBar> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="40de2-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span> <span data-ttu-id="40de2-104">기본 <xref:System.Windows.Controls.ControlTemplate>를 수정 하 여 컨트롤에 고유한 모양을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40de2-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="40de2-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="40de2-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="statusbar-parts"></a><span data-ttu-id="40de2-106">StatusBar 파트</span><span class="sxs-lookup"><span data-stu-id="40de2-106">StatusBar Parts</span></span>  
 <span data-ttu-id="40de2-107"><xref:System.Windows.Controls.Primitives.StatusBar> 컨트롤에는 명명 된 파트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="40de2-107">The <xref:System.Windows.Controls.Primitives.StatusBar> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="40de2-108">상태 표시줄 상태</span><span class="sxs-lookup"><span data-stu-id="40de2-108">StatusBar States</span></span>  
 <span data-ttu-id="40de2-109">다음 표에서는 <xref:System.Windows.Controls.Primitives.StatusBar> 컨트롤의 시각적 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="40de2-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
|<span data-ttu-id="40de2-110">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="40de2-110">VisualState Name</span></span>|<span data-ttu-id="40de2-111">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="40de2-111">VisualStateGroup Name</span></span>|<span data-ttu-id="40de2-112">설명</span><span class="sxs-lookup"><span data-stu-id="40de2-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="40de2-113">유효</span><span class="sxs-lookup"><span data-stu-id="40de2-113">Valid</span></span>|<span data-ttu-id="40de2-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="40de2-114">ValidationStates</span></span>|<span data-ttu-id="40de2-115">컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="40de2-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="40de2-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="40de2-116">InvalidFocused</span></span>|<span data-ttu-id="40de2-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="40de2-117">ValidationStates</span></span>|<span data-ttu-id="40de2-118">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40de2-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="40de2-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="40de2-119">InvalidUnfocused</span></span>|<span data-ttu-id="40de2-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="40de2-120">ValidationStates</span></span>|<span data-ttu-id="40de2-121">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="40de2-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbaritem-parts"></a><span data-ttu-id="40de2-122">StatusBarItem 파트</span><span class="sxs-lookup"><span data-stu-id="40de2-122">StatusBarItem Parts</span></span>  
 <span data-ttu-id="40de2-123"><xref:System.Windows.Controls.Primitives.StatusBarItem> 컨트롤에는 명명 된 파트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="40de2-123">The <xref:System.Windows.Controls.Primitives.StatusBarItem> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="40de2-124">상태 표시줄 상태</span><span class="sxs-lookup"><span data-stu-id="40de2-124">StatusBar States</span></span>  
 <span data-ttu-id="40de2-125">다음 표에서는 <xref:System.Windows.Controls.Primitives.StatusBarItem> 컨트롤의 시각적 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="40de2-125">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span></span>  
  
|<span data-ttu-id="40de2-126">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="40de2-126">VisualState Name</span></span>|<span data-ttu-id="40de2-127">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="40de2-127">VisualStateGroup Name</span></span>|<span data-ttu-id="40de2-128">설명</span><span class="sxs-lookup"><span data-stu-id="40de2-128">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="40de2-129">유효</span><span class="sxs-lookup"><span data-stu-id="40de2-129">Valid</span></span>|<span data-ttu-id="40de2-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="40de2-130">ValidationStates</span></span>|<span data-ttu-id="40de2-131">컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="40de2-131">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="40de2-132">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="40de2-132">InvalidFocused</span></span>|<span data-ttu-id="40de2-133">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="40de2-133">ValidationStates</span></span>|<span data-ttu-id="40de2-134">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40de2-134">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="40de2-135">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="40de2-135">InvalidUnfocused</span></span>|<span data-ttu-id="40de2-136">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="40de2-136">ValidationStates</span></span>|<span data-ttu-id="40de2-137">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="40de2-137">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbar-controltemplate-example"></a><span data-ttu-id="40de2-138">StatusBar ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="40de2-138">StatusBar ControlTemplate Example</span></span>  
 <span data-ttu-id="40de2-139">다음 예제에서는 <xref:System.Windows.Controls.Primitives.StatusBar> 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="40de2-139">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#StatusBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/statusbar.xaml#statusbar)]  
  
 <span data-ttu-id="40de2-140"><xref:System.Windows.Controls.ControlTemplate>는 다음 리소스 중 하나 이상을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="40de2-140">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="40de2-141">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="40de2-141">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40de2-142">참조</span><span class="sxs-lookup"><span data-stu-id="40de2-142">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="40de2-143">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="40de2-143">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="40de2-144">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="40de2-144">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="40de2-145">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="40de2-145">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="40de2-146">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="40de2-146">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
