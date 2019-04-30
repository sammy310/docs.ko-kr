---
title: '방법: 키 프레임을 사용하여 매트릭스에 애니메이션 효과 주기'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: ff5320fa5b4441ae3e0f414b274ab9118b77ec50
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62020246"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a>방법: 키 프레임을 사용하여 매트릭스에 애니메이션 효과 주기
애니메이션을 적용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.MatrixTransform.Matrix%2A> 의 속성을 <xref:System.Windows.Media.MatrixTransform> 키 프레임을 사용 하 여 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 합니다 <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> 클래스에 애니메이션 효과를 <xref:System.Windows.Media.MatrixTransform.Matrix%2A> 의 속성을 <xref:System.Windows.Media.MatrixTransform>합니다. 이 예제에서는 사용 합니다 <xref:System.Windows.Media.MatrixTransform> 모양 및 위치를 변환 하는 개체는 <xref:System.Windows.Controls.Button>합니다.  
  
 이 애니메이션에 사용 하 여는 <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> 두 개의 키 프레임을 만들려면 클래스 및 해당를 사용 하 여 다음 작업을 수행 합니다.  
  
1. 첫 번째 애니메이션 <xref:System.Windows.Media.Matrix> 첫 번째 0.2 초 동안. 변경 예제는 <xref:System.Windows.Media.Matrix.M11%2A> 및 <xref:System.Windows.Media.Matrix.M12%2A> 의 속성을 <xref:System.Windows.Media.Matrix>입니다. 이렇게이 변경 하면 단추를 늘어나고 기울어집니다. 예제도 변경 합니다 <xref:System.Windows.Media.Matrix.OffsetX%2A> 및 <xref:System.Windows.Media.Matrix.OffsetY%2A> 속성 단추 위치를 변경 되도록 합니다.  
  
2. 두 번째 애니메이션 <xref:System.Windows.Media.Matrix> 1.0 초에서. 단추는 단추는 더 이상 왜곡 또는 확장 하는 동안 다른 위치로 이동 합니다.  
  
3. 애니메이션을 무기한 반복 됩니다.  
  
> [!NOTE]
>  파생 된 키 프레임을 <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> 개체 값 간에 갑작스러운 이동을 만듭니다, 즉, 애니메이션의 이동을 비정상적입니다.  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 전체 샘플을 보려면 [키 프레임 애니메이션 샘플](https://go.microsoft.com/fwlink/?LinkID=160012)을 참조하세요.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [키 프레임 애니메이션 개요](key-frame-animations-overview.md)
- [키 프레임 방법 항목](key-frame-animation-how-to-topics.md)
