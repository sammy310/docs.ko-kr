---
title: '방법: 쿼터니언을 사용하여 3D 회전 애니메이션'
ms.date: 03/30/2017
helpviewer_keywords:
- quaternions [WPF]
- animation [WPF], 3D translations [WPF], with quaternions
- 3D translations [WPF], animating [WPF], with quaternions
ms.assetid: adca9cb1-066b-4de8-abbb-6b4007579ee7
ms.openlocfilehash: 0d229b0a714cc53459943fae751ab4d4f787d7d8
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112247"
---
# <a name="how-to-animate-a-3d-rotation-using-quaternions"></a>방법: 쿼터니언을 사용하여 3D 회전 애니메이션
이 예제에서는 쿼터니언을 사용하여 3D 오브젝트의 회전을 애니메이션하는 방법을 보여 주며, 이 예제에서는 쿼터니언을 사용하여 애니메이션을 사용하는 방법을 보여 주며, 3D 오브젝트의 회전을 애니메이션하는 방법을 보여 주며, 이 예제에서는 쿼터니언을 사용하여 3D 오브젝트의 회전을 애니메이션하는 방법을 보여  
  
 아래 코드는 <xref:System.Windows.Media.Media3D.QuaternionRotation3D> <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> <xref:System.Windows.Media.Media3D.RotateTransform3D>에 대한 속성값으로 사용된 값을 보여 주며,  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 이것은 <xref:System.Windows.Media.Media3D.QuaternionRotation3D> 아래 코드를 <xref:System.Windows.Media.Animation.QuaternionAnimation> <xref:System.Windows.Media.Animation.Storyboard> 사용하여 내에서 애니메이션됩니다.  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a>예제  
 다음 코드에는 전체 샘플을 보여 줍니다.  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a>참고 항목

- [애니메이션 개요](animation-overview.md)
- [3D 장면 만들기](how-to-create-a-3-d-scene.md)
- [3D 그래픽 개요](3-d-graphics-overview.md)
- [Transform 개요](transforms-overview.md)
- [스토리보드를 사용하여 3D 회전 애니메이션](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [회전3D애니메이션을 사용하여 3D 회전 애니메이션](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
