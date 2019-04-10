---
title: '방법: 애니메이션 지속 시간 설정'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], duration
- Timelines [WPF], description
- duration of animations [WPF]
ms.assetid: 155034ef-7d00-4416-a73c-b1713992d2eb
ms.openlocfilehash: bdae1689ffeb8c54d756b9debbd26d57a052892d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198792"
---
# <a name="how-to-set-a-duration-for-an-animation"></a><span data-ttu-id="49e9d-102">방법: 애니메이션 지속 시간 설정</span><span class="sxs-lookup"><span data-stu-id="49e9d-102">How to: Set a Duration for an Animation</span></span>
<span data-ttu-id="49e9d-103">A <xref:System.Windows.Media.Animation.Timeline> 시간의 세그먼트와 세그먼트의 길이 타임 라인의 의해 결정 됩니다 나타내는 <xref:System.Windows.Duration>합니다.</span><span class="sxs-lookup"><span data-stu-id="49e9d-103">A <xref:System.Windows.Media.Animation.Timeline> represents a segment of time and the length of that segment is determined by the timeline's <xref:System.Windows.Duration>.</span></span> <span data-ttu-id="49e9d-104">경우는 <xref:System.Windows.Media.Animation.Timeline> 끝에 도달 하면 해당 기간의 재생이 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="49e9d-104">When a <xref:System.Windows.Media.Animation.Timeline> reaches the end of its duration, it stops playing.</span></span> <span data-ttu-id="49e9d-105">경우는 <xref:System.Windows.Media.Animation.Timeline> 자식 타임 라인에도 재생을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="49e9d-105">If the <xref:System.Windows.Media.Animation.Timeline> has child timelines, they stop playing as well.</span></span> <span data-ttu-id="49e9d-106">애니메이션의 경우는 <xref:System.Windows.Duration> 애니메이션 걸리는 전환에서 해당 시작 값 끝 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="49e9d-106">In the case of an animation, the <xref:System.Windows.Duration> specifies how long the animation takes to transition from its starting value to its ending value.</span></span>  
  
 <span data-ttu-id="49e9d-107">지정할 수 있습니다는 <xref:System.Windows.Duration> 제한 된 특정 시간 또는 특수 한 값을 가진 <xref:System.Windows.Duration.Automatic%2A> 또는 <xref:System.Windows.Duration.Forever%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="49e9d-107">You can specify a <xref:System.Windows.Duration> with a specific, finite time or the special values <xref:System.Windows.Duration.Automatic%2A> or <xref:System.Windows.Duration.Forever%2A>.</span></span> <span data-ttu-id="49e9d-108">애니메이션에서 정의 되 고 유한 길이가 항상 있어야 하므로 애니메이션의 지속 시간 값을 반드시 해야-그러지 애니메이션 사실을 해당 대상 값 사이 전환 하는 방법을 알지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="49e9d-108">An animation's duration must always be a time value, because an animation must always have a defined, finite length—otherwise, the animation would not know how to transition between its target values.</span></span> <span data-ttu-id="49e9d-109">컨테이너 타임 라인 (<xref:System.Windows.Media.Animation.TimelineGroup> 개체)와 같은 <xref:System.Windows.Media.Animation.Storyboard> 하 고 <xref:System.Windows.Media.Animation.ParallelTimeline>, 기본 기간이 <xref:System.Windows.Duration.Automatic%2A>, 즉, 마지막 자식의 재생이 중지 되 면 자동으로 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="49e9d-109">Container timelines (<xref:System.Windows.Media.Animation.TimelineGroup> objects), such as <xref:System.Windows.Media.Animation.Storyboard> and <xref:System.Windows.Media.Animation.ParallelTimeline>, have a default duration of <xref:System.Windows.Duration.Automatic%2A>, which means they automatically end when their last child stops playing.</span></span>  
  
 <span data-ttu-id="49e9d-110">다음 예제에서는, 너비, 높이 및 채우기 색에서을 <xref:System.Windows.Shapes.Rectangle> 애니메이션 효과가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49e9d-110">In the following example, the width, height and fill color of a <xref:System.Windows.Shapes.Rectangle> is animated.</span></span> <span data-ttu-id="49e9d-111">애니메이션의 인지 된 속도 제어 하 고 컨테이너 타임 라인의 기간을 사용 하 여 자식 타임 라인이 기간 재정의 포함 하 여 애니메이션 효과 애니메이션 및 컨테이너 타임 라인의 기간 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49e9d-111">Durations are set on animation and container timelines resulting in animation effects including controlling the perceived speed of an animation and overriding the duration of child timelines with the duration of a container timeline.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49e9d-112">예제</span><span class="sxs-lookup"><span data-stu-id="49e9d-112">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#DurationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/DurationExample.xaml#durationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="49e9d-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="49e9d-113">See also</span></span>

- <xref:System.Windows.Duration>
- [<span data-ttu-id="49e9d-114">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="49e9d-114">Animation Overview</span></span>](animation-overview.md)
