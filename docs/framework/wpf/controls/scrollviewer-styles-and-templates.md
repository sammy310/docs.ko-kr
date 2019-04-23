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
ms.openlocfilehash: 9c0edfd7ab4772eb9a1f5ecdd3db611fa36bf8d3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59226835"
---
# <a name="scrollviewer-styles-and-templates"></a><span data-ttu-id="aa01e-102">ScrollViewer 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="aa01e-102">ScrollViewer Styles and Templates</span></span>
<span data-ttu-id="aa01e-103">이 항목에서는 스타일 및 템플릿에 대해 설명 합니다 <xref:System.Windows.Controls.ScrollViewer> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa01e-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span> <span data-ttu-id="aa01e-104">기본값을 수정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa01e-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="aa01e-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa01e-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollviewer-parts"></a><span data-ttu-id="aa01e-106">ScrollViewer 파트</span><span class="sxs-lookup"><span data-stu-id="aa01e-106">ScrollViewer Parts</span></span>  
 <span data-ttu-id="aa01e-107">다음 표에서 대 한 명명된 된 파트를 <xref:System.Windows.Controls.ScrollViewer> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa01e-107">The following table lists the named parts for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="aa01e-108">파트</span><span class="sxs-lookup"><span data-stu-id="aa01e-108">Part</span></span>|<span data-ttu-id="aa01e-109">형식</span><span class="sxs-lookup"><span data-stu-id="aa01e-109">Type</span></span>|<span data-ttu-id="aa01e-110">설명</span><span class="sxs-lookup"><span data-stu-id="aa01e-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="aa01e-111">PART_ScrollContentPresenter</span><span class="sxs-lookup"><span data-stu-id="aa01e-111">PART_ScrollContentPresenter</span></span>|<xref:System.Windows.Controls.ScrollContentPresenter>|<span data-ttu-id="aa01e-112">콘텐츠에 대 한 자리 표시자는 <xref:System.Windows.Controls.ScrollViewer>합니다.</span><span class="sxs-lookup"><span data-stu-id="aa01e-112">The placeholder for content in the <xref:System.Windows.Controls.ScrollViewer>.</span></span>|  
|<span data-ttu-id="aa01e-113">PART_HorizontalScrollBar</span><span class="sxs-lookup"><span data-stu-id="aa01e-113">PART_HorizontalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="aa01e-114"><xref:System.Windows.Controls.Primitives.ScrollBar> 콘텐츠를 가로 방향으로 스크롤 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa01e-114">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content horizontally.</span></span>|  
|<span data-ttu-id="aa01e-115">PART_VerticalScrollBar</span><span class="sxs-lookup"><span data-stu-id="aa01e-115">PART_VerticalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="aa01e-116"><xref:System.Windows.Controls.Primitives.ScrollBar> 콘텐츠를 세로 방향으로 스크롤 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa01e-116">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content vertically.</span></span>|  
  
## <a name="scrollviewer-states"></a><span data-ttu-id="aa01e-117">ScrollViewer 상태</span><span class="sxs-lookup"><span data-stu-id="aa01e-117">ScrollViewer States</span></span>  
 <span data-ttu-id="aa01e-118">다음 표에서 대 한 시각적 상태를 <xref:System.Windows.Controls.ScrollViewer> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa01e-118">The following table lists the visual states for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="aa01e-119">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="aa01e-119">VisualState Name</span></span>|<span data-ttu-id="aa01e-120">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="aa01e-120">VisualStateGroup Name</span></span>|<span data-ttu-id="aa01e-121">설명</span><span class="sxs-lookup"><span data-stu-id="aa01e-121">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="aa01e-122">유효</span><span class="sxs-lookup"><span data-stu-id="aa01e-122">Valid</span></span>|<span data-ttu-id="aa01e-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="aa01e-123">ValidationStates</span></span>|<span data-ttu-id="aa01e-124">컨트롤에서 사용 된 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="aa01e-124">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="aa01e-125">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="aa01e-125">InvalidFocused</span></span>|<span data-ttu-id="aa01e-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="aa01e-126">ValidationStates</span></span>|<span data-ttu-id="aa01e-127">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa01e-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="aa01e-128">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="aa01e-128">InvalidUnfocused</span></span>|<span data-ttu-id="aa01e-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="aa01e-129">ValidationStates</span></span>|<span data-ttu-id="aa01e-130">합니다 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `true` 가 컨트롤에 포커스가 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa01e-130">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollviewer-controltemplate-example"></a><span data-ttu-id="aa01e-131">ScrollViewer ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="aa01e-131">ScrollViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="aa01e-132">다음 예제에서는 정의 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.ScrollViewer> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa01e-132">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollviewer.xaml#scrollviewer)]  
  
 <span data-ttu-id="aa01e-133">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aa01e-133">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="aa01e-134">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa01e-134">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa01e-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="aa01e-135">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="aa01e-136">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="aa01e-136">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="aa01e-137">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="aa01e-137">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="aa01e-138">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="aa01e-138">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="aa01e-139">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="aa01e-139">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
