---
title: '방법: 키 프레임을 사용하여 테두리 두께에 애니메이션 효과 주기'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], border thickness with key frames
- key frames [WPF], animating border thickness with
- border thickness [WPF], animating with key frames
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
ms.openlocfilehash: b131ce444a91e518f6372b7aeac603687141b262
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360951"
---
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a><span data-ttu-id="b67bd-102">방법: 키 프레임을 사용하여 테두리 두께에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="b67bd-102">How to: Animate the Thickness of a Border by Using Key Frames</span></span>
<span data-ttu-id="b67bd-103">애니메이션을 적용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Control.BorderThickness%2A> 의 속성을 <xref:System.Windows.Controls.Border>입니다.</span><span class="sxs-lookup"><span data-stu-id="b67bd-103">This example shows how to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b67bd-104">예제</span><span class="sxs-lookup"><span data-stu-id="b67bd-104">Example</span></span>  
 <span data-ttu-id="b67bd-105">다음 예제에서는 합니다 <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> 클래스에 애니메이션 효과를 <xref:System.Windows.Controls.Control.BorderThickness%2A> 의 속성을 <xref:System.Windows.Controls.Border>합니다.</span><span class="sxs-lookup"><span data-stu-id="b67bd-105">The following example uses the <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span> <span data-ttu-id="b67bd-106">이 애니메이션은 다음과 같은 방식으로 세 가지 키 프레임을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b67bd-106">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="b67bd-107">처음 1/2 초 동안의 인스턴스를 사용 하 여는 <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> 클래스를 테두리의 두께 점차적으로 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="b67bd-107">During the first half second, uses an instance of the <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> class to gradually increase the thickness of the border.</span></span> <span data-ttu-id="b67bd-108">이 예제에서는 사용 <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> 값 사이 매끄러운 선형 증가 만들려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b67bd-108">The example uses <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> to create a smooth linear increase between values.</span></span>  
  
2.  <span data-ttu-id="b67bd-109">0.5 초가 고 끝에 다음의 인스턴스를 사용 하 여 <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> 테두리의 두께 갑자기 늘립니다 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b67bd-109">At the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> class to suddenly increase the thickness of the border.</span></span> <span data-ttu-id="b67bd-110">파생 된 것과 같은 불연속 키 프레임 <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> 애니메이션의 이동을 매끄럽지는, 즉 값 간에 갑작스러운 이동을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b67bd-110">Discrete key frames like those derived from <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
3.  <span data-ttu-id="b67bd-111">마지막 2 초 동안의 인스턴스를 사용 하 여는 <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> 클래스 테두리의 두께를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="b67bd-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> class to decrease the thickness of the border.</span></span> <span data-ttu-id="b67bd-112">파생 된 것과 같은 스플라인 키 프레임 <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> 의 값에 따라 값 사이 가변 전환을 만듭니다는 <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b67bd-112">Spline key frames like those derived from <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="b67bd-113">이 키 프레임에서 애니메이션은 느리게 시작하다가 시간 세그먼트의 끝에 다가가면 기하급수적으로 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="b67bd-113">In this key frame, the animation starts off slow and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="b67bd-114">전체 샘플을 보려면 [키 프레임 애니메이션 샘플](https://go.microsoft.com/fwlink/?LinkID=160012)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b67bd-114">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b67bd-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="b67bd-115">See also</span></span>
- <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>
- [<span data-ttu-id="b67bd-116">키 프레임 애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="b67bd-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="b67bd-117">키 프레임 방법 항목</span><span class="sxs-lookup"><span data-stu-id="b67bd-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
- [<span data-ttu-id="b67bd-118">BorderThickness 값에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="b67bd-118">Animate a BorderThickness Value</span></span>](../controls/how-to-animate-a-borderthickness-value.md)
