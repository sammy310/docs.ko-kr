---
title: '방법: 키 프레임을 사용하여 개체에 애니메이션 효과 주기'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: ffbe1845b634c8f94eb6a10dfa44fcf9903e0cd5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933902"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a><span data-ttu-id="bc9f0-102">방법: 키 프레임을 사용하여 개체에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="bc9f0-102">How to: Animate an Object by Using Key Frames</span></span>
<span data-ttu-id="bc9f0-103">이 예제에서는 개체에 애니메이션 효과를 주는 방법을 보여 줍니다 .이 예제 <xref:System.Windows.Controls.Page.Background%2A> 에서는 키 프레임 <xref:System.Windows.Controls.Page> 을 사용 하 여 컨트롤의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="bc9f0-103">This example shows how to animate an object, which in this example is the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc9f0-104">예제</span><span class="sxs-lookup"><span data-stu-id="bc9f0-104">Example</span></span>  
 <span data-ttu-id="bc9f0-105">다음 예제에서는 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> 클래스를 사용 하 여 <xref:System.Windows.Controls.Page> 컨트롤의 <xref:System.Windows.Controls.Page.Background%2A> 속성에 대 한 색 변경에 애니메이션 효과를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc9f0-105">The following example uses the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class to animate color changes for the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control.</span></span> <span data-ttu-id="bc9f0-106">예제 애니메이션은 일정 한 간격으로 다른 배경 브러시로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc9f0-106">The example animation changes to a different background brush at regular intervals.</span></span> <span data-ttu-id="bc9f0-107">이 애니메이션은 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> 클래스를 사용 하 여 세 개의 다른 키 프레임을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bc9f0-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> class to create three different key frames.</span></span> <span data-ttu-id="bc9f0-108">애니메이션은 다음과 같은 방식으로 키 프레임을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc9f0-108">The animation uses key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="bc9f0-109">첫 번째 초가 끝날 때 <xref:System.Windows.Media.LinearGradientBrush> 클래스의 인스턴스에 애니메이션 효과를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc9f0-109">At the end of the first second, animates an instance of the <xref:System.Windows.Media.LinearGradientBrush> class.</span></span> <span data-ttu-id="bc9f0-110">예제의이 섹션에서는 색이 노랑에서 주황, 빨강으로 전환 되도록 선형 그라데이션을 배경색에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc9f0-110">This section of the example applies a linear gradient to the background color so that the color transitions from yellow to orange to red.</span></span>  
  
2. <span data-ttu-id="bc9f0-111">다음 초가 끝날 때 <xref:System.Windows.Media.RadialGradientBrush> 클래스의 인스턴스에 애니메이션 효과를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc9f0-111">At the end of the next second, animates an instance of the <xref:System.Windows.Media.RadialGradientBrush> class.</span></span> <span data-ttu-id="bc9f0-112">예제의이 섹션에서는 색이 흰색에서 파랑으로 파랑으로 전환 되도록 방사형 그라데이션을 배경색에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc9f0-112">This section of the example applies a radial gradient to the background color so that the color transitions from white to blue to black.</span></span>  
  
3. <span data-ttu-id="bc9f0-113">세 번째 초가 끝날 때 <xref:System.Windows.Media.DrawingBrush> 클래스의 인스턴스에 애니메이션 효과를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc9f0-113">At the end of the third second, animates an instance of the <xref:System.Windows.Media.DrawingBrush> class.</span></span> <span data-ttu-id="bc9f0-114">예제의이 섹션에서는 배경에 바둑판 패턴을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc9f0-114">This section of the example applies a checkerboard pattern to the background.</span></span>  
  
4. <span data-ttu-id="bc9f0-115">애니메이션은 다시 시작 되 고 무기한 반복 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc9f0-115">The animation begins again and repeats indefinitely.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bc9f0-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>는 클래스에서 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> 사용할 수 있는 키 프레임의 유일한 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="bc9f0-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> is the only type of key frame that you can use with the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class.</span></span> <span data-ttu-id="bc9f0-117">이 예제의 색 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> 변경이 갑자기 발생 하는 경우와 같은 키 프레임은 값의 급격 한 변화를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bc9f0-117">Key frames like <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> create sudden changes in values, that is, the color changes in this example occur suddenly.</span></span>  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="bc9f0-118">전체 샘플을 보려면 [키 프레임 애니메이션 샘플](https://go.microsoft.com/fwlink/?LinkID=160012)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc9f0-118">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc9f0-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="bc9f0-119">See also</span></span>

- <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.Page.Background%2A>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>
- <xref:System.Windows.Media.LinearGradientBrush>
- <xref:System.Windows.Media.RadialGradientBrush>
- <xref:System.Windows.Media.DrawingBrush>
- [<span data-ttu-id="bc9f0-120">키 프레임 애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="bc9f0-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="bc9f0-121">키 프레임 방법 항목</span><span class="sxs-lookup"><span data-stu-id="bc9f0-121">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
