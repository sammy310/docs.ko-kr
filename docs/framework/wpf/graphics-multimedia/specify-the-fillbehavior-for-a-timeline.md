---
title: '방법: 활성 기간 끝에 도달한 Timeline에 대한 FillBehavior 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
ms.openlocfilehash: 9f03c5b8d4585c32e0a9f119649dd15a23523033
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091127"
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a><span data-ttu-id="ff1de-102">방법: 활성 기간 끝에 도달한 Timeline에 대한 FillBehavior 지정</span><span class="sxs-lookup"><span data-stu-id="ff1de-102">How to: Specify the FillBehavior for a Timeline that has Reached the End of Its Active Period</span></span>
<span data-ttu-id="ff1de-103">지정 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 비활성에 대 한 <xref:System.Windows.Media.Animation.Timeline> 의 애니메이션된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ff1de-103">This example shows how to specify the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> for the inactive <xref:System.Windows.Media.Animation.Timeline> of an animated property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff1de-104">예제</span><span class="sxs-lookup"><span data-stu-id="ff1de-104">Example</span></span>  
 <span data-ttu-id="ff1de-105"><xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 의 속성을 <xref:System.Windows.Media.Animation.Timeline> 되 고 있지 않습니다 때 애니메이션된 속성의 값에 수행할 작업을 결정 애니메이션, 즉, 경우를 <xref:System.Windows.Media.Animation.Timeline> 만 부모 활성 상태가 아닙니다 <xref:System.Windows.Media.Animation.Timeline> 는 활성 또는 보관 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="ff1de-105">The <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> determines what happens to the value of an animated property when it is not being animated, that is, when the <xref:System.Windows.Media.Animation.Timeline> is inactive but its parent <xref:System.Windows.Media.Animation.Timeline> is inside its active or hold period.</span></span> <span data-ttu-id="ff1de-106">예를 들어 애니메이션된 속성 계속 됩니다 끝 후 애니메이션 종료 나 되는 값은 애니메이션이 시작 되기 전의 값 돌아갑니다?</span><span class="sxs-lookup"><span data-stu-id="ff1de-106">For example, does an animated property remain at its end value after the animation ends or does it revert back to the value it had before the animation started?</span></span>  
  
 <span data-ttu-id="ff1de-107">다음 예에서는 <xref:System.Windows.Media.Animation.DoubleAnimation> 애니메이션 효과를 주는 <xref:System.Windows.FrameworkElement.Width%2A> 두 개의 사각형의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff1de-107">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.FrameworkElement.Width%2A> of two rectangles.</span></span> <span data-ttu-id="ff1de-108">각 사각형을 사용 하 여 다른 <xref:System.Windows.Media.Animation.Timeline> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ff1de-108">Each rectangle uses a different <xref:System.Windows.Media.Animation.Timeline> object.</span></span>  
  
 <span data-ttu-id="ff1de-109">하나 <xref:System.Windows.Media.Animation.Timeline> 에 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 로 설정 된 <xref:System.Windows.Media.Animation.FillBehavior.Stop>, 다시 돌아가려면 해당 애니메이션이 적용 되지 않은 사각형의 너비 값는 <xref:System.Windows.Media.Animation.Timeline> 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff1de-109">One <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> that is set to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, which causes the width of the rectangle to revert back to its non-animated value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span> <span data-ttu-id="ff1de-110">다른 <xref:System.Windows.Media.Animation.Timeline> 에 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 의 <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, 너비의 끝에 유지 되기 때문에 경우이 값을 <xref:System.Windows.Media.Animation.Timeline> 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff1de-110">The other <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> of <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, which causes the width to remain at its end value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 <span data-ttu-id="ff1de-111">전체 샘플을 참조 하세요 [애니메이션 예제 갤러리](https://go.microsoft.com/fwlink/?LinkID=159969)합니다.</span><span class="sxs-lookup"><span data-stu-id="ff1de-111">For the complete sample, see [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff1de-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="ff1de-112">See also</span></span>

- <xref:System.Windows.Media.Animation.DoubleAnimation>
- <xref:System.Windows.FrameworkElement.Width%2A>
- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.FillBehavior.Stop>
- <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>
- [<span data-ttu-id="ff1de-113">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="ff1de-113">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="ff1de-114">애니메이션 및 타이밍 방법 항목</span><span class="sxs-lookup"><span data-stu-id="ff1de-114">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
