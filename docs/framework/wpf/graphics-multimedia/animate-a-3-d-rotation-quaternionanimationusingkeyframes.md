---
title: '방법: 키 프레임을 사용하여 3D 회전 애니메이션(쿼터니언애니메이션키프레임)'
ms.date: 03/30/2017
helpviewer_keywords:
- 3D translations [WPF], animating [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
- key frames [WPF], QuaternionAnimationUsingKeyFrames
- animation [WPF], 3D translations [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
ms.assetid: 09e5707b-7523-4a08-9aa7-bb13cbedccdf
ms.openlocfilehash: 5273183aaa49a743cc401dec0b4b16bae09e3129
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112299"
---
# <a name="how-to-animate-a-3d-rotation-using-key-frames-quaternionanimationusingkeyframes"></a><span data-ttu-id="3e0ab-102">방법: 키 프레임을 사용하여 3D 회전 애니메이션(쿼터니언애니메이션키프레임)</span><span class="sxs-lookup"><span data-stu-id="3e0ab-102">How to: Animate a 3D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>
<span data-ttu-id="3e0ab-103">다음 예제에서는 <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> 3D 오브젝트를 회전하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0ab-103">In the following example, <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> is used to make a 3D object rotate.</span></span> <span data-ttu-id="3e0ab-104">이 애니메이션은 다음과 같은 키 프레임을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e0ab-104">This animation uses the following key frames:</span></span>  
  
1. <span data-ttu-id="3e0ab-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame>은 값 간에 매끄럽고 선형보간을 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0ab-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> is used to create a smooth, linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="3e0ab-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame>은 값 사이에 갑작스런 "점프"를 만드는 데 사용됩니다(보간 없음).</span><span class="sxs-lookup"><span data-stu-id="3e0ab-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3. <span data-ttu-id="3e0ab-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame>속성에 <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> 따라 값 간에 변수 전환을 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e0ab-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="3e0ab-108">아래 예제에서는 애니메이션의 이 부분이 느리게 시작되지만 시간 세그먼트가 끝날 때까지 기하급수적으로 속도가 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="3e0ab-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e0ab-109">예제</span><span class="sxs-lookup"><span data-stu-id="3e0ab-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="3e0ab-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3e0ab-110">See also</span></span>

- [<span data-ttu-id="3e0ab-111">스토리보드를 사용하여 3D 회전 애니메이션</span><span class="sxs-lookup"><span data-stu-id="3e0ab-111">Animate a 3D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="3e0ab-112">회전3D애니메이션을 사용하여 3D 회전 애니메이션</span><span class="sxs-lookup"><span data-stu-id="3e0ab-112">Animate a 3D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="3e0ab-113">쿼터니언을 사용하여 3D 회전 애니메이션</span><span class="sxs-lookup"><span data-stu-id="3e0ab-113">Animate a 3D Rotation Using Quaternions</span></span>](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [<span data-ttu-id="3e0ab-114">키 프레임을 사용하여 3D 회전 애니메이션(회전3DAnimationUsingKeyFrame)</span><span class="sxs-lookup"><span data-stu-id="3e0ab-114">Animate a 3D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [<span data-ttu-id="3e0ab-115">3D 그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="3e0ab-115">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="3e0ab-116">키 프레임 애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="3e0ab-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
