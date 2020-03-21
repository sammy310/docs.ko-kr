---
title: '방법: 활성 기간이 끝난 Timeline의 FillBehavior 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
ms.openlocfilehash: 1f54f2c1bb49bb7a0301f112a109194ab1a8658e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141175"
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a><span data-ttu-id="65791-102">방법: 활성 기간이 끝난 Timeline의 FillBehavior 지정</span><span class="sxs-lookup"><span data-stu-id="65791-102">How to: Specify the FillBehavior for a Timeline that has Reached the End of Its Active Period</span></span>
<span data-ttu-id="65791-103">이 예제에서는 애니메이션된 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성의 <xref:System.Windows.Media.Animation.Timeline> 비활성을 지정하는 방법을 보여 주며, 이 예제에서는 애니메이션된 속성의 비활성 을 지정하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65791-103">This example shows how to specify the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> for the inactive <xref:System.Windows.Media.Animation.Timeline> of an animated property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65791-104">예제</span><span class="sxs-lookup"><span data-stu-id="65791-104">Example</span></span>  
 <span data-ttu-id="65791-105">a의 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> <xref:System.Windows.Media.Animation.Timeline> 속성은 애니메이션되지 않을 때, 즉 비활성 상태이지만 부모가 <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Timeline> 활성 또는 보류 기간 내에 있을 때 애니메이션된 속성의 값에 어떤 일이 발생하는지 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="65791-105">The <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> determines what happens to the value of an animated property when it is not being animated, that is, when the <xref:System.Windows.Media.Animation.Timeline> is inactive but its parent <xref:System.Windows.Media.Animation.Timeline> is inside its active or hold period.</span></span> <span data-ttu-id="65791-106">예를 들어 애니메이션이 종료된 후에도 애니메이션 속성이 끝 값에 유지되거나 애니메이션이 시작되기 전에 있던 값으로 되돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="65791-106">For example, does an animated property remain at its end value after the animation ends or does it revert back to the value it had before the animation started?</span></span>  
  
 <span data-ttu-id="65791-107">다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation> a를 사용하여 <xref:System.Windows.FrameworkElement.Width%2A> 두 사각형의 애니메이션을 애니메이션합니다.</span><span class="sxs-lookup"><span data-stu-id="65791-107">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.FrameworkElement.Width%2A> of two rectangles.</span></span> <span data-ttu-id="65791-108">각 사각형은 다른 <xref:System.Windows.Media.Animation.Timeline> 개체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="65791-108">Each rectangle uses a different <xref:System.Windows.Media.Animation.Timeline> object.</span></span>  
  
 <span data-ttu-id="65791-109">하나는 사각형의 너비가 <xref:System.Windows.Media.Animation.Timeline> 끝날 때 애니메이션되지 않은 값으로 되돌아갑니다. <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> <xref:System.Windows.Media.Animation.FillBehavior.Stop></span><span class="sxs-lookup"><span data-stu-id="65791-109">One <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> that is set to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, which causes the width of the rectangle to revert back to its non-animated value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span> <span data-ttu-id="65791-110">다른 <xref:System.Windows.Media.Animation.Timeline> 하나는 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 의 <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>를 가지며, 이로 인해 너비가 <xref:System.Windows.Media.Animation.Timeline> 끝날 때 끝 값으로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="65791-110">The other <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> of <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, which causes the width to remain at its end value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 <span data-ttu-id="65791-111">전체 샘플은 [애니메이션 예제 갤러리](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="65791-111">For the complete sample, see [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65791-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="65791-112">See also</span></span>

- <xref:System.Windows.Media.Animation.DoubleAnimation>
- <xref:System.Windows.FrameworkElement.Width%2A>
- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.FillBehavior.Stop>
- <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>
- [<span data-ttu-id="65791-113">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="65791-113">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="65791-114">애니메이션 및 타이밍 방법 항목</span><span class="sxs-lookup"><span data-stu-id="65791-114">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
