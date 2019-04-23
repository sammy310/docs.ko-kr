---
title: 잉크 스레딩 모델
ms.date: 03/30/2017
helpviewer_keywords:
- application user interface thread [WPF]
- stylus plug-in
- ink threading model [WPF]
- ink [WPF], rendering
- pen thread [WPF]
- threading model [WPF]
- rendering ink [WPF]
- dynamic rendering thread [WPF]
- ink collection plug-in
- plug-ins [WPF], for ink
ms.assetid: c85fcad1-cb50-4431-847c-ac4145a35c89
ms.openlocfilehash: 80e7ef202c46a23069766512cf4e67bb21a49564
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59335324"
---
# <a name="the-ink-threading-model"></a><span data-ttu-id="a3fd5-102">잉크 스레딩 모델</span><span class="sxs-lookup"><span data-stu-id="a3fd5-102">The Ink Threading Model</span></span>
<span data-ttu-id="a3fd5-103">Tablet pc 잉크의 이점 중 하나는 마치 많은 쓰기와 같은 일반 펜과 종이 사용 하 여 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-103">One of the benefits of ink on a Tablet PC is that it feels a lot like writing with a regular pen and paper.</span></span>  <span data-ttu-id="a3fd5-104">태블릿 펜이를 위해 마우스 않으며 사용자가 쓸 때 잉크를 렌더링 하는 보다 훨씬 빠른 속도로 입력된 데이터를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-104">To accomplish this, the tablet pen collects input data at a much higher rate than a mouse does and renders the ink as the user writes.</span></span>  <span data-ttu-id="a3fd5-105">차단 될 수 있으므로 응용 프로그램의 사용자 인터페이스 (UI) 스레드에서 펜 데이터와 렌더링 잉크를 수집 하기 위한 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-105">The application's user interface (UI) thread is not sufficient for collecting pen data and rendering ink, because it can become blocked.</span></span>  <span data-ttu-id="a3fd5-106">이 해결 하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 사용자 잉크를 쓸 때 응용 프로그램에서는 두 개의 추가 스레드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-106">To solve this, a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application uses two additional threads when a user writes ink.</span></span>  
  
 <span data-ttu-id="a3fd5-107">다음 목록은 수집 하 고 디지털 잉크를 렌더링에 참여 하는 스레드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-107">The following list describes the threads that take part in collecting and rendering digital ink:</span></span>  
  
-   <span data-ttu-id="a3fd5-108">펜 스레드-스레드 스타일러스에서 입력입니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-108">Pen thread - the thread that takes input from the stylus.</span></span>  <span data-ttu-id="a3fd5-109">(실제로 스레드 풀 이지만이 항목에서는 펜 스레드는이를 나타냅니다.)</span><span class="sxs-lookup"><span data-stu-id="a3fd5-109">(In reality, this is a thread pool, but this topic refers to it as a pen thread.)</span></span>  
  
-   <span data-ttu-id="a3fd5-110">응용 프로그램 사용자 인터페이스 스레드 응용 프로그램의 사용자 인터페이스를 제어 하는 스레드입니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-110">Application user interface thread - the thread that controls the user interface of the application.</span></span>  
  
-   <span data-ttu-id="a3fd5-111">동적 렌더링 스레드-사용자 동안 잉크를 렌더링 하는 스레드는 스트로크를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-111">Dynamic rendering thread - the thread that renders the ink while the user draws a stroke.</span></span> <span data-ttu-id="a3fd5-112">Window Presentation Foundation에서 설명 했 듯이 동적 렌더링 스레드는 응용 프로그램의 다른 UI 요소를 렌더링 하는 스레드가 아닌 다른 [스레딩 모델](threading-model.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-112">The dynamic rendering thread is different than the thread that renders other UI elements for the application, as mentioned in Window Presentation Foundation [Threading Model](threading-model.md).</span></span>  
  
 <span data-ttu-id="a3fd5-113">잉크 입력 기능 모델이 동일 응용 프로그램을 사용 합니다 <xref:System.Windows.Controls.InkCanvas> 또는 사용자 지정 컨트롤에서 비슷하게 [잉크 입력 컨트롤 만들기](creating-an-ink-input-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-113">The inking model is the same whether the application uses the <xref:System.Windows.Controls.InkCanvas> or a custom control similar to the one in [Creating an Ink Input Control](creating-an-ink-input-control.md).</span></span>  <span data-ttu-id="a3fd5-114">이 항목에서는 설명의 측면에서 스레딩 있지만 <xref:System.Windows.Controls.InkCanvas>, 사용자 지정 컨트롤을 만들 때 동일한 개념이 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-114">Although this topic discusses threading in terms of the <xref:System.Windows.Controls.InkCanvas>, the same concepts apply when you create a custom control.</span></span>  
  
## <a name="threading-overview"></a><span data-ttu-id="a3fd5-115">스레딩 개요</span><span class="sxs-lookup"><span data-stu-id="a3fd5-115">Threading Overview</span></span>  
 <span data-ttu-id="a3fd5-116">다음 다이어그램에서는 사용자가 스트로크를 그릴 때 스레딩 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-116">The following diagram illustrates the threading model when a user draws a stroke:</span></span>  
  
 <span data-ttu-id="a3fd5-117">![스트로크를 그리는 동안 스레딩 모델입니다. ](./media/inkthreading-drawingink.png "InkThreading_DrawingInk")</span><span class="sxs-lookup"><span data-stu-id="a3fd5-117">![Threading model while drawing a stroke.](./media/inkthreading-drawingink.png "InkThreading_DrawingInk")</span></span>  
  
1. <span data-ttu-id="a3fd5-118">사용자가 스트로크를 그리는 동안 발생 하는 작업</span><span class="sxs-lookup"><span data-stu-id="a3fd5-118">Actions occurring while the user draws the stroke</span></span>  
  
    1.  <span data-ttu-id="a3fd5-119">사용자가 스트로크를 그릴, 펜 스레드에서 스타일러스 지점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-119">When the user draws a stroke, the stylus points come in on the pen thread.</span></span>  <span data-ttu-id="a3fd5-120">스타일러스 플러그 인을 포함 하는 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>와 펜 스레드에서 스타일러스 지점을 적용 하기 전에 수정 하 게는 <xref:System.Windows.Controls.InkCanvas> 를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-120">Stylus plug-ins, including the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, accept the stylus points on the pen thread and have the chance to modify them before the <xref:System.Windows.Controls.InkCanvas> receives them.</span></span>  
  
    2.  <span data-ttu-id="a3fd5-121"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 스타일러스 지점을 동적 렌더링 스레드에서 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-121">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> renders the stylus points on the dynamic rendering thread.</span></span> <span data-ttu-id="a3fd5-122">이전 단계와 동시에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-122">This happens at the same time as the previous step.</span></span>  
  
    3.  <span data-ttu-id="a3fd5-123"><xref:System.Windows.Controls.InkCanvas> 스타일러스 포인트 UI 스레드를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-123">The <xref:System.Windows.Controls.InkCanvas> receives the stylus points on the UI thread.</span></span>  
  
2. <span data-ttu-id="a3fd5-124">사용자가 스트로크를 종료 한 후 발생 하는 작업</span><span class="sxs-lookup"><span data-stu-id="a3fd5-124">Actions occurring after the user ends the stroke</span></span>  
  
    1.  <span data-ttu-id="a3fd5-125">사용자가 스트로크를 그리는 마치면 합니다 <xref:System.Windows.Controls.InkCanvas> 만듭니다를 <xref:System.Windows.Ink.Stroke> 개체에 추가 합니다는 <xref:System.Windows.Controls.InkPresenter>를 정적으로 렌더링 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-125">When the user finishes drawing the stroke, the <xref:System.Windows.Controls.InkCanvas> creates a <xref:System.Windows.Ink.Stroke> object and adds it to the <xref:System.Windows.Controls.InkPresenter>, which statically renders it.</span></span>  
  
    2.  <span data-ttu-id="a3fd5-126">UI 스레드 경고는 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 스트로크를 정적으로 렌더링 하는 하므로 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 스트로크의 시각적 표시를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-126">The UI thread alerts the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> that the stroke is statically rendered, so the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> removes its visual representation of the stroke.</span></span>  
  
## <a name="ink-collection-and-stylus-plug-ins"></a><span data-ttu-id="a3fd5-127">잉크 수집 및 스타일러스 플러그 인</span><span class="sxs-lookup"><span data-stu-id="a3fd5-127">Ink collection and Stylus Plug-ins</span></span>  
 <span data-ttu-id="a3fd5-128">각 <xref:System.Windows.UIElement> 에 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-128">Each <xref:System.Windows.UIElement> has a <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.</span></span>  <span data-ttu-id="a3fd5-129">합니다 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 개체는 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> 받고 펜 스레드에서 스타일러스 지점을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-129">The <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> objects in the <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> receive and can modify the stylus points on the pen thread.</span></span> <span data-ttu-id="a3fd5-130">합니다 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 개체에서 해당 순서에 따라 스타일러스 지점이 수신는 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-130">The <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> objects receive the stylus points according to their order in the <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.</span></span>  
  
 <span data-ttu-id="a3fd5-131">다음 다이어그램에서는 가상의 상황 위치는 <xref:System.Windows.UIElement.StylusPlugIns%2A> 의 컬렉션을 <xref:System.Windows.UIElement> 포함 `stylusPlugin1`, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, 및 `stylusPlugin2`해당 순서.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-131">The following diagram illustrates the hypothetical situation where the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection of a <xref:System.Windows.UIElement> contains `stylusPlugin1`, a <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, and `stylusPlugin2`, in that order.</span></span>  
  
 <span data-ttu-id="a3fd5-132">![스타일러스 플러그 인 순서가 출력을 영향을 줍니다. ](./media/inkthreading-pluginorder.png "InkThreading_PluginOrder")</span><span class="sxs-lookup"><span data-stu-id="a3fd5-132">![Order of Stylus Plugins affect output.](./media/inkthreading-pluginorder.png "InkThreading_PluginOrder")</span></span>  
  
 <span data-ttu-id="a3fd5-133">이전 다이어그램에서 다음과 같은 동작이 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-133">In the previous diagram, the following behavior takes place:</span></span>  
  
1. <span data-ttu-id="a3fd5-134">`StylusPlugin1` x에 대 한 값을 수정 하 고 y입니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-134">`StylusPlugin1` modifies the values for x and y.</span></span>  
  
2. <span data-ttu-id="a3fd5-135"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 수정 된 스타일러스 지점을 받고 동적 렌더링 스레드에서 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-135"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> receives the modified stylus points and renders them on the dynamic rendering thread.</span></span>  
  
3. <span data-ttu-id="a3fd5-136">`StylusPlugin2` 수정된 된 스타일러스 포인트를 수신 하 고 추가 x에 대 한 값을 수정 하 고 y입니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-136">`StylusPlugin2` receives the modified stylus points and further modifies the values for x and y.</span></span>  
  
4. <span data-ttu-id="a3fd5-137">응용 프로그램 스타일러스 지점을 수집 하 고 사용자가 스트로크를 끝내는 정적으로 스트로크를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-137">The application collects the stylus points, and, when the user finishes the stroke, statically renders the stroke.</span></span>  
  
 <span data-ttu-id="a3fd5-138">가정 `stylusPlugin1` 스타일러스 지점이 사각형에 제한 및 `stylusPlugin2` 오른쪽으로 스타일러스 포인트를 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-138">Suppose that `stylusPlugin1` restricts the stylus points to a rectangle and `stylusPlugin2` translates the stylus points to the right.</span></span>  <span data-ttu-id="a3fd5-139">앞의 시나리오에는 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 제한 스타일러스 포인트를 받지만 번역 된 스타일러스 지점이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-139">In the previous scenario, the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> receives the restricted stylus points, but not the translated stylus points.</span></span>  <span data-ttu-id="a3fd5-140">사용자가 스트로크를 그리면 사각형의 경계 내 스트로크 렌더링 되지만 사용자가 펜을 뗄 때까지 변환할 스트로크 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-140">When the user draws the stroke, the stroke is rendered within the bounds of the rectangle, but the stroke doesn't appear to be translated until the user lifts the pen.</span></span>  
  
### <a name="performing-operations-with-a-stylus-plug-in-on-the-ui-thread"></a><span data-ttu-id="a3fd5-141">UI 스레드에서 플러그 스타일러스를 사용 하 여 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-141">Performing operations with a Stylus Plug-in on the UI thread</span></span>  
 <span data-ttu-id="a3fd5-142">펜 스레드에서 정확한 적중 테스트를 수행할 수 없으므로, 일부 요소가 다른 요소에 대 한 스타일러스 입력을 받는 경우도 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-142">Because accurate hit-testing cannot be performed on the pen thread, some elements might occasionally receive stylus input intended for other elements.</span></span> <span data-ttu-id="a3fd5-143">입력이 작업을 수행 하기 전에 올바르게 라우트 되도록 해야 하는 경우 등록 하 고 작업을 수행 합니다 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusDownProcessed%2A>, <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusMoveProcessed%2A>, 또는 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusUpProcessed%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-143">If you need to make sure the input was routed correctly before performing an operation, subscribe to and perform the operation in the <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusDownProcessed%2A>, <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusMoveProcessed%2A>, or <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusUpProcessed%2A> method.</span></span> <span data-ttu-id="a3fd5-144">이러한 메서드는 정확한 적중 테스트가 수행 된 후 응용 프로그램 스레드에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-144">These methods are invoked by the application thread after accurate hit-testing has been performed.</span></span> <span data-ttu-id="a3fd5-145">를 구독 하려면 이러한 메서드 호출을 <xref:System.Windows.Input.StylusPlugIns.RawStylusInput.NotifyWhenProcessed%2A> 펜 스레드에서 발생 하는 방법에 대 한 메서드.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-145">To subscribe to these methods, call the <xref:System.Windows.Input.StylusPlugIns.RawStylusInput.NotifyWhenProcessed%2A> method in the method that occurs on the pen thread.</span></span>  
  
 <span data-ttu-id="a3fd5-146">다음 다이어그램은 펜 스레드 및 스타일러스 이벤트를 기준으로 UI 스레드 간의 관계를 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>입니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-146">The following diagram illustrates the relationship between the pen thread and UI thread with respect to the stylus events of a <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>.</span></span>  
  
 <span data-ttu-id="a3fd5-147">![잉크 스레딩 모델 &#40;UI 및 펜&#41;](./media/inkthreading-plugincallbacks.png "InkThreading_PluginCallbacks")</span><span class="sxs-lookup"><span data-stu-id="a3fd5-147">![Ink Threading Models &#40;UI and Pen&#41;](./media/inkthreading-plugincallbacks.png "InkThreading_PluginCallbacks")</span></span>  
  
## <a name="rendering-ink"></a><span data-ttu-id="a3fd5-148">잉크 렌더링</span><span class="sxs-lookup"><span data-stu-id="a3fd5-148">Rendering Ink</span></span>  
 <span data-ttu-id="a3fd5-149">사용자가 스트로크를 그릴 때 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 잉크가 "흘러나오는" 펜에서 UI 스레드가 사용 중인 경우에 표시 되도록 별도 스레드에서 잉크를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-149">As the user draws a stroke, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> renders the ink on a separate thread so the ink appears to "flow" from the pen even when the UI thread is busy.</span></span>  <span data-ttu-id="a3fd5-150"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 시각적 트리를 기반으로 동적 렌더링 스레드 스타일러스 포인트를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-150">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> builds a visual tree on the dynamic rendering thread as it collects stylus points.</span></span>  <span data-ttu-id="a3fd5-151">사용자가 스트로크를 끝내는 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 응용 프로그램이 다음 렌더링 과정을 수행 하는 경우 알려 주도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-151">When the user finishes the stroke, the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> asks to be notified when the application does the next rendering pass.</span></span>  <span data-ttu-id="a3fd5-152">응용 프로그램에는 다음 렌더링 과정을 완료 된 후의 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 시각적 트리를 정리 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-152">After the application completes the next rendering pass, the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> cleans up its visual tree.</span></span>  <span data-ttu-id="a3fd5-153">다음 다이어그램에서는이 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-153">The following diagram illustrates this process.</span></span>  
  
 <span data-ttu-id="a3fd5-154">![잉크 스레딩 다이어그램](./media/inkthreading-visualtree.png "InkThreading_VisualTree")</span><span class="sxs-lookup"><span data-stu-id="a3fd5-154">![Ink threading diagram](./media/inkthreading-visualtree.png "InkThreading_VisualTree")</span></span>  
  
1. <span data-ttu-id="a3fd5-155">사용자가 스트로크를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-155">The user begins the stroke.</span></span>  
  
    1.  <span data-ttu-id="a3fd5-156"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 시각적 트리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-156">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> creates the visual tree.</span></span>  
  
2. <span data-ttu-id="a3fd5-157">사용자가 스트로크를 그리고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-157">The user is drawing the stroke.</span></span>  
  
    1.  <span data-ttu-id="a3fd5-158"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 시각적 트리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-158">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> builds the visual tree.</span></span>  
  
3. <span data-ttu-id="a3fd5-159">사용자가 스트로크를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-159">The user ends the stroke.</span></span>  
  
    1.  <span data-ttu-id="a3fd5-160"><xref:System.Windows.Controls.InkPresenter> 스트로크 해당 시각적 트리를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-160">The <xref:System.Windows.Controls.InkPresenter> adds the stroke to its visual tree.</span></span>  
  
    2.  <span data-ttu-id="a3fd5-161">미디어 통합 계층 (MIL) 스트로크를 정적으로 렌더링합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-161">The Media Integration Layer (MIL) statically renders the strokes.</span></span>  
  
    3.  <span data-ttu-id="a3fd5-162"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 시각적 개체를 정리 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3fd5-162">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> cleans up the visuals.</span></span>
