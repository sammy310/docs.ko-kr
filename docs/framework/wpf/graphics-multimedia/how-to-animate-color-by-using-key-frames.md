---
title: '방법: 키 프레임을 사용하여 색에 애니메이션 효과 주기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [WPF], animating with key frames
- animation [WPF], colors with key frames
- key frames [WPF], animating colors with
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
ms.openlocfilehash: 8a444706f7541b52722ab8257a88e76c3e1b0938
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344744"
---
# <a name="how-to-animate-color-by-using-key-frames"></a><span data-ttu-id="117c3-102">방법: 키 프레임을 사용하여 색에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="117c3-102">How to: Animate Color by Using Key Frames</span></span>
<span data-ttu-id="117c3-103">이 예제에서는 키 프레임을 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 사용하여 <xref:System.Windows.Media.SolidColorBrush> 에 애니메이션을 애니메이션하는 방법을 보여 주며, 이 예제에서는</span><span class="sxs-lookup"><span data-stu-id="117c3-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> of a <xref:System.Windows.Media.SolidColorBrush> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="117c3-104">예제</span><span class="sxs-lookup"><span data-stu-id="117c3-104">Example</span></span>  
 <span data-ttu-id="117c3-105">다음 예제에서는 <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> 클래스를 사용하여 의 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 속성을 <xref:System.Windows.Media.SolidColorBrush>애니메이션합니다.</span><span class="sxs-lookup"><span data-stu-id="117c3-105">The following example uses the <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> property of a <xref:System.Windows.Media.SolidColorBrush>.</span></span> <span data-ttu-id="117c3-106">이 애니메이션은 다음과 같은 방식으로 세 가지 키 프레임을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="117c3-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="117c3-107">처음 2초 동안 <xref:System.Windows.Media.Animation.LinearColorKeyFrame> 클래스의 인스턴스를 사용하여 색상을 녹색에서 빨간색으로 점진적으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="117c3-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearColorKeyFrame> class to gradually change the color from green to red.</span></span> <span data-ttu-id="117c3-108">과 같은 선형 키 프레임 <xref:System.Windows.Media.Animation.LinearColorKeyFrame> 값 사이 매끄러운 선형 전환을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="117c3-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearColorKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="117c3-109">다음 후반초가 끝날 때는 클래스의 <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> 인스턴스를 사용하여 색상을 빨간색에서 노란색으로 빠르게 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="117c3-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> class to quickly change the color from red to yellow.</span></span> <span data-ttu-id="117c3-110">이산 키 프레임은 <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> 값 간에 갑작스런 변화를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="117c3-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> create sudden changes between values, that is, the color change in this part of the animation occurs quickly and is not subtle.</span></span>  
  
3. <span data-ttu-id="117c3-111">마지막 2초 동안 <xref:System.Windows.Media.Animation.SplineColorKeyFrame> 클래스의 인스턴스를 사용하여 색상을 다시 변경합니다(이번에는 노란색에서 다시 녹색으로)</span><span class="sxs-lookup"><span data-stu-id="117c3-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame> class to change the color again—this time from yellow back to green.</span></span> <span data-ttu-id="117c3-112">스프라인 키 <xref:System.Windows.Media.Animation.SplineColorKeyFrame> 프레임은 <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> 속성값에 따라 값 간에 가변 전환을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="117c3-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineColorKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="117c3-113">이 예제에서 색 변화는 느리게 시작하다가 시간 세그먼트의 끝에 다가가면 기하급수적으로 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="117c3-113">In this example, the change in color begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="117c3-114">전체 샘플을 보려면 [키 프레임 애니메이션 샘플](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="117c3-114">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="117c3-115">참조</span><span class="sxs-lookup"><span data-stu-id="117c3-115">See also</span></span>

- <xref:System.Windows.Media.SolidColorBrush.Color%2A>
- <xref:System.Windows.Media.SolidColorBrush>
- <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>
- [<span data-ttu-id="117c3-116">키 프레임 애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="117c3-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="117c3-117">키 프레임 방법 항목</span><span class="sxs-lookup"><span data-stu-id="117c3-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
