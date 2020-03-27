---
title: '방법: 키 프레임을 사용하여 개체에 애니메이션 효과 주기'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: 0bc33b189fd856dbe8106c1db35bc18e27ea131e
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344714"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a>방법: 키 프레임을 사용하여 개체에 애니메이션 효과 주기
이 예제에서는 키 프레임을 사용하여 <xref:System.Windows.Controls.Page.Background%2A> <xref:System.Windows.Controls.Page> 컨트롤의 속성인 개체를 애니메이션하는 방법을 보여 주습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> 클래스를 사용 하 여 <xref:System.Windows.Controls.Page.Background%2A> <xref:System.Windows.Controls.Page> 컨트롤의 속성에 대 한 색상 변경 내용을 애니메이션합니다. 예제 애니메이션은 정기적으로 다른 배경 브러시로 변경됩니다. 이 애니메이션은 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> 클래스를 사용하여 세 가지 키 프레임을 만듭니다. 애니메이션은 다음과 같은 방식으로 키 프레임을 사용합니다.  
  
1. 첫 번째 초가 끝나면 클래스의 인스턴스에 <xref:System.Windows.Media.LinearGradientBrush> 애니메이션이 애니메이션됩니다. 이 예제의 이 섹션에서는 색상이 노란색에서 주황색으로 바각하도록 배경 색에 선형 그라데이션을 적용합니다.  
  
2. 다음 두 번째 초가 끝나면 클래스의 인스턴스에 애니메이션이 애니메이션됩니다. <xref:System.Windows.Media.RadialGradientBrush> 이 예제의 이 섹션에서는 색상이 흰색에서 파란색에서 검은색으로 전환되도록 배경 색에 방사형 그라데이션을 적용합니다.  
  
3. 세 번째 초가 끝나면 클래스의 인스턴스에 <xref:System.Windows.Media.DrawingBrush> 애니메이션이 애니메이션됩니다. 예제의 이 섹션에서는 바둑판 패턴을 배경에 적용합니다.  
  
4. 애니메이션이 다시 시작되고 무기한 반복됩니다.  
  
> [!NOTE]
> <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>클래스와 함께 사용할 수 있는 키 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> 프레임의 유일한 유형입니다. 키 프레임같은 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> 것은 값의 급격한 변화를 만드는 것, 즉 이 예제의 색상 변화가 갑자기 발생한다.  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 전체 샘플을 보려면 [키 프레임 애니메이션 샘플](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)을 참조하세요.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.Page.Background%2A>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>
- <xref:System.Windows.Media.LinearGradientBrush>
- <xref:System.Windows.Media.RadialGradientBrush>
- <xref:System.Windows.Media.DrawingBrush>
- [키 프레임 애니메이션 개요](key-frame-animations-overview.md)
- [키 프레임 방법 항목](key-frame-animation-how-to-topics.md)
