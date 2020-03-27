---
title: '방법: 키 프레임 애니메이션 타이밍 제어'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], timing
- timing key-frame animation
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
ms.openlocfilehash: 8cfd2be0bbc526ed92a5fb1b558a5a41dc9c3113
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344731"
---
# <a name="how-to-control-key-frame-animation-timing"></a><span data-ttu-id="166c1-102">방법: 키 프레임 애니메이션 타이밍 제어</span><span class="sxs-lookup"><span data-stu-id="166c1-102">How to: Control Key-Frame Animation Timing</span></span>

<span data-ttu-id="166c1-103">이 예제에서는 키 프레임 애니메이션 내에서 키 프레임의 타이밍을 제어하는 방법을 보여 주며, 키 프레임 애니메이션을 보여 주며, 키 프레임의 타이밍을 제어하는 방법을 보여 주며, 이 예제에서는 키 프레임 애니메이션의 타이밍을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="166c1-103">This example shows how to control the timing of key frames within a key-frame animation.</span></span> <span data-ttu-id="166c1-104">다른 애니메이션과 마찬가지로 키 프레임 애니메이션에는 속성이 있습니다. <xref:System.Windows.Media.Animation.Timeline.Duration%2A></span><span class="sxs-lookup"><span data-stu-id="166c1-104">Like other animations, key-frame animations have a <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property.</span></span> <span data-ttu-id="166c1-105">애니메이션의 지속 시간을 지정하는 것 외에도 해당 기간의 일부가 각 키 프레임에 할당되도록 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="166c1-105">In addition to specifying the duration of an animation, you need to specify what part of that duration is allotted to each of its key frames.</span></span> <span data-ttu-id="166c1-106">시간을 할당하려면 애니메이션의 각 <xref:System.Windows.Media.Animation.KeyTime> 키 프레임에 대해 a를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="166c1-106">To allot the time, you specify a <xref:System.Windows.Media.Animation.KeyTime> for each key frame in the animation.</span></span>

<span data-ttu-id="166c1-107">각 <xref:System.Windows.Media.Animation.KeyTime> 키 프레임에 대해 키 프레임이 끝날 때 지정합니다(키 프레임이 재생되는 시간을 지정하지 않음).</span><span class="sxs-lookup"><span data-stu-id="166c1-107">The <xref:System.Windows.Media.Animation.KeyTime> for each key frame specifies when a key frame ends (it does not specify the length of time a key frame plays).</span></span> <span data-ttu-id="166c1-108">a를 <xref:System.Windows.Media.Animation.KeyTime> <xref:System.TimeSpan> 값으로, 백분율로 또는 <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> 특수 값으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166c1-108">You can specify a <xref:System.Windows.Media.Animation.KeyTime> as a <xref:System.TimeSpan> value, as a percentage, or as the <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> or <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> special value.</span></span>

## <a name="example"></a><span data-ttu-id="166c1-109">예제</span><span class="sxs-lookup"><span data-stu-id="166c1-109">Example</span></span>

<span data-ttu-id="166c1-110">다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> a를 사용하여 화면에서 사각형을 애니메이션합니다.</span><span class="sxs-lookup"><span data-stu-id="166c1-110">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> to animate a rectangle across the screen.</span></span> <span data-ttu-id="166c1-111">키 프레임의 키 시간은 <xref:System.TimeSpan> 값으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="166c1-111">The key frames' key times are set with <xref:System.TimeSpan> values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
[!code-vb[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
[!code-xaml[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]

<span data-ttu-id="166c1-112">다음 그림은 각 키 프레임의 값에 도달하는 시기를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="166c1-112">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="166c1-113">![3, 4, 10초에 키 값에 도달](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span><span class="sxs-lookup"><span data-stu-id="166c1-113">![Key values are reached at 3, 4, and 10 seconds](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span></span>

<span data-ttu-id="166c1-114">다음 예제에서는 키 프레임의 키 시간이 백분율 값으로 설정되는 경우를 제외하고 동일한 애니메이션을 보여 주며, 이 애니메이션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="166c1-114">The next example shows an animation that is identical, except that the key frames' key times are set with percentage values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
[!code-vb[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
[!code-xaml[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]

<span data-ttu-id="166c1-115">다음 그림은 각 키 프레임의 값에 도달하는 시기를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="166c1-115">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="166c1-116">![3, 4, 10초에 키 값에 도달](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span><span class="sxs-lookup"><span data-stu-id="166c1-116">![Key values are reached at 3, 4, and 10 seconds](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span></span>

<span data-ttu-id="166c1-117">다음 예제에서는 <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> 키 시간 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="166c1-117">The next example uses <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> key time values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
[!code-vb[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
[!code-xaml[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]

<span data-ttu-id="166c1-118">다음 그림은 각 키 프레임의 값에 도달하는 시기를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="166c1-118">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="166c1-119">![키 값은 3.3, 6.6 및 9.9초에 도달](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span><span class="sxs-lookup"><span data-stu-id="166c1-119">![Key values are reached at 3.3,6.6, and 9.9 seconds](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span></span>

<span data-ttu-id="166c1-120">마지막 예제에서는 <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> 키 시간 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="166c1-120">The final example uses <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> key time values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
[!code-vb[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
[!code-xaml[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]

<span data-ttu-id="166c1-121">다음 그림은 각 키 프레임의 값에 도달하는 시기를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="166c1-121">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="166c1-122">![0, 5, 10초에 키 값에 도달](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span><span class="sxs-lookup"><span data-stu-id="166c1-122">![Key values are reached at 0, 5, and 10 seconds](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span></span>

<span data-ttu-id="166c1-123">간단히 하기 위해 이 예제의 코드 버전은 단일 애니메이션만 단일 속성에 적용되기 때문에 스토리보드가 아닌 로컬 애니메이션을 사용하지만 예제는 스토리보드를 대신 사용하도록 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="166c1-123">For simplicity, the code versions of this example use local animations, not storyboards, because only a single animation is being applied to a single property, but the examples may be modified to use storyboards instead.</span></span> <span data-ttu-id="166c1-124">코드에서 스토리보드를 선언하는 방법을 보여 줄 예제에서는 [스토리보드를 사용하여 속성 애니메이션을](how-to-animate-a-property-by-using-a-storyboard.md)참조하세요.</span><span class="sxs-lookup"><span data-stu-id="166c1-124">For an example showing how to declare a storyboard in code, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md).</span></span>

<span data-ttu-id="166c1-125">전체 샘플을 보려면 [키 프레임 애니메이션 샘플](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="166c1-125">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span> <span data-ttu-id="166c1-126">키 프레임 애니메이션에 대한 자세한 내용은 [키 프레임 애니메이션 개요를](key-frame-animations-overview.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="166c1-126">For more information about key frame animations, see the [Key-Frame Animations Overview](key-frame-animations-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="166c1-127">참조</span><span class="sxs-lookup"><span data-stu-id="166c1-127">See also</span></span>

- [<span data-ttu-id="166c1-128">키 프레임 애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="166c1-128">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="166c1-129">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="166c1-129">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="166c1-130">방법 항목</span><span class="sxs-lookup"><span data-stu-id="166c1-130">How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
