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
# <a name="how-to-animate-camera-position-and-direction-in-a-3d-scene"></a>방법: 3차원 장면에서 카메라 위치 및 방향에 애니메이션 효과 주기
다음 예제에서는 카메라의 위치를 애니메이션하고 3D 장면에서 가리키는 방향을 애니메이션하는 방법을 보여 주며, 카메라의 위치를 애니메이션하는 방법을 보여 주습니다. 이 작업은 <xref:System.Windows.Media.Animation.Point3DAnimation> <xref:System.Windows.Media.Animation.Vector3DAnimation> <xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A> <xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A> <xref:System.Windows.Media.Media3D.PerspectiveCamera>의 각각 의 및 속성을 사용하고 애니메이션하여 수행됩니다. 이와 같은 애니메이션을 사용하여 이벤트에 대한 응답으로 장면에 대한 구경꾼의 보기를 변경할 수 있습니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationExample.xaml#pointvector3danimationexamplewholepage)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Media.Animation.Vector3DAnimation>
- <xref:System.Windows.Media.Animation.Point3DAnimation>
- [키 프레임을 사용하여 카메라 위치 및 방향에 애니메이션 효과 주기](how-to-animate-camera-position-and-direction-using-key-frames.md)
- [3D 그래픽 개요](3-d-graphics-overview.md)
