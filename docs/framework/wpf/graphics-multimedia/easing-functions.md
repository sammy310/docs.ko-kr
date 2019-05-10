---
title: 감속/가속 함수
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applying mathematical formulas to animations [WPF]
- applying easing functions to animations [WPF]
- mathematical formulas [WPF], applying to animations
- animations [WPF], realistic movement
- easing functions [WPF]
- customizing easing functions [WPF]
- easing functions [WPF], definition
- easing functions [WPF], customizing
- animations [WPF], applying
ms.assetid: 075b9c2b-82c4-43fa-b3cd-de0b6236eb38
ms.openlocfilehash: a74142b8d8ee3a68daa9966e3f20f3b8e3becb72
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64615397"
---
# <a name="easing-functions"></a><span data-ttu-id="2bed9-102">감속/가속 함수</span><span class="sxs-lookup"><span data-stu-id="2bed9-102">Easing Functions</span></span>
<span data-ttu-id="2bed9-103">감속/가속 함수를 사용하여 사용자 지정 수식을 애니메이션에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bed9-103">Easing functions allow you to apply custom mathematical formulas to your animations.</span></span> <span data-ttu-id="2bed9-104">예를 들어 마치 스프링 위에 있는 것처럼 개체가 사실적으로 바운스되거나 동작하도록 하고 싶을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bed9-104">For example, you may want an object to realistically bounce or behave as though it were on a spring.</span></span> <span data-ttu-id="2bed9-105">키 프레임 또는 심지어 From/To/By 애니메이션을 사용하여 이러한 효과를 대략적으로 나타낼 수 있지만 상당히 복잡한 작업이 필요하며 수식을 사용할 때보다 애니메이션이 덜 정확해집니다.</span><span class="sxs-lookup"><span data-stu-id="2bed9-105">You could use Key-Frame or even From/To/By animations to approximate these effects but it would take a significant amount of work and the animation would be less accurate than using a mathematical formula.</span></span>  
  
 <span data-ttu-id="2bed9-106">상속 하 여 사용자 고유의 사용자 지정 감속/가속 함수를 만드는 것 외에 <xref:System.Windows.Media.Animation.EasingFunctionBase>, 일반적인 효과를 만들 런타임에서 제공 하는 여러 감속/가속 함수 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bed9-106">Besides creating your own custom easing function by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>, you can use one of several easing functions provided by the runtime to create common effects.</span></span>  
  
- <span data-ttu-id="2bed9-107"><xref:System.Windows.Media.Animation.BackEase>: 표시 된 경로로 애니메이션을 시작 하기 전에 애니메이션의 이동을 약간 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bed9-107"><xref:System.Windows.Media.Animation.BackEase>: Retracts the motion of an animation slightly before it begins to animate in the path indicated.</span></span>  
  
- <span data-ttu-id="2bed9-108"><xref:System.Windows.Media.Animation.BounceEase>: 바운스 효과 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2bed9-108"><xref:System.Windows.Media.Animation.BounceEase>: Creates a bouncing effect.</span></span>  
  
- <span data-ttu-id="2bed9-109"><xref:System.Windows.Media.Animation.CircleEase>: 및/또는 감속 순환 함수를 사용 하 여 감속 하는 애니메이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2bed9-109"><xref:System.Windows.Media.Animation.CircleEase>: Creates an animation that accelerates and/or decelerates using a circular function.</span></span>  
  
- <span data-ttu-id="2bed9-110"><xref:System.Windows.Media.Animation.CubicEase>: 가속 및/또는 수식을 사용 하 여 감속 하는 애니메이션을 만듭니다 *f*(*t*) = *t*<sup>3</sup>합니다.</span><span class="sxs-lookup"><span data-stu-id="2bed9-110"><xref:System.Windows.Media.Animation.CubicEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>3</sup>.</span></span>  
  
- <span data-ttu-id="2bed9-111"><xref:System.Windows.Media.Animation.ElasticEase>: 완전히 정지할 때까지 앞뒤로 진동 하는 스프링과 유사한 애니메이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2bed9-111"><xref:System.Windows.Media.Animation.ElasticEase>: Creates an animation that resembles a spring oscillating back and forth until it comes to rest.</span></span>  
  
- <span data-ttu-id="2bed9-112"><xref:System.Windows.Media.Animation.ExponentialEase>: 가속 및/또는 지 수 식을 사용 하 여 감속 하는 애니메이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2bed9-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Creates an animation that accelerates and/or decelerates using an exponential formula.</span></span>  
  
- <span data-ttu-id="2bed9-113"><xref:System.Windows.Media.Animation.PowerEase>: 가속 및/또는 수식을 사용 하 여 감속 하는 애니메이션을 만듭니다 *f*(*t*) = *t*<sup>p</sup> 여기서 p는 합니다 같음<xref:System.Windows.Media.Animation.PowerEase.Power%2A>속성입니다.</span><span class="sxs-lookup"><span data-stu-id="2bed9-113"><xref:System.Windows.Media.Animation.PowerEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>p</sup> where p is equal to the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span>  
  
- <span data-ttu-id="2bed9-114"><xref:System.Windows.Media.Animation.QuadraticEase>: 가속 및/또는 수식을 사용 하 여 감속 하는 애니메이션을 만듭니다 *f*(*t*) = *t*<sup>2</sup>합니다.</span><span class="sxs-lookup"><span data-stu-id="2bed9-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>2</sup>.</span></span>  
  
- <span data-ttu-id="2bed9-115"><xref:System.Windows.Media.Animation.QuarticEase>: 가속 및/또는 수식을 사용 하 여 감속 하는 애니메이션을 만듭니다 *f*(*t*) = *t*<sup>4</sup>합니다.</span><span class="sxs-lookup"><span data-stu-id="2bed9-115"><xref:System.Windows.Media.Animation.QuarticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>4</sup>.</span></span>  
  
- <span data-ttu-id="2bed9-116"><xref:System.Windows.Media.Animation.QuinticEase>: 애니메이션을 가속화 및/또는 수식을 사용 하 여 감속 *f*(*t*) = *t*<sup>5</sup>합니다.</span><span class="sxs-lookup"><span data-stu-id="2bed9-116"><xref:System.Windows.Media.Animation.QuinticEase>: Create an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>5</sup>.</span></span>  
  
- <span data-ttu-id="2bed9-117"><xref:System.Windows.Media.Animation.SineEase>: 가속 및/또는 감속 사인 수식을 사용 하는 애니메이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2bed9-117"><xref:System.Windows.Media.Animation.SineEase>: Creates an animation that accelerates and/or decelerates using a sine formula.</span></span>  
  
 <span data-ttu-id="2bed9-118">애니메이션에 감속/가속 함수를 적용 하려면 사용 된 `EasingFunction` 애니메이션의 속성에 애니메이션을 적용할 감속/가속 함수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bed9-118">To apply an easing function to an animation, use the `EasingFunction` property of the animation specify the easing function to apply to the animation.</span></span> <span data-ttu-id="2bed9-119">적용 하는 다음 예제는 <xref:System.Windows.Media.Animation.BounceEase> 감속/가속 함수를를 <xref:System.Windows.Media.Animation.DoubleAnimation> 바운스 효과를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2bed9-119">The following example applies a <xref:System.Windows.Media.Animation.BounceEase> easing function to a <xref:System.Windows.Media.Animation.DoubleAnimation> to create a bouncing effect.</span></span>  
  
 [!code-xaml[BounceEase_snippet#BounceEase](~/samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 <span data-ttu-id="2bed9-120">이전 예제에서는 감속/가속 함수를 From/To/By 애니메이션에 적용했습니다.</span><span class="sxs-lookup"><span data-stu-id="2bed9-120">In the previous example, the easing function was applied to a From/To/By animation.</span></span> <span data-ttu-id="2bed9-121">이러한 감속/가속 함수를 키 프레임 애니메이션에 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bed9-121">You can also apply these easing functions to Key-Frame animations.</span></span> <span data-ttu-id="2bed9-122">다음 예제에서는 키 프레임과 연결된 감속/가속 함수를 사용하여 위로 수축했다가 느려진 다음 아래로 늘어난 후(떨어지는 것처럼) 바운스되었다가 정지되는 사각형의 애니메이션을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2bed9-122">The following example shows how to use key frames with easing functions associated with them to create an animation of a rectangle that contracts upward, slows down, then expands downward (as though falling) and then bounces to a stop.</span></span>  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](~/samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 <span data-ttu-id="2bed9-123">사용할 수는 <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> , 감속/가속 함수가 동작 방식을 변경 하는 속성 애니메이션 보간 방법을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bed9-123">You can use the <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> property to alter how the easing function behaves, that is, change how the animation interpolates.</span></span> <span data-ttu-id="2bed9-124">세 가지 가능한 값에 대해 제공할 수 있습니다 <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span><span class="sxs-lookup"><span data-stu-id="2bed9-124">There are three possible values you can give for <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span></span>  
  
- <span data-ttu-id="2bed9-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: 보간은 감속/가속 함수와 연결 된 수식을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="2bed9-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Interpolation follows the mathematical formula associated with the easing function.</span></span>  
  
- <span data-ttu-id="2bed9-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: 보간은은 100% 보간에서 감속/가속 함수와 연결 된 수식의 출력을 뺀 값을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="2bed9-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Interpolation follows 100% interpolation minus the output of the formula associated with the easing function.</span></span>  
  
- <span data-ttu-id="2bed9-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: 보간 사용 <xref:System.Windows.Media.Animation.EasingMode.EaseIn> 애니메이션의 처음 절반에 대 한 및 <xref:System.Windows.Media.Animation.EasingMode.EaseOut> 하반기에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bed9-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Interpolation uses <xref:System.Windows.Media.Animation.EasingMode.EaseIn> for the first half of the animation and <xref:System.Windows.Media.Animation.EasingMode.EaseOut> for the second half.</span></span>  
  
 <span data-ttu-id="2bed9-128">아래 그래프의 다른 값을 보여 줍니다 <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> 여기서 *f*(*x*)는 애니메이션 진행 상태를 나타냅니다와 *t* 시간을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2bed9-128">The graphs below demonstrate the different values of <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> where *f*(*x*) represents the animation progress and *t* represents time.</span></span>  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 <span data-ttu-id="2bed9-129">![BackEase EasingMode 그래프](./media/backease-graph.png "BackEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="2bed9-129">![BackEase EasingMode graphs.](./media/backease-graph.png "BackEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 <span data-ttu-id="2bed9-130">![BounceEase EasingMode 그래프](./media/bounceease-graph.png "BounceEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="2bed9-130">![BounceEase EasingMode graphs.](./media/bounceease-graph.png "BounceEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 <span data-ttu-id="2bed9-131">![CircleEase EasingMode 그래프](./media/circleease-graph.png "CircleEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="2bed9-131">![CircleEase EasingMode graphs.](./media/circleease-graph.png "CircleEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 <span data-ttu-id="2bed9-132">![CubicEase EasingMode 그래프](./media/cubicease-graph.png "CubicEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="2bed9-132">![CubicEase EasingMode graphs.](./media/cubicease-graph.png "CubicEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 <span data-ttu-id="2bed9-133">![다양한 easingmode 그래프로 나타낸 ElasticEase](./media/elasticease-graph.png "ElasticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="2bed9-133">![ElasticEase with graphs of different easingmodes.](./media/elasticease-graph.png "ElasticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 <span data-ttu-id="2bed9-134">![다양한 easingmode 그래프로 나타낸 ExponentialEase](./media/exponentialease-graph.png "ExponentialEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="2bed9-134">![ExponentialEase graphs of different easingmodes.](./media/exponentialease-graph.png "ExponentialEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 <span data-ttu-id="2bed9-135">![다양한 easingmode 그래프로 나타낸 QuarticEase](./media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="2bed9-135">![QuarticEase with graphs of different easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 <span data-ttu-id="2bed9-136">![다양한 easingmode 그래프로 나타낸 QuadraticEase](./media/quadraticease-graph.png "QuadraticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="2bed9-136">![QuadraticEase with graphs of different easingmodes](./media/quadraticease-graph.png "QuadraticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 <span data-ttu-id="2bed9-137">![다양한 easingmode 그래프로 나타낸 QuarticEase](./media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="2bed9-137">![QuarticEase with graphs of different easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 <span data-ttu-id="2bed9-138">![다양한 easingmode 그래프로 나타낸 QuinticEase](./media/quinticease-graph.png "QuinticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="2bed9-138">![QuinticEase with graphs of different easingmodes.](./media/quinticease-graph.png "QuinticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 <span data-ttu-id="2bed9-139">![다양한 EasingMode 값의 SineEase](./media/sineease-graph.png "SineEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="2bed9-139">![SineEase for different EasingMode values](./media/sineease-graph.png "SineEase_Graph")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2bed9-140">사용할 수 있습니다 <xref:System.Windows.Media.Animation.PowerEase> 와 같은 동작을 만들려면 <xref:System.Windows.Media.Animation.CubicEase>를 <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, 및 <xref:System.Windows.Media.Animation.QuinticEase> 사용 하 여는 <xref:System.Windows.Media.Animation.PowerEase.Power%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="2bed9-140">You can use <xref:System.Windows.Media.Animation.PowerEase> to create the same behavior as <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, and <xref:System.Windows.Media.Animation.QuinticEase> by using the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span> <span data-ttu-id="2bed9-141">예를 들어 사용 하려는 <xref:System.Windows.Media.Animation.PowerEase> 를 대체할 <xref:System.Windows.Media.Animation.CubicEase>, 지정는 <xref:System.Windows.Media.Animation.PowerEase.Power%2A> 값 3입니다.</span><span class="sxs-lookup"><span data-stu-id="2bed9-141">For example, if you want to use <xref:System.Windows.Media.Animation.PowerEase> to substitute for <xref:System.Windows.Media.Animation.CubicEase>, specify a <xref:System.Windows.Media.Animation.PowerEase.Power%2A> value of 3.</span></span>  
  
 <span data-ttu-id="2bed9-142">런타임에 포함 된 감속/가속 함수를 사용 하는 것 외에도 상속 하 여 사용자 고유의 사용자 지정 감속/가속 함수를 만들 수 있습니다 <xref:System.Windows.Media.Animation.EasingFunctionBase>합니다.</span><span class="sxs-lookup"><span data-stu-id="2bed9-142">In addition to using the easing functions included in the run-time, you can create your own custom easing functions by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>.</span></span> <span data-ttu-id="2bed9-143">다음 예제에서는 단일 사용자 지정 감속/가속 함수를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2bed9-143">The following example demonstrates how to create a simple custom easing function.</span></span> <span data-ttu-id="2bed9-144">감속/가속 함수를 재정의 하 여 작동 하는 방법에 대 한 고유한 수학 논리를 추가할 수는 <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="2bed9-144">You can add your own mathematical logic for how the easing function behaves by overriding the <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> method.</span></span>   
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
