---
title: 애니메이션에 대한 유용한 정보
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- troubleshooting [WPF], animation
- animations [WPF], FillBehavior property
- troubleshooting animation [WPF]
- animating objects [WPF], troubleshooting
- animation tips and tricks [WPF]
- tips and tricks [WPF], animation
- performance troubleshooting [WPF], animation
- animations [WPF], use of system resources
ms.assetid: e467796b-d5d4-45a6-a108-8c5d7ff69a0f
ms.openlocfilehash: ef59631663e6cf1c98adfed77a2dbdb6ca124fa1
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636031"
---
# <a name="animation-tips-and-tricks"></a>애니메이션에 대한 유용한 정보
WPF에서 애니메이션을 사용할 때 애니메이션을 더 잘 수행 하 고 문제가 발생 하지 않도록 하는 다양 한 팁과 트릭이 있습니다.  
  
<a name="generalissuessection"></a>   
## <a name="general-issues"></a>일반적인 문제  
  
### <a name="animating-the-position-of-a-scroll-bar-or-slider-freezes-it"></a>스크롤 막대 또는 슬라이더의 위치에 애니메이션 효과를 줄 경우 고정됨  
 <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> (기본값) <xref:System.Windows.Media.Animation.FillBehavior> 있는 애니메이션을 사용 하 여 스크롤 막대 또는 슬라이더의 위치에 애니메이션 효과를 줄 경우 더 이상 사용자가 스크롤 막대 또는 슬라이더를 이동할 수 없습니다. 그 이유는 애니메이션이 종료되더라도 대상 속성의 기본값은 여전히 재정의되기 때문입니다. 애니메이션에서 속성의 현재 값을 재정의 하는 것을 중지 하려면 해당 값을 제거 하거나 <xref:System.Windows.Media.Animation.FillBehavior.Stop><xref:System.Windows.Media.Animation.FillBehavior> 제공 합니다. 자세한 내용 및 예제는 [Storyboard를 사용 하 여 애니메이션 효과를 적용 한 후 속성 설정](how-to-set-a-property-after-animating-it-with-a-storyboard.md)을 참조 하세요.  
  
### <a name="animating-the-output-of-an-animation-has-no-effect"></a>애니메이션의 출력에 애니메이션을 적용해도 효과가 없음  
 다른 애니메이션의 출력에 해당하는 개체에 애니메이션 효과를 줄 수 없습니다. 예를 들어, 사용 하는 경우는 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> 애니메이션 효과를 <xref:System.Windows.Shapes.Shape.Fill%2A> 의 <xref:System.Windows.Shapes.Rectangle> 에서 <xref:System.Windows.Media.RadialGradientBrush> 에 <xref:System.Windows.Media.SolidColorBrush>의 모든 속성에 애니메이션을 적용할 수 없습니다는 <xref:System.Windows.Media.RadialGradientBrush> 또는 <xref:System.Windows.Media.SolidColorBrush>.  
  
### <a name="cant-change-the-value-of-a-property-after-animating-it"></a>애니메이션 효과를 적용한 후 속성 값을 변경할 수 없음  
 경우에 따라 애니메이션이 종료된 후에도 애니메이션 효과를 적용한 속성의 값을 변경할 수 없는 것처럼 나타납니다. 그 이유는 애니메이션이 종료되더라도 속성의 기본값은 여전히 재정의되기 때문입니다. 애니메이션에서 속성의 현재 값을 재정의 하는 것을 중지 하려면 해당 값을 제거 하거나 <xref:System.Windows.Media.Animation.FillBehavior.Stop><xref:System.Windows.Media.Animation.FillBehavior> 제공 합니다. 자세한 내용 및 예제는 [Storyboard를 사용 하 여 애니메이션 효과를 적용 한 후 속성 설정](how-to-set-a-property-after-animating-it-with-a-storyboard.md)을 참조 하세요.  
  
### <a name="changing-a-timeline-has-no-effect"></a>타임라인을 변경해도 효과가 없음  
 대부분의 <xref:System.Windows.Media.Animation.Timeline> 속성은 애니메이션 효과 데이터 바인딩될 수 있지만 활성 <xref:System.Windows.Media.Animation.Timeline>의 속성 값을 변경 해도 아무런 영향을 주지 않습니다. <xref:System.Windows.Media.Animation.Timeline> 시작 될 때 타이밍 시스템은 <xref:System.Windows.Media.Animation.Timeline>의 복사본을 만들고이를 사용 하 여 <xref:System.Windows.Media.Animation.Clock> 개체를 만듭니다. 원본을 수정해도 시스템의 복사본에는 영향을 주지 않습니다.  
  
 변경 내용을 반영 하려면 해당 clock을 다시 생성 하 고 이전에 만든 clock을 교체 하는 데 사용 해야 합니다. <xref:System.Windows.Media.Animation.Timeline> 클록은 자동으로 다시 생성되지 않습니다. 다음은 타임라인 변경 내용을 적용하는 몇 가지 방법입니다.  
  
- 타임 라인은 또는에 속하는 경우는 <xref:System.Windows.Media.Animation.Storyboard>를 사용 하 여 해당 storyboard를 다시 적용 하 여 변경 내용을 반영 만들 수 있습니다를 <xref:System.Windows.Media.Animation.BeginStoryboard> 또는 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드. 부작용으로 애니메이션까지 다시 시작됩니다. 코드에서 사용할 수는 <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> 메서드 storyboard를 이전 위치로 다시 합니다.  
  
- 사용 하 여 속성에 직접 애니메이션을 적용 하는 경우는 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 메서드를 호출 합니다 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 메서드를 다시 수정 된 애니메이션을 전달 합니다.  
  
- 클록 수준에서 직접 작업하는 경우 새 클록 집합을 만들어 적용하고 이 클록 집합을 사용하여 이전에 생성된 클록 집합을 대체합니다.  
  
 타임 라인과 클록에 대 한 자세한 내용은 [애니메이션 및 타이밍 시스템 개요](animation-and-timing-system-overview.md)를 참조 하세요.  
  
### <a name="fillbehaviorstop-doesnt-work-as-expected"></a>FillBehavior.Stop이 예상대로 작동하지 않음  
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성을 <xref:System.Windows.Media.Animation.FillBehavior.Stop>로 설정 하는 것은 <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>의 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> 설정을 포함 하 여 한 애니메이션이 다른 애니메이션에 "손을 끄는" 경우와 같이 아무런 영향도 미치지 않는 경우가 있습니다.  
  
 다음 예에서는 <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Shapes.Rectangle> 및 <xref:System.Windows.Media.TranslateTransform>를 만듭니다. <xref:System.Windows.Media.TranslateTransform>는 <xref:System.Windows.Controls.Canvas><xref:System.Windows.Shapes.Rectangle> 이동 하기 위해 애니메이션 효과가 적용 됩니다.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipAnimatedObject](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipanimatedobject)]  
  
 이 단원의 예제에서는 위의 개체를 사용 하 여 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성이 예상과 다르게 동작 하는 여러 가지 경우를 보여 줍니다.  
  
#### <a name="fillbehaviorstop-and-handoffbehavior-with-multiple-animations"></a>여러 애니메이션에서의 FillBehavior="Stop" 및 HandoffBehavior  
 경우에 따라 애니메이션이 두 번째 애니메이션으로 바뀔 때 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성을 무시 하는 것 처럼 보입니다. 다음 예제를 사용 하 여 두 개의 <xref:System.Windows.Media.Animation.Storyboard> 개체를 만들고이를 사용 하 여 앞의 예제에 표시 된 것과 동일한 <xref:System.Windows.Media.TranslateTransform>에 애니메이션 효과를 줍니다.  
  
 첫 번째 <xref:System.Windows.Media.Animation.Storyboard>`B1`는 0에서 350 사이의 <xref:System.Windows.Media.TranslateTransform> <xref:System.Windows.Media.TranslateTransform.X%2A> 속성에 애니메이션을 적용 하 여 350 픽셀을 오른쪽으로 이동 합니다. 애니메이션이 지속 시간의 끝에 도달 하 고 재생을 중지 하면 <xref:System.Windows.Media.TranslateTransform.X%2A> 속성은 원래 값인 0으로 되돌아갑니다. 결과적으로 사각형은 오른쪽으로 350픽셀만큼 이동한 다음 원래 위치로 되돌아갑니다.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB1Button](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb1button)]  
  
 두 번째 <xref:System.Windows.Media.Animation.Storyboard>`B2`는 동일한 <xref:System.Windows.Media.TranslateTransform>의 <xref:System.Windows.Media.TranslateTransform.X%2A> 속성에도 애니메이션 효과를 적용 합니다. 이 <xref:System.Windows.Media.Animation.Storyboard> 애니메이션의 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성만 설정 되었으므로 애니메이션은 애니메이션이 적용 되는 속성의 현재 값을 시작 값으로 사용 합니다.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB2Button](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb2button)]  
  
 첫 번째 <xref:System.Windows.Media.Animation.Storyboard>를 재생 하는 동안 두 번째 단추를 클릭 하면 다음과 같은 동작이 발생할 수 있습니다.  
  
1. 애니메이션에 <xref:System.Windows.Media.Animation.FillBehavior.Stop>의 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 있으므로 첫 번째 storyboard가 끝나고 사각형을 원래 위치로 다시 보냅니다.  
  
2. 두 번째 Storyboard가 적용되며, 0에 해당하는 현재 위치에서 500으로 애니메이션 효과를 줍니다.  
  
 **그러나 이 작업이 수행되지 않습니다.** 대신, 사각형이 원래 위치로 돌아가지 않고 계속 오른쪽으로 이동됩니다. 그 이유는 두 번째 애니메이션이 첫 번째 애니메이션의 현재 값을 시작 값으로 사용하고 해당 값에서 500으로 애니메이션 효과를 주기 때문입니다. <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace><xref:System.Windows.Media.Animation.HandoffBehavior>를 사용 하기 때문에 두 번째 애니메이션이 첫 번째 애니메이션을 대체 하면 첫 번째 애니메이션의 <xref:System.Windows.Media.Animation.FillBehavior> 중요 하지 않습니다.  
  
#### <a name="fillbehavior-and-the-completed-event"></a>FillBehavior 및 Completed 이벤트  
 다음 예에서는 <xref:System.Windows.Media.Animation.FillBehavior.Stop><xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>에 영향을 주지 않는 다른 시나리오를 보여 줍니다. 이 예제에서는 Storyboard를 사용 하 여 <xref:System.Windows.Media.TranslateTransform>의 <xref:System.Windows.Media.TranslateTransform.X%2A> 속성에 0에서 350까지 애니메이션 효과를 적용 합니다. 그러나이 예제에서는 <xref:System.Windows.Media.Animation.Timeline.Completed> 이벤트에 등록 합니다.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardCButton](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardcbutton)]  
  
 <xref:System.Windows.Media.Animation.Timeline.Completed> 이벤트 처리기는 현재 값에서 500로 동일한 속성에 애니메이션 효과를 주는 다른 <xref:System.Windows.Media.Animation.Storyboard>를 시작 합니다.  
  
 [!code-csharp[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml.cs#fillbehaviortipstoryboardc1completedhandler)]
 [!code-vb[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/VisualBasic/FillBehaviorTip.xaml.vb#fillbehaviortipstoryboardc1completedhandler)]  
  
 다음은 두 번째 <xref:System.Windows.Media.Animation.Storyboard>를 리소스로 정의 하는 태그입니다.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipResources](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipresources)]  
  
 <xref:System.Windows.Media.Animation.Storyboard>를 실행 하는 경우 <xref:System.Windows.Media.TranslateTransform>의 <xref:System.Windows.Media.TranslateTransform.X%2A> 속성이 0에서 350까지 애니메이션 효과를 적용 하 고 완료 되 면 0으로 되돌린 다음 (<xref:System.Windows.Media.Animation.FillBehavior.Stop>의 <xref:System.Windows.Media.Animation.FillBehavior> 설정이 있으므로) 0에서 500으로 애니메이션 효과를 적용할 수 있습니다. 대신 <xref:System.Windows.Media.TranslateTransform> 0에서 350, 500에 애니메이션 효과를 적용 합니다.  
  
 이는 WPF가 이벤트를 발생 시키는 순서와 속성 값이 캐시 되 고 속성이 무효화 되지 않는 한 다시 계산 되지 않기 때문입니다. <xref:System.Windows.Media.Animation.Timeline.Completed> 이벤트는 루트 타임 라인 (첫 번째 <xref:System.Windows.Media.Animation.Storyboard>)에 의해 트리거 되었으므로 먼저 처리 됩니다. 현재는 아직 무효화 되지 않았기 때문에 <xref:System.Windows.Media.TranslateTransform.X%2A> 속성은 애니메이션이 적용 된 값을 계속 반환 합니다. 두 번째 <xref:System.Windows.Media.Animation.Storyboard>는 캐시 된 값을 시작 값으로 사용 하 여 애니메이션 효과를 시작 합니다.  
  
<a name="performancesection"></a>   
## <a name="performance"></a>성능  
  
### <a name="animations-continue-to-run-after-navigating-away-from-a-page"></a>페이지 외부로 이동한 후에도 애니메이션이 계속 실행됨  
 실행 중인 애니메이션을 포함 하는 <xref:System.Windows.Controls.Page>에서 벗어나면 <xref:System.Windows.Controls.Page> 가비지 수집 될 때까지 해당 애니메이션이 계속 재생 됩니다. 사용 중인 탐색 시스템에 따라, 빠져 나간 페이지가 제한 없는 시간 동안 메모리에 남아 있으며 해당 애니메이션을 재생하느라 리소스를 계속 사용할 수 있습니다. 페이지에 계속 실행되는("주변") 애니메이션이 포함되어 있을 때 이러한 상황이 가장 두드러지게 나타납니다.  
  
 따라서 페이지에서 이동할 때 애니메이션을 제거 하려면 <xref:System.Windows.FrameworkElement.Unloaded> 이벤트를 사용 하는 것이 좋습니다.  
  
 애니메이션을 제거하는 방법에는 여러 가지가 있습니다. 다음 기법을 사용 하 여 <xref:System.Windows.Media.Animation.Storyboard>에 속한 애니메이션을 제거할 수 있습니다.  
  
- 이벤트 트리거를 시작 하는 <xref:System.Windows.Media.Animation.Storyboard> 제거 하려면 [방법: 스토리 보드 제거](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms749412(v=vs.90))를 참조 하세요.  
  
- 코드를 사용 하 여 <xref:System.Windows.Media.Animation.Storyboard>를 제거 하려면 <xref:System.Windows.Media.Animation.Storyboard.Remove%2A> 메서드를 참조 하세요.  
  
 애니메이션이 시작된 방법에 관계없이 다음 기법을 사용할 수 있습니다.  
  
- 특정 속성에서 애니메이션을 제거 하려면 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> 메서드를 사용 합니다. 첫 번째 매개 변수로 애니메이션 효과가 적용 되는 속성을 지정 하 고 `null` 두 번째입니다. 이렇게 하면 해당 속성에서 모든 애니메이션 클록이 제거됩니다.  
  
 속성에 애니메이션 효과를 주는 다양 한 방법에 대 한 자세한 내용은 [속성 애니메이션 기술 개요](property-animation-techniques-overview.md)를 참조 하세요.  
  
### <a name="using-the-compose-handoffbehavior-consumes-system-resources"></a>Compose HandoffBehavior를 사용하여 시스템 리소스 소비  
 <xref:System.Windows.Media.Animation.HandoffBehavior.Compose><xref:System.Windows.Media.Animation.HandoffBehavior>를 사용 하 여 속성에 <xref:System.Windows.Media.Animation.Storyboard>, <xref:System.Windows.Media.Animation.AnimationTimeline>또는 <xref:System.Windows.Media.Animation.AnimationClock>를 적용 하는 경우 이전에 해당 속성과 연결 된 모든 <xref:System.Windows.Media.Animation.Clock> 개체는 계속 시스템 리소스를 사용 합니다. 타이밍 시스템은 이러한 클록을 자동으로 제거 하지 않습니다.  
  
 많은 수의 시계를 사용 하 여 적용 하는 경우 성능 문제를 방지 하려면 <xref:System.Windows.Media.Animation.HandoffBehavior.Compose>를 완성 한 후 애니메이션된 속성에서 구성 중인 클록을 제거 해야 합니다. 여러 가지 방법으로 클록을 제거할 수 있습니다.  
  
- 속성에서 모든 클록을 제거 하려면 사용 합니다 <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationClock%29> 또는 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> 애니메이션된 개체의 메서드. 첫 번째 매개 변수로 애니메이션 효과가 적용 되는 속성을 지정 하 고 `null` 두 번째입니다. 이렇게 하면 해당 속성에서 모든 애니메이션 클록이 제거됩니다.  
  
- 특정 제거할 <xref:System.Windows.Media.Animation.AnimationClock> 클록 목록에서 사용 하 여는 <xref:System.Windows.Media.Animation.Clock.Controller%2A> 의 속성을 <xref:System.Windows.Media.Animation.AnimationClock> 검색할를 <xref:System.Windows.Media.Animation.ClockController>, 호출를 <xref:System.Windows.Media.Animation.ClockController.Remove%2A> 메서드의 <xref:System.Windows.Media.Animation.ClockController>합니다. 이 일반적으로 수행 된 <xref:System.Windows.Media.Animation.Clock.Completed> 클록에 대 한 이벤트 처리기입니다. 루트 클록만 하 여 제어 될 수는 <xref:System.Windows.Media.Animation.ClockController>; <xref:System.Windows.Media.Animation.Clock.Controller%2A> 자식 클록의 속성은 반환 `null`합니다. 또한는 <xref:System.Windows.Media.Animation.Clock.Completed> 클록의 유효 기간 무제한 인 경우 이벤트가 호출 되지 것입니다.  호출 시기를 결정 하는 사용자가 해야 하는 경우 <xref:System.Windows.Media.Animation.ClockController.Remove%2A>합니다.  
  
 이것은 주로 수명이 긴 개체에 대한 애니메이션에서 문제가 됩니다.  개체가 가비지 수집될 경우 해당 클록도 연결이 끊어지고 가비지가 수집됩니다.  
  
 클록 개체에 대 한 자세한 내용은 참조 하세요. [애니메이션 및 타이밍 시스템 개요](animation-and-timing-system-overview.md)합니다.  
  
## <a name="see-also"></a>참조

- [애니메이션 개요](animation-overview.md)
