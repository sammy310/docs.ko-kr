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
ms.openlocfilehash: 32d8aac99d40693e66c7b52a6c7d2c116d2f3baf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225809"
---
# <a name="navigationwindow-styles-and-templates"></a><span data-ttu-id="2ae7a-102">NavigationWindow 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="2ae7a-102">NavigationWindow Styles and Templates</span></span>
<span data-ttu-id="2ae7a-103">이 항목에서는 스타일 및 템플릿에 대해 설명 합니다 <xref:System.Windows.Navigation.NavigationWindow> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ae7a-103">This topic describes the styles and templates for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span> <span data-ttu-id="2ae7a-104">기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ae7a-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="2ae7a-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ae7a-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="navigationwindow-parts"></a><span data-ttu-id="2ae7a-106">NavigationWindow 파트</span><span class="sxs-lookup"><span data-stu-id="2ae7a-106">NavigationWindow Parts</span></span>  
 <span data-ttu-id="2ae7a-107">다음 표에서 대 한 명명된 된 파트를 <xref:System.Windows.Navigation.NavigationWindow> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ae7a-107">The following table lists the named parts for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="2ae7a-108">파트</span><span class="sxs-lookup"><span data-stu-id="2ae7a-108">Part</span></span>|<span data-ttu-id="2ae7a-109">형식</span><span class="sxs-lookup"><span data-stu-id="2ae7a-109">Type</span></span>|<span data-ttu-id="2ae7a-110">설명</span><span class="sxs-lookup"><span data-stu-id="2ae7a-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="2ae7a-111">PART_NavWinCP</span><span class="sxs-lookup"><span data-stu-id="2ae7a-111">PART_NavWinCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="2ae7a-112">콘텐츠에 대 한 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="2ae7a-112">The area for the content.</span></span>|  
  
## <a name="navigationwindow-states"></a><span data-ttu-id="2ae7a-113">NavigationWindow 상태</span><span class="sxs-lookup"><span data-stu-id="2ae7a-113">NavigationWindow States</span></span>  
 <span data-ttu-id="2ae7a-114">다음 표에서 대 한 시각적 상태를 <xref:System.Windows.Navigation.NavigationWindow> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ae7a-114">The following table lists the visual states for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="2ae7a-115">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="2ae7a-115">VisualState Name</span></span>|<span data-ttu-id="2ae7a-116">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="2ae7a-116">VisualStateGroup Name</span></span>|<span data-ttu-id="2ae7a-117">설명</span><span class="sxs-lookup"><span data-stu-id="2ae7a-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="2ae7a-118">유효</span><span class="sxs-lookup"><span data-stu-id="2ae7a-118">Valid</span></span>|<span data-ttu-id="2ae7a-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2ae7a-119">ValidationStates</span></span>|<span data-ttu-id="2ae7a-120">컨트롤에서 사용 된 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="2ae7a-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="2ae7a-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="2ae7a-121">InvalidFocused</span></span>|<span data-ttu-id="2ae7a-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2ae7a-122">ValidationStates</span></span>|<span data-ttu-id="2ae7a-123">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ae7a-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="2ae7a-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="2ae7a-124">InvalidUnfocused</span></span>|<span data-ttu-id="2ae7a-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2ae7a-125">ValidationStates</span></span>|<span data-ttu-id="2ae7a-126">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ae7a-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="navigationwindow-controltemplate-example"></a><span data-ttu-id="2ae7a-127">NavigationWindow ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="2ae7a-127">NavigationWindow ControlTemplate Example</span></span>  
 <span data-ttu-id="2ae7a-128">이 예제에서는 모든 요소에 정의 된 포함 하지만 합니다 <xref:System.Windows.Controls.ControlTemplate> 의 <xref:System.Windows.Navigation.NavigationWindow> 기본적으로 특정 값을 생각해 야 예제로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ae7a-128">Although this example contains all of the elements that are defined in the <xref:System.Windows.Controls.ControlTemplate> of a <xref:System.Windows.Navigation.NavigationWindow> by default, the specific values should be thought of as examples.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#NavigationWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/navigationwindow.xaml#navigationwindow)]  
  
 <span data-ttu-id="2ae7a-129">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2ae7a-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="2ae7a-130">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ae7a-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ae7a-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="2ae7a-131">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="2ae7a-132">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="2ae7a-132">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="2ae7a-133">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="2ae7a-133">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="2ae7a-134">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="2ae7a-134">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="2ae7a-135">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="2ae7a-135">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
