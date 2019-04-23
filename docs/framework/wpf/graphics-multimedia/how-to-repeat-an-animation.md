---
title: '방법: 애니메이션 반복'
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
ms.openlocfilehash: a80f72b0e67c13890d4befcbd5ab7c4a92a93fe7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150542"
---
# <a name="how-to-repeat-an-animation"></a><span data-ttu-id="40cf4-102">방법: 애니메이션 반복</span><span class="sxs-lookup"><span data-stu-id="40cf4-102">How to: Repeat an Animation</span></span>
<span data-ttu-id="40cf4-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 의 속성을 <xref:System.Windows.Media.Animation.Timeline> 애니메이션의 반복 동작을 제어 하기 위해.</span><span class="sxs-lookup"><span data-stu-id="40cf4-103">This example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> in order to control the repeat behavior of an animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40cf4-104">예제</span><span class="sxs-lookup"><span data-stu-id="40cf4-104">Example</span></span>  
 <span data-ttu-id="40cf4-105">합니다 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 의 속성을 <xref:System.Windows.Media.Animation.Timeline> 애니메이션이 단순 지속 시간을 반복 횟수를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="40cf4-105">The <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> controls how many times an animation repeats its simple duration.</span></span> <span data-ttu-id="40cf4-106">사용 하 여 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>를 지정할 수 있습니다는 <xref:System.Windows.Media.Animation.Timeline> 동안 특정 횟수 만큼 반복 (반복 횟수) 또는 지정된 된 기간에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="40cf4-106">By using <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, you can specify that a <xref:System.Windows.Media.Animation.Timeline> repeats for a certain number of times (an iteration count) or for a specified time period.</span></span> <span data-ttu-id="40cf4-107">두 경우 모두 애니메이션 하는 요청 된 횟수 또는 기간을 입력 하는 데 필요한 만큼 시작-끝 실행을 통해 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="40cf4-107">In either case, the animation goes through as many beginning-to-end runs that it needs in order to fill the requested count or duration.</span></span>  
  
 <span data-ttu-id="40cf4-108">기본적으로 타임 라인 반복 실행 횟수가 한 번만 재생 되 고 반복 되지 않는 1.0 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="40cf4-108">By default, timelines have a repeat count of 1.0, which means they play one time and do not repeat.</span></span> <span data-ttu-id="40cf4-109">그러나 설정 하는 경우는 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 의 속성을 <xref:System.Windows.Media.Animation.Timeline> 에 <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, 타임 라인이 무기한 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="40cf4-109">However, if you set the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> to <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, the timeline repeats indefinitely.</span></span>  
  
 <span data-ttu-id="40cf4-110">다음 예제에서는 사용 하는 방법의 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 애니메이션의 반복 동작을 제어 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="40cf4-110">The following example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property to control the repeat behavior of an animation.</span></span> <span data-ttu-id="40cf4-111">예제에서는 애니메이션을 적용 합니다 <xref:System.Windows.FrameworkElement.Width%2A> 다른 유형의 반복 동작을 사용 하 여 각 사각형을 사용 하 여 5 개의 사각형의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="40cf4-111">The example animates the <xref:System.Windows.FrameworkElement.Width%2A> property of five rectangles with each rectangle using a different type of repeat behavior.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 <span data-ttu-id="40cf4-112">전체 샘플을 참조 하세요 [애니메이션 타이밍 동작 샘플](https://go.microsoft.com/fwlink/?LinkID=159970)합니다.</span><span class="sxs-lookup"><span data-stu-id="40cf4-112">For the complete sample, see [Animation Timing Behavior Sample](https://go.microsoft.com/fwlink/?LinkID=159970).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40cf4-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="40cf4-113">See also</span></span>

- [<span data-ttu-id="40cf4-114">주기가 반복되는 동안 애니메이션 값 누적</span><span class="sxs-lookup"><span data-stu-id="40cf4-114">Accumulate Animation Values During Repeat Cycles</span></span>](how-to-accumulate-animation-values-during-repeat-cycles.md)
- [<span data-ttu-id="40cf4-115">타임라인을 자동으로 뒤집을지 여부 지정</span><span class="sxs-lookup"><span data-stu-id="40cf4-115">Specify Whether a Timeline Automatically Reverses</span></span>](how-to-specify-whether-a-timeline-automatically-reverses.md)
- [<span data-ttu-id="40cf4-116">애니메이션 및 타이밍 방법 항목</span><span class="sxs-lookup"><span data-stu-id="40cf4-116">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="40cf4-117">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="40cf4-117">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="40cf4-118">애니메이션 타이밍 동작 샘플</span><span class="sxs-lookup"><span data-stu-id="40cf4-118">Animation Timing Behavior Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159970)
