---
title: 표시기 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], about adorners
ms.assetid: 33d4c5c2-2daf-4e45-ba9a-5b673e2b8280
ms.openlocfilehash: 22d9b1eddbb6db47fb15deebf94cfc5f8d37a380
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040844"
---
# <a name="adorners-overview"></a><span data-ttu-id="7e6a0-102">표시기 개요</span><span class="sxs-lookup"><span data-stu-id="7e6a0-102">Adorners Overview</span></span>

<span data-ttu-id="7e6a0-103">표시기는 사용자에 게 시각적 신호를 제공 하는 데 사용 되는 특별 한 유형의 <xref:System.Windows.FrameworkElement>입니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-103">Adorners are a special type of <xref:System.Windows.FrameworkElement>, used to provide visual cues to a user.</span></span> <span data-ttu-id="7e6a0-104">표시기는 다른 용도로 요소에 기능 핸들을 추가하거나 컨트롤에 대한 상태 정보를 제공하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-104">Among other uses, Adorners can be used to add functional handles to elements or provide state information about a control.</span></span>

## <a name="about-adorners"></a><span data-ttu-id="7e6a0-105">표시기 정보</span><span class="sxs-lookup"><span data-stu-id="7e6a0-105">About Adorners</span></span>

<span data-ttu-id="7e6a0-106"><xref:System.Windows.Documents.Adorner>는 <xref:System.Windows.UIElement>에 바인딩되는 사용자 지정 <xref:System.Windows.FrameworkElement>입니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-106">An <xref:System.Windows.Documents.Adorner> is a custom <xref:System.Windows.FrameworkElement> that is bound to a <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="7e6a0-107">표시기는 항상 표시 된 요소 또는 표시 된 요소 컬렉션의 맨 위에 있는 렌더링 화면인 <xref:System.Windows.Documents.AdornerLayer>에서 렌더링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-107">Adorners are rendered in an <xref:System.Windows.Documents.AdornerLayer>, which is a rendering surface that is always on top of the adorned element or a collection of adorned elements.</span></span> <span data-ttu-id="7e6a0-108">표시기 렌더링은 표시기가 바인딩되는 <xref:System.Windows.UIElement> 렌더링과는 독립적입니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-108">Rendering of an adorner is independent from rendering of the <xref:System.Windows.UIElement> that the adorner is bound to.</span></span> <span data-ttu-id="7e6a0-109">표시기는 일반적으로 표시한 요소의 왼쪽 위에 있는 표준 2차원 좌표 원점을 사용하여, 바인딩되어 있는 요소에 상대적으로 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-109">An adorner is typically positioned relative to the element to which it is bound, using the standard 2-D coordinate origin located at the upper-left of the adorned element.</span></span>

<span data-ttu-id="7e6a0-110">표시기에 대한 일반 애플리케이션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-110">Common applications for adorners include:</span></span>

- <span data-ttu-id="7e6a0-111">사용자가 요소를 조작 (크기 조정, 회전, 위치 변경 등) 할 수 있도록 하는 <xref:System.Windows.UIElement>에 기능 핸들을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-111">Adding functional handles to a <xref:System.Windows.UIElement> that enable a user to manipulate the element in some way (resize, rotate, reposition, etc.).</span></span>
- <span data-ttu-id="7e6a0-112">다양한 상태를 나타내거나 다양한 이벤트에 대한 응답으로 시각적 피드백을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-112">Provide visual feedback to indicate various states, or in response to various events.</span></span>
- <span data-ttu-id="7e6a0-113"><xref:System.Windows.UIElement>의 오버레이 비주얼 장식입니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-113">Overlay visual decorations on a <xref:System.Windows.UIElement>.</span></span>
- <span data-ttu-id="7e6a0-114"><xref:System.Windows.UIElement>일부 또는 전체를 시각적으로 마스킹 또는 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-114">Visually mask or override part or all of a <xref:System.Windows.UIElement>.</span></span>

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="7e6a0-115">는 시각적 요소를 표시하는 기본 프레임워크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-115">provides a basic framework for adorning visual elements.</span></span> <span data-ttu-id="7e6a0-116">다음 표에 개체 및 해당 용도를 표시할 때 사용되는 기본 유형이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-116">The following table lists the primary types used when adorning objects, and their purpose.</span></span> <span data-ttu-id="7e6a0-117">몇 가지 사용 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-117">Several usage examples follow:</span></span>

|||
|-|-|
|<xref:System.Windows.Documents.Adorner>|<span data-ttu-id="7e6a0-118">모든 구체적인 표시기 구현이 상속받는 추상 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-118">An abstract base class from which all concrete adorner implementations inherit.</span></span>|
|<xref:System.Windows.Documents.AdornerLayer>|<span data-ttu-id="7e6a0-119">하나 이상의 표시한 요소의 표시기에 대한 렌더링 계층을 나타내는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-119">A class representing a rendering layer for the adorner(s) of one or more adorned elements.</span></span>|
|<xref:System.Windows.Documents.AdornerDecorator>|<span data-ttu-id="7e6a0-120">표시기 계층이 요소 컬렉션에 연결될 수 있도록 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-120">A class that enables an adorner layer to be associated with a collection of elements.</span></span>|

## <a name="implementing-a-custom-adorner"></a><span data-ttu-id="7e6a0-121">사용자 지정 표시기 구현</span><span class="sxs-lookup"><span data-stu-id="7e6a0-121">Implementing a Custom Adorner</span></span>

<span data-ttu-id="7e6a0-122">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 제공하는 표시기 프레임워크는 기본적으로 사용자 지정 표시기의 생성을 지원하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-122">The adorners framework provided by [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] is intended primarily to support the creation of custom adorners.</span></span> <span data-ttu-id="7e6a0-123">사용자 지정 표시기는 추상 <xref:System.Windows.Documents.Adorner> 클래스에서 상속 되는 클래스를 구현 하 여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-123">A custom adorner is created by implementing a class that inherits from the abstract <xref:System.Windows.Documents.Adorner> class.</span></span>

> [!NOTE]
> <span data-ttu-id="7e6a0-124"><xref:System.Windows.Documents.Adorner>의 부모는 표시 되는 요소가 아니라 <xref:System.Windows.Documents.Adorner>을 렌더링 하는 <xref:System.Windows.Documents.AdornerLayer>입니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-124">The parent of an <xref:System.Windows.Documents.Adorner> is the <xref:System.Windows.Documents.AdornerLayer> that renders the <xref:System.Windows.Documents.Adorner>, not the element being adorned.</span></span>

<span data-ttu-id="7e6a0-125">다음 예제에서는 간단한 표시기를 구현하는 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-125">The following example shows a class that implements a simple adorner.</span></span> <span data-ttu-id="7e6a0-126">예제 표시기는 단순히 <xref:System.Windows.UIElement>의 모퉁이를 원으로 원으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-126">The example adorner simply adorns the corners of a <xref:System.Windows.UIElement> with circles.</span></span>

[!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
[!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]
  
<span data-ttu-id="7e6a0-127">다음 이미지는 <xref:System.Windows.Controls.TextBox>에 적용 되는 SimpleCircleAdorner를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-127">The following image shows the SimpleCircleAdorner applied to a <xref:System.Windows.Controls.TextBox>:</span></span>

![표시 된 텍스트 상자를 표시 하는 스크린샷](./media/adorners-overview/simplecircleadorner-textbox.png)

## <a name="rendering-behavior-for-adorners"></a><span data-ttu-id="7e6a0-129">표시기에 대한 렌더링 동작</span><span class="sxs-lookup"><span data-stu-id="7e6a0-129">Rendering Behavior for Adorners</span></span>

<span data-ttu-id="7e6a0-130">표시기에는 고유 렌더링 동작이 포함되어 있지 않음에 유의해야 합니다. 표시기를 렌더링하는 것은 표시기 구현자의 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-130">It is important to note that adorners do not include any inherent rendering behavior; ensuring that an adorner renders is the responsibility of the adorner implementer.</span></span> <span data-ttu-id="7e6a0-131">렌더링 동작을 구현 하는 일반적인 방법은 <xref:System.Windows.UIElement.OnRender%2A> 메서드를 재정의 하 고 하나 이상의 <xref:System.Windows.Media.DrawingContext> 개체를 사용 하 여 필요에 따라 표시기의 시각적 개체를 렌더링 하는 것입니다 (위 예제에 표시 된 것 처럼).</span><span class="sxs-lookup"><span data-stu-id="7e6a0-131">A common way of implementing rendering behavior is to override the <xref:System.Windows.UIElement.OnRender%2A> method and use one or more <xref:System.Windows.Media.DrawingContext> objects to render the adorner's visuals as needed (as shown in the example above).</span></span>

> [!NOTE]
> <span data-ttu-id="7e6a0-132">표시기 계층에 배치된 모든 개체는 설정한 스타일의 나머지 부분 맨 위에 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-132">Anything placed in the adorner layer is rendered on top of the rest of any styles you have set.</span></span> <span data-ttu-id="7e6a0-133">즉, 표시기는 시각적으로 항상 맨 위에 있으며 z-순서를 사용하여 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-133">In other words, adorners are always visually on top and cannot be overridden using z-order.</span></span>

## <a name="events-and-hit-testing"></a><span data-ttu-id="7e6a0-134">이벤트 및 적중 횟수 테스트</span><span class="sxs-lookup"><span data-stu-id="7e6a0-134">Events and Hit Testing</span></span>

<span data-ttu-id="7e6a0-135">표시기는 다른 <xref:System.Windows.FrameworkElement>와 마찬가지로 입력 이벤트를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-135">Adorners receive input events just like any other <xref:System.Windows.FrameworkElement>.</span></span>  <span data-ttu-id="7e6a0-136">표시기의 z 순서는 항상 원으로 요소 보다 더 높습니다. 표시기는 기본 표시 된 요소에 사용할 수 있는 입력 이벤트 (예: <xref:System.Windows.UIElement.Drop> 또는 <xref:System.Windows.UIElement.MouseMove>)를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-136">Because an adorner always has a higher z-order than the element it adorns, the adorner receives input events (such as <xref:System.Windows.UIElement.Drop> or <xref:System.Windows.UIElement.MouseMove>) that may be intended for the underlying adorned element.</span></span>  <span data-ttu-id="7e6a0-137">표시기는 특정 입력 이벤트를 수신하고 이벤트를 다시 발생시켜 표시한 기본 요소에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-137">An adorner can listen for certain input events and pass these on to the underlying adorned element by re-raising the event.</span></span>

<span data-ttu-id="7e6a0-138">표시기에서 요소에 대 한 통과 적중 테스트를 사용 하도록 설정 하려면 표시기에서 적중 테스트 <xref:System.Windows.UIElement.IsHitTestVisible%2A> 속성을 **false** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-138">To enable pass-through hit testing of elements under an adorner, set the hit test <xref:System.Windows.UIElement.IsHitTestVisible%2A> property to **false** on the adorner.</span></span>  <span data-ttu-id="7e6a0-139">적중 테스트에 대 한 자세한 내용은 [시각적 계층의 적중 테스트](../graphics-multimedia/hit-testing-in-the-visual-layer.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-139">For more information about hit testing, see [Hit Testing in the Visual Layer](../graphics-multimedia/hit-testing-in-the-visual-layer.md).</span></span>

## <a name="adorning-a-single-uielement"></a><span data-ttu-id="7e6a0-140">단일 UIElement 표시</span><span class="sxs-lookup"><span data-stu-id="7e6a0-140">Adorning a Single UIElement</span></span>

<span data-ttu-id="7e6a0-141">표시기를 특정 <xref:System.Windows.UIElement>바인딩하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-141">To bind an adorner to a particular <xref:System.Windows.UIElement>, follow these steps:</span></span>

1. <span data-ttu-id="7e6a0-142"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> 정적 메서드를 호출 하 여 표시할 <xref:System.Windows.UIElement>에 대 한 <xref:System.Windows.Documents.AdornerLayer> 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-142">Call the static method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to get an <xref:System.Windows.Documents.AdornerLayer> object for the <xref:System.Windows.UIElement> to be adorned.</span></span> <span data-ttu-id="7e6a0-143"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> 지정 된 <xref:System.Windows.UIElement>부터 시작 하 여 시각적 트리를 탐색 하 고 찾은 첫 번째 표시기 계층을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-143"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> walks up the visual tree, starting at the specified <xref:System.Windows.UIElement>, and returns the first adorner layer it finds.</span></span> <span data-ttu-id="7e6a0-144">(표시기 계층이 없으면 메서드가 null을 반환합니다.)</span><span class="sxs-lookup"><span data-stu-id="7e6a0-144">(If no adorner layers are found, the method returns null.)</span></span>

2. <span data-ttu-id="7e6a0-145"><xref:System.Windows.Documents.AdornerLayer.Add%2A> 메서드를 호출 하 여 표시기를 대상 <xref:System.Windows.UIElement>에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-145">Call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind the adorner to the target <xref:System.Windows.UIElement>.</span></span>

 <span data-ttu-id="7e6a0-146">다음 예에서는 SimpleCircleAdorner (위에 표시 됨)를 *Mytextbox*라는 <xref:System.Windows.Controls.TextBox>에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-146">The following example binds a SimpleCircleAdorner (shown above) to a <xref:System.Windows.Controls.TextBox> named *myTextBox*:</span></span>

 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]

> [!NOTE]
> <span data-ttu-id="7e6a0-147">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]를 사용하여 표시기를 다른 요소에 바인딩하는 것은 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-147">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>

## <a name="adorning-the-children-of-a-panel"></a><span data-ttu-id="7e6a0-148">패널의 자식 표시</span><span class="sxs-lookup"><span data-stu-id="7e6a0-148">Adorning the Children of a Panel</span></span>

<span data-ttu-id="7e6a0-149">표시기를 <xref:System.Windows.Controls.Panel>자식에 바인딩하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-149">To bind an adorner to the children of a <xref:System.Windows.Controls.Panel>, follow these steps:</span></span>

1. <span data-ttu-id="7e6a0-150">`static` 메서드 <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>를 호출 하 여 자식을 표시할 요소의 표시기 계층을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-150">Call the `static` method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to find an adorner layer for the element whose children are to be adorned.</span></span>

2. <span data-ttu-id="7e6a0-151">부모 요소의 자식을 열거 하 고 <xref:System.Windows.Documents.AdornerLayer.Add%2A> 메서드를 호출 하 여 각 자식 요소에 표시기를 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-151">Enumerate through the children of the parent element and call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind an adorner to each child element.</span></span>

<span data-ttu-id="7e6a0-152">다음 예제에서는 SimpleCircleAdorner (위에 표시 됨)를 *Mystackpanel*이라는 <xref:System.Windows.Controls.StackPanel>의 자식에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="7e6a0-152">The following example binds a SimpleCircleAdorner (shown above) to the children of a <xref:System.Windows.Controls.StackPanel> named *myStackPanel*:</span></span>

[!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
[!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]

## <a name="see-also"></a><span data-ttu-id="7e6a0-153">참조</span><span class="sxs-lookup"><span data-stu-id="7e6a0-153">See also</span></span>

- <xref:System.Windows.Media.AdornerHitTestResult>
- [<span data-ttu-id="7e6a0-154">WPF에서 Shape 및 기본 그리기 개요</span><span class="sxs-lookup"><span data-stu-id="7e6a0-154">Shapes and Basic Drawing in WPF Overview</span></span>](../graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="7e6a0-155">이미지, 그림 및 시각적 표시로 그리기</span><span class="sxs-lookup"><span data-stu-id="7e6a0-155">Painting with Images, Drawings, and Visuals</span></span>](../graphics-multimedia/painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="7e6a0-156">Drawing 개체 개요</span><span class="sxs-lookup"><span data-stu-id="7e6a0-156">Drawing Objects Overview</span></span>](../graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="7e6a0-157">방법 항목</span><span class="sxs-lookup"><span data-stu-id="7e6a0-157">How-to Topics</span></span>](adorners-how-to-topics.md)
