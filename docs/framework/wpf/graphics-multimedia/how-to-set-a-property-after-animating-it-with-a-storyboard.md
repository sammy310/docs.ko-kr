---
title: '방법: 스토리보드를 사용하여 애니메이션 효과를 적용한 후 속성 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], changing property values after
ms.assetid: 79466556-4dbf-40bd-9c1e-a77613b07077
ms.openlocfilehash: 2e1389392c6465ed56b2c71e53b2e3c1947acbe2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59188320"
---
# <a name="how-to-set-a-property-after-animating-it-with-a-storyboard"></a><span data-ttu-id="13efa-102">방법: 스토리보드를 사용하여 애니메이션 효과를 적용한 후 속성 설정</span><span class="sxs-lookup"><span data-stu-id="13efa-102">How to: Set a Property After Animating It with a Storyboard</span></span>
<span data-ttu-id="13efa-103">경우에 따라 애니메이션이 적용 된 후에 속성의 값을 변경할 수 없습니다 나타날 것입니다.</span><span class="sxs-lookup"><span data-stu-id="13efa-103">In some cases, it might appear that you can't change the value of a property after it has been animated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13efa-104">예제</span><span class="sxs-lookup"><span data-stu-id="13efa-104">Example</span></span>  
 <span data-ttu-id="13efa-105">다음 예제에서는 <xref:System.Windows.Media.Animation.Storyboard> 색에 애니메이션을 적용 하는 데 사용 되는 <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="13efa-105">In the following example, a <xref:System.Windows.Media.Animation.Storyboard> is used to animate the color of a <xref:System.Windows.Media.SolidColorBrush>.</span></span> <span data-ttu-id="13efa-106">스토리 보드는 단추를 클릭할 때 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="13efa-106">The storyboard is triggered when the button is clicked.</span></span> <span data-ttu-id="13efa-107">합니다 <xref:System.Windows.Media.Animation.Timeline.Completed> 프로그램 알림을 받을 수 있도록 이벤트를 처리 때는 <xref:System.Windows.Media.Animation.ColorAnimation> 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="13efa-107">The <xref:System.Windows.Media.Animation.Timeline.Completed> event is handled so that the program is notified when the <xref:System.Windows.Media.Animation.ColorAnimation> completes.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton1Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton1declaration)]  
  
## <a name="example"></a><span data-ttu-id="13efa-108">예제</span><span class="sxs-lookup"><span data-stu-id="13efa-108">Example</span></span>  
 <span data-ttu-id="13efa-109">이후에 <xref:System.Windows.Media.Animation.ColorAnimation> 완료 되 면 프로그램 하려고 브러시의 색을 파란색을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="13efa-109">After the <xref:System.Windows.Media.Animation.ColorAnimation> completes, the program attempts to change the brush's color to blue.</span></span>  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton1Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton1handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton1Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton1handler)]  
  
 <span data-ttu-id="13efa-110">이전 코드는 작업을 수행할 나타나지: 값인 yellow, 브러시 유지가 제공한는 <xref:System.Windows.Media.Animation.ColorAnimation> 작업도 합니다.</span><span class="sxs-lookup"><span data-stu-id="13efa-110">The previous code doesn't appear to do anything: the brush remains yellow, which is the value supplied by the <xref:System.Windows.Media.Animation.ColorAnimation> that animated the brush.</span></span> <span data-ttu-id="13efa-111">기본 속성 값 (기본값)는 실제로 파란색으로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13efa-111">The underlying property value (the base value) is actually changed to blue.</span></span> <span data-ttu-id="13efa-112">효과적으로 또는 현재 값은 노란색으로 남아 있지만 때문에 <xref:System.Windows.Media.Animation.ColorAnimation> 여전히 기본 값을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="13efa-112">However, the effective, or current, value remains yellow because the <xref:System.Windows.Media.Animation.ColorAnimation> is still overriding the base value.</span></span> <span data-ttu-id="13efa-113">유효한 값을 다시 되도록 기본 값을 원하는 경우 속성에 영향을 주지 애니메이션을 중지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13efa-113">If you want the base value to become the effective value again, you must stop the animation from influencing the property.</span></span> <span data-ttu-id="13efa-114">Storyboard 애니메이션을 사용 하 여이 작업을 수행 하는 방법은 세 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13efa-114">There are three ways to do this with storyboard animations:</span></span>  
  
-   <span data-ttu-id="13efa-115">애니메이션의 설정 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성 <xref:System.Windows.Media.Animation.FillBehavior.Stop></span><span class="sxs-lookup"><span data-stu-id="13efa-115">Set the animation's <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property to <xref:System.Windows.Media.Animation.FillBehavior.Stop></span></span>  
  
-   <span data-ttu-id="13efa-116">전체 스토리 보드를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="13efa-116">Remove the entire Storyboard.</span></span>  
  
-   <span data-ttu-id="13efa-117">개별 속성에서 애니메이션을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="13efa-117">Remove the animation from the individual property.</span></span>  
  
## <a name="set-the-animations-fillbehavior-property-to-stop"></a><span data-ttu-id="13efa-118">애니메이션의 FillBehavior 속성 Stop으로 설정</span><span class="sxs-lookup"><span data-stu-id="13efa-118">Set the animation's FillBehavior property to Stop</span></span>  
 <span data-ttu-id="13efa-119">설정 하 여 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 에 <xref:System.Windows.Media.Animation.FillBehavior.Stop>을 활성 기간의 끝에 도달한 후 대상 속성에 영향을 주지 않으려면 애니메이션을 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="13efa-119">By setting <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, you tell the animation to stop affecting its target property after it reaches the end of its active period.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton2Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton2declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton2Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton2handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton2Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton2handler)]  
  
## <a name="remove-the-entire-storyboard"></a><span data-ttu-id="13efa-120">전체 스토리 보드를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="13efa-120">Remove the entire storyboard</span></span>  
 <span data-ttu-id="13efa-121">사용 하 여는 <xref:System.Windows.Media.Animation.RemoveStoryboard> 트리거 또는 <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType> 메서드를 알리는 해당 대상 속성에 영향을 주지 않으려면 storyboard 애니메이션 합니다.</span><span class="sxs-lookup"><span data-stu-id="13efa-121">By using a <xref:System.Windows.Media.Animation.RemoveStoryboard> trigger or the <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType> method, you tell the storyboard animations to stop affecting their target properties.</span></span> <span data-ttu-id="13efa-122">이 접근 방식 및 설정 간의 차이 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성은 스토리 보드를 제거할 수 있습니다 있는 동안 언제 든 지는 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성에만 효과가 애니메이션 활성 기간의 끝에 도달 합니다.</span><span class="sxs-lookup"><span data-stu-id="13efa-122">The difference between this approach and setting the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property is that you can remove the storyboard at anytime, while the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property only has an effect when the animation reaches the end of its active period.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton3Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton3declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton3Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton3handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton3Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton3handler)]  
  
## <a name="remove-an-animation-from-an-individual-property"></a><span data-ttu-id="13efa-123">개별 속성에서 애니메이션을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="13efa-123">Remove an animation from an individual property</span></span>  
 <span data-ttu-id="13efa-124">애니메이션 속성에 영향을 주지 않으려면 다른 기술을 사용 하는 것은 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> 애니메이션 효과 줄 개체의 메서드.</span><span class="sxs-lookup"><span data-stu-id="13efa-124">Another technique to stop an animation from affecting a property is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> method of the object being animated.</span></span> <span data-ttu-id="13efa-125">첫 번째 매개 변수로 애니메이션 효과가 적용 되는 속성을 지정 하 고 `null` 두 번째입니다.</span><span class="sxs-lookup"><span data-stu-id="13efa-125">Specify the property being animated as the first parameter and `null` as the second.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton4Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton4declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton4Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton4handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton4Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton4handler)]  
  
 <span data-ttu-id="13efa-126">이 기술은 비 storyboard 애니메이션 에서도 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="13efa-126">This technique also works for non-storyboard animations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13efa-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="13efa-127">See also</span></span>

- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Media.Animation.RemoveStoryboard>
- [<span data-ttu-id="13efa-128">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="13efa-128">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="13efa-129">속성 애니메이션 기술 개요</span><span class="sxs-lookup"><span data-stu-id="13efa-129">Property Animation Techniques Overview</span></span>](property-animation-techniques-overview.md)
