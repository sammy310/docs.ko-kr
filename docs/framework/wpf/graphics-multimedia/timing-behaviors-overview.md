---
title: 타이밍 동작 개요
ms.date: 03/30/2017
helpviewer_keywords:
- timing behaviors [WPF]
- behaviors [WPF], timing
ms.assetid: 5b714d46-bd46-48b8-b467-b4be89ba3091
ms.openlocfilehash: a85f980a0cefaa282e9e92d533a2306a9009e3e7
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559952"
---
# <a name="timing-behaviors-overview"></a>타이밍 동작 개요
이 항목에서는 애니메이션 및 기타 <xref:System.Windows.Media.Animation.Timeline> 개체의 타이밍 동작에 대해 설명 합니다.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>전제 조건  
 이 항목을 이해하려면 기본 애니메이션 기능을 잘 알고 있어야 입니다. 자세한 내용은 [애니메이션 개요](animation-overview.md)를 참조 하세요.  
  
<a name="timelinetypes"></a>   
## <a name="timeline-types"></a>타임라인 형식  
 <xref:System.Windows.Media.Animation.Timeline>는 시간 세그먼트를 나타냅니다. 해당 세그먼트의 길이, 시작 시기, 반복 횟수, 해당 세그먼트에서 진행되는 속도 등을 지정할 수 있는 속성이 제공됩니다.  
  
 타임라인 클래스에서 상속하는 클래스는 애니메이션 및 미디어 재생 등의 추가 기능을 제공합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 다음과 같은 <xref:System.Windows.Media.Animation.Timeline> 유형을 제공 합니다.  
  
|타임라인 형식|설명|  
|-------------------|-----------------|  
|<xref:System.Windows.Media.Animation.AnimationTimeline>|속성에 애니메이션 효과를 주기 위해 출력 값을 생성 하는 <xref:System.Windows.Media.Animation.Timeline> 개체에 대 한 추상 기본 클래스입니다.|  
|<xref:System.Windows.Media.MediaTimeline>|미디어 파일에서 출력을 생성합니다.|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|자식 <xref:System.Windows.Media.Animation.Timeline> 개체를 그룹화 하 고 제어 하는 <xref:System.Windows.Media.Animation.TimelineGroup> 형식입니다.|  
|<xref:System.Windows.Media.Animation.Storyboard>|포함 된 Timeline 개체에 대 한 대상 정보를 제공 하는 <xref:System.Windows.Media.Animation.ParallelTimeline> 형식입니다.|  
|<xref:System.Windows.Media.Animation.Timeline>|타이밍 동작을 정의하는 추상 기본 클래스입니다.|  
|<xref:System.Windows.Media.Animation.TimelineGroup>|다른 <xref:System.Windows.Media.Animation.Timeline> 개체를 포함할 수 있는 <xref:System.Windows.Media.Animation.Timeline> 개체에 대 한 추상 클래스입니다.|  
  
<a name="propertiesthatcontroltimelinelength"></a>   
## <a name="properties-that-control-the-length-of-a-timeline"></a>타임라인의 길이를 제어하는 속성  
 <xref:System.Windows.Media.Animation.Timeline>는 시간 세그먼트를 나타내고 타임 라인의 길이는 여러 가지 방법으로 설명할 수 있습니다. 다음 표에서는 타임라인의 길이를 설명하기 위한 몇 가지 용어를 정의합니다.  
  
|용어|설명|속성||||  
|----------|-----------------|----------------|-|-|-|  
|단순 지속 시간|타임라인이 단일 정방향 반복을 수행하는 데 걸리는 시간입니다.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>||||  
|1회 반복|시간 표시 막대를 한 번만 재생 하는 데 걸리는 시간입니다. <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 속성이 true 이면 뒤로 재생 합니다.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>||||  
|활성 기간|Timeline이 <xref:System.Windows.Media.Animation.RepeatBehavior> 속성으로 지정 된 모든 반복을 완료 하는 데 소요 되는 시간입니다.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>에서 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>에서 <xref:System.Windows.Media.Animation.RepeatBehavior>||||  
  
<a name="duration"></a>   
### <a name="the-duration-property"></a>Duration 속성  
 앞서 설명한 것처럼 타임라인은 시간 세그먼트를 나타냅니다. 이 세그먼트의 길이는 타임 라인의 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>에 의해 결정 됩니다. 타임라인이 기간 끝에 도달하면 재생을 중지합니다. 타임라인에 자식 타임라인이 있어도 재생을 중지합니다. 애니메이션의 경우 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>는 애니메이션이 시작 값에서 끝 값으로 전환 하는 데 걸리는 시간을 지정 합니다. Timeline의 지속 시간은 단일 반복의 기간과 반복을 포함 하 여 애니메이션을 재생 하는 총 시간을 구분 하기 위해 *간단한 기간*이라고 합니다. 한정 된 시간 값 또는 <xref:System.Windows.Duration.Automatic%2A> 또는 <xref:System.Windows.Duration.Forever%2A>특수 값을 사용 하 여 기간을 지정할 수 있습니다. 애니메이션의 지속 시간은 <xref:System.Windows.Duration.TimeSpan%2A> 값으로 확인 되므로 값 사이를 전환할 수 있습니다.  
  
 다음 예에서는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 5 초를 사용 하는 <xref:System.Windows.Media.Animation.DoubleAnimation>를 보여 줍니다.  
  
 [!code-xaml[animation_ovws_snippet#AnimationWith5SecondDurationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#animationwith5seconddurationinline)]  
  
 <xref:System.Windows.Media.Animation.Storyboard> 및 <xref:System.Windows.Media.Animation.ParallelTimeline>와 같은 컨테이너 타임 라인에는 기본 기간이 <xref:System.Windows.Duration.Automatic%2A>있습니다. 즉, 마지막 자식이 재생을 중지 하면 자동으로 종료 됩니다. 다음 예제에서는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>의 모든 자식 <xref:System.Windows.Media.Animation.DoubleAnimation> 개체를 완료 하는 데 걸리는 시간을 5 초로 확인 하는 <xref:System.Windows.Media.Animation.Storyboard>를 보여 줍니다.  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelineexampleinline)]  
  
 컨테이너 타임 라인의 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> <xref:System.Windows.Duration.TimeSpan%2A> 값으로 설정 하면 자식 <xref:System.Windows.Media.Animation.Timeline> 개체가 재생 하는 것 보다 더 길거나 짧게 재생할 수 있습니다. <xref:System.Windows.Media.Animation.Timeline.Duration%2A>를 컨테이너 타임 라인의 자식 <xref:System.Windows.Media.Animation.Timeline> 개체 길이 보다 작은 값으로 설정 하는 경우 자식 <xref:System.Windows.Media.Animation.Timeline> 개체는 컨테이너 타임 라인이 실행 될 때 재생을 중지 합니다. 다음 예제에서는 <xref:System.Windows.Media.Animation.Storyboard>의 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>를 앞의 예제에서 3 초로 설정 합니다. 결과적으로 대상 사각형의 너비를 60에 애니메이션을 적용 하는 경우 첫 번째 <xref:System.Windows.Media.Animation.DoubleAnimation> 3 초 후에 진행이 중지 됩니다.  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineWithShorterDurationExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelinewithshorterdurationexampleinline)]  
  
<a name="repeatinganimations"></a>   
### <a name="the-repeatbehavior-property"></a>RepeatBehavior 속성  
 <xref:System.Windows.Media.Animation.Timeline>의 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성은 단순 지속 시간을 반복 하는 횟수를 제어 합니다. <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성을 사용 하 여 timeline이 재생 되는 횟수 (반복 <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A>) 또는 재생 해야 하는 총 시간 (반복 <xref:System.Windows.Media.Animation.RepeatBehavior.Duration%2A>)을 지정할 수 있습니다. 두 경우 모두 애니메이션은 요청된 횟수 또는 기간을 채우는 데 필요한만큼 시작-끝 실행을 반복합니다. 기본적으로 타임 라인의 반복 횟수는 한 번만 재생 되 고 전혀 반복 되지 않음을 의미 하는 `1.0`입니다.  
  
 다음 예에서는 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성을 사용 하 여 반복 횟수를 지정 하 여 두 번의 간단한 지속 시간 동안 <xref:System.Windows.Media.Animation.DoubleAnimation>를 재생 합니다.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior2xExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior2xexampleinline)]  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성을 사용 하 여 <xref:System.Windows.Media.Animation.DoubleAnimation>가 단순 지속 시간의 절반을 재생 하도록 합니다.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior05xExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior05xexampleinline)]  
  
 <xref:System.Windows.Media.Animation.Timeline>의 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성을 <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>로 설정 하면 대화형으로 또는 타이밍 시스템에서 중지 될 때까지 <xref:System.Windows.Media.Animation.Timeline> 반복 됩니다. 다음 예제에서는 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성을 사용 하 여 <xref:System.Windows.Media.Animation.DoubleAnimation> 무기한 재생 되도록 합니다.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehaviorForeverExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehaviorforeverexampleinline)]  
  
 추가 예제는 [애니메이션 반복](how-to-repeat-an-animation.md)을 참조 하세요.  
  
<a name="autoreverseproperty"></a>   
### <a name="the-autoreverse-property"></a>AutoReverse 속성  
 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 속성은 <xref:System.Windows.Media.Animation.Timeline> 각 전방 반복이 끝날 때 뒤로 재생 되는지 여부를 지정 합니다. 다음 예에서는를 `true`<xref:System.Windows.Media.Animation.DoubleAnimation>의 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 속성으로 설정 합니다. 따라서 0에서 100 사이에 애니메이션 효과를 적용 한 다음 100에서 0으로의 애니메이션을 적용 합니다. 총 10초 동안 재생됩니다.  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverseexampleinline)]  
  
 <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> 값을 사용 하 여 <xref:System.Windows.Media.Animation.Timeline>의 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>를 지정 하 고 해당 <xref:System.Windows.Media.Animation.Timeline>의 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 속성을 `true`하는 경우 한 번의 반복은 하나의 전방 반복으로 구성 된 후 하나의 역방향 반복으로 구성 됩니다.  다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation>의 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>를 앞의 예제에서 <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> 2로 설정 합니다. 결과적으로, <xref:System.Windows.Media.Animation.DoubleAnimation>은 20 초 동안 재생 됩니다. 5 초 동안 앞으로, 5 초 동안 뒤로, 5 초 동안 앞으로, 5 초 동안 뒤로 이동 합니다.  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseRepeatExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverserepeatexampleinline)]  
  
 컨테이너 타임 라인에 자식 <xref:System.Windows.Media.Animation.Timeline> 개체가 있으면 해당 개체는 컨테이너 타임 라인이 수행 될 때 반전 됩니다. 추가 예제는 [타임 라인이 자동으로 반전 되는지 여부 지정](how-to-specify-whether-a-timeline-automatically-reverses.md)을 참조 하세요.  
  
<a name="timelinebegin"></a>   
## <a name="the-begintime-property"></a>BeginTime 속성  
 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> 속성을 사용 하면 타임 라인이 시작 되는 시기를 지정할 수 있습니다.  타임라인의 시작 시간은 부모 타임라인에 상대적입니다. 타임라인 0초는 부모 타임라인이 시작되자마자 해당 타임라인이 시작됨을 의미합니다. 다른 값을 지정하면 부모 타임라인이 재생을 시작하는 시간과 자식 타임라인이 재생되는 시간 사이에 오프셋이 생성됩니다. 예를 들어 시작 시간이 2초면 부모 타임라인이 2초에 도달할 때 해당 타임라인이 재생을 시작함을 의미합니다. 기본적으로 모든 타임라인의 시작 시간은 0초입니다. 타임 라인의 시작 시간을 `null`설정 하 여 타임 라인이 시작 되지 않도록 할 수도 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][X:Null 태그 확장](../../../desktop-wpf/xaml-services/xnull-markup-extension.md)을 사용 하 여 null을 지정 합니다.  
  
 타임 라인이 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 설정으로 인해 반복 될 때마다 시작 시간이 적용 되지 않습니다. 10 초의 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>와 <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A><xref:System.Windows.Media.Animation.RepeatBehavior> 사용 하 여 애니메이션을 만드는 경우 처음에는 애니메이션이 처음 재생 될 때까지 10 초의 지연이 발생 하지만 각 연속 반복에 대해서는 반복 되지 않습니다. 그러나 애니메이션의 부모 타임라인이 다시 시작되거나 반복되면 10초의 지연이 발생할 것입니다.  
  
 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> 속성은 타임 라인에 시차를 주는 데 유용 합니다. 다음 예에서는 두 개의 자식 <xref:System.Windows.Media.Animation.DoubleAnimation> 개체가 있는 <xref:System.Windows.Media.Animation.Storyboard>를 만듭니다. 첫 번째 애니메이션의 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>는 5 초이 고, 두 번째 애니메이션의 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 3 초입니다. 이 예에서는 두 번째 <xref:System.Windows.Media.Animation.DoubleAnimation> <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>를 5 초로 설정 하 여 첫 번째 <xref:System.Windows.Media.Animation.DoubleAnimation> 끝난 후 재생이 시작 되도록 합니다.  
  
 [!code-xaml[animation_ovws_snippet#TBBeginTimeExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbbegintimeexampleinline)]  
  
<a name="fillbehaviorproperty"></a>   
## <a name="the-fillbehavior-property"></a>FillBehavior 속성  
 <xref:System.Windows.Media.Animation.Timeline> 전체 활성 기간의 끝에 도달 하면 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성은 마지막 값을 중지 하거나 유지할지 여부를 지정 합니다. <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> "이 (가) 포함 된 애니메이션은 출력 값을 포함 합니다. 애니메이션이 적용 되는 속성은 애니메이션의 마지막 값을 유지 합니다. <xref:System.Windows.Media.Animation.FillBehavior.Stop> 값은 애니메이션이 종료 된 후 대상 속성에 영향을 주지 않도록 합니다.  
  
 다음 예에서는 두 개의 자식 <xref:System.Windows.Media.Animation.DoubleAnimation> 개체가 있는 <xref:System.Windows.Media.Animation.Storyboard>를 만듭니다. 두 <xref:System.Windows.Media.Animation.DoubleAnimation> 개체는 모두 0에서 100 <xref:System.Windows.Shapes.Rectangle> <xref:System.Windows.FrameworkElement.Width%2A>에 애니메이션 효과를 적용 합니다. <xref:System.Windows.Shapes.Rectangle> 요소에는 애니메이션이 적용 되지 않은 <xref:System.Windows.FrameworkElement.Width%2A> 값 500 [장치 독립적 픽셀]이 있습니다.  
  
- 첫 번째 <xref:System.Windows.Media.Animation.DoubleAnimation>의 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성은 기본값인 <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>로 설정 됩니다. 따라서 <xref:System.Windows.Media.Animation.DoubleAnimation> 끝난 후 사각형의 너비가 100에 그대로 유지 됩니다.  
  
- 두 번째 <xref:System.Windows.Media.Animation.DoubleAnimation>의 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성은 <xref:System.Windows.Media.Animation.FillBehavior.Stop>로 설정 됩니다. 결과적으로, 두 번째 <xref:System.Windows.Shapes.Rectangle>의 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.Media.Animation.DoubleAnimation> 끝난 후 500로 되돌아갑니다.  
  
 [!code-xaml[animation_ovws_snippet#TBFillBehaviorExample](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbfillbehaviorexample)]  
  
<a name="speedproperties"></a>   
## <a name="properties-that-control-the-speed-of-a-timeline"></a>타임라인의 속도를 제어하는 속성  
 <xref:System.Windows.Media.Animation.Timeline> 클래스는 속도를 지정 하기 위한 세 가지 속성을 제공 합니다.  
  
- <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> – 해당 부모를 기준으로 시간을 지정 하 여 <xref:System.Windows.Media.Animation.Timeline>에 대 한 진행 속도를 지정 합니다. 값이 1 보다 크면 <xref:System.Windows.Media.Animation.Timeline> 속도와 자식 <xref:System.Windows.Media.Animation.Timeline> 개체가 증가 합니다. 0에서 1 사이의 값을 낮춥니다. 값 1은 <xref:System.Windows.Media.Animation.Timeline> 부모와 동일한 속도로 진행 됨을 나타냅니다. 컨테이너 타임 라인의 <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> 설정은 모든 자식 <xref:System.Windows.Media.Animation.Timeline> 개체에도 영향을 줍니다.  
  
- <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> – 시간을 단축할 때 시간 표시 막대 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>의 비율을 지정 합니다. 예제는 [방법: 애니메이션 가속 또는 감속](how-to-accelerate-or-decelerate-an-animation.md)을 참조 하세요. 
  
- <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A>-감속 소요 된 타임 라인 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>의 비율을 지정 합니다. 예제는 [방법: 애니메이션 가속 또는 감속](how-to-accelerate-or-decelerate-an-animation.md)을 참조 하세요.  
  
## <a name="see-also"></a>참조

- [애니메이션 개요](animation-overview.md)
- [애니메이션 및 타이밍 시스템 개요](animation-and-timing-system-overview.md)
- [타이밍 이벤트 개요](timing-events-overview.md)
- [방법 항목](animation-and-timing-how-to-topics.md)
- [애니메이션 타이밍 동작 샘플](https://go.microsoft.com/fwlink/?LinkID=159970)
