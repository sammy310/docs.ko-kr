---
title: '방법: 키 프레임을 사용하여 개체에 애니메이션 효과 주기'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: b0a0f7c00125a43228a2658415b72f4d541f37be
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62020155"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a><span data-ttu-id="c0b22-102">방법: 키 프레임을 사용하여 개체에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="c0b22-102">How to: Animate an Object by Using Key Frames</span></span>
<span data-ttu-id="c0b22-103">이 예제에서는입니다 개체에 애니메이션을 적용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Page.Background%2A> 의 속성을 <xref:System.Windows.Controls.Page> 키 프레임을 사용 하 여 컨트롤을 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0b22-103">This example shows how to animate an object, which in this example is the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0b22-104">예제</span><span class="sxs-lookup"><span data-stu-id="c0b22-104">Example</span></span>  
 <span data-ttu-id="c0b22-105">다음 예제에서는 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> 색에 애니메이션 효과를 클래스에 대 한 변경 합니다 <xref:System.Windows.Controls.Page.Background%2A> 의 속성을 <xref:System.Windows.Controls.Page> 컨트롤.</span><span class="sxs-lookup"><span data-stu-id="c0b22-105">The following example uses the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class to animate color changes for the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control.</span></span> <span data-ttu-id="c0b22-106">예제에서는 애니메이션 배경 브러시를 정기적으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="c0b22-106">The example animation changes to a different background brush at regular intervals.</span></span> <span data-ttu-id="c0b22-107">이 애니메이션 사용을 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> 세 가지 다른 키 프레임을 만들 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c0b22-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> class to create three different key frames.</span></span> <span data-ttu-id="c0b22-108">애니메이션 키 프레임을 사용 하 여 다음과 같은 방법으로:</span><span class="sxs-lookup"><span data-stu-id="c0b22-108">The animation uses key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="c0b22-109">첫 번째 두 번째 끝의 인스턴스를 애니메이션 합니다 <xref:System.Windows.Media.LinearGradientBrush> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c0b22-109">At the end of the first second, animates an instance of the <xref:System.Windows.Media.LinearGradientBrush> class.</span></span> <span data-ttu-id="c0b22-110">예제의이 섹션에서는 색 노랑에서 빨강 주황색 전환 되도록 배경색으로 선형 그라데이션을 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0b22-110">This section of the example applies a linear gradient to the background color so that the color transitions from yellow to orange to red.</span></span>  
  
2. <span data-ttu-id="c0b22-111">끝에 다음 두 번째 애니메이션의 인스턴스는 <xref:System.Windows.Media.RadialGradientBrush> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c0b22-111">At the end of the next second, animates an instance of the <xref:System.Windows.Media.RadialGradientBrush> class.</span></span> <span data-ttu-id="c0b22-112">예제의이 섹션에서는 색을 검정으로 파란색 흰색에서 전환 되도록 배경색에 방사형 그라데이션을 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0b22-112">This section of the example applies a radial gradient to the background color so that the color transitions from white to blue to black.</span></span>  
  
3. <span data-ttu-id="c0b22-113">세 번째 두 번째 끝의 인스턴스를 애니메이션 합니다 <xref:System.Windows.Media.DrawingBrush> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c0b22-113">At the end of the third second, animates an instance of the <xref:System.Windows.Media.DrawingBrush> class.</span></span> <span data-ttu-id="c0b22-114">예제의이 섹션에는 백그라운드에 체크 무늬 패턴을 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0b22-114">This section of the example applies a checkerboard pattern to the background.</span></span>  
  
4. <span data-ttu-id="c0b22-115">애니메이션이 다시 시작 되 고 무기한 반복 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0b22-115">The animation begins again and repeats indefinitely.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0b22-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> 사용 하 여 사용할 수 있는 키 프레임의 유일한 형식인는 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c0b22-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> is the only type of key frame that you can use with the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class.</span></span> <span data-ttu-id="c0b22-117">같은 키 프레임 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> 즉 값에서 급격 한 변화를 만들고,이 예제에서 색 변경 갑자기 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0b22-117">Key frames like <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> create sudden changes in values, that is, the color changes in this example occur suddenly.</span></span>  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="c0b22-118">전체 샘플을 보려면 [키 프레임 애니메이션 샘플](https://go.microsoft.com/fwlink/?LinkID=160012)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0b22-118">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0b22-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="c0b22-119">See also</span></span>

- <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.Page.Background%2A>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>
- <xref:System.Windows.Media.LinearGradientBrush>
- <xref:System.Windows.Media.RadialGradientBrush>
- <xref:System.Windows.Media.DrawingBrush>
- [<span data-ttu-id="c0b22-120">키 프레임 애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="c0b22-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="c0b22-121">키 프레임 방법 항목</span><span class="sxs-lookup"><span data-stu-id="c0b22-121">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
