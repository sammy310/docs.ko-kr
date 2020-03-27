---
title: '방법: 키 프레임을 사용하여 사각형에 애니메이션 효과 주기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating RectangleGeometry objects with
- RectangleGeometry objects [WPF], animating with key frames
- animation [WPF], RectangleGeometry objects with key frames
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
ms.openlocfilehash: bcc9e7f198b8a20ffe13daf6508fb8a735937652
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344687"
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a>방법: 키 프레임을 사용하여 사각형에 애니메이션 효과 주기
이 예제에서는 키 프레임을 <xref:System.Windows.Media.RectangleGeometry.Rect%2A> 사용하여 a의 <xref:System.Windows.Media.RectangleGeometry> 속성을 애니메이션하는 방법을 보여 주며, 이 예제에서는  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> 클래스를 사용하여 의 <xref:System.Windows.Media.RectangleGeometry.Rect%2A> 속성을 <xref:System.Windows.Media.RectangleGeometry>애니메이션합니다. 이 애니메이션은 다음과 같은 방식으로 세 가지 키 프레임을 사용합니다.  
  
1. 처음 2초 동안 <xref:System.Windows.Media.Animation.LinearRectKeyFrame> 클래스의 인스턴스를 사용하여 사각형의 위치, 너비 및 높이가 점진적으로 변경됩니다. 과 같은 선형 키 프레임 <xref:System.Windows.Media.Animation.LinearRectKeyFrame> 값 사이 매끄러운 선형 전환을 만듭니다.  
  
2. 다음 절반 초가 끝날 때 클래스의 <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> 인스턴스를 사용하여 사각형의 높이를 갑자기 줄입니다. 이산 키 프레임은 <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> 값 사이에 갑작스런 변화를 만듭니다, 즉 높이의 감소가 빠르게 발생하고 미묘하지 않습니다.  
  
3. 마지막 2초 동안 <xref:System.Windows.Media.Animation.SplineRectKeyFrame> 클래스의 인스턴스를 사용하여 사각형을 원래 크기와 위치로 다시 변경합니다. 스프라인 키 <xref:System.Windows.Media.Animation.SplineRectKeyFrame> 프레임은 <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> 속성값에 따라 값 간에 가변 전환을 만듭니다. 이 예제에서 변화는 느리게 시작하다가 시간 세그먼트의 끝에 다가가면 기하급수적으로 빨라집니다.  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 전체 샘플을 보려면 [키 프레임 애니메이션 샘플](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)을 참조하세요.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Media.RectangleGeometry>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>
- [키 프레임 애니메이션 개요](key-frame-animations-overview.md)
- [키 프레임 방법 항목](key-frame-animation-how-to-topics.md)
