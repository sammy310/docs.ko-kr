---
title: '방법: 키 프레임을 사용하여 매트릭스에 애니메이션 효과 주기'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: eb596cf728f8a7cc1964963b8509f42bdd7a392a
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344911"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a><span data-ttu-id="3a54b-102">방법: 키 프레임을 사용하여 매트릭스에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="3a54b-102">How to: Animate a Matrix by Using Key Frames</span></span>
<span data-ttu-id="3a54b-103">이 예제에서는 키 프레임을 <xref:System.Windows.Media.MatrixTransform.Matrix%2A> 사용하여 a의 <xref:System.Windows.Media.MatrixTransform> 속성을 애니메이션하는 방법을 보여 주며, 이 예제에서는</span><span class="sxs-lookup"><span data-stu-id="3a54b-103">This example shows how to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a54b-104">예제</span><span class="sxs-lookup"><span data-stu-id="3a54b-104">Example</span></span>  
 <span data-ttu-id="3a54b-105">다음 예제에서는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> 클래스를 사용하여 의 <xref:System.Windows.Media.MatrixTransform.Matrix%2A> 속성을 <xref:System.Windows.Media.MatrixTransform>애니메이션합니다.</span><span class="sxs-lookup"><span data-stu-id="3a54b-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="3a54b-106">이 예제에서는 <xref:System.Windows.Media.MatrixTransform> 개체를 사용하여 <xref:System.Windows.Controls.Button>의 모양과 위치를 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="3a54b-106">The example uses the <xref:System.Windows.Media.MatrixTransform> object to transform the appearance and position of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="3a54b-107">이 애니메이션은 <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> 클래스를 사용하여 두 개의 키 프레임을 만들고 다음과 같은 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3a54b-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> class to create two key frames and does the following with them:</span></span>  
  
1. <span data-ttu-id="3a54b-108">처음 0.2초 동안 첫 번째 <xref:System.Windows.Media.Matrix> 애니메이션을 애니메이션합니다.</span><span class="sxs-lookup"><span data-stu-id="3a54b-108">Animates the first <xref:System.Windows.Media.Matrix> during the first 0.2 seconds.</span></span> <span data-ttu-id="3a54b-109">이 예제는 <xref:System.Windows.Media.Matrix.M11%2A> <xref:System.Windows.Media.Matrix.M12%2A> <xref:System.Windows.Media.Matrix>의 및 속성을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3a54b-109">The example changes the <xref:System.Windows.Media.Matrix.M11%2A> and <xref:System.Windows.Media.Matrix.M12%2A> properties of the <xref:System.Windows.Media.Matrix>.</span></span> <span data-ttu-id="3a54b-110">이렇게 변경하면 버튼이 늘어나고 기울어집니다.</span><span class="sxs-lookup"><span data-stu-id="3a54b-110">This change causes the button to stretch and become skewed.</span></span> <span data-ttu-id="3a54b-111">또한 이 예제는 단추의 <xref:System.Windows.Media.Matrix.OffsetX%2A> 위치가 변경되도록 및 <xref:System.Windows.Media.Matrix.OffsetY%2A> 속성을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3a54b-111">The example also changes the <xref:System.Windows.Media.Matrix.OffsetX%2A> and <xref:System.Windows.Media.Matrix.OffsetY%2A> properties so that the button changes position.</span></span>  
  
2. <span data-ttu-id="3a54b-112">1.0초에서 <xref:System.Windows.Media.Matrix> 두 번째 애니메이션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3a54b-112">Animates the second <xref:System.Windows.Media.Matrix> at 1.0 seconds.</span></span> <span data-ttu-id="3a54b-113">버튼이 더 이상 기울어지거나 늘어나지 않는 동안 버튼이 다른 위치로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3a54b-113">The button moves to another position while the button is no longer skewed or stretched.</span></span>  
  
3. <span data-ttu-id="3a54b-114">애니메이션을 무기한 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="3a54b-114">Repeats the animation indefinitely.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3a54b-115"><xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> 오브젝트에서 파생된 키 프레임은 값 간에 갑작스런 점프, 즉 애니메이션의 이동이 육포됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a54b-115">Key frames that derive from the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> object create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="3a54b-116">전체 샘플을 보려면 [키 프레임 애니메이션 샘플](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a54b-116">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a54b-117">참조</span><span class="sxs-lookup"><span data-stu-id="3a54b-117">See also</span></span>

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [<span data-ttu-id="3a54b-118">키 프레임 애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="3a54b-118">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="3a54b-119">키 프레임 방법 항목</span><span class="sxs-lookup"><span data-stu-id="3a54b-119">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
