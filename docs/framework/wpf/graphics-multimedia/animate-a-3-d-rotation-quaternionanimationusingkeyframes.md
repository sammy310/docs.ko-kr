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
# <a name="how-to-animate-a-3d-rotation-using-key-frames-quaternionanimationusingkeyframes"></a>방법: 키 프레임을 사용하여 3D 회전 애니메이션(쿼터니언애니메이션키프레임)
다음 예제에서는 <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> 3D 오브젝트를 회전하는 데 사용됩니다. 이 애니메이션은 다음과 같은 키 프레임을 사용합니다.  
  
1. <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame>은 값 간에 매끄럽고 선형보간을 만드는 데 사용됩니다.  
  
2. <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame>은 값 사이에 갑작스런 "점프"를 만드는 데 사용됩니다(보간 없음).  
  
3. <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame>속성에 <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> 따라 값 간에 변수 전환을 만드는 데 사용됩니다. 아래 예제에서는 애니메이션의 이 부분이 느리게 시작되지만 시간 세그먼트가 끝날 때까지 기하급수적으로 속도가 빨라집니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>참고 항목

- [스토리보드를 사용하여 3D 회전 애니메이션](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [회전3D애니메이션을 사용하여 3D 회전 애니메이션](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [쿼터니언을 사용하여 3D 회전 애니메이션](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [키 프레임을 사용하여 3D 회전 애니메이션(회전3DAnimationUsingKeyFrame)](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [3D 그래픽 개요](3-d-graphics-overview.md)
- [키 프레임 애니메이션 개요](key-frame-animations-overview.md)
