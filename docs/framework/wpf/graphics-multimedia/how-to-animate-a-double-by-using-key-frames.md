---
title: '방법: 키 프레임을 사용하여 Double에 애니메이션 효과 주기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Doubles [WPF], animating with key frames
- animation [WPF], Doubles with key frames
- key frames [WPF], animating Doubles with
ms.assetid: 3a1a7dba-7694-4907-8a2f-3408baebfa82
ms.openlocfilehash: 73cbeab8aee566313bad8e8a18a5500374287de0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010204"
---
# <a name="how-to-animate-a-double-by-using-key-frames"></a><span data-ttu-id="643eb-102">방법: 키 프레임을 사용하여 Double에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="643eb-102">How to: Animate a Double by Using Key Frames</span></span>
<span data-ttu-id="643eb-103">이 예제에서는 사용 하는 속성의 값에 애니메이션 효과 <xref:System.Double> 키 프레임을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="643eb-103">This example shows how to animate the value of a property that takes a <xref:System.Double> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="643eb-104">예제</span><span class="sxs-lookup"><span data-stu-id="643eb-104">Example</span></span>  
 <span data-ttu-id="643eb-105">다음 예제는 화면에서 사각형을 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="643eb-105">The following example moves a rectangle across a screen.</span></span> <span data-ttu-id="643eb-106">예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> 클래스에 애니메이션 효과를 <xref:System.Windows.Media.TranslateTransform.X%2A> 의 속성을 <xref:System.Windows.Media.TranslateTransform> 적용할를 <xref:System.Windows.Shapes.Rectangle>입니다.</span><span class="sxs-lookup"><span data-stu-id="643eb-106">The example uses the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.TranslateTransform.X%2A> property of a <xref:System.Windows.Media.TranslateTransform> applied to a <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="643eb-107">무제한 반복되는 이 애니메이션은 다음과 같은 방식으로 세 가지 키 프레임을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="643eb-107">This animation, which repeats indefinitely, uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="643eb-108">처음 3 초 동안의 인스턴스를 사용 하 여는 <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> 500 위치 시작 위치부터 일정 한 속도로 경로 따라 사각형을 이동 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="643eb-108">During the first three seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> class to move the rectangle along a path at a steady rate from its starting position to the 500 position.</span></span> <span data-ttu-id="643eb-109">과 같은 선형 키 프레임 <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> 값 사이 매끄러운 선형 전환을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="643eb-109">Linear key frames like <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="643eb-110">4 초가 끝나면의 인스턴스를 사용 하는 <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> 갑자기 다음 위치로 사각형을 이동 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="643eb-110">At the end of the fourth second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> class to suddenly move the rectangle to the next position.</span></span> <span data-ttu-id="643eb-111">과 같은 불연속 키 프레임 <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> 값 간에 갑작스러운 이동을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="643eb-111">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> create sudden jumps between values.</span></span> <span data-ttu-id="643eb-112">이 예제에서 사각형은 시작 위치에 있다가 갑자기 500 위치에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="643eb-112">In this example, the rectangle is at the starting position and then suddenly appears at the 500 position.</span></span>  
  
3. <span data-ttu-id="643eb-113">마지막 2 초의 인스턴스를 사용 하는 <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> 클래스 사각형을 다시 시작 위치로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="643eb-113">In the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> class to move the rectangle back to its starting position.</span></span> <span data-ttu-id="643eb-114">과 같은 스플라인 키 프레임 <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> 의 값에 따라 값 사이 가변 전환을 만듭니다는 <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="643eb-114">Spline key frames like <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> create a variable transition between values according to the value of the <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="643eb-115">이 예제에서 사각형은 처음에는 느리게 이동하다가 시간 세그먼트의 끝에 다가가면 기하급수적으로 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="643eb-115">In this example, the rectangle begins by moving slowly and then speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/AltDoubleAnimationUsingKeyFramesExample.cs#altdoubleanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/altdoubleanimationusingkeyframesexample.vb#altdoubleanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/AltDoubleAnimationUsingKeyFramesExample.xaml#altdoubleanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="643eb-116">전체 샘플을 보려면 [키 프레임 애니메이션 샘플](https://go.microsoft.com/fwlink/?LinkID=160012)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="643eb-116">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
 <span data-ttu-id="643eb-117">다른 애니메이션 예제를 사용 하 여 일관성을 위해이 예제의 코드 버전 사용을 <xref:System.Windows.Media.Animation.Storyboard> 적용할 개체는 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>합니다.</span><span class="sxs-lookup"><span data-stu-id="643eb-117">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span></span> <span data-ttu-id="643eb-118">또는 코드에서 단일 애니메이션을 적용할 때 간단 하 게 사용 합니다 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 사용 하는 대신 메서드를 <xref:System.Windows.Media.Animation.Storyboard>입니다.</span><span class="sxs-lookup"><span data-stu-id="643eb-118">Alternatively, when applying a single animation in code, it is simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="643eb-119">예제를 보려면 [Storyboard를 사용하지 않고 속성에 애니메이션 효과 주기](how-to-animate-a-property-without-using-a-storyboard.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="643eb-119">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="643eb-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="643eb-120">See also</span></span>

- <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>
- <xref:System.Windows.Shapes.Rectangle>
- <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>
- <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>
- [<span data-ttu-id="643eb-121">키 프레임 애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="643eb-121">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="643eb-122">키 프레임 방법 항목</span><span class="sxs-lookup"><span data-stu-id="643eb-122">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
