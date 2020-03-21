---
title: '방법: 키 프레임을 사용하여 카메라 위치 및 방향에 애니메이션 효과 주기'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], camera direction with key frames
- key frames [WPF], animating camera direction
- animation [WPF], camera position with key frames
- camera position [WPF], animating with key frames
- key frames [WPF], animating camera position
- camera direction [WPF], animating with key frames
ms.assetid: 5753024e-0057-454d-947f-43ea686879c7
ms.openlocfilehash: 28471f9b42140a6c75b043d33939503528b63194
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112169"
---
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a><span data-ttu-id="9a270-102">방법: 키 프레임을 사용하여 카메라 위치 및 방향에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="9a270-102">How to: Animate Camera Position and Direction Using Key Frames</span></span>
<span data-ttu-id="9a270-103">다음 예제에서는 <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> 3D 장면에서 a의 <xref:System.Windows.Media.Media3D.PerspectiveCamera> 위치를 애니메이션하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a270-103">In the following example, <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> is used to animate the position of a <xref:System.Windows.Media.Media3D.PerspectiveCamera> in a 3D scene.</span></span> <span data-ttu-id="9a270-104">또한 <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> 카메라가 3D 장면에서 가리키는 방향을 애니메이션하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a270-104">In addition, <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> is used to animate the direction the camera is pointing in the 3D scene.</span></span> <span data-ttu-id="9a270-105">이 두 애니메이션은 모두 일련의 애니메이션 효과를 만드는 여러 키 프레임을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9a270-105">Both of these animations use several key frames which create a series of animation effects:</span></span>  
  
1. <span data-ttu-id="9a270-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame>값 <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> 간에 매끄럽고 선형보간을 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a270-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> and <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> are used to create a smooth, linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="9a270-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame>값 <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> 간에 갑자기 "점프"를 만드는 데 사용됩니다(보간 없음).</span><span class="sxs-lookup"><span data-stu-id="9a270-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> are used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3. <span data-ttu-id="9a270-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame>속성에 <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> 따라 값 간에 변수 전환을 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a270-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> are used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="9a270-109">아래 예제에서는 애니메이션이 느리게 시작되지만 시간 세그먼트가 끝날 때까지 기하급수적으로 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="9a270-109">In the example below, the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a270-110">예제</span><span class="sxs-lookup"><span data-stu-id="9a270-110">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="9a270-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a270-111">See also</span></span>

- [<span data-ttu-id="9a270-112">3차원 장면에서 카메라 위치 및 방향에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="9a270-112">Animate Camera Position and Direction in a 3D Scene</span></span>](how-to-animate-camera-position-and-direction-in-a-3d-scene.md)
- [<span data-ttu-id="9a270-113">3D 그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="9a270-113">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
