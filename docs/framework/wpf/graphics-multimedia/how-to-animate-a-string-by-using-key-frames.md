---
title: '방법: 키 프레임을 사용하여 문자열에 애니메이션 효과 주기'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
ms.openlocfilehash: c954806ca901bbfc3ab6d4bbcc237cd0e404f154
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344659"
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a>방법: 키 프레임을 사용하여 문자열에 애니메이션 효과 주기
이 예제에서는 키 프레임을 사용하여 컨트롤의 <xref:System.Windows.Controls.ContentControl.Content%2A> 속성인 문자열을 <xref:System.Windows.Controls.Button> 애니메이션하는 방법을 보여 주며, 이 예제에서는 컨트롤의 속성입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> 클래스를 사용하여 의 <xref:System.Windows.Controls.ContentControl.Content%2A> 속성을 <xref:System.Windows.Controls.Button>애니메이션합니다.  
  
 키 프레임으로 만든 문자열 애니메이션은 <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> 개별 키 프레임만 사용할 수 있으므로 이 예제의 모든 키 프레임은 클래스의 인스턴스를 사용합니다. 이산 키 프레임은 값 간에 갑작스런 점프를 만드는 것과 같이 <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> 애니메이션의 변경이 빠르게 발생하고 미묘하지 않습니다.  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 전체 샘플을 보려면 [키 프레임 애니메이션 샘플](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)을 참조하세요.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.ContentControl.Content%2A>
- <xref:System.Windows.Controls.Button>
- <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>
- [키 프레임 애니메이션 개요](key-frame-animations-overview.md)
- [키 프레임 방법 항목](key-frame-animation-how-to-topics.md)
