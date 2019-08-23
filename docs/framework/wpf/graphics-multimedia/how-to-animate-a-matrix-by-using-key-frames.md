---
title: '방법: 키 프레임을 사용하여 매트릭스에 애니메이션 효과 주기'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: 6aa3e27cdfda7597c9b6acbf2980a2774f2b667b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963034"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a><span data-ttu-id="04ad0-102">방법: 키 프레임을 사용하여 매트릭스에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="04ad0-102">How to: Animate a Matrix by Using Key Frames</span></span>
<span data-ttu-id="04ad0-103">이 예제에서는 키 프레임을 사용 <xref:System.Windows.Media.MatrixTransform.Matrix%2A> 하 <xref:System.Windows.Media.MatrixTransform> 여의 속성에 애니메이션 효과를 주는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="04ad0-103">This example shows how to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04ad0-104">예제</span><span class="sxs-lookup"><span data-stu-id="04ad0-104">Example</span></span>  
 <span data-ttu-id="04ad0-105">다음 예제에서는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> 클래스를 사용 하 여의 <xref:System.Windows.Media.MatrixTransform.Matrix%2A> <xref:System.Windows.Media.MatrixTransform>속성에 애니메이션 효과를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="04ad0-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="04ad0-106">이 예제에서는 <xref:System.Windows.Media.MatrixTransform> 개체를 사용 하 여 <xref:System.Windows.Controls.Button>의 모양과 위치를 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="04ad0-106">The example uses the <xref:System.Windows.Media.MatrixTransform> object to transform the appearance and position of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="04ad0-107">이 애니메이션은 <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> 클래스를 사용 하 여 두 개의 키 프레임을 만들고이를 사용 하 여 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="04ad0-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> class to create two key frames and does the following with them:</span></span>  
  
1. <span data-ttu-id="04ad0-108">처음 0.2 초 <xref:System.Windows.Media.Matrix> 동안 처음에 애니메이션 효과를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="04ad0-108">Animates the first <xref:System.Windows.Media.Matrix> during the first 0.2 seconds.</span></span> <span data-ttu-id="04ad0-109">이 예제에서는의 <xref:System.Windows.Media.Matrix.M11%2A> <xref:System.Windows.Media.Matrix.M12%2A>및속성 을 변경 합니다 <xref:System.Windows.Media.Matrix>.</span><span class="sxs-lookup"><span data-stu-id="04ad0-109">The example changes the <xref:System.Windows.Media.Matrix.M11%2A> and <xref:System.Windows.Media.Matrix.M12%2A> properties of the <xref:System.Windows.Media.Matrix>.</span></span> <span data-ttu-id="04ad0-110">이렇게 변경 하면 단추가 늘어나거나 왜곡 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04ad0-110">This change causes the button to stretch and become skewed.</span></span> <span data-ttu-id="04ad0-111">또한이 예제에서는 단추가 <xref:System.Windows.Media.Matrix.OffsetX%2A> 위치 <xref:System.Windows.Media.Matrix.OffsetY%2A> 를 변경 하도록 및 속성을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="04ad0-111">The example also changes the <xref:System.Windows.Media.Matrix.OffsetX%2A> and <xref:System.Windows.Media.Matrix.OffsetY%2A> properties so that the button changes position.</span></span>  
  
2. <span data-ttu-id="04ad0-112">초 <xref:System.Windows.Media.Matrix> (1.0 초)에 애니메이션 효과를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="04ad0-112">Animates the second <xref:System.Windows.Media.Matrix> at 1.0 seconds.</span></span> <span data-ttu-id="04ad0-113">단추가 더 이상 기울어짐 또는 스트레치 되지 않은 상태에서 단추가 다른 위치로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="04ad0-113">The button moves to another position while the button is no longer skewed or stretched.</span></span>  
  
3. <span data-ttu-id="04ad0-114">애니메이션을 무기한 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="04ad0-114">Repeats the animation indefinitely.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="04ad0-115"><xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> 개체에서 파생 되는 키 프레임은 값 간에 급격 한 점프가 생성 됩니다. 즉, 애니메이션의 이동이 jerky 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04ad0-115">Key frames that derive from the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> object create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="04ad0-116">전체 샘플을 보려면 [키 프레임 애니메이션 샘플](https://go.microsoft.com/fwlink/?LinkID=160012)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="04ad0-116">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04ad0-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="04ad0-117">See also</span></span>

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [<span data-ttu-id="04ad0-118">키 프레임 애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="04ad0-118">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="04ad0-119">키 프레임 방법 항목</span><span class="sxs-lookup"><span data-stu-id="04ad0-119">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
