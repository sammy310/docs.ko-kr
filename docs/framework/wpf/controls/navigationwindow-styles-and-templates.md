---
title: NavigationWindow 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], NavigationWindow
- NavigationWindow [WPF], styles and templates
- ControlTemplate [WPF], NavigationWindow
- parts [WPF], NavigationWindow
- styles [WPF], NavigationWindow
- templates [WPF], NavigationWindow
ms.assetid: 3656055e-3222-43c8-b868-fd0c90cc31a3
ms.openlocfilehash: 4aae14299b3959e7d2122991954cc62505d2a19e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460196"
---
# <a name="navigationwindow-styles-and-templates"></a><span data-ttu-id="37793-102">NavigationWindow 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="37793-102">NavigationWindow Styles and Templates</span></span>
<span data-ttu-id="37793-103">이 항목에서는 <xref:System.Windows.Navigation.NavigationWindow> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="37793-103">This topic describes the styles and templates for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span> <span data-ttu-id="37793-104">기본 <xref:System.Windows.Controls.ControlTemplate>를 수정 하 여 컨트롤에 고유한 모양을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37793-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="37793-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="37793-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="navigationwindow-parts"></a><span data-ttu-id="37793-106">NavigationWindow 파트</span><span class="sxs-lookup"><span data-stu-id="37793-106">NavigationWindow Parts</span></span>  
 <span data-ttu-id="37793-107">다음 표에서는 <xref:System.Windows.Navigation.NavigationWindow> 컨트롤의 명명 된 파트를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="37793-107">The following table lists the named parts for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="37793-108">파트</span><span class="sxs-lookup"><span data-stu-id="37793-108">Part</span></span>|<span data-ttu-id="37793-109">Type</span><span class="sxs-lookup"><span data-stu-id="37793-109">Type</span></span>|<span data-ttu-id="37793-110">설명</span><span class="sxs-lookup"><span data-stu-id="37793-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="37793-111">PART_NavWinCP</span><span class="sxs-lookup"><span data-stu-id="37793-111">PART_NavWinCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="37793-112">콘텐츠의 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="37793-112">The area for the content.</span></span>|  
  
## <a name="navigationwindow-states"></a><span data-ttu-id="37793-113">NavigationWindow 상태</span><span class="sxs-lookup"><span data-stu-id="37793-113">NavigationWindow States</span></span>  
 <span data-ttu-id="37793-114">다음 표에서는 <xref:System.Windows.Navigation.NavigationWindow> 컨트롤의 시각적 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="37793-114">The following table lists the visual states for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="37793-115">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="37793-115">VisualState Name</span></span>|<span data-ttu-id="37793-116">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="37793-116">VisualStateGroup Name</span></span>|<span data-ttu-id="37793-117">설명</span><span class="sxs-lookup"><span data-stu-id="37793-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="37793-118">유효</span><span class="sxs-lookup"><span data-stu-id="37793-118">Valid</span></span>|<span data-ttu-id="37793-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="37793-119">ValidationStates</span></span>|<span data-ttu-id="37793-120">컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="37793-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="37793-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="37793-121">InvalidFocused</span></span>|<span data-ttu-id="37793-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="37793-122">ValidationStates</span></span>|<span data-ttu-id="37793-123">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37793-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="37793-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="37793-124">InvalidUnfocused</span></span>|<span data-ttu-id="37793-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="37793-125">ValidationStates</span></span>|<span data-ttu-id="37793-126">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="37793-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="navigationwindow-controltemplate-example"></a><span data-ttu-id="37793-127">NavigationWindow ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="37793-127">NavigationWindow ControlTemplate Example</span></span>  
 <span data-ttu-id="37793-128">이 예제에서는 기본적으로 <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Controls.ControlTemplate>에 정의 된 모든 요소를 포함 하지만 특정 값은 예제로 간주 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37793-128">Although this example contains all of the elements that are defined in the <xref:System.Windows.Controls.ControlTemplate> of a <xref:System.Windows.Navigation.NavigationWindow> by default, the specific values should be thought of as examples.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#NavigationWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/navigationwindow.xaml#navigationwindow)]  
  
 <span data-ttu-id="37793-129">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="37793-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="37793-130">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="37793-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37793-131">참조</span><span class="sxs-lookup"><span data-stu-id="37793-131">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="37793-132">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="37793-132">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="37793-133">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="37793-133">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="37793-134">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="37793-134">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="37793-135">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="37793-135">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
