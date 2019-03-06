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
ms.openlocfilehash: 5df3a201eaae4ddcf2e5d5aac3de6e0d5013947c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353402"
---
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a><span data-ttu-id="02899-102">방법: 키 프레임을 사용하여 카메라 위치 및 방향에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="02899-102">How to: Animate Camera Position and Direction Using Key Frames</span></span>
<span data-ttu-id="02899-103">다음 예에서 <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> 위치에 애니메이션을 적용 하는 데 사용 되는 <xref:System.Windows.Media.Media3D.PerspectiveCamera> 3D 장면에서.</span><span class="sxs-lookup"><span data-stu-id="02899-103">In the following example, <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> is used to animate the position of a <xref:System.Windows.Media.Media3D.PerspectiveCamera> in a 3D scene.</span></span> <span data-ttu-id="02899-104">또한 <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> 3D 장면에서 카메라 가리키고 방향에 애니메이션을 적용 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02899-104">In addition, <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> is used to animate the direction the camera is pointing in the 3D scene.</span></span> <span data-ttu-id="02899-105">이러한 애니메이션은 둘 다 다양 한 애니메이션 효과 만드는 몇 가지 키 프레임을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="02899-105">Both of these animations use several key frames which create a series of animation effects:</span></span>  
  
1.  <span data-ttu-id="02899-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> 및 <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> 값 사이 매끄러운 선형 보간을 만드는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02899-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> and <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> are used to create a smooth, linear interpolation between values.</span></span>  
  
2.  <span data-ttu-id="02899-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> 및 <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> "사이 갑작스러운" 값 (보간 없음)를 만드는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02899-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> are used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3.  <span data-ttu-id="02899-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> 및 <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> 에 따라 값 사이 가변 전환을 만드는 데 사용 되는 <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="02899-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> are used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="02899-109">아래 예제에서는 애니메이션이 서서히 하지만 시간 세그먼트의 끝에 다가가 시작, 면 기하급수적으로 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="02899-109">In the example below, the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02899-110">예제</span><span class="sxs-lookup"><span data-stu-id="02899-110">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="02899-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="02899-111">See also</span></span>
- [<span data-ttu-id="02899-112">3차원 장면에서 카메라 위치 및 방향에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="02899-112">Animate Camera Position and Direction in a 3D Scene</span></span>](how-to-animate-camera-position-and-direction-in-a-3d-scene.md)
- [<span data-ttu-id="02899-113">3차원 그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="02899-113">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
