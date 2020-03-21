---
title: 도구 설명 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], about ToolTip control
- controls [WPF], ToolTip
ms.assetid: f06c1603-e9cb-4809-8a62-234607fc52f7
ms.openlocfilehash: 0fec31b28a21c2e17986210c852b3d630087842d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181942"
---
# <a name="tooltip-overview"></a><span data-ttu-id="51a51-102">도구 설명 개요</span><span class="sxs-lookup"><span data-stu-id="51a51-102">ToolTip Overview</span></span>
<span data-ttu-id="51a51-103">도구 설명은 사용자가 <xref:System.Windows.Controls.Button>에 대한 요소 위에 마우스 포인터를 일시 중지할 때 나타나는 작은 팝업 창입니다.</span><span class="sxs-lookup"><span data-stu-id="51a51-103">A tooltip is a small pop-up window that appears when a user pauses the mouse pointer over an element, such as over a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="51a51-104">이 항목에서는 도구 설명을 소개하고 도구 설명 콘텐츠를 만들고 사용자 지정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="51a51-104">This topic introduces the tooltip and discusses how to create and customize tooltip content.</span></span>  

<a name="what_is_a_tooltip"></a>
## <a name="what-is-a-tooltip"></a><span data-ttu-id="51a51-105">도구 설명이란?</span><span class="sxs-lookup"><span data-stu-id="51a51-105">What Is a Tooltip?</span></span>  
 <span data-ttu-id="51a51-106">사용자가 마우스 포인터를 도구 설명이 있는 요소 위로 이동하면 도구 설명 콘텐츠(예: 컨트롤 함수를 설명하는 텍스트 콘텐츠)가 포함된 창이 지정된 시간 동안 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="51a51-106">When a user moves the mouse pointer over an element that has a tooltip, a window that contains tooltip content (for example, text content that describes the function of a control) appears for a specified amount of time.</span></span> <span data-ttu-id="51a51-107">사용자가 마우스 포인터를 컨트롤 외부로 이동하면 도구 설명 콘텐츠가 포커스를 받을 수 없기 때문에 창이 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="51a51-107">If the user moves the mouse pointer away from the control, the window disappears because the tooltip content cannot receive focus.</span></span>  
  
 <span data-ttu-id="51a51-108">도구 설명 콘텐츠에는 하나 이상의 텍스트 줄, 이미지, 도형 및 기타 시각적 콘텐츠가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51a51-108">The content of a tooltip can contain one or more lines of text, images, shapes, or other visual content.</span></span> <span data-ttu-id="51a51-109">컨트롤에 대한 도구 설명을 정의하려면 다음 속성 중 하나를 도구 설명 콘텐츠로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="51a51-109">You define a tooltip for a control by setting one of the following properties to the tooltip content.</span></span>  
  
- <xref:System.Windows.FrameworkContentElement.ToolTip%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="51a51-110">사용할 속성은 도구 설명또는 <xref:System.Windows.FrameworkContentElement> <xref:System.Windows.FrameworkElement> 클래스에서 도구 설명을 정의하는 컨트롤이 상속되는지 여부에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="51a51-110">Which property you use depends on whether the control that defines the tooltip inherits from the <xref:System.Windows.FrameworkContentElement> or <xref:System.Windows.FrameworkElement> class.</span></span>  
  
<a name="create_tooltip"></a>
## <a name="creating-a-tooltip"></a><span data-ttu-id="51a51-111">ToolTip 만들기</span><span class="sxs-lookup"><span data-stu-id="51a51-111">Creating a ToolTip</span></span>  
 <span data-ttu-id="51a51-112">다음 예제에서는 <xref:System.Windows.FrameworkElement.ToolTip%2A> <xref:System.Windows.Controls.Button> 컨트롤에 대 한 속성을 텍스트 문자열로 설정 하 여 간단한 도구 모음을 만드는 방법을 보여 주입니다.</span><span class="sxs-lookup"><span data-stu-id="51a51-112">The following example shows how to create a simple tooltip by setting the <xref:System.Windows.FrameworkElement.ToolTip%2A> property for a <xref:System.Windows.Controls.Button> control to a text string.</span></span>  
  
 [!code-xaml[GroupBoxSnippet#ToolTipString](~/samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipstring)]  
  
 <span data-ttu-id="51a51-113">도구 설명은 객체로 <xref:System.Windows.Controls.ToolTip> 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51a51-113">You can also define a tooltip as a <xref:System.Windows.Controls.ToolTip> object.</span></span> <span data-ttu-id="51a51-114">다음 예제에서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 객체를 <xref:System.Windows.Controls.ToolTip> 요소의 툴팁으로 <xref:System.Windows.Controls.TextBox> 지정하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="51a51-114">The following example uses [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] to specify a <xref:System.Windows.Controls.ToolTip> object as the tooltip of a <xref:System.Windows.Controls.TextBox> element.</span></span> <span data-ttu-id="51a51-115">이 예제는 속성을 <xref:System.Windows.Controls.ToolTip> 설정하여 지정합니다. <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="51a51-115">Note that the example specifies the <xref:System.Windows.Controls.ToolTip> by setting the <xref:System.Windows.FrameworkElement.ToolTip%2A?displayProperty=nameWithType> property.</span></span>  
  
 [!code-xaml[ToolTipSimple#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#tooltip)]  
  
 <span data-ttu-id="51a51-116">다음 예제에서는 코드를 사용하여 <xref:System.Windows.Controls.ToolTip> 개체를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="51a51-116">The following example uses code to generate a <xref:System.Windows.Controls.ToolTip> object.</span></span> <span data-ttu-id="51a51-117">이 예제에서는 <xref:System.Windows.Controls.ToolTip> `tt`(를 <xref:System.Windows.Controls.Button>만들고) 를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="51a51-117">The example creates a <xref:System.Windows.Controls.ToolTip> (`tt`) and associates it with a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-csharp[ToolTipSimple#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ToolTipSimple#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipSimple/VisualBasic/Window1.xaml.vb#2)]  
  
 <span data-ttu-id="51a51-118">도구 설명 콘텐츠를 와 같은 레이아웃 요소의 도구 설명 구성 요소로 둘러싸서 <xref:System.Windows.Controls.ToolTip> 개체로 정의되지 않은 도구 팁 컨텐츠를 만들 수도 <xref:System.Windows.Controls.DockPanel>있습니다.</span><span class="sxs-lookup"><span data-stu-id="51a51-118">You can also create tooltip content that is not defined as a <xref:System.Windows.Controls.ToolTip> object by enclosing the tooltip content in a layout element, such as a <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="51a51-119">다음 예제에서는 <xref:System.Windows.FrameworkElement.ToolTip%2A> <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.DockPanel> 컨트롤에 동봉된 콘텐츠에 a의 속성을 설정하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51a51-119">The following example shows how to set the <xref:System.Windows.FrameworkElement.ToolTip%2A> property of a <xref:System.Windows.Controls.TextBox> to content that is enclosed in a <xref:System.Windows.Controls.DockPanel> control.</span></span>  
  
 [!code-xaml[GroupBoxSnippet#ToolTipDockPanel](~/samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#tooltipdockpanel)]  
  
<a name="Using_the_ToolTip_and_ToolTipService_Properties"></a>
## <a name="using-the-properties-of-the-tooltip-and-tooltipservice-classes"></a><span data-ttu-id="51a51-120">ToolTip 및 ToolTipService 클래스의 속성 사용</span><span class="sxs-lookup"><span data-stu-id="51a51-120">Using the Properties of the ToolTip and ToolTipService Classes</span></span>  
 <span data-ttu-id="51a51-121">시각적 속성을 설정하고 스타일을 적용하여 도구 설명 콘텐츠를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51a51-121">You can customize tooltip content by setting visual properties and applying styles.</span></span> <span data-ttu-id="51a51-122">도구 설명 내용을 <xref:System.Windows.Controls.ToolTip> 개체로 정의하는 경우 <xref:System.Windows.Controls.ToolTip> 개체의 시각적 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51a51-122">If you define the tooltip content as a <xref:System.Windows.Controls.ToolTip> object, you can set the visual properties of the <xref:System.Windows.Controls.ToolTip> object.</span></span> <span data-ttu-id="51a51-123">그렇지 않으면 <xref:System.Windows.Controls.ToolTipService> 클래스에 동일한 연결된 속성을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51a51-123">Otherwise, you must set equivalent attached properties on the <xref:System.Windows.Controls.ToolTipService> class.</span></span>  
  
 <span data-ttu-id="51a51-124">및 및 속성을 사용하여 tooltip 콘텐츠의 위치를 지정하기 위해 속성을 설정하는 방법의 예는 [ToolTip 위치](how-to-position-a-tooltip.md)를 참조하십시오. <xref:System.Windows.Controls.ToolTipService> <xref:System.Windows.Controls.ToolTip></span><span class="sxs-lookup"><span data-stu-id="51a51-124">For an example of how to set properties in order to specify the position of tooltip content by using the <xref:System.Windows.Controls.ToolTip> and <xref:System.Windows.Controls.ToolTipService> properties, see [Position a ToolTip](how-to-position-a-tooltip.md).</span></span>  
  
<a name="StylingToolTip"></a>
## <a name="styling-a-tooltip"></a><span data-ttu-id="51a51-125">ToolTip 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="51a51-125">Styling a ToolTip</span></span>  
 <span data-ttu-id="51a51-126">사용자 지정을 <xref:System.Windows.Controls.ToolTip> <xref:System.Windows.Style>정의하여 스타일을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51a51-126">You can style a <xref:System.Windows.Controls.ToolTip> by defining a custom <xref:System.Windows.Style>.</span></span> <span data-ttu-id="51a51-127">다음 예제에서는 의 <xref:System.Windows.Style> `Simple` <xref:System.Windows.Controls.ToolTip> 배치를 오프셋하고 의 모양을 설정하여 모양을 <xref:System.Windows.Controls.Control.Background%2A>변경하는 <xref:System.Windows.Controls.Control.Foreground%2A> <xref:System.Windows.Controls.Control.FontSize%2A>방법을 <xref:System.Windows.Controls.Control.FontWeight%2A>보여 주는 호출을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="51a51-127">The following example defines a <xref:System.Windows.Style> called `Simple` that shows how to offset the placement of the <xref:System.Windows.Controls.ToolTip> and change its appearance by setting the <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>, and <xref:System.Windows.Controls.Control.FontWeight%2A>.</span></span>  
  
 [!code-xaml[ToolTipSimple#Style](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipSimple/CSharp/Pane1.xaml#style)]  
  
<a name="UsingtheToolTipServiceTimeIntervalProperties"></a>
## <a name="using-the-time-interval-properties-of-tooltipservice"></a><span data-ttu-id="51a51-128">ToolTipService의 시간 간격 속성 사용</span><span class="sxs-lookup"><span data-stu-id="51a51-128">Using the Time Interval Properties of ToolTipService</span></span>  
 <span data-ttu-id="51a51-129"><xref:System.Windows.Controls.ToolTipService> 클래스는 도구 설명 표시 시간을 설정하는 데 <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>다음과 <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>같은 <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A>속성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="51a51-129">The <xref:System.Windows.Controls.ToolTipService> class provides the following properties for you to set tooltip display times: <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A>, <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A>, and <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A>.</span></span>  
  
 <span data-ttu-id="51a51-130">및 속성을 <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A> 사용하여 지연이 <xref:System.Windows.Controls.ToolTip> 나타나기 전에 일반적으로 간략하게 지연을 <xref:System.Windows.Controls.ToolTip> 지정하고 표시되는 남은 시간도 지정합니다. <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A></span><span class="sxs-lookup"><span data-stu-id="51a51-130">Use the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> and <xref:System.Windows.Controls.ToolTipService.ShowDuration%2A> properties to specify a delay, typically brief, before a <xref:System.Windows.Controls.ToolTip> appears and also to specify how long a <xref:System.Windows.Controls.ToolTip> remains visible.</span></span> <span data-ttu-id="51a51-131">자세한 내용은 [How to: Delay the Display of a ToolTip](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms747264(v=vs.90))(방법: ToolTip 표시 지연)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51a51-131">For more information, see [How to: Delay the Display of a ToolTip](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms747264(v=vs.90)).</span></span>  
  
 <span data-ttu-id="51a51-132">이 <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> 속성은 마우스 포인터를 빠르게 이동할 때 다른 컨트롤에 대한 도구 설명이 초기 지연 없이 나타나는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="51a51-132">The <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> property determines if tooltips for different controls appear without an initial delay when you move the mouse pointer quickly between them.</span></span> <span data-ttu-id="51a51-133">속성에 <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> 대한 자세한 내용은 [BetweenShowDelay 속성 사용을](how-to-use-the-betweenshowdelay-property.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="51a51-133">For more information about the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> property, see [Use the BetweenShowDelay Property](how-to-use-the-betweenshowdelay-property.md).</span></span>  
  
 <span data-ttu-id="51a51-134">다음 예제에서는 도구 설명에 대한 이러한 속성을 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="51a51-134">The following example shows how to set these properties for a tooltip.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
## <a name="see-also"></a><span data-ttu-id="51a51-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="51a51-135">See also</span></span>

- <xref:System.Windows.Controls.ToolTipService>
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipEventArgs>
- <xref:System.Windows.Controls.ToolTipEventHandler>
- [<span data-ttu-id="51a51-136">방법 주제</span><span class="sxs-lookup"><span data-stu-id="51a51-136">How-to Topics</span></span>](tooltip-how-to-topics.md)
