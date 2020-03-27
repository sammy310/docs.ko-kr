---
title: '방법: 키 프레임을 사용하여 포인트에 애니메이션 효과 주기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating Points with
- Points [WPF], animating with key frames
- animation [WPF], Points with key frames
ms.assetid: d2e2ef10-0773-4133-856e-d41c09f60ded
ms.openlocfilehash: edcba36644cf78d6e98f934d9bd8b593af38b328
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344876"
---
# <a name="how-to-animate-a-point-by-using-key-frames"></a>방법: 키 프레임을 사용하여 포인트에 애니메이션 효과 주기
이 예제에서는 클래스를 <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> 사용하여 에 애니메이션을 <xref:System.Windows.Point>애니메이션하는 방법을 보여 주며 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 삼각형 경로를 따라 타원을 이동합니다. 이 예제에서는 <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> 클래스를 사용하여 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 의 속성을 <xref:System.Windows.Media.EllipseGeometry>애니메이션합니다. 이 애니메이션은 다음과 같은 방식으로 세 가지 키 프레임을 사용합니다.  
  
1. 전반초에는 클래스의 인스턴스를 <xref:System.Windows.Media.Animation.LinearPointKeyFrame> 사용하여 시작 위치에서 일정한 속도로 경로를 따라 타원을 이동합니다. 같은 <xref:System.Windows.Media.Animation.LinearPointKeyFrame> 선형 키 프레임은 값 사이에 부드러운 선형 보간을 만듭니다.  
  
2. 다음 후반초가 끝날 때 <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> 클래스의 인스턴스를 사용하여 경로를 따라 타원을 다음 위치로 갑자기 이동합니다. 과 같은 불연속 키 프레임 <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> 값 간에 갑작스러운 이동을 만듭니다.  
  
3. 마지막 2초 동안 <xref:System.Windows.Media.Animation.SplinePointKeyFrame> 클래스의 인스턴스를 사용하여 타원을 다시 시작 위치로 이동합니다. 스프라인 키 <xref:System.Windows.Media.Animation.SplinePointKeyFrame> 프레임은 <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> 속성값에 따라 값 간에 가변 전환을 만듭니다. 이 예제에서 애니메이션은 느리게 시작하다가 시간 세그먼트의 끝에 다가가면 기하급수적으로 빨라집니다.  
  
 [!code-csharp[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/PointAnimationUsingKeyFramesExample.cs#pointanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/pointanimationusingkeyframesexample.vb#pointanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/PointAnimationUsingKeyFramesExample.xaml#pointanimationusingkeyframeswholepage)]  
  
 전체 샘플을 보려면 [키 프레임 애니메이션 샘플](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)을 참조하세요.  
  
 다른 애니메이션 예제와 일관성을 유지하기 위해 이 예제의 코드 버전은 개체를 <xref:System.Windows.Media.Animation.Storyboard> 사용하여 을 적용합니다. <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> 그러나 코드에 단일 애니메이션을 적용할 때 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> <xref:System.Windows.Media.Animation.Storyboard>는 을 사용하는 대신 메서드를 사용하는 것이 더 간단합니다. 예를 들어 [스토리보드를 사용하지 않고 속성 애니메이션을](how-to-animate-a-property-without-using-a-storyboard.md)참조하십시오.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A?displayProperty=nameWithType>
- <xref:System.Windows.Media.EllipseGeometry>
- [키 프레임 애니메이션 개요](key-frame-animations-overview.md)
- [키 프레임 방법 항목](key-frame-animation-how-to-topics.md)
