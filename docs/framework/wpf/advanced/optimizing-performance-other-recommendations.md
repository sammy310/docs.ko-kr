---
title: '성능 최적화: 기타 권장 사항'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Terminal Services rendering [WPF]
- opacity [WPF]
- hit-test objects [WPF]
- ScrollBarVisibility enumeration [WPF]
- brushes [WPF], performance
ms.assetid: d028cc65-7e97-4a4f-9859-929734eaf40d
ms.openlocfilehash: 727331adb41251460209f157d1804ff455bcf473
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186297"
---
# <a name="optimizing-performance-other-recommendations"></a><span data-ttu-id="cf7d1-102">성능 최적화: 기타 권장 사항</span><span class="sxs-lookup"><span data-stu-id="cf7d1-102">Optimizing Performance: Other Recommendations</span></span>
<a name="introduction"></a> <span data-ttu-id="cf7d1-103">이 항목에서는 [WPF 애플리케이션 성능 최적화](optimizing-wpf-application-performance.md) 섹션의 항목 내용에 추가되는 성능 권장 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7d1-103">This topic provides performance recommendations in addition to the ones covered by the topics in the [Optimizing WPF Application Performance](optimizing-wpf-application-performance.md) section.</span></span>  
  
 <span data-ttu-id="cf7d1-104">이 항목에는 다음과 같은 섹션이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7d1-104">This topic contains the following sections:</span></span>  
  
- [<span data-ttu-id="cf7d1-105">브러시의 불투명도와 요소의 불투명도 비교</span><span class="sxs-lookup"><span data-stu-id="cf7d1-105">Opacity on Brushes Versus Opacity on Elements</span></span>](#Opacity)  
  
- [<span data-ttu-id="cf7d1-106">개체 탐색</span><span class="sxs-lookup"><span data-stu-id="cf7d1-106">Navigation to Object</span></span>](#Navigation_Objects)  
  
- [<span data-ttu-id="cf7d1-107">대형 3D 화면에서의 적중 횟수 테스트</span><span class="sxs-lookup"><span data-stu-id="cf7d1-107">Hit Testing on Large 3D Surfaces</span></span>](#Hit_Testing)  
  
- [<span data-ttu-id="cf7d1-108">CompositionTarget.Rendering 이벤트</span><span class="sxs-lookup"><span data-stu-id="cf7d1-108">CompositionTarget.Rendering Event</span></span>](#CompositionTarget_Rendering_Event)  
  
- [<span data-ttu-id="cf7d1-109">ScrollBarVisibility=Auto 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="cf7d1-109">Avoid Using ScrollBarVisibility=Auto</span></span>](#Avoid_Using_ScrollBarVisibility)  
  
- [<span data-ttu-id="cf7d1-110">시작 시간을 줄이도록 글꼴 캐시 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="cf7d1-110">Configure Font Cache Service to Reduce Start-up Time</span></span>](#FontCache)  
  
<a name="Opacity"></a>
## <a name="opacity-on-brushes-versus-opacity-on-elements"></a><span data-ttu-id="cf7d1-111">브러시의 불투명도와 요소의 불투명도 비교</span><span class="sxs-lookup"><span data-stu-id="cf7d1-111">Opacity on Brushes Versus Opacity on Elements</span></span>  
 <span data-ttu-id="cf7d1-112">a를 <xref:System.Windows.Media.Brush> 사용하여 요소의 <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Shape.Stroke%2A> 또는 집합을 사용하는 경우 요소의 <xref:System.Windows.Media.Brush.Opacity%2A?displayProperty=nameWithType> <xref:System.Windows.UIElement.Opacity%2A> 속성을 설정하는 것보다 값을 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7d1-112">When you use a <xref:System.Windows.Media.Brush> to set the <xref:System.Windows.Shapes.Shape.Fill%2A> or <xref:System.Windows.Shapes.Shape.Stroke%2A> of an element, it is better to set the <xref:System.Windows.Media.Brush.Opacity%2A?displayProperty=nameWithType> value rather than the setting the element's <xref:System.Windows.UIElement.Opacity%2A> property.</span></span> <span data-ttu-id="cf7d1-113">요소의 <xref:System.Windows.UIElement.Opacity%2A> 속성을 수정하면 임시 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 서피스가 작성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7d1-113">Modifying an element's <xref:System.Windows.UIElement.Opacity%2A> property can cause [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to create a temporary surface.</span></span>  
  
<a name="Navigation_Objects"></a>
## <a name="navigation-to-object"></a><span data-ttu-id="cf7d1-114">개체 탐색</span><span class="sxs-lookup"><span data-stu-id="cf7d1-114">Navigation to Object</span></span>  
 <span data-ttu-id="cf7d1-115">개체는 <xref:System.Windows.Navigation.NavigationWindow> 주로 <xref:System.Windows.Window> 집계 및 저널을 통해 콘텐츠 탐색 지원에서 <xref:System.Windows.Navigation.NavigationService> 파생되고 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf7d1-115">The <xref:System.Windows.Navigation.NavigationWindow> object derives from <xref:System.Windows.Window> and extends it with content navigation support, primarily by aggregating <xref:System.Windows.Navigation.NavigationService> and the journal.</span></span> <span data-ttu-id="cf7d1-116">균일 한 리소스 식별자 (URI) 또는 개체를 지정 하 여 의 <xref:System.Windows.Navigation.NavigationWindow> 클라이언트 영역을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7d1-116">You can update the client area of <xref:System.Windows.Navigation.NavigationWindow> by specifying either a uniform resource identifier (URI) or an object.</span></span> <span data-ttu-id="cf7d1-117">다음 샘플에서는 이러한 두 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cf7d1-117">The following sample shows both methods:</span></span>  
  
 [!code-csharp[Performance#PerformanceSnippet14](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/TestNavigation.xaml.cs#performancesnippet14)]
 [!code-vb[Performance#PerformanceSnippet14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/testnavigation.xaml.vb#performancesnippet14)]  
  
 <span data-ttu-id="cf7d1-118">각 <xref:System.Windows.Navigation.NavigationWindow> 개체에는 해당 창에 사용자의 탐색 기록을 기록하는 저널이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7d1-118">Each <xref:System.Windows.Navigation.NavigationWindow> object has a journal that records the user's navigation history in that window.</span></span> <span data-ttu-id="cf7d1-119">저널의 목적 중 하나는 사용자가 단계를 다시 수행할 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cf7d1-119">One of the purposes of the journal is to allow users to retrace their steps.</span></span>  
  
 <span data-ttu-id="cf7d1-120">균일 한 리소스 식별자 (URI)를 사용 하 여 탐색 하는 경우 저널균일 한 리소스 식별자 (URI) 참조만 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7d1-120">When you navigate using a uniform resource identifier (URI), the journal stores only the uniform resource identifier (URI) reference.</span></span> <span data-ttu-id="cf7d1-121">이는 페이지를 다시 방문할 때마다 동적으로 다시 구성하기 때문에 페이지가 복잡할 경우 많은 시간이 걸릴 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7d1-121">This means that each time you revisit the page, it is dynamically reconstructed, which may be time consuming depending on the complexity of the page.</span></span> <span data-ttu-id="cf7d1-122">이 경우 저널 스토리지 비용은 낮지만 페이지를 다시 구성하는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7d1-122">In this case, the journal storage cost is low, but the time to reconstitute the page is potentially high.</span></span>  
  
 <span data-ttu-id="cf7d1-123">개체를 사용하여 탐색하면 저널에서 개체의 전체 시각적 트리를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7d1-123">When you navigate using an object, the journal stores the entire visual tree of the object.</span></span> <span data-ttu-id="cf7d1-124">즉, 페이지를 다시 방문할 때마다 페이지를 다시 구성하지 않고 바로 렌더링합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7d1-124">This means that each time you revisit the page, it renders immediately without having to be reconstructed.</span></span> <span data-ttu-id="cf7d1-125">이 경우 저널 스토리지 비용은 높지만 페이지를 다시 구성하는 시간이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="cf7d1-125">In this case, the journal storage cost is high, but the time to reconstitute the page is low.</span></span>  
  
 <span data-ttu-id="cf7d1-126">개체를 <xref:System.Windows.Navigation.NavigationWindow> 사용할 때 저널링 지원이 응용 프로그램의 성능에 미치는 영향을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7d1-126">When you use the <xref:System.Windows.Navigation.NavigationWindow> object, you will need to keep in mind how the journaling support impacts your application's performance.</span></span> <span data-ttu-id="cf7d1-127">자세한 내용은 [탐색 개요를](../app-development/navigation-overview.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cf7d1-127">For more information, see [Navigation Overview](../app-development/navigation-overview.md).</span></span>  
  
<a name="Hit_Testing"></a>
## <a name="hit-testing-on-large-3d-surfaces"></a><span data-ttu-id="cf7d1-128">대형 3D 화면에서의 적중 횟수 테스트</span><span class="sxs-lookup"><span data-stu-id="cf7d1-128">Hit Testing on Large 3D Surfaces</span></span>  
 <span data-ttu-id="cf7d1-129">대형 3D 화면에서의 적중 횟수 테스트는 CPU 사용 면으로 볼 때 성능에 영향을 미치는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="cf7d1-129">Hit testing on large 3D surfaces is a very performance intensive operation in terms of CPU consumption.</span></span> <span data-ttu-id="cf7d1-130">3D 화면에 애니메이션 효과를 주는 경우 특히 더 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="cf7d1-130">This is especially true when the 3D surface is animating.</span></span> <span data-ttu-id="cf7d1-131">이러한 화면에서 적중 횟수 테스트가 필요 없는 경우에는 적중 횟수 테스트를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="cf7d1-131">If you do not require hit testing on these surfaces, then disable hit testing.</span></span> <span data-ttu-id="cf7d1-132">에서 <xref:System.Windows.UIElement> 파생 된 개체는 <xref:System.Windows.UIElement.IsHitTestVisible%2A> 속성을 설정 하 `false`여 적중 테스트를 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7d1-132">Objects that are derived from <xref:System.Windows.UIElement> can disable hit testing by setting the <xref:System.Windows.UIElement.IsHitTestVisible%2A> property to `false`.</span></span>  
  
<a name="CompositionTarget_Rendering_Event"></a>
## <a name="compositiontargetrendering-event"></a><span data-ttu-id="cf7d1-133">CompositionTarget.Rendering 이벤트</span><span class="sxs-lookup"><span data-stu-id="cf7d1-133">CompositionTarget.Rendering Event</span></span>  
 <span data-ttu-id="cf7d1-134">이 <xref:System.Windows.Media.CompositionTarget.Rendering?displayProperty=nameWithType> 이벤트로 인해 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 계속 애니메이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf7d1-134">The <xref:System.Windows.Media.CompositionTarget.Rendering?displayProperty=nameWithType> event causes [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to continuously animate.</span></span> <span data-ttu-id="cf7d1-135">이 이벤트를 사용하는 경우 기회가 될 때마다 이 이벤트를 분리하세요.</span><span class="sxs-lookup"><span data-stu-id="cf7d1-135">If you use this event, detach it at every opportunity.</span></span>  
  
<a name="Avoid_Using_ScrollBarVisibility"></a>
## <a name="avoid-using-scrollbarvisibilityauto"></a><span data-ttu-id="cf7d1-136">ScrollBarVisibility=Auto 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="cf7d1-136">Avoid Using ScrollBarVisibility=Auto</span></span>  
 <span data-ttu-id="cf7d1-137">가능하면 <xref:System.Windows.Controls.ScrollBarVisibility.Auto?displayProperty=nameWithType> `HorizontalScrollBarVisibility` 및 `VerticalScrollBarVisibility` 속성에 대한 값을 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="cf7d1-137">Whenever possible, avoid using the <xref:System.Windows.Controls.ScrollBarVisibility.Auto?displayProperty=nameWithType> value for the `HorizontalScrollBarVisibility` and `VerticalScrollBarVisibility` properties.</span></span> <span data-ttu-id="cf7d1-138">이러한 속성은 <xref:System.Windows.Controls.RichTextBox>에 <xref:System.Windows.Controls.ScrollViewer>대해 <xref:System.Windows.Controls.TextBox> 및 개체에 대해 정의되며 개체에 <xref:System.Windows.Controls.ListBox> 대해 연결된 속성으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf7d1-138">These properties are defined for <xref:System.Windows.Controls.RichTextBox>, <xref:System.Windows.Controls.ScrollViewer>, and <xref:System.Windows.Controls.TextBox> objects, and as an attached property for the <xref:System.Windows.Controls.ListBox> object.</span></span> <span data-ttu-id="cf7d1-139">대신 에 <xref:System.Windows.Controls.ScrollBarVisibility> <xref:System.Windows.Controls.ScrollBarVisibility.Disabled> <xref:System.Windows.Controls.ScrollBarVisibility.Hidden>대해 " <xref:System.Windows.Controls.ScrollBarVisibility.Visible>또는 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7d1-139">Instead, set <xref:System.Windows.Controls.ScrollBarVisibility> to <xref:System.Windows.Controls.ScrollBarVisibility.Disabled>, <xref:System.Windows.Controls.ScrollBarVisibility.Hidden>, or <xref:System.Windows.Controls.ScrollBarVisibility.Visible>.</span></span>  
  
 <span data-ttu-id="cf7d1-140">이 <xref:System.Windows.Controls.ScrollBarVisibility.Auto> 값은 공간이 제한되어 있고 필요한 경우에만 스크롤 막대를 표시해야 하는 경우에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7d1-140">The <xref:System.Windows.Controls.ScrollBarVisibility.Auto> value is intended for cases when space is limited and scrollbars should only be displayed when necessary.</span></span> <span data-ttu-id="cf7d1-141">예를 들어 수백 <xref:System.Windows.Controls.ScrollBarVisibility> <xref:System.Windows.Controls.ListBox> 줄의 텍스트가 있는 항목과 달리 이 <xref:System.Windows.Controls.TextBox> 값을 30개 항목으로 사용하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7d1-141">For example, it may be useful to use this <xref:System.Windows.Controls.ScrollBarVisibility> value with a <xref:System.Windows.Controls.ListBox> of 30 items as opposed to a <xref:System.Windows.Controls.TextBox> with hundreds of lines of text.</span></span>  
  
<a name="FontCache"></a>
## <a name="configure-font-cache-service-to-reduce-start-up-time"></a><span data-ttu-id="cf7d1-142">시작 시간을 줄이도록 글꼴 캐시 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="cf7d1-142">Configure Font Cache Service to Reduce Start-up Time</span></span>  
 <span data-ttu-id="cf7d1-143">WPF 글꼴 캐시 서비스는 WPF 응용 프로그램 간에 글꼴 데이터를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7d1-143">The WPF Font Cache service shares font data between WPF applications.</span></span> <span data-ttu-id="cf7d1-144">실행하는 첫 번째 WPF 응용 프로그램은 서비스가 아직 실행중이 아닌 경우 이 서비스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7d1-144">The first WPF application you run starts this service if the service is not already running.</span></span> <span data-ttu-id="cf7d1-145">Windows Vista를 사용하는 경우 "수동"(기본값)에서 "자동(지연된 시작)"으로 "WPF 프레젠테이션 기반(WPF) 글꼴 캐시 3.0.0.0" 서비스를 설정하여 WPF 응용 프로그램의 초기 시작 시간을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7d1-145">If you are using Windows Vista, you can set the "Windows Presentation Foundation (WPF) Font Cache 3.0.0.0" service from "Manual" (the default) to "Automatic (Delayed Start)" to reduce the initial start-up time of WPF applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf7d1-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf7d1-146">See also</span></span>

- [<span data-ttu-id="cf7d1-147">애플리케이션 성능 계획</span><span class="sxs-lookup"><span data-stu-id="cf7d1-147">Planning for Application Performance</span></span>](planning-for-application-performance.md)
- [<span data-ttu-id="cf7d1-148">하드웨어 활용</span><span class="sxs-lookup"><span data-stu-id="cf7d1-148">Taking Advantage of Hardware</span></span>](optimizing-performance-taking-advantage-of-hardware.md)
- [<span data-ttu-id="cf7d1-149">레이아웃 및 디자인</span><span class="sxs-lookup"><span data-stu-id="cf7d1-149">Layout and Design</span></span>](optimizing-performance-layout-and-design.md)
- [<span data-ttu-id="cf7d1-150">2D 그래픽 및 이미징</span><span class="sxs-lookup"><span data-stu-id="cf7d1-150">2D Graphics and Imaging</span></span>](optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="cf7d1-151">개체 동작</span><span class="sxs-lookup"><span data-stu-id="cf7d1-151">Object Behavior</span></span>](optimizing-performance-object-behavior.md)
- [<span data-ttu-id="cf7d1-152">응용 프로그램 리소스</span><span class="sxs-lookup"><span data-stu-id="cf7d1-152">Application Resources</span></span>](optimizing-performance-application-resources.md)
- [<span data-ttu-id="cf7d1-153">텍스트</span><span class="sxs-lookup"><span data-stu-id="cf7d1-153">Text</span></span>](optimizing-performance-text.md)
- [<span data-ttu-id="cf7d1-154">데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="cf7d1-154">Data Binding</span></span>](optimizing-performance-data-binding.md)
- [<span data-ttu-id="cf7d1-155">애니메이션에 대한 유용한 정보</span><span class="sxs-lookup"><span data-stu-id="cf7d1-155">Animation Tips and Tricks</span></span>](../graphics-multimedia/animation-tips-and-tricks.md)
