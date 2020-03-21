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
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a>방법: 키 프레임을 사용하여 카메라 위치 및 방향에 애니메이션 효과 주기
다음 예제에서는 <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> 3D 장면에서 a의 <xref:System.Windows.Media.Media3D.PerspectiveCamera> 위치를 애니메이션하는 데 사용됩니다. 또한 <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> 카메라가 3D 장면에서 가리키는 방향을 애니메이션하는 데 사용됩니다. 이 두 애니메이션은 모두 일련의 애니메이션 효과를 만드는 여러 키 프레임을 사용합니다.  
  
1. <xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame>값 <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> 간에 매끄럽고 선형보간을 만드는 데 사용됩니다.  
  
2. <xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame>값 <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> 간에 갑자기 "점프"를 만드는 데 사용됩니다(보간 없음).  
  
3. <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame>속성에 <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> 따라 값 간에 변수 전환을 만드는 데 사용됩니다. 아래 예제에서는 애니메이션이 느리게 시작되지만 시간 세그먼트가 끝날 때까지 기하급수적으로 빨라집니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>참고 항목

- [3차원 장면에서 카메라 위치 및 방향에 애니메이션 효과 주기](how-to-animate-camera-position-and-direction-in-a-3d-scene.md)
- [3D 그래픽 개요](3-d-graphics-overview.md)
