---
title: '방법: 키 프레임을 사용하여 3D 회전 애니메이션'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3D translations [WPF], with key frames (Rotation3DAnimation)
- key frames [WPF], Rotation3DAnimation
- 3D translations [WPF], animating [WPF], with key frames (Rotation3DAnimation)
ms.assetid: 6f671b95-7f30-4836-9a4f-aeb7dc30121f
ms.openlocfilehash: 2b9059df079125c34c70237c0f600751020044c6
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112312"
---
# <a name="how-to-animate-a-3d-rotation-using-key-frames"></a>방법: 키 프레임을 사용하여 3D 회전 애니메이션
다음 예제에서는 <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> 3D 오브젝트가 회전하는 동안 회전 축이 애니메이션되어 "흔들림"이 발생하도록 하는 데 사용됩니다. 이 애니메이션은 다음과 같은 키 프레임을 사용합니다.  
  
1. <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame>은 값 간에 매끄럽고 선형보간을 만드는 데 사용됩니다.  
  
2. <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame>은 값 사이에 갑작스런 "점프"를 만드는 데 사용됩니다(보간 없음).  
  
3. <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame>속성에 <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> 따라 값 간에 변수 전환을 만드는 데 사용됩니다. 아래 예제에서는 애니메이션의 이 부분이 느리게 시작되지만 시간 세그먼트가 끝날 때까지 기하급수적으로 속도가 빨라집니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[Animation3DGallery_snip#Rotation3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotation3DAnimationUsingKeyFramesExample.xaml#rotation3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>참고 항목

- [3D 그래픽 개요](3-d-graphics-overview.md)
- [키 프레임 애니메이션 개요](key-frame-animations-overview.md)
- [스토리보드를 사용하여 3D 회전 애니메이션](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [회전3D애니메이션을 사용하여 3D 회전 애니메이션](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [쿼터니언을 사용하여 3D 회전 애니메이션](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [키 프레임을 사용하여 3D 회전 애니메이션(쿼터니언애니메이션키프레임)](animate-a-3-d-rotation-quaternionanimationusingkeyframes.md)
