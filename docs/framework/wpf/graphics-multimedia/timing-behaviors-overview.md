---
title: 타이밍 동작 개요
ms.date: 03/30/2017
helpviewer_keywords:
- timing behaviors [WPF]
- behaviors [WPF], timing
ms.assetid: 5b714d46-bd46-48b8-b467-b4be89ba3091
ms.openlocfilehash: 3bb42ddd991d3ae1221cc794afdd4aafc74a6046
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145399"
---
# <a name="timing-behaviors-overview"></a>타이밍 동작 개요
이 항목에서는 애니메이션 및 기타 <xref:System.Windows.Media.Animation.Timeline> 개체의 타이밍 동작에 대해 설명합니다.  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>전제 조건  
 이 항목을 이해하려면 기본 애니메이션 기능을 잘 알고 있어야 입니다. 자세한 내용은 애니메이션 [개요](animation-overview.md)를 참조하십시오.  
  
<a name="timelinetypes"></a>
## <a name="timeline-types"></a>타임라인 형식  
 A는 <xref:System.Windows.Media.Animation.Timeline> 시간 세그먼트를 나타냅니다. 해당 세그먼트의 길이, 시작 시기, 반복 횟수, 해당 세그먼트에서 진행되는 속도 등을 지정할 수 있는 속성이 제공됩니다.  
  
 타임라인 클래스에서 상속하는 클래스는 애니메이션 및 미디어 재생 등의 추가 기능을 제공합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]은 다음 <xref:System.Windows.Media.Animation.Timeline> 유형을 제공합니다.  
  
|타임라인 유형|Description|  
|-------------------|-----------------|  
|<xref:System.Windows.Media.Animation.AnimationTimeline>|속성 애니메이션에 <xref:System.Windows.Media.Animation.Timeline> 대한 출력 값을 생성하는 개체에 대한 기본 클래스를 추상화합니다.|  
|<xref:System.Windows.Media.MediaTimeline>|미디어 파일에서 출력을 생성합니다.|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|해당 그룹화 및 컨트롤자 <xref:System.Windows.Media.Animation.TimelineGroup> <xref:System.Windows.Media.Animation.Timeline> 개체의 형식입니다.|  
|<xref:System.Windows.Media.Animation.Storyboard>|포함된 타임라인 <xref:System.Windows.Media.Animation.ParallelTimeline> 개체에 대한 타겟팅 정보를 제공하는 유형입니다.|  
|<xref:System.Windows.Media.Animation.Timeline>|타이밍 동작을 정의하는 추상 기본 클래스입니다.|  
|<xref:System.Windows.Media.Animation.TimelineGroup>|다른 <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Timeline> 개체를 포함할 수 있는 개체에 대한 추상 클래스입니다.|  
  
<a name="propertiesthatcontroltimelinelength"></a>
## <a name="properties-that-control-the-length-of-a-timeline"></a>타임라인의 길이를 제어하는 속성  
 A는 <xref:System.Windows.Media.Animation.Timeline> 시간 세그먼트를 나타내며 타임라인의 길이는 여러 가지 방법으로 설명할 수 있습니다. 다음 표에서는 타임라인의 길이를 설명하기 위한 몇 가지 용어를 정의합니다.  
  
|용어|Description|속성||||  
|----------|-----------------|----------------|-|-|-|  
|단순 지속 시간|타임라인이 단일 정방향 반복을 수행하는 데 걸리는 시간입니다.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>||||  
|1회 반복|타임라인이 한 번 앞으로 재생되고 속성이 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> true인 경우 한 번 뒤로 재생하는 데 걸리는 시간입니다.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>||||  
|활성 기간|타임라인이 <xref:System.Windows.Media.Animation.RepeatBehavior> 해당 속성에 지정된 모든 반복을 완료하는 데 걸리는 시간입니다.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, <xref:System.Windows.Media.Animation.RepeatBehavior>||||  
  
<a name="duration"></a>
### <a name="the-duration-property"></a>Duration 속성  
 앞서 설명한 것처럼 타임라인은 시간 세그먼트를 나타냅니다. 해당 세그먼트의 길이는 타임라인의 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>에 의해 결정됩니다. 타임라인이 기간 끝에 도달하면 재생을 중지합니다. 타임라인에 자식 타임라인이 있어도 재생을 중지합니다. 애니메이션의 경우 애니메이션이 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 시작 값에서 끝 값으로 전환하는 데 걸리는 시간을 지정합니다. 타임라인의 지속 시간을 간단한 *기간이라고도*하며, 단일 반복 의 지속 시간과 반복을 포함하여 애니메이션이 재생되는 총 시간을 구별합니다. 유한 시간 값 또는 특수 값 <xref:System.Windows.Duration.Automatic%2A> 또는 <xref:System.Windows.Duration.Forever%2A>을 사용하여 기간을 지정할 수 있습니다. 애니메이션의 지속 시간은 <xref:System.Windows.Duration.TimeSpan%2A> 값으로 확인되어야 하므로 값 간에 전환할 수 있습니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation> 5초가 있는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> a를 보여 주십습니다.  
  
 [!code-xaml[animation_ovws_snippet#AnimationWith5SecondDurationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#animationwith5seconddurationinline)]  
  
 컨테이너 타임라인(예: <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.ParallelTimeline>및)의 기본 <xref:System.Windows.Duration.Automatic%2A>기간은 마지막 자식이 재생을 중지할 때 자동으로 종료된다는 것을 의미합니다. 다음 예제에서는 <xref:System.Windows.Media.Animation.Storyboard> 5초로 결심하는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> a를 보여 주며, <xref:System.Windows.Media.Animation.DoubleAnimation> 모든 자식 개체를 완료하는 데 걸리는 시간을 보여 주십습니다.  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelineexampleinline)]  
  
 컨테이너 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 타임라인을 <xref:System.Windows.Duration.TimeSpan%2A> 값으로 설정하면 자식 <xref:System.Windows.Media.Animation.Timeline> 오브젝트가 재생하는 것보다 더 길거나 짧게 재생하도록 강제할 수 있습니다. 컨테이너 타임라인의 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 자식 <xref:System.Windows.Media.Animation.Timeline> 개체 길이보다 작은 값으로 설정하면 컨테이너 타임라인이 <xref:System.Windows.Media.Animation.Timeline> 수행될 때 자식 개체의 재생이 중지됩니다. 다음 예제는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 위의 <xref:System.Windows.Media.Animation.Storyboard> 예제에서 의 를 3초로 설정합니다. 따라서 대상 사각형의 <xref:System.Windows.Media.Animation.DoubleAnimation> 너비를 60으로 애니메이션하면 3초 후에 첫 번째 진행이 중지됩니다.  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineWithShorterDurationExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelinewithshorterdurationexampleinline)]  
  
<a name="repeatinganimations"></a>
### <a name="the-repeatbehavior-property"></a>RepeatBehavior 속성  
 속성은 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> <xref:System.Windows.Media.Animation.Timeline> 단순 기간을 반복하는 횟수를 제어합니다. 속성을 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 사용하여 타임라인이 재생되는 횟수(반복) <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A>또는 재생해야 하는 총 시간(반복)을 <xref:System.Windows.Media.Animation.RepeatBehavior.Duration%2A>지정할 수 있습니다. 두 경우 모두 애니메이션은 요청된 횟수 또는 기간을 채우는 데 필요한만큼 시작-끝 실행을 반복합니다. 기본적으로 타임라인에는 `1.0`반복 수가 있는데, 이는 한 번 재생되고 전혀 반복되지 않음을 의미합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 반복 수를 <xref:System.Windows.Media.Animation.DoubleAnimation> 지정하여 간단한 기간의 두 배 동안 재생을 만들기 위해 속성을 사용합니다.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior2xExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior2xexampleinline)]  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성을 사용하여 <xref:System.Windows.Media.Animation.DoubleAnimation> 간단한 지속 시간의 절반으로 재생합니다.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior05xExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior05xexampleinline)]  
  
 의 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> <xref:System.Windows.Media.Animation.Timeline> 속성을 설정하는 경우 <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>대화식으로 <xref:System.Windows.Media.Animation.Timeline> 또는 타이밍 시스템에 의해 중지될 때까지 반복됩니다. 다음 예제에서는 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성을 사용하여 <xref:System.Windows.Media.Animation.DoubleAnimation> 재생을 무기한으로 만듭니다.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehaviorForeverExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehaviorforeverexampleinline)]  
  
 추가 예제는 [애니메이션 반복](how-to-repeat-an-animation.md)을 참조하십시오.  
  
<a name="autoreverseproperty"></a>
### <a name="the-autoreverse-property"></a>AutoReverse 속성  
 속성은 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 각 정방향 <xref:System.Windows.Media.Animation.Timeline> 반복이 끝날 때 a가 뒤로 재생되는지 여부를 지정합니다. 다음 예제는 a의 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 속성으로 <xref:System.Windows.Media.Animation.DoubleAnimation> `true`설정합니다. 결과적으로 0에서 100으로 애니메이션한 다음 100에서 0으로 애니메이션합니다. 총 10초 동안 재생됩니다.  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverseexampleinline)]  
  
 <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> 값을 사용하여 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> a및 <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 의 <xref:System.Windows.Media.Animation.Timeline> 속성을 지정하는 경우 `true`단일 반복은 하나의 순방향 반복다음에 한 번의 뒤로 반복으로 구성됩니다.  다음 예제는 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 위의 <xref:System.Windows.Media.Animation.DoubleAnimation> 예제에서 <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> 두 개로 의 를 설정합니다. 그 결과, <xref:System.Windows.Media.Animation.DoubleAnimation> 20초 동안 재생됩니다: 5초 동안 앞으로, 5초 동안 뒤로, 5초 동안 다시 앞으로, 그리고 5초 동안 뒤로 재생됩니다.  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseRepeatExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverserepeatexampleinline)]  
  
 컨테이너 타임라인에 자식 <xref:System.Windows.Media.Animation.Timeline> 개체가 있는 경우 컨테이너 타임라인이 수행될 때 반대로 됩니다. 추가 예제의 경우 [타임라인이 자동으로 되돌릴지 여부를 지정합니다.](how-to-specify-whether-a-timeline-automatically-reverses.md)  
  
<a name="timelinebegin"></a>
## <a name="the-begintime-property"></a>BeginTime 속성  
 이 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> 속성을 사용하면 타임라인이 시작되는 시기를 지정할 수 있습니다.  타임라인의 시작 시간은 부모 타임라인에 상대적입니다. 타임라인 0초는 부모 타임라인이 시작되자마자 해당 타임라인이 시작됨을 의미합니다. 다른 값을 지정하면 부모 타임라인이 재생을 시작하는 시간과 자식 타임라인이 재생되는 시간 사이에 오프셋이 생성됩니다. 예를 들어 시작 시간이 2초면 부모 타임라인이 2초에 도달할 때 해당 타임라인이 재생을 시작함을 의미합니다. 기본적으로 모든 타임라인의 시작 시간은 0초입니다. 타임라인의 시작 시간을 로 설정하여 `null`타임라인이 시작되지 않도록 할 수도 있습니다. 에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [x:Null 마크업 확장을](../../../desktop-wpf/xaml-services/xnull-markup-extension.md)사용하여 null을 지정합니다.  
  
 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 설정으로 인해 타임라인이 반복될 때마다 시작 시간이 적용되지 않습니다. 10초 및 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> <xref:System.Windows.Media.Animation.RepeatBehavior> <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>의 단위로 애니메이션을 만드는 경우 애니메이션이 처음 재생되기 전에 10초 지연되지만 연속적인 반복마다는 그렇지 않습니다. 그러나 애니메이션의 부모 타임라인이 다시 시작되거나 반복되면 10초의 지연이 발생할 것입니다.  
  
 이 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> 속성은 비틀거리는 일정에 유용합니다. 다음 예제는 <xref:System.Windows.Media.Animation.Storyboard> 두 개의 <xref:System.Windows.Media.Animation.DoubleAnimation> 자식 개체가 있는 a를 만듭니다. 첫 번째 애니메이션의 경우 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 5초, 두 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 번째 애니메이션은 3초입니다. 이 예제에서는 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> 두 <xref:System.Windows.Media.Animation.DoubleAnimation> 번째 초를 5초로 설정하여 첫 <xref:System.Windows.Media.Animation.DoubleAnimation> 번째 종료 후 재생을 시작합니다.  
  
 [!code-xaml[animation_ovws_snippet#TBBeginTimeExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbbegintimeexampleinline)]  
  
<a name="fillbehaviorproperty"></a>
## <a name="the-fillbehavior-property"></a>FillBehavior 속성  
 a가 <xref:System.Windows.Media.Animation.Timeline> 총 활성 지속 시간의 끝에 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 도달하면 속성은 중지또는 마지막 값을 보유할지 여부를 지정합니다. 출력 값을 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> "보유"하는 애니메이션: 애니메이션중인 속성은 애니메이션의 마지막 값을 유지합니다. 애니메이션이 <xref:System.Windows.Media.Animation.FillBehavior.Stop> 종료된 후 대상 속성에 영향을 주는 것을 중지하는 원인의 값입니다.  
  
 다음 예제는 <xref:System.Windows.Media.Animation.Storyboard> 두 개의 <xref:System.Windows.Media.Animation.DoubleAnimation> 자식 개체가 있는 a를 만듭니다. 두 <xref:System.Windows.Media.Animation.DoubleAnimation> 오브젝트 모두 <xref:System.Windows.FrameworkElement.Width%2A> 0에서 <xref:System.Windows.Shapes.Rectangle> 100까지의 애니메이션을 애니메이션합니다. <xref:System.Windows.Shapes.Rectangle> 요소에는 애니메이션되지 <xref:System.Windows.FrameworkElement.Width%2A> 않은 값이 500[장치 독립 픽셀]입니다.  
  
- 첫 번째 속성은 기본값으로 <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>설정됩니다. <xref:System.Windows.Media.Animation.DoubleAnimation> <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 따라서 사각형의 너비는 <xref:System.Windows.Media.Animation.DoubleAnimation> 종료 후 100으로 유지됩니다.  
  
- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 두 번째 <xref:System.Windows.Media.Animation.DoubleAnimation> 속성은 로 <xref:System.Windows.Media.Animation.FillBehavior.Stop>설정됩니다. 결과적으로 두 번째 <xref:System.Windows.FrameworkElement.Width%2A> 의 <xref:System.Windows.Shapes.Rectangle> 경우 <xref:System.Windows.Media.Animation.DoubleAnimation> 종료 후 500으로 되돌아갑니다.  
  
 [!code-xaml[animation_ovws_snippet#TBFillBehaviorExample](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbfillbehaviorexample)]  
  
<a name="speedproperties"></a>
## <a name="properties-that-control-the-speed-of-a-timeline"></a>타임라인의 속도를 제어하는 속성  
 클래스는 <xref:System.Windows.Media.Animation.Timeline> 속도를 지정하기 위한 세 가지 속성을 제공합니다.  
  
- <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A>– 해당 비율을 지정, 부모를 기준으로, 이 시간에 대해 <xref:System.Windows.Media.Animation.Timeline>진행. 값이 하나보다 큰 값은 <xref:System.Windows.Media.Animation.Timeline> 자식 <xref:System.Windows.Media.Animation.Timeline> 개체와 자식 개체의 속도를 증가시킵니다. 값이 0에서 1 사이로 느려집니다. 값이 1이면 <xref:System.Windows.Media.Animation.Timeline> 상위 값과 동일한 속도로 진행됩니다. 컨테이너 <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> 타임라인설정은 모든 자식 <xref:System.Windows.Media.Animation.Timeline> 개체에도 영향을 줍니다.  
  
- <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A>– 가속화하는 데 소요된 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 타임라인의 백분율을 지정합니다. 예를 들어 애니메이션 [가속 또는 감속 방법:](how-to-accelerate-or-decelerate-an-animation.md)애니메이션 을 참조하세요.
  
- <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A>- 감속에 소요된 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 타임라인의 백분율을 지정합니다. 예를 들어 애니메이션 [가속 또는 감속 방법:](how-to-accelerate-or-decelerate-an-animation.md)애니메이션 을 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- [애니메이션 개요](animation-overview.md)
- [애니메이션 및 타이밍 시스템 개요](animation-and-timing-system-overview.md)
- [타이밍 이벤트 개요](timing-events-overview.md)
- [방법 주제](animation-and-timing-how-to-topics.md)
- [애니메이션 타이밍 동작 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)
