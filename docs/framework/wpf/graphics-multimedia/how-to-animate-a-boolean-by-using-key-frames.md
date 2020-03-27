---
title: '방법: 키 프레임을 사용하여 부울에 애니메이션 효과 주기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Booleans [WPF], animating with key frames
- animation [WPF], Booleans with key frames
- key frames [WPF], animating Booleans with
ms.assetid: 4b0fac96-6231-4fcf-9775-4dd673ddc785
ms.openlocfilehash: 35704996dcf21fe463169dc13572941bcd8fbad1
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344928"
---
# <a name="how-to-animate-a-boolean-by-using-key-frames"></a><span data-ttu-id="b7b38-102">방법: 키 프레임을 사용하여 부울에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="b7b38-102">How to: Animate a Boolean by Using Key Frames</span></span>
<span data-ttu-id="b7b38-103">이 예제에서는 키 프레임을 사용하여 컨트롤의 부울 속성 값을 애니메이션하는 방법을 보여 주며, 이 예제에서는 컨트롤의 부울 속성 값을 애니메이션하는 방법을 보여 주며, 이 예제에서는 <xref:System.Windows.Controls.Button></span><span class="sxs-lookup"><span data-stu-id="b7b38-103">This example shows how to animate the Boolean property value of a <xref:System.Windows.Controls.Button> control by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7b38-104">예제</span><span class="sxs-lookup"><span data-stu-id="b7b38-104">Example</span></span>  
 <span data-ttu-id="b7b38-105">다음 예제에서는 <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> 클래스를 사용하여 컨트롤의 <xref:System.Windows.UIElement.IsEnabled%2A> 속성을 <xref:System.Windows.Controls.Button> 애니메이션합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b38-105">The following example uses the <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> class to animate the <xref:System.Windows.UIElement.IsEnabled%2A> property of a <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="b7b38-106">이 예제의 모든 키 프레임은 <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> 클래스의 인스턴스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b38-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> class.</span></span> <span data-ttu-id="b7b38-107">이산 키 프레임은 값 간에 갑작스런 점프를 만드는 것과 같이 <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> 애니메이션의 움직임이 육포입니다.</span><span class="sxs-lookup"><span data-stu-id="b7b38-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-csharp[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/BooleanAnimationUsingKeyFramesExample.cs#booleananimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/booleananimationusingkeyframesexample.vb#booleananimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/BooleanAnimationUsingKeyFramesExample.xaml#booleananimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="b7b38-108">전체 샘플을 보려면 [키 프레임 애니메이션 샘플](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b7b38-108">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7b38-109">참조</span><span class="sxs-lookup"><span data-stu-id="b7b38-109">See also</span></span>

- <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>
- <xref:System.Windows.UIElement.IsEnabled%2A>
- <xref:System.Windows.Controls.Button>
- [<span data-ttu-id="b7b38-110">키 프레임 애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="b7b38-110">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="b7b38-111">키 프레임 방법 항목</span><span class="sxs-lookup"><span data-stu-id="b7b38-111">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
