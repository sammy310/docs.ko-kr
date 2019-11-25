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
ms.openlocfilehash: 5cc504956ce036505ac9261ea1438c7881fa2790
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283485"
---
# <a name="navigationwindow-styles-and-templates"></a><span data-ttu-id="14af4-102">NavigationWindow 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="14af4-102">NavigationWindow Styles and Templates</span></span>
<span data-ttu-id="14af4-103">이 항목에서는 <xref:System.Windows.Navigation.NavigationWindow> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="14af4-103">This topic describes the styles and templates for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span> <span data-ttu-id="14af4-104">기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14af4-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="14af4-105">자세한 내용은 [컨트롤에 대 한 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="14af4-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="navigationwindow-parts"></a><span data-ttu-id="14af4-106">NavigationWindow 파트</span><span class="sxs-lookup"><span data-stu-id="14af4-106">NavigationWindow Parts</span></span>  
 <span data-ttu-id="14af4-107">다음 표에서는 <xref:System.Windows.Navigation.NavigationWindow> 컨트롤의 명명 된 파트를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="14af4-107">The following table lists the named parts for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="14af4-108">부분</span><span class="sxs-lookup"><span data-stu-id="14af4-108">Part</span></span>|<span data-ttu-id="14af4-109">형식</span><span class="sxs-lookup"><span data-stu-id="14af4-109">Type</span></span>|<span data-ttu-id="14af4-110">설명</span><span class="sxs-lookup"><span data-stu-id="14af4-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="14af4-111">PART_NavWinCP</span><span class="sxs-lookup"><span data-stu-id="14af4-111">PART_NavWinCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="14af4-112">콘텐츠의 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="14af4-112">The area for the content.</span></span>|  
  
## <a name="navigationwindow-states"></a><span data-ttu-id="14af4-113">NavigationWindow 상태</span><span class="sxs-lookup"><span data-stu-id="14af4-113">NavigationWindow States</span></span>  
 <span data-ttu-id="14af4-114">다음 표에서는 <xref:System.Windows.Navigation.NavigationWindow> 컨트롤의 시각적 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="14af4-114">The following table lists the visual states for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="14af4-115">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="14af4-115">VisualState Name</span></span>|<span data-ttu-id="14af4-116">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="14af4-116">VisualStateGroup Name</span></span>|<span data-ttu-id="14af4-117">설명</span><span class="sxs-lookup"><span data-stu-id="14af4-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="14af4-118">유효</span><span class="sxs-lookup"><span data-stu-id="14af4-118">Valid</span></span>|<span data-ttu-id="14af4-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="14af4-119">ValidationStates</span></span>|<span data-ttu-id="14af4-120">컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="14af4-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="14af4-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="14af4-121">InvalidFocused</span></span>|<span data-ttu-id="14af4-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="14af4-122">ValidationStates</span></span>|<span data-ttu-id="14af4-123">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14af4-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="14af4-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="14af4-124">InvalidUnfocused</span></span>|<span data-ttu-id="14af4-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="14af4-125">ValidationStates</span></span>|<span data-ttu-id="14af4-126">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="14af4-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="navigationwindow-controltemplate-example"></a><span data-ttu-id="14af4-127">NavigationWindow ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="14af4-127">NavigationWindow ControlTemplate Example</span></span>  
 <span data-ttu-id="14af4-128">이 예제에서는 기본적으로 <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Controls.ControlTemplate>에 정의 된 모든 요소를 포함 하지만 특정 값은 예제로 간주 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14af4-128">Although this example contains all of the elements that are defined in the <xref:System.Windows.Controls.ControlTemplate> of a <xref:System.Windows.Navigation.NavigationWindow> by default, the specific values should be thought of as examples.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#NavigationWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/navigationwindow.xaml#navigationwindow)]  
  
 <span data-ttu-id="14af4-129">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="14af4-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="14af4-130">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14af4-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14af4-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="14af4-131">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="14af4-132">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="14af4-132">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="14af4-133">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="14af4-133">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="14af4-134">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="14af4-134">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="14af4-135">컨트롤에 대 한 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="14af4-135">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
