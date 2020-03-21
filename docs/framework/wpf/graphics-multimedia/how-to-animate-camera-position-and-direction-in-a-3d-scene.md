---
title: '방법: 3차원 장면에서 카메라 위치 및 방향에 애니메이션 효과 주기'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], camera position in 3D scenes
- camera direction [WPF], animating in 3D scenes
- 3D scenes [WPF], animating camera position
- 3D scenes [WPF], animating camera direction
- camera position [WPF], animating in 3D scenes
- animation [WPF], camera direction in 3D scenes
ms.assetid: 480224b7-a5e5-4165-ba7f-ef760ddff94a
ms.openlocfilehash: 5ce94e154cd5aa29b59260f893ec2b63a08db0fc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112215"
---
# <a name="how-to-animate-camera-position-and-direction-in-a-3d-scene"></a><span data-ttu-id="b88fc-102">방법: 3차원 장면에서 카메라 위치 및 방향에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="b88fc-102">How to: Animate Camera Position and Direction in a 3D Scene</span></span>
<span data-ttu-id="b88fc-103">다음 예제에서는 카메라의 위치를 애니메이션하고 3D 장면에서 가리키는 방향을 애니메이션하는 방법을 보여 주며, 카메라의 위치를 애니메이션하는 방법을 보여 주습니다.</span><span class="sxs-lookup"><span data-stu-id="b88fc-103">The following example shows how to animate the position of a camera and animate the direction it is pointing in a 3D scene.</span></span> <span data-ttu-id="b88fc-104">이 작업은 <xref:System.Windows.Media.Animation.Point3DAnimation> <xref:System.Windows.Media.Animation.Vector3DAnimation> <xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A> <xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A> <xref:System.Windows.Media.Media3D.PerspectiveCamera>의 각각 의 및 속성을 사용하고 애니메이션하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b88fc-104">This is done by using <xref:System.Windows.Media.Animation.Point3DAnimation> and <xref:System.Windows.Media.Animation.Vector3DAnimation> to animate the <xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A> and <xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A> properties respectively of the <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span></span> <span data-ttu-id="b88fc-105">이와 같은 애니메이션을 사용하여 이벤트에 대한 응답으로 장면에 대한 구경꾼의 보기를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b88fc-105">You might use an animation like this to change the onlooker's view of a scene in response to an event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b88fc-106">예제</span><span class="sxs-lookup"><span data-stu-id="b88fc-106">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationExample.xaml#pointvector3danimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="b88fc-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b88fc-107">See also</span></span>

- <xref:System.Windows.Media.Animation.Vector3DAnimation>
- <xref:System.Windows.Media.Animation.Point3DAnimation>
- [<span data-ttu-id="b88fc-108">키 프레임을 사용하여 카메라 위치 및 방향에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="b88fc-108">Animate Camera Position and Direction Using Key Frames</span></span>](how-to-animate-camera-position-and-direction-using-key-frames.md)
- [<span data-ttu-id="b88fc-109">3D 그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="b88fc-109">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
