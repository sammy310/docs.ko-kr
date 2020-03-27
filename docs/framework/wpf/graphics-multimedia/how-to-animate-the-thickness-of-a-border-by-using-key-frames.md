---
title: '방법: 키 프레임을 사용하여 테두리 두께에 애니메이션 효과 주기'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], border thickness with key frames
- key frames [WPF], animating border thickness with
- border thickness [WPF], animating with key frames
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
ms.openlocfilehash: 884b62e88c347449ae39caa9c028d09db39b9f4b
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344700"
---
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a>방법: 키 프레임을 사용하여 테두리 두께에 애니메이션 효과 주기
이 예제에서는 <xref:System.Windows.Controls.Control.BorderThickness%2A> <xref:System.Windows.Controls.Border>의 속성을 애니메이션하는 방법을 보여 주며 의 속성을 애니메이션합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> 클래스를 사용하여 의 <xref:System.Windows.Controls.Control.BorderThickness%2A> 속성을 <xref:System.Windows.Controls.Border>애니메이션합니다. 이 애니메이션은 다음과 같은 방식으로 세 가지 키 프레임을 사용합니다.  
  
1. 전반초에는 클래스의 인스턴스를 <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> 사용하여 테두리의 두께를 점진적으로 늘립니다. 이 예제에서는 값 간에 부드러운 선형 증가를 만드는 데 사용합니다. <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>  
  
2. 다음 후반초가 끝나면 클래스의 인스턴스를 <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> 사용하여 갑자기 테두리의 두께를 늘립니다. 값 간에 갑작스런 점프를 만드는 <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> 것과 같은 불연속 키 프레임, 즉 애니메이션의 이동이 육포입니다.  
  
3. 마지막 2초 동안 클래스의 인스턴스를 <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> 사용하여 테두리의 두께를 줄입니다. <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> 속성값에 <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> 따라 값 간에 변수 전환을 만드는 것과 같은 스프라인 키 프레임입니다. 이 키 프레임에서 애니메이션은 느리게 시작하다가 시간 세그먼트의 끝에 다가가면 기하급수적으로 빨라집니다.  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 전체 샘플을 보려면 [키 프레임 애니메이션 샘플](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)을 참조하세요.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>
- [키 프레임 애니메이션 개요](key-frame-animations-overview.md)
- [키 프레임 방법 항목](key-frame-animation-how-to-topics.md)
- [BorderThickness 값에 애니메이션 효과 주기](../controls/how-to-animate-a-borderthickness-value.md)
