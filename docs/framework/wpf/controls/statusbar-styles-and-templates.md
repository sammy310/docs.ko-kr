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
ms.openlocfilehash: 64b5b66f7f32ea31b51b4da990ceede4078c27cf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790964"
---
# <a name="statusbar-styles-and-templates"></a><span data-ttu-id="d7f43-102">StatusBar 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="d7f43-102">StatusBar Styles and Templates</span></span>
<span data-ttu-id="d7f43-103">이 항목에서는 스타일 및 템플릿에 대해 설명 합니다 <xref:System.Windows.Controls.Primitives.StatusBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f43-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span> <span data-ttu-id="d7f43-104">기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7f43-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="d7f43-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7f43-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="statusbar-parts"></a><span data-ttu-id="d7f43-106">상태 표시줄 파트</span><span class="sxs-lookup"><span data-stu-id="d7f43-106">StatusBar Parts</span></span>  
 <span data-ttu-id="d7f43-107"><xref:System.Windows.Controls.Primitives.StatusBar> 컨트롤에 명명된 된 파트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7f43-107">The <xref:System.Windows.Controls.Primitives.StatusBar> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="d7f43-108">상태 표시줄 상태</span><span class="sxs-lookup"><span data-stu-id="d7f43-108">StatusBar States</span></span>  
 <span data-ttu-id="d7f43-109">다음 표에서 대 한 시각적 상태를 <xref:System.Windows.Controls.Primitives.StatusBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f43-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
|<span data-ttu-id="d7f43-110">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="d7f43-110">VisualState Name</span></span>|<span data-ttu-id="d7f43-111">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="d7f43-111">VisualStateGroup Name</span></span>|<span data-ttu-id="d7f43-112">설명</span><span class="sxs-lookup"><span data-stu-id="d7f43-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="d7f43-113">유효</span><span class="sxs-lookup"><span data-stu-id="d7f43-113">Valid</span></span>|<span data-ttu-id="d7f43-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d7f43-114">ValidationStates</span></span>|<span data-ttu-id="d7f43-115">컨트롤에서 사용 된 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f43-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="d7f43-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="d7f43-116">InvalidFocused</span></span>|<span data-ttu-id="d7f43-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d7f43-117">ValidationStates</span></span>|<span data-ttu-id="d7f43-118">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7f43-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="d7f43-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="d7f43-119">InvalidUnfocused</span></span>|<span data-ttu-id="d7f43-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d7f43-120">ValidationStates</span></span>|<span data-ttu-id="d7f43-121">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f43-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbaritem-parts"></a><span data-ttu-id="d7f43-122">StatusBarItem 파트</span><span class="sxs-lookup"><span data-stu-id="d7f43-122">StatusBarItem Parts</span></span>  
 <span data-ttu-id="d7f43-123"><xref:System.Windows.Controls.Primitives.StatusBarItem> 컨트롤에 명명된 된 파트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7f43-123">The <xref:System.Windows.Controls.Primitives.StatusBarItem> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="d7f43-124">상태 표시줄 상태</span><span class="sxs-lookup"><span data-stu-id="d7f43-124">StatusBar States</span></span>  
 <span data-ttu-id="d7f43-125">다음 표에서 대 한 시각적 상태를 <xref:System.Windows.Controls.Primitives.StatusBarItem> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f43-125">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span></span>  
  
|<span data-ttu-id="d7f43-126">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="d7f43-126">VisualState Name</span></span>|<span data-ttu-id="d7f43-127">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="d7f43-127">VisualStateGroup Name</span></span>|<span data-ttu-id="d7f43-128">설명</span><span class="sxs-lookup"><span data-stu-id="d7f43-128">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="d7f43-129">유효</span><span class="sxs-lookup"><span data-stu-id="d7f43-129">Valid</span></span>|<span data-ttu-id="d7f43-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d7f43-130">ValidationStates</span></span>|<span data-ttu-id="d7f43-131">컨트롤에서 사용 된 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f43-131">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="d7f43-132">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="d7f43-132">InvalidFocused</span></span>|<span data-ttu-id="d7f43-133">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d7f43-133">ValidationStates</span></span>|<span data-ttu-id="d7f43-134">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7f43-134">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="d7f43-135">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="d7f43-135">InvalidUnfocused</span></span>|<span data-ttu-id="d7f43-136">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d7f43-136">ValidationStates</span></span>|<span data-ttu-id="d7f43-137">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f43-137">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbar-controltemplate-example"></a><span data-ttu-id="d7f43-138">StatusBar ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="d7f43-138">StatusBar ControlTemplate Example</span></span>  
 <span data-ttu-id="d7f43-139">다음 예제에서는 정의 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.Primitives.StatusBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f43-139">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#StatusBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/statusbar.xaml#statusbar)]  
  
 <span data-ttu-id="d7f43-140"><xref:System.Windows.Controls.ControlTemplate> 다음 리소스 중 하나 이상을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f43-140">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="d7f43-141">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7f43-141">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7f43-142">참고자료</span><span class="sxs-lookup"><span data-stu-id="d7f43-142">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="d7f43-143">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="d7f43-143">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="d7f43-144">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="d7f43-144">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="d7f43-145">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="d7f43-145">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="d7f43-146">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="d7f43-146">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
