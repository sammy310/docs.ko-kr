---
title: '방법: 키 프레임을 사용하여 크기 변경에 애니메이션 효과 주기'
ms.date: 03/30/2017
helpviewer_keywords:
- key frames [WPF], animating size changes with
- animation [WPF], size changes with key frames
- size changes [WPF], animating with key frames
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
ms.openlocfilehash: 42cecfc9df4304be4033ea39edc0517016de4a92
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344645"
---
# <a name="how-to-animate-size-changes-by-using-key-frames"></a>방법: 키 프레임을 사용하여 크기 변경에 애니메이션 효과 주기
이 예제에서는 키 프레임을 사용하여 크기 변경에 애니메이션 효과를 주는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> 클래스를 사용하여 의 <xref:System.Windows.Media.ArcSegment.Size%2A> 속성을 <xref:System.Windows.Media.ArcSegment>애니메이션합니다. 이 애니메이션은 다음과 같은 방식으로 세 가지 키 프레임을 사용합니다.  
  
1. 애니메이션의 첫 번째 후반초 동안 클래스의 <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> 인스턴스를 사용하여 점차적으로 호의 크기를 늘립니다. 같은 <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> 선형 키 프레임은 값 간에 부드러운 선형 전환을 만듭니다.  
  
2. 다음 후반초가 끝나면 클래스의 인스턴스를 <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> 사용하여 갑자기 호의 크기를 늘립니다. 이산 키 프레임은 값 사이에 갑작스런 점프를 만드는 것과 같이, <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> 즉 크기 변화가 갑자기 발생하고 미묘하지 않습니다.  
  
3. 마지막 2초 동안 클래스의 인스턴스를 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> 사용하여 호의 크기를 늘립니다. 스프라인 키 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> 프레임은 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> 속성값에 따라 값 간에 가변 전환을 만듭니다. 이 예제에서 원호의 크기는 처음에는 느리게 증가했다가 시간 세그먼트가 끝나면서 기하급수적으로 증가합니다.  
  
 [!code-xaml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 전체 샘플을 보려면 [키 프레임 애니메이션 샘플](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)을 참조하세요.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>
- <xref:System.Windows.Media.ArcSegment.Size%2A>
- <xref:System.Windows.Media.ArcSegment>
- <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>
- <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>
- [키 프레임 애니메이션 개요](key-frame-animations-overview.md)
- [키 프레임 방법 항목](key-frame-animation-how-to-topics.md)
