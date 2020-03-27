---
title: '방법: 키 프레임을 사용하여 사각형에 애니메이션 효과 주기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating RectangleGeometry objects with
- RectangleGeometry objects [WPF], animating with key frames
- animation [WPF], RectangleGeometry objects with key frames
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
ms.openlocfilehash: bcc9e7f198b8a20ffe13daf6508fb8a735937652
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344687"
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a><span data-ttu-id="d31ef-102">방법: 키 프레임을 사용하여 사각형에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="d31ef-102">How to: Animate a Rectangle Geometry by Using Key Frames</span></span>
<span data-ttu-id="d31ef-103">이 예제에서는 키 프레임을 <xref:System.Windows.Media.RectangleGeometry.Rect%2A> 사용하여 a의 <xref:System.Windows.Media.RectangleGeometry> 속성을 애니메이션하는 방법을 보여 주며, 이 예제에서는</span><span class="sxs-lookup"><span data-stu-id="d31ef-103">This example shows how to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d31ef-104">예제</span><span class="sxs-lookup"><span data-stu-id="d31ef-104">Example</span></span>  
 <span data-ttu-id="d31ef-105">다음 예제에서는 <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> 클래스를 사용하여 의 <xref:System.Windows.Media.RectangleGeometry.Rect%2A> 속성을 <xref:System.Windows.Media.RectangleGeometry>애니메이션합니다.</span><span class="sxs-lookup"><span data-stu-id="d31ef-105">The following example uses the <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry>.</span></span> <span data-ttu-id="d31ef-106">이 애니메이션은 다음과 같은 방식으로 세 가지 키 프레임을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d31ef-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="d31ef-107">처음 2초 동안 <xref:System.Windows.Media.Animation.LinearRectKeyFrame> 클래스의 인스턴스를 사용하여 사각형의 위치, 너비 및 높이가 점진적으로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="d31ef-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearRectKeyFrame> class to animate a gradual change in the position, width, and height of a rectangle.</span></span> <span data-ttu-id="d31ef-108">과 같은 선형 키 프레임 <xref:System.Windows.Media.Animation.LinearRectKeyFrame> 값 사이 매끄러운 선형 전환을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d31ef-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearRectKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="d31ef-109">다음 절반 초가 끝날 때 클래스의 <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> 인스턴스를 사용하여 사각형의 높이를 갑자기 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="d31ef-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> class to suddenly decrease the height of the rectangle.</span></span> <span data-ttu-id="d31ef-110">이산 키 프레임은 <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> 값 사이에 갑작스런 변화를 만듭니다, 즉 높이의 감소가 빠르게 발생하고 미묘하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d31ef-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> create sudden changes between values, that is, the decrease in height occurs quickly and is not subtle.</span></span>  
  
3. <span data-ttu-id="d31ef-111">마지막 2초 동안 <xref:System.Windows.Media.Animation.SplineRectKeyFrame> 클래스의 인스턴스를 사용하여 사각형을 원래 크기와 위치로 다시 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="d31ef-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame> class to change the rectangle back to its original size and position.</span></span> <span data-ttu-id="d31ef-112">스프라인 키 <xref:System.Windows.Media.Animation.SplineRectKeyFrame> 프레임은 <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> 속성값에 따라 값 간에 가변 전환을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d31ef-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineRectKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="d31ef-113">이 예제에서 변화는 느리게 시작하다가 시간 세그먼트의 끝에 다가가면 기하급수적으로 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="d31ef-113">In this example, the change begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="d31ef-114">전체 샘플을 보려면 [키 프레임 애니메이션 샘플](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d31ef-114">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d31ef-115">참조</span><span class="sxs-lookup"><span data-stu-id="d31ef-115">See also</span></span>

- <xref:System.Windows.Media.RectangleGeometry>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>
- [<span data-ttu-id="d31ef-116">키 프레임 애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="d31ef-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="d31ef-117">키 프레임 방법 항목</span><span class="sxs-lookup"><span data-stu-id="d31ef-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
