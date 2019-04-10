---
title: '방법: 키 프레임을 사용하여 3차원 회전에 애니메이션 효과 주기(QuaternionAnimationUsingKeyFrames)'
ms.date: 03/30/2017
helpviewer_keywords:
- 3-D translations [WPF], animating [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
- key frames [WPF], QuaternionAnimationUsingKeyFrames
- animation [WPF], 3-D translations [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
ms.assetid: 09e5707b-7523-4a08-9aa7-bb13cbedccdf
ms.openlocfilehash: 87176df26405a69cb2c3d63620def0575b750b52
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59338022"
---
# <a name="how-to-animate-a-3-d-rotation-using-key-frames-quaternionanimationusingkeyframes"></a><span data-ttu-id="400e3-102">방법: 키 프레임을 사용하여 3차원 회전에 애니메이션 효과 주기(QuaternionAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="400e3-102">How to: Animate a 3-D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>
<span data-ttu-id="400e3-103">다음 예에서 <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> 회전 3D 개체를 만드는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="400e3-103">In the following example, <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> is used to make a 3D object rotate.</span></span> <span data-ttu-id="400e3-104">이 애니메이션에는 다음 키 프레임을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="400e3-104">This animation uses the following key frames:</span></span>  
  
1. <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> <span data-ttu-id="400e3-105">만드는 값 사이 매끄러운 선형 보간을 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="400e3-105">is used to create a smooth, linear interpolation between values.</span></span>  
  
2. <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> <span data-ttu-id="400e3-106">갑작스러운 이동을 만듭니다 "" 값 (보간 없음) 사이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="400e3-106">is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3. <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> <span data-ttu-id="400e3-107">에 따라 값 사이 가변 전환을 만드는 데 사용 되는 <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="400e3-107">is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="400e3-108">아래 예제에서 애니메이션의이 부분 느린 해제 하지만 시간 세그먼트의 끝에 다가가 시작, 면 기하급수적으로 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="400e3-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="400e3-109">예제</span><span class="sxs-lookup"><span data-stu-id="400e3-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="400e3-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="400e3-110">See also</span></span>

- [<span data-ttu-id="400e3-111">스토리보드를 사용하여 3차원 회전에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="400e3-111">Animate a 3-D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="400e3-112">Rotation3DAnimation을 사용하여 3차원 회전에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="400e3-112">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="400e3-113">4원수를 사용하여 3차원 회전에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="400e3-113">Animate a 3-D Rotation Using Quaternions</span></span>](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [<span data-ttu-id="400e3-114">키 프레임을 사용하여 3차원 회전에 애니메이션 효과 주기(Rotation3DAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="400e3-114">Animate a 3-D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [<span data-ttu-id="400e3-115">3차원 그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="400e3-115">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="400e3-116">키 프레임 애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="400e3-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
