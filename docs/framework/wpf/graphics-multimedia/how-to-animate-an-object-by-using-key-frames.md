---
title: '방법: 키 프레임을 사용하여 개체에 애니메이션 효과 주기'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: 0bc33b189fd856dbe8106c1db35bc18e27ea131e
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344714"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a><span data-ttu-id="9b19f-102">방법: 키 프레임을 사용하여 개체에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="9b19f-102">How to: Animate an Object by Using Key Frames</span></span>
<span data-ttu-id="9b19f-103">이 예제에서는 키 프레임을 사용하여 <xref:System.Windows.Controls.Page.Background%2A> <xref:System.Windows.Controls.Page> 컨트롤의 속성인 개체를 애니메이션하는 방법을 보여 주습니다.</span><span class="sxs-lookup"><span data-stu-id="9b19f-103">This example shows how to animate an object, which in this example is the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b19f-104">예제</span><span class="sxs-lookup"><span data-stu-id="9b19f-104">Example</span></span>  
 <span data-ttu-id="9b19f-105">다음 예제에서는 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> 클래스를 사용 하 여 <xref:System.Windows.Controls.Page.Background%2A> <xref:System.Windows.Controls.Page> 컨트롤의 속성에 대 한 색상 변경 내용을 애니메이션합니다.</span><span class="sxs-lookup"><span data-stu-id="9b19f-105">The following example uses the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class to animate color changes for the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control.</span></span> <span data-ttu-id="9b19f-106">예제 애니메이션은 정기적으로 다른 배경 브러시로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b19f-106">The example animation changes to a different background brush at regular intervals.</span></span> <span data-ttu-id="9b19f-107">이 애니메이션은 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> 클래스를 사용하여 세 가지 키 프레임을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9b19f-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> class to create three different key frames.</span></span> <span data-ttu-id="9b19f-108">애니메이션은 다음과 같은 방식으로 키 프레임을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9b19f-108">The animation uses key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="9b19f-109">첫 번째 초가 끝나면 클래스의 인스턴스에 <xref:System.Windows.Media.LinearGradientBrush> 애니메이션이 애니메이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b19f-109">At the end of the first second, animates an instance of the <xref:System.Windows.Media.LinearGradientBrush> class.</span></span> <span data-ttu-id="9b19f-110">이 예제의 이 섹션에서는 색상이 노란색에서 주황색으로 바각하도록 배경 색에 선형 그라데이션을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="9b19f-110">This section of the example applies a linear gradient to the background color so that the color transitions from yellow to orange to red.</span></span>  
  
2. <span data-ttu-id="9b19f-111">다음 두 번째 초가 끝나면 클래스의 인스턴스에 애니메이션이 애니메이션됩니다. <xref:System.Windows.Media.RadialGradientBrush></span><span class="sxs-lookup"><span data-stu-id="9b19f-111">At the end of the next second, animates an instance of the <xref:System.Windows.Media.RadialGradientBrush> class.</span></span> <span data-ttu-id="9b19f-112">이 예제의 이 섹션에서는 색상이 흰색에서 파란색에서 검은색으로 전환되도록 배경 색에 방사형 그라데이션을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="9b19f-112">This section of the example applies a radial gradient to the background color so that the color transitions from white to blue to black.</span></span>  
  
3. <span data-ttu-id="9b19f-113">세 번째 초가 끝나면 클래스의 인스턴스에 <xref:System.Windows.Media.DrawingBrush> 애니메이션이 애니메이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b19f-113">At the end of the third second, animates an instance of the <xref:System.Windows.Media.DrawingBrush> class.</span></span> <span data-ttu-id="9b19f-114">예제의 이 섹션에서는 바둑판 패턴을 배경에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="9b19f-114">This section of the example applies a checkerboard pattern to the background.</span></span>  
  
4. <span data-ttu-id="9b19f-115">애니메이션이 다시 시작되고 무기한 반복됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b19f-115">The animation begins again and repeats indefinitely.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9b19f-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>클래스와 함께 사용할 수 있는 키 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> 프레임의 유일한 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="9b19f-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> is the only type of key frame that you can use with the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class.</span></span> <span data-ttu-id="9b19f-117">키 프레임같은 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> 것은 값의 급격한 변화를 만드는 것, 즉 이 예제의 색상 변화가 갑자기 발생한다.</span><span class="sxs-lookup"><span data-stu-id="9b19f-117">Key frames like <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> create sudden changes in values, that is, the color changes in this example occur suddenly.</span></span>  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="9b19f-118">전체 샘플을 보려면 [키 프레임 애니메이션 샘플](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b19f-118">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b19f-119">참조</span><span class="sxs-lookup"><span data-stu-id="9b19f-119">See also</span></span>

- <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.Page.Background%2A>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>
- <xref:System.Windows.Media.LinearGradientBrush>
- <xref:System.Windows.Media.RadialGradientBrush>
- <xref:System.Windows.Media.DrawingBrush>
- [<span data-ttu-id="9b19f-120">키 프레임 애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="9b19f-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="9b19f-121">키 프레임 방법 항목</span><span class="sxs-lookup"><span data-stu-id="9b19f-121">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
