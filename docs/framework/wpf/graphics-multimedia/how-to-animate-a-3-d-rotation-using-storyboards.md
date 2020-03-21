---
title: '방법: 스토리보드를 사용하여 3D 회전 애니메이션'
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF]
- 3D translations [WPF], animating [WPF], with Storyboards
- animation [WPF], 3D translations [WPF], with Storyboards
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
ms.openlocfilehash: 088f1a33cfc73a706ffed55ffff6494adaf8fca4
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112218"
---
# <a name="how-to-animate-a-3d-rotation-using-storyboards"></a>방법: 스토리보드를 사용하여 3D 회전 애니메이션
다음 예제에서는 3D 오브젝트가 오브젝트의 <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> 속성과 <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> 속성을 애니메이션하여 "흔들리는" 동안 <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> 회전하도록 만드는 방법을 보여 주습니다. 이 <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> 오브젝트는 3D 오브젝트의 회전 변환을 지정하므로 해당 속성에 애니메이션을 적용하면 욕구 회전 효과가 만들어집니다. 스토리보드 <xref:System.Windows.Media.Animation.DoubleAnimation> 내에서 <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> 속성을 애니메이션하는 데 사용되며 <xref:System.Windows.Media.Animation.Vector3DAnimation> 속성에 애니메이션을 <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> 사용하는 데 사용됩니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a>참고 항목

- [회전3D애니메이션을 사용하여 3D 회전 애니메이션](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [키 프레임을 사용하여 3D 회전 애니메이션(회전3DAnimationUsingKeyFrame)](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [3D 그래픽 개요](3-d-graphics-overview.md)
- [Storyboard 개요](storyboards-overview.md)
