---
title: '방법: Timeline을 자동으로 뒤집을지 여부 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- AutoReverse property of timelines [WPF]
- Timelines [WPF], AutoReverse property
ms.assetid: 1648dd90-1bee-409a-ac69-ac729867f557
ms.openlocfilehash: 0fe2d337d8afa5197475e5b9ee40950226596e8b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354208"
---
# <a name="how-to-specify-whether-a-timeline-automatically-reverses"></a>방법: Timeline을 자동으로 뒤집을지 여부 지정
타임 라인의 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 속성 정방향 반복을 완료 한 후 반대 방향에서 재생 여부를 결정 합니다. 다음 예제에서는 동일한 기간 및 대상 값이 포함 되지만 다른 여러 애니메이션 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 설정 합니다. 보여 주기 위해 하는 방법을 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 속성의 다른 동작 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 설정을 일부 애니메이션 반복으로 설정 됩니다. 애니메이션은 마지막 방법을 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 속성이 중첩된 타임 라인에서 작동 합니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]
