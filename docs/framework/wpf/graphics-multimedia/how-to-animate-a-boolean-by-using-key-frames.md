---
title: '방법: 키 프레임을 사용하여 부울에 애니메이션 효과 주기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Booleans [WPF], animating with key frames
- animation [WPF], Booleans with key frames
- key frames [WPF], animating Booleans with
ms.assetid: 4b0fac96-6231-4fcf-9775-4dd673ddc785
ms.openlocfilehash: 35704996dcf21fe463169dc13572941bcd8fbad1
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344928"
---
# <a name="how-to-animate-a-boolean-by-using-key-frames"></a>방법: 키 프레임을 사용하여 부울에 애니메이션 효과 주기
이 예제에서는 키 프레임을 사용하여 컨트롤의 부울 속성 값을 애니메이션하는 방법을 보여 주며, 이 예제에서는 컨트롤의 부울 속성 값을 애니메이션하는 방법을 보여 주며, 이 예제에서는 <xref:System.Windows.Controls.Button>  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> 클래스를 사용하여 컨트롤의 <xref:System.Windows.UIElement.IsEnabled%2A> 속성을 <xref:System.Windows.Controls.Button> 애니메이션합니다. 이 예제의 모든 키 프레임은 <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> 클래스의 인스턴스를 사용합니다. 이산 키 프레임은 값 간에 갑작스런 점프를 만드는 것과 같이 <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> 애니메이션의 움직임이 육포입니다.  
  
 [!code-csharp[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/BooleanAnimationUsingKeyFramesExample.cs#booleananimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/booleananimationusingkeyframesexample.vb#booleananimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/BooleanAnimationUsingKeyFramesExample.xaml#booleananimationusingkeyframeswholepage)]  
  
 전체 샘플을 보려면 [키 프레임 애니메이션 샘플](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)을 참조하세요.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>
- <xref:System.Windows.UIElement.IsEnabled%2A>
- <xref:System.Windows.Controls.Button>
- [키 프레임 애니메이션 개요](key-frame-animations-overview.md)
- [키 프레임 방법 항목](key-frame-animation-how-to-topics.md)
