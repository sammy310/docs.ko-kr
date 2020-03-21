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
ms.openlocfilehash: a25bde5098af853c3906a174a189fc35f33f0525
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186494"
---
# <a name="easing-functions"></a><span data-ttu-id="8fde8-102">감속/가속 함수</span><span class="sxs-lookup"><span data-stu-id="8fde8-102">Easing Functions</span></span>
<span data-ttu-id="8fde8-103">감속/가속 함수를 사용하여 사용자 지정 수식을 애니메이션에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fde8-103">Easing functions allow you to apply custom mathematical formulas to your animations.</span></span> <span data-ttu-id="8fde8-104">예를 들어 마치 스프링 위에 있는 것처럼 개체가 사실적으로 바운스되거나 동작하도록 하고 싶을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fde8-104">For example, you may want an object to realistically bounce or behave as though it were on a spring.</span></span> <span data-ttu-id="8fde8-105">키 프레임 또는 심지어 From/To/By 애니메이션을 사용하여 이러한 효과를 대략적으로 나타낼 수 있지만 상당히 복잡한 작업이 필요하며 수식을 사용할 때보다 애니메이션이 덜 정확해집니다.</span><span class="sxs-lookup"><span data-stu-id="8fde8-105">You could use Key-Frame or even From/To/By animations to approximate these effects but it would take a significant amount of work and the animation would be less accurate than using a mathematical formula.</span></span>  
  
 <span data-ttu-id="8fde8-106"><xref:System.Windows.Media.Animation.EasingFunctionBase>에서 상속 하여 사용자 지정 감속/가속 함수를 만드는 것 외에도 런타임에서 제공하는 여러 감속/가속 함수 중 하나를 사용하여 공통 효과를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fde8-106">Besides creating your own custom easing function by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>, you can use one of several easing functions provided by the runtime to create common effects.</span></span>  
  
- <span data-ttu-id="8fde8-107"><xref:System.Windows.Media.Animation.BackEase>: 애니메이션이 표시된 경로에 애니메이션이 되기 전에 애니메이션의 모션을 약간 후퇴합니다.</span><span class="sxs-lookup"><span data-stu-id="8fde8-107"><xref:System.Windows.Media.Animation.BackEase>: Retracts the motion of an animation slightly before it begins to animate in the path indicated.</span></span>  
  
- <span data-ttu-id="8fde8-108"><xref:System.Windows.Media.Animation.BounceEase>: 바운싱 효과를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8fde8-108"><xref:System.Windows.Media.Animation.BounceEase>: Creates a bouncing effect.</span></span>  
  
- <span data-ttu-id="8fde8-109"><xref:System.Windows.Media.Animation.CircleEase>: 원형 함수를 사용하여 가속 및/또는 감속하는 애니메이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8fde8-109"><xref:System.Windows.Media.Animation.CircleEase>: Creates an animation that accelerates and/or decelerates using a circular function.</span></span>  
  
- <span data-ttu-id="8fde8-110"><xref:System.Windows.Media.Animation.CubicEase>: 수식 *f\*\*(t)*= *t*<sup>3을</sup>사용하여 가속 및 / 또는 감속하는 애니메이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8fde8-110"><xref:System.Windows.Media.Animation.CubicEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>3</sup>.</span></span>  
  
- <span data-ttu-id="8fde8-111"><xref:System.Windows.Media.Animation.ElasticEase>: 쉬기 전까지 앞뒤로 진동하는 스프링과 유사한 애니메이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8fde8-111"><xref:System.Windows.Media.Animation.ElasticEase>: Creates an animation that resembles a spring oscillating back and forth until it comes to rest.</span></span>  
  
- <span data-ttu-id="8fde8-112"><xref:System.Windows.Media.Animation.ExponentialEase>: 지수 수식을 사용하여 가속 및/또는 감속하는 애니메이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8fde8-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Creates an animation that accelerates and/or decelerates using an exponential formula.</span></span>  
  
- <span data-ttu-id="8fde8-113"><xref:System.Windows.Media.Animation.PowerEase>: p가 속성과 동일한 수식 *f\*\*(t)*= *t*<sup>p를</sup> 사용하여 가속 <xref:System.Windows.Media.Animation.PowerEase.Power%2A> 및 / 또는 감속하는 애니메이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8fde8-113"><xref:System.Windows.Media.Animation.PowerEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>p</sup> where p is equal to the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span>  
  
- <span data-ttu-id="8fde8-114"><xref:System.Windows.Media.Animation.QuadraticEase>: 수식 *f\*\*(t)*= *t*<sup>2를</sup>사용하여 가속 및 / 또는 감속하는 애니메이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8fde8-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>2</sup>.</span></span>  
  
- <span data-ttu-id="8fde8-115"><xref:System.Windows.Media.Animation.QuarticEase>: 수식 *f\*\*(t)*= *t*<sup>4를</sup>사용하여 가속 및 / 또는 감속하는 애니메이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8fde8-115"><xref:System.Windows.Media.Animation.QuarticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>4</sup>.</span></span>  
  
- <span data-ttu-id="8fde8-116"><xref:System.Windows.Media.Animation.QuinticEase>: 수식 *f\*\*(t)*= *t*<sup>5를</sup>사용하여 가속 및 / 또는 감속하는 애니메이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8fde8-116"><xref:System.Windows.Media.Animation.QuinticEase>: Create an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>5</sup>.</span></span>  
  
- <span data-ttu-id="8fde8-117"><xref:System.Windows.Media.Animation.SineEase>: sine 수식을 사용하여 가속 및/또는 감속하는 애니메이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8fde8-117"><xref:System.Windows.Media.Animation.SineEase>: Creates an animation that accelerates and/or decelerates using a sine formula.</span></span>  
  
 <span data-ttu-id="8fde8-118">애니메이션에 감속/가속 함수를 `EasingFunction` 적용하려면 애니메이션의 속성을 사용하여 애니메이션에 적용할 감속/가속 함수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8fde8-118">To apply an easing function to an animation, use the `EasingFunction` property of the animation specify the easing function to apply to the animation.</span></span> <span data-ttu-id="8fde8-119">적용 하는 다음 예제는 <xref:System.Windows.Media.Animation.BounceEase> 감속/가속 함수를를 <xref:System.Windows.Media.Animation.DoubleAnimation> 바운스 효과를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8fde8-119">The following example applies a <xref:System.Windows.Media.Animation.BounceEase> easing function to a <xref:System.Windows.Media.Animation.DoubleAnimation> to create a bouncing effect.</span></span>  
  
 [!code-xaml[BounceEase_snippet#BounceEase](~/samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 <span data-ttu-id="8fde8-120">이전 예제에서는 감속/가속 함수를 From/To/By 애니메이션에 적용했습니다.</span><span class="sxs-lookup"><span data-stu-id="8fde8-120">In the previous example, the easing function was applied to a From/To/By animation.</span></span> <span data-ttu-id="8fde8-121">이러한 감속/가속 함수를 키 프레임 애니메이션에 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fde8-121">You can also apply these easing functions to Key-Frame animations.</span></span> <span data-ttu-id="8fde8-122">다음 예제에서는 키 프레임과 연결된 감속/가속 함수를 사용하여 위로 수축했다가 느려진 다음 아래로 늘어난 후(떨어지는 것처럼) 바운스되었다가 정지되는 사각형의 애니메이션을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8fde8-122">The following example shows how to use key frames with easing functions associated with them to create an animation of a rectangle that contracts upward, slows down, then expands downward (as though falling) and then bounces to a stop.</span></span>  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](~/samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 <span data-ttu-id="8fde8-123">속성을 <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> 사용하여 감속/가속 함수의 작동 방식, 즉 애니메이션보간 방식을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fde8-123">You can use the <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> property to alter how the easing function behaves, that is, change how the animation interpolates.</span></span> <span data-ttu-id="8fde8-124">세 가지 가능한 값에 <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>대해 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fde8-124">There are three possible values you can give for <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span></span>  
  
- <span data-ttu-id="8fde8-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: 보간은 감속/가속 함수와 관련된 수학 공식을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="8fde8-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Interpolation follows the mathematical formula associated with the easing function.</span></span>  
  
- <span data-ttu-id="8fde8-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: 보간은 감속/가속 함수와 연관된 수식의 출력을 뺀 100% 보간을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="8fde8-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Interpolation follows 100% interpolation minus the output of the formula associated with the easing function.</span></span>  
  
- <span data-ttu-id="8fde8-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: 보간은 <xref:System.Windows.Media.Animation.EasingMode.EaseIn> 애니메이션의 전반부와 <xref:System.Windows.Media.Animation.EasingMode.EaseOut> 후반부에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8fde8-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Interpolation uses <xref:System.Windows.Media.Animation.EasingMode.EaseIn> for the first half of the animation and <xref:System.Windows.Media.Animation.EasingMode.EaseOut> for the second half.</span></span>  
  
 <span data-ttu-id="8fde8-128">아래 그래프는 *f(x)가*애니메이션*x*진행률을 나타내고 *t가* 시간을 나타내는 위치의 <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> 다른 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8fde8-128">The graphs below demonstrate the different values of <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> where *f*(*x*) represents the animation progress and *t* represents time.</span></span>  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 <span data-ttu-id="8fde8-129">![BackEase EasingMode 그래프](./media/backease-graph.png "BackEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="8fde8-129">![BackEase EasingMode graphs.](./media/backease-graph.png "BackEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 <span data-ttu-id="8fde8-130">![BounceEase EasingMode 그래프](./media/bounceease-graph.png "BounceEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="8fde8-130">![BounceEase EasingMode graphs.](./media/bounceease-graph.png "BounceEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 <span data-ttu-id="8fde8-131">![CircleEase EasingMode 그래프](./media/circleease-graph.png "CircleEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="8fde8-131">![CircleEase EasingMode graphs.](./media/circleease-graph.png "CircleEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 <span data-ttu-id="8fde8-132">![CubicEase EasingMode 그래프](./media/cubicease-graph.png "CubicEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="8fde8-132">![CubicEase EasingMode graphs.](./media/cubicease-graph.png "CubicEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 <span data-ttu-id="8fde8-133">![다양한 easingmode 그래프로 나타낸 ElasticEase](./media/elasticease-graph.png "ElasticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="8fde8-133">![ElasticEase with graphs of different easingmodes.](./media/elasticease-graph.png "ElasticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 <span data-ttu-id="8fde8-134">![다양한 easingmode 그래프로 나타낸 ExponentialEase](./media/exponentialease-graph.png "ExponentialEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="8fde8-134">![ExponentialEase graphs of different easingmodes.](./media/exponentialease-graph.png "ExponentialEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 <span data-ttu-id="8fde8-135">![다양한 easingmode 그래프로 나타낸 QuarticEase](./media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="8fde8-135">![QuarticEase with graphs of different easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 <span data-ttu-id="8fde8-136">![다양한 easingmode 그래프로 나타낸 QuadraticEase](./media/quadraticease-graph.png "QuadraticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="8fde8-136">![QuadraticEase with graphs of different easingmodes](./media/quadraticease-graph.png "QuadraticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 <span data-ttu-id="8fde8-137">![다양한 easingmode 그래프로 나타낸 QuarticEase](./media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="8fde8-137">![QuarticEase with graphs of different easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 <span data-ttu-id="8fde8-138">![다양한 easingmode 그래프로 나타낸 QuinticEase](./media/quinticease-graph.png "QuinticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="8fde8-138">![QuinticEase with graphs of different easingmodes.](./media/quinticease-graph.png "QuinticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 <span data-ttu-id="8fde8-139">![다양한 EasingMode 값의 SineEase](./media/sineease-graph.png "SineEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="8fde8-139">![SineEase for different EasingMode values](./media/sineease-graph.png "SineEase_Graph")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8fde8-140">사용할 수 있습니다 <xref:System.Windows.Media.Animation.PowerEase> 와 같은 동작을 만들려면 <xref:System.Windows.Media.Animation.CubicEase>를 <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, 및 <xref:System.Windows.Media.Animation.QuinticEase> 사용 하 여는 <xref:System.Windows.Media.Animation.PowerEase.Power%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="8fde8-140">You can use <xref:System.Windows.Media.Animation.PowerEase> to create the same behavior as <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, and <xref:System.Windows.Media.Animation.QuinticEase> by using the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span> <span data-ttu-id="8fde8-141">예를 들어 사용 하려는 <xref:System.Windows.Media.Animation.PowerEase> 를 대체할 <xref:System.Windows.Media.Animation.CubicEase>, 지정는 <xref:System.Windows.Media.Animation.PowerEase.Power%2A> 값 3입니다.</span><span class="sxs-lookup"><span data-stu-id="8fde8-141">For example, if you want to use <xref:System.Windows.Media.Animation.PowerEase> to substitute for <xref:System.Windows.Media.Animation.CubicEase>, specify a <xref:System.Windows.Media.Animation.PowerEase.Power%2A> value of 3.</span></span>  
  
 <span data-ttu-id="8fde8-142">런타임에 포함 된 감속/가속 함수를 사용 하는 것 외에도 상속 하 여 사용자 고유의 사용자 지정 감속/가속 함수를 만들 수 있습니다 <xref:System.Windows.Media.Animation.EasingFunctionBase>합니다.</span><span class="sxs-lookup"><span data-stu-id="8fde8-142">In addition to using the easing functions included in the run-time, you can create your own custom easing functions by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>.</span></span> <span data-ttu-id="8fde8-143">다음 예제에서는 단일 사용자 지정 감속/가속 함수를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8fde8-143">The following example demonstrates how to create a simple custom easing function.</span></span> <span data-ttu-id="8fde8-144">감속/가속 함수를 재정의 하 여 작동 하는 방법에 대 한 고유한 수학 논리를 추가할 수는 <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="8fde8-144">You can add your own mathematical logic for how the easing function behaves by overriding the <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> method.</span></span>
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
