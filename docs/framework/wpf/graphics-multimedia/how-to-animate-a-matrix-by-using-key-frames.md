---
title: '방법: 키 프레임을 사용하여 매트릭스에 애니메이션 효과 주기'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: eb596cf728f8a7cc1964963b8509f42bdd7a392a
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344911"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a>방법: 키 프레임을 사용하여 매트릭스에 애니메이션 효과 주기
이 예제에서는 키 프레임을 <xref:System.Windows.Media.MatrixTransform.Matrix%2A> 사용하여 a의 <xref:System.Windows.Media.MatrixTransform> 속성을 애니메이션하는 방법을 보여 주며, 이 예제에서는  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> 클래스를 사용하여 의 <xref:System.Windows.Media.MatrixTransform.Matrix%2A> 속성을 <xref:System.Windows.Media.MatrixTransform>애니메이션합니다. 이 예제에서는 <xref:System.Windows.Media.MatrixTransform> 개체를 사용하여 <xref:System.Windows.Controls.Button>의 모양과 위치를 변환합니다.  
  
 이 애니메이션은 <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> 클래스를 사용하여 두 개의 키 프레임을 만들고 다음과 같은 작업을 수행합니다.  
  
1. 처음 0.2초 동안 첫 번째 <xref:System.Windows.Media.Matrix> 애니메이션을 애니메이션합니다. 이 예제는 <xref:System.Windows.Media.Matrix.M11%2A> <xref:System.Windows.Media.Matrix.M12%2A> <xref:System.Windows.Media.Matrix>의 및 속성을 변경합니다. 이렇게 변경하면 버튼이 늘어나고 기울어집니다. 또한 이 예제는 단추의 <xref:System.Windows.Media.Matrix.OffsetX%2A> 위치가 변경되도록 및 <xref:System.Windows.Media.Matrix.OffsetY%2A> 속성을 변경합니다.  
  
2. 1.0초에서 <xref:System.Windows.Media.Matrix> 두 번째 애니메이션을 사용합니다. 버튼이 더 이상 기울어지거나 늘어나지 않는 동안 버튼이 다른 위치로 이동합니다.  
  
3. 애니메이션을 무기한 반복합니다.  
  
> [!NOTE]
> <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> 오브젝트에서 파생된 키 프레임은 값 간에 갑작스런 점프, 즉 애니메이션의 이동이 육포됩니다.  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 전체 샘플을 보려면 [키 프레임 애니메이션 샘플](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)을 참조하세요.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [키 프레임 애니메이션 개요](key-frame-animations-overview.md)
- [키 프레임 방법 항목](key-frame-animation-how-to-topics.md)
