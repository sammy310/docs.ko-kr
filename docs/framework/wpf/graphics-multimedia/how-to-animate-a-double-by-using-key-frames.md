---
title: '방법: 키 프레임을 사용하여 Double에 애니메이션 효과 주기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Doubles [WPF], animating with key frames
- animation [WPF], Doubles with key frames
- key frames [WPF], animating Doubles with
ms.assetid: 3a1a7dba-7694-4907-8a2f-3408baebfa82
ms.openlocfilehash: 9eab794cc8411230226cddc97beaa13c1bdd9405
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344927"
---
# <a name="how-to-animate-a-double-by-using-key-frames"></a>방법: 키 프레임을 사용하여 Double에 애니메이션 효과 주기
이 예제에서는 키 프레임을 사용하여 사용하는 <xref:System.Double> 속성의 값을 애니메이션하는 방법을 보여 주며, 이 예제에서는  
  
## <a name="example"></a>예제  
 다음 예제는 화면에서 사각형을 이동합니다. 이 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> 클래스를 사용하여 <xref:System.Windows.Media.TranslateTransform.X%2A> 에 적용된 <xref:System.Windows.Media.TranslateTransform> 의 <xref:System.Windows.Shapes.Rectangle>속성을 애니메이션합니다. 무제한 반복되는 이 애니메이션은 다음과 같은 방식으로 세 가지 키 프레임을 사용합니다.  
  
1. 처음 3 초 동안의 인스턴스를 사용 하 여는 <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> 500 위치 시작 위치부터 일정 한 속도로 경로 따라 사각형을 이동 하는 클래스입니다. 과 같은 선형 키 프레임 <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> 값 사이 매끄러운 선형 전환을 만듭니다.  
  
2. 4 초가 끝나면의 인스턴스를 사용 하는 <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> 갑자기 다음 위치로 사각형을 이동 하는 클래스입니다. 과 같은 불연속 키 프레임 <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> 값 간에 갑작스러운 이동을 만듭니다. 이 예제에서 사각형은 시작 위치에 있다가 갑자기 500 위치에 나타납니다.  
  
3. 마지막 2 초의 인스턴스를 사용 하는 <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> 클래스 사각형을 다시 시작 위치로 이동 합니다. 과 같은 스플라인 키 프레임 <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> 의 값에 따라 값 사이 가변 전환을 만듭니다는 <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A> 속성입니다. 이 예제에서 사각형은 처음에는 느리게 이동하다가 시간 세그먼트의 끝에 다가가면 기하급수적으로 빨라집니다.  
  
 [!code-csharp[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/AltDoubleAnimationUsingKeyFramesExample.cs#altdoubleanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/altdoubleanimationusingkeyframesexample.vb#altdoubleanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/AltDoubleAnimationUsingKeyFramesExample.xaml#altdoubleanimationusingkeyframeswholepage)]  
  
 전체 샘플을 보려면 [키 프레임 애니메이션 샘플](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)을 참조하세요.  
  
 다른 애니메이션 예제와 일관성을 유지하기 위해 이 예제의 코드 버전은 개체를 <xref:System.Windows.Media.Animation.Storyboard> 사용하여 을 적용합니다. <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> 또는 코드에 단일 애니메이션을 적용할 때 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> <xref:System.Windows.Media.Animation.Storyboard>을 사용하는 대신 메서드를 사용하는 것이 더 간단합니다. 예를 들어 [스토리보드를 사용하지 않고 속성 애니메이션을](how-to-animate-a-property-without-using-a-storyboard.md)참조하십시오.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>
- <xref:System.Windows.Shapes.Rectangle>
- <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>
- <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>
- [키 프레임 애니메이션 개요](key-frame-animations-overview.md)
- [키 프레임 방법 항목](key-frame-animation-how-to-topics.md)
