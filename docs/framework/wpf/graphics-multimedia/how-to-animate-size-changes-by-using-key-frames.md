---
title: '방법: 키 프레임을 사용하여 크기 변경에 애니메이션 효과 주기'
ms.date: 03/30/2017
helpviewer_keywords:
- key frames [WPF], animating size changes with
- animation [WPF], size changes with key frames
- size changes [WPF], animating with key frames
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
ms.openlocfilehash: 42cecfc9df4304be4033ea39edc0517016de4a92
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344645"
---
# <a name="how-to-animate-size-changes-by-using-key-frames"></a><span data-ttu-id="dbe89-102">방법: 키 프레임을 사용하여 크기 변경에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="dbe89-102">How to: Animate Size Changes by Using Key Frames</span></span>
<span data-ttu-id="dbe89-103">이 예제에서는 키 프레임을 사용하여 크기 변경에 애니메이션 효과를 주는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dbe89-103">This example shows how to animate size changes by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dbe89-104">예제</span><span class="sxs-lookup"><span data-stu-id="dbe89-104">Example</span></span>  
 <span data-ttu-id="dbe89-105">다음 예제에서는 <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> 클래스를 사용하여 의 <xref:System.Windows.Media.ArcSegment.Size%2A> 속성을 <xref:System.Windows.Media.ArcSegment>애니메이션합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe89-105">The following example uses the <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.ArcSegment.Size%2A> property of an <xref:System.Windows.Media.ArcSegment>.</span></span> <span data-ttu-id="dbe89-106">이 애니메이션은 다음과 같은 방식으로 세 가지 키 프레임을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe89-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="dbe89-107">애니메이션의 첫 번째 후반초 동안 클래스의 <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> 인스턴스를 사용하여 점차적으로 호의 크기를 늘립니다. 같은 <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> 선형 키 프레임은 값 간에 부드러운 선형 전환을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dbe89-107">During the first half second of the animation, uses an instance of the <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> class to gradually increase the size of the arc. Linear key frames like <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="dbe89-108">다음 후반초가 끝나면 클래스의 인스턴스를 <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> 사용하여 갑자기 호의 크기를 늘립니다. 이산 키 프레임은 값 사이에 갑작스런 점프를 만드는 것과 같이, <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> 즉 크기 변화가 갑자기 발생하고 미묘하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dbe89-108">At the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> class to suddenly increase the size of the arc. Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> create sudden jumps between values, that is, the size changes occur suddenly and are not subtle.</span></span>  
  
3. <span data-ttu-id="dbe89-109">마지막 2초 동안 클래스의 인스턴스를 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> 사용하여 호의 크기를 늘립니다. 스프라인 키 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> 프레임은 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> 속성값에 따라 값 간에 가변 전환을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dbe89-109">Over the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> class to increase the size of the arc. Spline key frames like <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="dbe89-110">이 예제에서 원호의 크기는 처음에는 느리게 증가했다가 시간 세그먼트가 끝나면서 기하급수적으로 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="dbe89-110">In this example, the size of the arc increases slowly at first and then increases exponentially toward the end of the time segment.</span></span>  
  
 [!code-xaml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="dbe89-111">전체 샘플을 보려면 [키 프레임 애니메이션 샘플](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dbe89-111">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbe89-112">참조</span><span class="sxs-lookup"><span data-stu-id="dbe89-112">See also</span></span>

- <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>
- <xref:System.Windows.Media.ArcSegment.Size%2A>
- <xref:System.Windows.Media.ArcSegment>
- <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>
- <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>
- [<span data-ttu-id="dbe89-113">키 프레임 애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="dbe89-113">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="dbe89-114">키 프레임 방법 항목</span><span class="sxs-lookup"><span data-stu-id="dbe89-114">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
