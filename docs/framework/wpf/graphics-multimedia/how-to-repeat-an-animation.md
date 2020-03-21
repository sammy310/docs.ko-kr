---
title: '방법: 애니메이션 반복'
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
ms.openlocfilehash: 1512c49a658c80f3ab6af652839c3562af3dd205
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141551"
---
# <a name="how-to-repeat-an-animation"></a><span data-ttu-id="98696-102">방법: 애니메이션 반복</span><span class="sxs-lookup"><span data-stu-id="98696-102">How to: Repeat an Animation</span></span>
<span data-ttu-id="98696-103">이 예제에서는 애니메이션의 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 반복 <xref:System.Windows.Media.Animation.Timeline> 동작을 제어하기 위해 a의 속성을 사용하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98696-103">This example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> in order to control the repeat behavior of an animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98696-104">예제</span><span class="sxs-lookup"><span data-stu-id="98696-104">Example</span></span>  
 <span data-ttu-id="98696-105">애니메이션의 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> <xref:System.Windows.Media.Animation.Timeline> 속성은 애니메이션이 간단한 지속 시간을 반복하는 횟수를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="98696-105">The <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> controls how many times an animation repeats its simple duration.</span></span> <span data-ttu-id="98696-106">을 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>사용하여 특정 횟수(반복 개수) 또는 지정된 기간 동안 <xref:System.Windows.Media.Animation.Timeline> 반복되도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98696-106">By using <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, you can specify that a <xref:System.Windows.Media.Animation.Timeline> repeats for a certain number of times (an iteration count) or for a specified time period.</span></span> <span data-ttu-id="98696-107">두 경우 모두 애니메이션은 요청된 개수 또는 기간을 채우기 위해 필요한 많은 시작-끝 실행을 거칩니다.</span><span class="sxs-lookup"><span data-stu-id="98696-107">In either case, the animation goes through as many beginning-to-end runs that it needs in order to fill the requested count or duration.</span></span>  
  
 <span data-ttu-id="98696-108">기본적으로 타임라인의 반복 수는 1.0이며, 이는 한 번 재생되고 반복되지 않음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="98696-108">By default, timelines have a repeat count of 1.0, which means they play one time and do not repeat.</span></span> <span data-ttu-id="98696-109">그러나 에 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>의 속성을 설정 하면 타임라인이 무기한 반복 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98696-109">However, if you set the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> to <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, the timeline repeats indefinitely.</span></span>  
  
 <span data-ttu-id="98696-110">다음 예제에서는 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성을 사용하여 애니메이션의 반복 동작을 제어하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98696-110">The following example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property to control the repeat behavior of an animation.</span></span> <span data-ttu-id="98696-111">이 예제는 다른 <xref:System.Windows.FrameworkElement.Width%2A> 유형의 반복 동작을 사용하여 각 사각형과 함께 5개의 사각형의 속성을 애니메이션합니다.</span><span class="sxs-lookup"><span data-stu-id="98696-111">The example animates the <xref:System.Windows.FrameworkElement.Width%2A> property of five rectangles with each rectangle using a different type of repeat behavior.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 <span data-ttu-id="98696-112">전체 샘플은 [애니메이션 타이밍 동작 샘플을](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="98696-112">For the complete sample, see [Animation Timing Behavior Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98696-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="98696-113">See also</span></span>

- [<span data-ttu-id="98696-114">주기가 반복되는 동안 애니메이션 값 누적</span><span class="sxs-lookup"><span data-stu-id="98696-114">Accumulate Animation Values During Repeat Cycles</span></span>](how-to-accumulate-animation-values-during-repeat-cycles.md)
- [<span data-ttu-id="98696-115">타임라인을 자동으로 뒤집을지 여부 지정</span><span class="sxs-lookup"><span data-stu-id="98696-115">Specify Whether a Timeline Automatically Reverses</span></span>](how-to-specify-whether-a-timeline-automatically-reverses.md)
- [<span data-ttu-id="98696-116">애니메이션 및 타이밍 방법 항목</span><span class="sxs-lookup"><span data-stu-id="98696-116">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="98696-117">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="98696-117">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="98696-118">애니메이션 타이밍 동작 샘플</span><span class="sxs-lookup"><span data-stu-id="98696-118">Animation Timing Behavior Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)
