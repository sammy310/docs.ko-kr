---
title: 애니메이션 및 타이밍 시스템 개요
ms.date: 03/30/2017
helpviewer_keywords:
- timing system [WPF]
- animation [WPF]
ms.assetid: 172cd5a8-a333-4c81-9456-fafccc19f382
ms.openlocfilehash: d0ac2a8160a1e6f9bcdb333593ec207954b391aa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187712"
---
# <a name="animation-and-timing-system-overview"></a>애니메이션 및 타이밍 시스템 개요
이 항목에서는 타이밍 시스템에서 애니메이션 <xref:System.Windows.Media.Animation.Timeline>및 <xref:System.Windows.Media.Animation.Clock> 클래스를 사용하여 속성을 애니메이션하는 방법을 설명합니다.  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>전제 조건  
 이 항목을 이해하려면 [애니메이션 개요](animation-overview.md)에 설명된 대로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애니메이션을 사용하여 속성에 애니메이션 효과를 줄 수 있어야 합니다. 종속성 속성에 익숙한 것도 도움이 됩니다. 자세한 내용은 [종속성 속성 개요](../advanced/dependency-properties-overview.md)를 참조하세요.  
  
<a name="timelinesandclocks"></a>
## <a name="timelines-and-clocks"></a>타임라인 및 시계  
 [애니메이션 개요에서는](animation-overview.md) a가 <xref:System.Windows.Media.Animation.Timeline> 시간 세그먼트를 나타내는 방법과 애니메이션이 <xref:System.Windows.Media.Animation.Timeline> 출력 값을 생성하는 유형입니다. 은 시간 <xref:System.Windows.Media.Animation.Timeline>세그먼트를 설명하는 것 외에는 아무 것도 하지 않습니다. 실제 작업을 수행하는 것은 <xref:System.Windows.Media.Animation.Clock> 타임라인의 개체입니다. 마찬가지로 애니메이션은 실제로 속성에 애니메이션을 적용하지 않습니다: 애니메이션 클래스는 출력 값을 계산하는 <xref:System.Windows.Media.Animation.Clock> 방법을 설명하지만 애니메이션 출력을 구동하고 속성에 적용하는 애니메이션에 대해 만들어진 것입니다.  
  
 A는 <xref:System.Windows.Media.Animation.Clock> 에 대한 타이밍 관련 런타임 상태를 유지하는 특수 <xref:System.Windows.Media.Animation.Timeline>한 유형의 개체입니다. 애니메이션 및 타이밍 시스템에 필수적인 세 가지 정보 비트를 <xref:System.Windows.Media.Animation.Clock.CurrentTime%2A> <xref:System.Windows.Media.Animation.Clock.CurrentProgress%2A>제공합니다. <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> <xref:System.Windows.Media.Animation.Clock> A는 <xref:System.Windows.Media.Animation.Timeline>의 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>: 에 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>의해 설명된 타이밍 동작을 사용하여 현재 시간, 진행률 및 상태를 결정합니다.  
  
 대부분의 경우 A는 <xref:System.Windows.Media.Animation.Clock> 타임라인에 대해 자동으로 만들어집니다. 또는 <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 메서드를 사용하여 애니메이션을 적용하면 타임라인 및 애니메이션에 대해 시계가 자동으로 생성되고 대상 속성에 적용됩니다. 의 <xref:System.Windows.Media.Animation.Clock> <xref:System.Windows.Media.Animation.Timeline.CreateClock%2A> 메서드를 사용하여 명시적으로 만들 수도 <xref:System.Windows.Media.Animation.Timeline>있습니다. 메서드는 <xref:System.Windows.Media.MediaTimeline.CreateClock%2A?displayProperty=nameWithType> 호출 되는 <xref:System.Windows.Media.Animation.Timeline> 에 대 한 적절 한 형식의 시계를 만듭니다. 하위 <xref:System.Windows.Media.Animation.Timeline> 타임라인이 포함된 경우 <xref:System.Windows.Media.Animation.Clock> 개체도 만듭니다. 결과 <xref:System.Windows.Media.Animation.Clock> 객체는 작성된 객체 트리의 구조와 일치하는 트리에 <xref:System.Windows.Media.Animation.Timeline> 정렬됩니다.  
  
 다양한 유형의 타임라인에 대한 여러 유형의 시계가 있습니다. 다음 표에서는 <xref:System.Windows.Media.Animation.Clock> 일부 다른 <xref:System.Windows.Media.Animation.Timeline> 형식에 해당하는 형식을 보여 주며 있습니다.  
  
|타임라인 유형|시계 유형|시계 용도|  
|-------------------|----------------|-------------------|  
|<xref:System.Windows.Media.Animation.AnimationTimeline>애니메이션(상속)|<xref:System.Windows.Media.Animation.AnimationClock>|종속성 속성에 대한 출력 값을 생성합니다.|  
|<xref:System.Windows.Media.MediaTimeline>|<xref:System.Windows.Media.MediaClock>|미디어 파일을 처리합니다.|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|<xref:System.Windows.Media.Animation.ClockGroup>|자식 <xref:System.Windows.Media.Animation.Clock> 개체를 그룹및 제어합니다.|  
|<xref:System.Windows.Media.Animation.Storyboard>|<xref:System.Windows.Media.Animation.ClockGroup>|자식 <xref:System.Windows.Media.Animation.Clock> 개체를 그룹및 제어합니다.|  
  
 메서드를 사용 <xref:System.Windows.Media.Animation.AnimationClock> 하 여 호환 되는 종속성 <xref:System.Windows.Media.Animation.IAnimatable.ApplyAnimationClock%2A> 속성에 만든 모든 개체를 적용할 수 있습니다.  
  
 많은 수의 유사한 개체에 애니메이션을 제공하는 것과 같이 성능이 <xref:System.Windows.Media.Animation.Clock> 집약적인 시나리오에서는 사용자 고유의 사용을 관리하면 성능이 향상될 수 있습니다.  
  
<a name="timemanager"></a>
## <a name="clocks-and-the-time-manager"></a>시계 및 시간 관리자  
 에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]개체에 애니메이션을 만들 면 타임라인에 대해 <xref:System.Windows.Media.MediaPlayer.Clock%2A> 만든 개체를 관리하는 시간 관리자입니다. 시간 관리자는 <xref:System.Windows.Media.MediaPlayer.Clock%2A> 개체 트리의 루트이며 해당 트리에서 시간의 흐름을 제어합니다.  시간 관리자는 각 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애플리케이션에 대해 자동으로 만들어지며 애플리케이션 개발자에게 표시되지 않습니다. 시간 관리자에서 매초 여러 번 "틱"이 발생하는데 초당 발생하는 실제 틱 수는 사용 가능한 시스템 리소스에 따라 다릅니다. 이러한 각 눈금 동안 시간 관리자는 타이밍 트리의 <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.Clock> 모든 개체의 상태를 계산합니다.  
  
 다음 그림에서는 시간 관리자와 <xref:System.Windows.Media.Animation.AnimationClock>에 애니메이션된 종속성 속성 간의 관계를 보여 주며,  
  
 ![타이밍 시스템 구성 요소](./media/graphicsmm-clocks-1clock1prop.png "graphicsmm_clocks_1clock1prop")  
속성에 애니메이션 효과 주기  
  
 시간 관리자가 체크하면 응용 프로그램의 모든 <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.Clock> 시간을 업데이트합니다. 을 <xref:System.Windows.Media.Animation.Clock> <xref:System.Windows.Media.Animation.AnimationClock>사용하는 경우 는 <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> 현재 출력 <xref:System.Windows.Media.Animation.AnimationTimeline> 값을 계산하기 위해 생성된 메서드를 사용합니다. 는 <xref:System.Windows.Media.Animation.AnimationClock> 현재 <xref:System.Windows.Media.Animation.AnimationTimeline> 현지 시간, 일반적으로 속성의 기본 값인 입력 값 및 기본 대상 값을 제공합니다. <xref:System.Windows.DependencyObject.GetValue%2A> 메서드 또는 해당 CLR 접근자를 사용하여 속성별로 애니메이션된 값을 검색하면 의 <xref:System.Windows.Media.Animation.AnimationClock>출력을 얻을 수 있습니다.  
  
#### <a name="clock-groups"></a>시계 그룹  
 앞의 섹션에서는 다양한 유형의 <xref:System.Windows.Media.Animation.Clock> 타임라인에 대해 다양한 유형의 개체가 있는 방법을 설명합니다. 다음 그림에서는 시간 관리자, a <xref:System.Windows.Media.Animation.ClockGroup>및 <xref:System.Windows.Media.Animation.AnimationClock>애니메이션된 종속성 속성 간의 관계를 보여 주며 있습니다. A는 <xref:System.Windows.Media.Animation.ClockGroup> 애니메이션 및 기타 타임라인을 그룹화하는 <xref:System.Windows.Media.Animation.Storyboard> 클래스와 같은 다른 타임라인을 그룹화하는 타임라인에 대해 만들어집니다.  
  
 ![타이밍 시스템 구성 요소](./media/graphicsmm-clocks-2clock1clockgroup2prop.png "graphicsmm_clocks_2clock1clockgroup2prop")  
ClockGroup  
  
#### <a name="composition"></a>컴퍼지션  
 여러 시계를 단일 속성에 연결할 수 있습니다. 이 경우 각 시계에서 이전 시계의 출력 값을 기준 값으로 사용합니다. 다음 그림에서는 <xref:System.Windows.Media.Animation.AnimationClock> 동일한 속성에 적용된 세 개의 객체를 보여 주시면 됩니다. Clock1은 애니메이션 속성의 기준 값을 해당 입력으로 사용하고 이를 사용하여 출력을 생성합니다. Clock2는 Clock1의 출력을 입력으로 받고 이를 사용하여 출력을 생성합니다. Clock3은 Clock2의 출력을 입력으로 받고 이를 사용하여 출력을 생성합니다. 여러 시계가 같은 속성에 동시에 영향을 주는 경우 컴퍼지션 체인에 있다고 합니다.  
  
 ![타이밍 시스템 구성 요소](./media/graphicsmm-clocks-2clock1prop.png "graphicsmm_clocks_2clock1prop")  
컴퍼지션 체인  
  
 컴포지션 체인에 있는 <xref:System.Windows.Media.Animation.AnimationClock> 개체의 입력 및 출력 간에 관계가 만들어지지만 타이밍 동작은 영향을 받지 않습니다. <xref:System.Windows.Media.Animation.Clock> 개체(개체 <xref:System.Windows.Media.Animation.AnimationClock> 포함)에는 상위 <xref:System.Windows.Media.Animation.Clock> 개체에 계층적 종속성이 있습니다.  
  
 동일한 속성에 여러 클럭을 적용하려면 <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> <xref:System.Windows.Media.Animation.HandoffBehavior> <xref:System.Windows.Media.Animation.Storyboard>에 적용 할 때 <xref:System.Windows.Media.Animation.AnimationClock>를 사용하십시오 .  
  
#### <a name="ticks-and-event-consolidation"></a>틱 및 이벤트 통합  
 출력 값을 계산하는 것 외에도 시간 관리자는 틱을 발생시킬 때마다 다른 작업을 수행합니다. 각 시계의 상태를 결정하고 적절하게 이벤트를 발생시킵니다.  
  
 틱은 자주 발생하지만 틱 간에 많은 사항이 발생할 수 있습니다. 예를 들어 <xref:System.Windows.Media.Animation.Clock> a를 중지, 시작 및 다시 중지할 <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> 수 있으며, 이 경우 해당 값이 세 번 변경됩니다. 이론적으로, <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> 이벤트는 하나의 틱에서 여러 번 제기 될 수있다; 그러나 타이밍 엔진은 이벤트를 통합하므로 틱당 <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> 한 번씩 이벤트를 발생시킬 수 있습니다. 이는 모든 타이밍 이벤트에 해당합니다. <xref:System.Windows.Media.Animation.Clock>  
  
 스위치가 <xref:System.Windows.Media.Animation.Clock> 상태를 변경하고 틱 간에 원래 상태로 되돌아가는 경우(예: 전환 <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.ClockState.Stopped> 및 뒤로 <xref:System.Windows.Media.Animation.ClockState.Active>변경) 연결된 이벤트가 계속 발생합니다.  
  
 타이밍 이벤트에 대한 자세한 내용은 [타이밍 이벤트 개요](timing-events-overview.md)를 참조하세요.  
  
<a name="currentvaluesbasevaluesofproperties"></a>
## <a name="current-values-and-base-values-of-properties"></a>속성의 현재 값 및 기준 값  
 애니메이션 효과를 줄 수 있는 속성은 두 값(기준 값 및 현재 값)을 가질 수 있습니다. CLR 접근자 또는 메서드를 <xref:System.Windows.DependencyObject.SetValue%2A> 사용하여 속성을 설정하면 기본 값을 설정합니다. 속성에 애니메이션 효과를 줄 수 없는 경우 해당 기준 값과 현재 값은 동일합니다.  
  
 속성에 애니메이션을 사용하면 속성의 <xref:System.Windows.Media.Animation.AnimationClock> *현재* 값이 설정됩니다. CLR 접근자 또는 <xref:System.Windows.DependencyObject.GetValue%2A> 메서드를 통해 속성값을 검색하면 의 <xref:System.Windows.Media.Animation.AnimationClock> 출력이 <xref:System.Windows.Media.Animation.AnimationClock> <xref:System.Windows.Media.Animation.ClockState.Active> 반환됩니다. <xref:System.Windows.Media.Animation.ClockState.Filling> 메서드를 사용 하 여 속성의 <xref:System.Windows.Media.Animation.IAnimatable.GetAnimationBaseValue%2A> 기본 값을 검색할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목

- [애니메이션 개요](animation-overview.md)
- [타이밍 이벤트 개요](timing-events-overview.md)
- [타이밍 동작 개요](timing-behaviors-overview.md)
