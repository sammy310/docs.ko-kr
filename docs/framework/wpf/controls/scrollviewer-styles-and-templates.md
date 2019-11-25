---
title: ScrollViewer 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ScrollViewer
- states [WPF], ScrollViewer
- styles [WPF], ScrollViewer
- templates [WPF], ScrollViewer
- ControlTemplate [WPF], ScrollViewer
- ScrollViewer [WPF], styles and templates
ms.assetid: dffdd822-ae69-4946-abaf-710860cd65b2
ms.openlocfilehash: b54dcacf55a750d7c1253db20147d18de47d027e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283403"
---
# <a name="scrollviewer-styles-and-templates"></a><span data-ttu-id="60b61-102">ScrollViewer 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="60b61-102">ScrollViewer Styles and Templates</span></span>
<span data-ttu-id="60b61-103">이 항목에서는 <xref:System.Windows.Controls.ScrollViewer> 컨트롤의 스타일 및 템플릿에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="60b61-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span> <span data-ttu-id="60b61-104">기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b61-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="60b61-105">자세한 내용은 [컨트롤에 대 한 템플릿 만들기](../../../desktop-wpf/themes/how-to-create-apply-template.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="60b61-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="scrollviewer-parts"></a><span data-ttu-id="60b61-106">ScrollViewer 파트</span><span class="sxs-lookup"><span data-stu-id="60b61-106">ScrollViewer Parts</span></span>  
 <span data-ttu-id="60b61-107">다음 표에서는 <xref:System.Windows.Controls.ScrollViewer> 컨트롤의 명명 된 파트를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="60b61-107">The following table lists the named parts for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="60b61-108">부분</span><span class="sxs-lookup"><span data-stu-id="60b61-108">Part</span></span>|<span data-ttu-id="60b61-109">형식</span><span class="sxs-lookup"><span data-stu-id="60b61-109">Type</span></span>|<span data-ttu-id="60b61-110">설명</span><span class="sxs-lookup"><span data-stu-id="60b61-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="60b61-111">PART_ScrollContentPresenter</span><span class="sxs-lookup"><span data-stu-id="60b61-111">PART_ScrollContentPresenter</span></span>|<xref:System.Windows.Controls.ScrollContentPresenter>|<span data-ttu-id="60b61-112"><xref:System.Windows.Controls.ScrollViewer>콘텐츠에 대 한 자리 표시자입니다.</span><span class="sxs-lookup"><span data-stu-id="60b61-112">The placeholder for content in the <xref:System.Windows.Controls.ScrollViewer>.</span></span>|  
|<span data-ttu-id="60b61-113">PART_HorizontalScrollBar</span><span class="sxs-lookup"><span data-stu-id="60b61-113">PART_HorizontalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="60b61-114">콘텐츠를 가로로 스크롤 하는 데 사용 되는 <xref:System.Windows.Controls.Primitives.ScrollBar>입니다.</span><span class="sxs-lookup"><span data-stu-id="60b61-114">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content horizontally.</span></span>|  
|<span data-ttu-id="60b61-115">PART_VerticalScrollBar</span><span class="sxs-lookup"><span data-stu-id="60b61-115">PART_VerticalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="60b61-116">콘텐츠를 세로로 스크롤 하는 데 사용 되는 <xref:System.Windows.Controls.Primitives.ScrollBar>입니다.</span><span class="sxs-lookup"><span data-stu-id="60b61-116">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content vertically.</span></span>|  
  
## <a name="scrollviewer-states"></a><span data-ttu-id="60b61-117">ScrollViewer 상태</span><span class="sxs-lookup"><span data-stu-id="60b61-117">ScrollViewer States</span></span>  
 <span data-ttu-id="60b61-118">다음 표에서는 <xref:System.Windows.Controls.ScrollViewer> 컨트롤의 시각적 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="60b61-118">The following table lists the visual states for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="60b61-119">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="60b61-119">VisualState Name</span></span>|<span data-ttu-id="60b61-120">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="60b61-120">VisualStateGroup Name</span></span>|<span data-ttu-id="60b61-121">설명</span><span class="sxs-lookup"><span data-stu-id="60b61-121">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="60b61-122">유효</span><span class="sxs-lookup"><span data-stu-id="60b61-122">Valid</span></span>|<span data-ttu-id="60b61-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="60b61-123">ValidationStates</span></span>|<span data-ttu-id="60b61-124">컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용 하 고 연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `false`됩니다.</span><span class="sxs-lookup"><span data-stu-id="60b61-124">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="60b61-125">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="60b61-125">InvalidFocused</span></span>|<span data-ttu-id="60b61-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="60b61-126">ValidationStates</span></span>|<span data-ttu-id="60b61-127">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성 `true` 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b61-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="60b61-128">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="60b61-128">InvalidUnfocused</span></span>|<span data-ttu-id="60b61-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="60b61-129">ValidationStates</span></span>|<span data-ttu-id="60b61-130">연결 된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성이 `true` 컨트롤에 포커스가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="60b61-130">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollviewer-controltemplate-example"></a><span data-ttu-id="60b61-131">ScrollViewer ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="60b61-131">ScrollViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="60b61-132">다음 예제에서는 <xref:System.Windows.Controls.ScrollViewer> 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate>를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="60b61-132">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollviewer.xaml#scrollviewer)]  
  
 <span data-ttu-id="60b61-133">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="60b61-133">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="60b61-134">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="60b61-134">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60b61-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="60b61-135">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="60b61-136">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="60b61-136">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="60b61-137">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="60b61-137">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="60b61-138">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="60b61-138">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="60b61-139">컨트롤에 대 한 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="60b61-139">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
