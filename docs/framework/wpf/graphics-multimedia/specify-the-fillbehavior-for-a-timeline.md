---
title: '방법: 활성 기간이 끝난 Timeline의 FillBehavior 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
ms.openlocfilehash: 1f54f2c1bb49bb7a0301f112a109194ab1a8658e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141175"
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a>방법: 활성 기간이 끝난 Timeline의 FillBehavior 지정
이 예제에서는 애니메이션된 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성의 <xref:System.Windows.Media.Animation.Timeline> 비활성을 지정하는 방법을 보여 주며, 이 예제에서는 애니메이션된 속성의 비활성 을 지정하는 방법을 보여 주며 있습니다.  
  
## <a name="example"></a>예제  
 a의 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> <xref:System.Windows.Media.Animation.Timeline> 속성은 애니메이션되지 않을 때, 즉 비활성 상태이지만 부모가 <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Timeline> 활성 또는 보류 기간 내에 있을 때 애니메이션된 속성의 값에 어떤 일이 발생하는지 결정합니다. 예를 들어 애니메이션이 종료된 후에도 애니메이션 속성이 끝 값에 유지되거나 애니메이션이 시작되기 전에 있던 값으로 되돌아갑니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation> a를 사용하여 <xref:System.Windows.FrameworkElement.Width%2A> 두 사각형의 애니메이션을 애니메이션합니다. 각 사각형은 다른 <xref:System.Windows.Media.Animation.Timeline> 개체를 사용합니다.  
  
 하나는 사각형의 너비가 <xref:System.Windows.Media.Animation.Timeline> 끝날 때 애니메이션되지 않은 값으로 되돌아갑니다. <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> <xref:System.Windows.Media.Animation.FillBehavior.Stop> 다른 <xref:System.Windows.Media.Animation.Timeline> 하나는 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 의 <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>를 가지며, 이로 인해 너비가 <xref:System.Windows.Media.Animation.Timeline> 끝날 때 끝 값으로 유지됩니다.  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 전체 샘플은 [애니메이션 예제 갤러리](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples)를 참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Media.Animation.DoubleAnimation>
- <xref:System.Windows.FrameworkElement.Width%2A>
- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.FillBehavior.Stop>
- <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>
- [애니메이션 개요](animation-overview.md)
- [애니메이션 및 타이밍 방법 항목](animation-and-timing-how-to-topics.md)
