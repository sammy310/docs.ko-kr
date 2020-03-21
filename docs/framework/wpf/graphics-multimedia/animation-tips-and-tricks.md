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
ms.openlocfilehash: 6b540448599c1e1083ed367a312ef60fceacd0d5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187646"
---
# <a name="animation-tips-and-tricks"></a>애니메이션에 대한 유용한 정보
WPF에서 애니메이션으로 작업할 때 애니메이션의 성능을 향상시키고 좌절감을 줄일 수 있는 여러 가지 팁과 요령이 있습니다.  
  
<a name="generalissuessection"></a>
## <a name="general-issues"></a>일반적인 문제  
  
### <a name="animating-the-position-of-a-scroll-bar-or-slider-freezes-it"></a>스크롤 막대 또는 슬라이더의 위치에 애니메이션 효과를 줄 경우 고정됨  
 (기본값)가 있는 <xref:System.Windows.Media.Animation.FillBehavior> <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> 애니메이션을 사용하여 스크롤 막대 또는 슬라이더의 위치에 애니메이션을 지정하면 사용자는 더 이상 스크롤 막대 또는 슬라이더를 이동할 수 없습니다. 그 이유는 애니메이션이 종료되더라도 대상 속성의 기본값은 여전히 재정의되기 때문입니다. 애니메이션이 속성의 현재 값을 재정의하지 못하도록 하려면 을 <xref:System.Windows.Media.Animation.FillBehavior> 제거하거나 <xref:System.Windows.Media.Animation.FillBehavior.Stop>을 지정합니다. 자세한 정보 및 예제는 [스토리보드로 속성 애니메이션후 속성 설정을](how-to-set-a-property-after-animating-it-with-a-storyboard.md)참조하십시오.  
  
### <a name="animating-the-output-of-an-animation-has-no-effect"></a>애니메이션의 출력에 애니메이션을 적용해도 효과가 없음  
 다른 애니메이션의 출력에 해당하는 개체에 애니메이션 효과를 줄 수 없습니다. 예를 들어, 사용 하는 경우는 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> 애니메이션 효과를 <xref:System.Windows.Shapes.Shape.Fill%2A> 의 <xref:System.Windows.Shapes.Rectangle> 에서 <xref:System.Windows.Media.RadialGradientBrush> 에 <xref:System.Windows.Media.SolidColorBrush>의 모든 속성에 애니메이션을 적용할 수 없습니다는 <xref:System.Windows.Media.RadialGradientBrush> 또는 <xref:System.Windows.Media.SolidColorBrush>.  
  
### <a name="cant-change-the-value-of-a-property-after-animating-it"></a>애니메이션 효과를 적용한 후 속성 값을 변경할 수 없음  
 경우에 따라 애니메이션이 종료된 후에도 애니메이션 효과를 적용한 속성의 값을 변경할 수 없는 것처럼 나타납니다. 그 이유는 애니메이션이 종료되더라도 속성의 기본값은 여전히 재정의되기 때문입니다. 애니메이션이 속성의 현재 값을 재정의하지 못하도록 하려면 을 <xref:System.Windows.Media.Animation.FillBehavior> 제거하거나 <xref:System.Windows.Media.Animation.FillBehavior.Stop>을 지정합니다. 자세한 정보 및 예제는 [스토리보드로 속성 애니메이션후 속성 설정을](how-to-set-a-property-after-animating-it-with-a-storyboard.md)참조하십시오.  
  
### <a name="changing-a-timeline-has-no-effect"></a>타임라인을 변경해도 효과가 없음  
 대부분의 <xref:System.Windows.Media.Animation.Timeline> 속성은 애니메이션가능하며 데이터 바인딩될 수 있지만 활성의 <xref:System.Windows.Media.Animation.Timeline> 속성 값을 변경하면 아무런 효과가 없는 것 같습니다. 왜냐하면 a가 <xref:System.Windows.Media.Animation.Timeline> 시작되면 타이밍 시스템이 의 복사본을 <xref:System.Windows.Media.Animation.Timeline> 만들어 오브젝트를 <xref:System.Windows.Media.Animation.Clock> 만드는 데 사용하기 때문입니다. 원본을 수정해도 시스템의 복사본에는 영향을 주지 않습니다.  
  
 변경 <xref:System.Windows.Media.Animation.Timeline> 사항을 반영하려면 해당 클럭을 다시 생성하고 이전에 만든 클럭을 대체하는 데 사용해야 합니다. 클록은 자동으로 다시 생성되지 않습니다. 다음은 타임라인 변경 내용을 적용하는 몇 가지 방법입니다.  
  
- 타임 라인은 또는에 속하는 경우는 <xref:System.Windows.Media.Animation.Storyboard>를 사용 하 여 해당 storyboard를 다시 적용 하 여 변경 내용을 반영 만들 수 있습니다를 <xref:System.Windows.Media.Animation.BeginStoryboard> 또는 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드. 부작용으로 애니메이션까지 다시 시작됩니다. 코드에서 사용할 수는 <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> 메서드 storyboard를 이전 위치로 다시 합니다.  
  
- 사용 하 여 속성에 직접 애니메이션을 적용 하는 경우는 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 메서드를 호출 합니다 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 메서드를 다시 수정 된 애니메이션을 전달 합니다.  
  
- 클록 수준에서 직접 작업하는 경우 새 클록 집합을 만들어 적용하고 이 클록 집합을 사용하여 이전에 생성된 클록 집합을 대체합니다.  
  
 타임라인 및 시계에 대한 자세한 내용은 [애니메이션 및 타이밍 시스템 개요를](animation-and-timing-system-overview.md)참조하십시오.  
  
### <a name="fillbehaviorstop-doesnt-work-as-expected"></a>FillBehavior.Stop이 예상대로 작동하지 않음  
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성을 <xref:System.Windows.Media.Animation.FillBehavior.Stop> <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> 설정하지 않는 경우와 같이 한 애니메이션이 다른 애니메이션에 "손을 떼는" 경우의 <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>설정이 있기 때문에 영향을 주지 않는 경우가 있습니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.Canvas>에서 <xref:System.Windows.Shapes.Rectangle> 와 <xref:System.Windows.Media.TranslateTransform>를 만듭니다. 의 <xref:System.Windows.Media.TranslateTransform> <xref:System.Windows.Shapes.Rectangle> 주위에 이동애니메이션됩니다. <xref:System.Windows.Controls.Canvas>  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipAnimatedObject](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipanimatedobject)]  
  
 이 섹션의 예제에서는 앞의 개체를 사용하여 속성이 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 예상대로 작동하지 않는 몇 가지 경우를 보여 줍니다.  
  
#### <a name="fillbehaviorstop-and-handoffbehavior-with-multiple-animations"></a>여러 애니메이션에서의 FillBehavior="Stop" 및 HandoffBehavior  
 때로는 애니메이션이 두 번째 애니메이션으로 대체 될 때 해당 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성을 무시하는 것처럼 보입니다. 두 개체를 <xref:System.Windows.Media.Animation.Storyboard> 만들고 이를 사용하여 앞의 예제와 동일한 <xref:System.Windows.Media.TranslateTransform> 애니메이션을 만드는 다음 예제를 예로 들어 보겠습니다.  
  
 첫 <xref:System.Windows.Media.Animation.Storyboard>번째 `B1`는 <xref:System.Windows.Media.TranslateTransform.X%2A> <xref:System.Windows.Media.TranslateTransform> 0에서 350까지의 속성에 애니메이션을 주어 사각형을 오른쪽으로 350픽셀 이동합니다. 애니메이션이 지속 시간의 끝에 도달하고 재생을 <xref:System.Windows.Media.TranslateTransform.X%2A> 중지하면 속성은 원래 값인 0으로 되돌아갑니다. 결과적으로 사각형은 오른쪽으로 350픽셀만큼 이동한 다음 원래 위치로 되돌아갑니다.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB1Button](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb1button)]  
  
 두 <xref:System.Windows.Media.Animation.Storyboard>번째 `B2`는 동일한 <xref:System.Windows.Media.TranslateTransform>의 <xref:System.Windows.Media.TranslateTransform.X%2A> 속성에도 애니메이션을 애니메이션합니다. 이 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> <xref:System.Windows.Media.Animation.Storyboard> 애니메이션의 속성만 설정되므로 애니메이션은 애니메이션이 애니메이션하는 속성의 현재 값을 시작 값으로 사용합니다.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB2Button](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb2button)]  
  
 첫 번째 <xref:System.Windows.Media.Animation.Storyboard> 버튼을 재생하는 동안 두 번째 단추를 클릭하면 다음과 같은 동작이 발생할 수 있습니다.  
  
1. 첫 번째 스토리보드는 애니메이션에 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> <xref:System.Windows.Media.Animation.FillBehavior.Stop>의 한 을 가있기 때문에 사각형을 종료하고 원래 위치로 다시 보냅니다.  
  
2. 두 번째 Storyboard가 적용되며, 0에 해당하는 현재 위치에서 500으로 애니메이션 효과를 줍니다.  
  
 **그러나 이 작업이 수행되지 않습니다.** 대신, 사각형이 원래 위치로 돌아가지 않고 계속 오른쪽으로 이동됩니다. 그 이유는 두 번째 애니메이션이 첫 번째 애니메이션의 현재 값을 시작 값으로 사용하고 해당 값에서 500으로 애니메이션 효과를 주기 때문입니다. 두 번째 애니메이션이 사용되어 <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> <xref:System.Windows.Media.Animation.HandoffBehavior> 첫 번째 <xref:System.Windows.Media.Animation.FillBehavior> 애니메이션을 대체하면 첫 번째 애니메이션의 여부는 중요하지 않습니다.  
  
#### <a name="fillbehavior-and-the-completed-event"></a>FillBehavior 및 Completed 이벤트  
 다음 예제에서는 아무런 효과가 <xref:System.Windows.Media.Animation.FillBehavior.Stop> <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 없는 것으로 보이는 또 다른 시나리오를 보여 줍니다. 이 예제에서는 스토리보드를 사용하여 0에서 <xref:System.Windows.Media.TranslateTransform.X%2A> 350까지의 속성을 애니메이션합니다. <xref:System.Windows.Media.TranslateTransform> 그러나 이번에는 <xref:System.Windows.Media.Animation.Timeline.Completed> 예제가 이벤트에 등록합니다.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardCButton](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardcbutton)]  
  
 이벤트 <xref:System.Windows.Media.Animation.Timeline.Completed> 처리기는 <xref:System.Windows.Media.Animation.Storyboard> 동일한 속성을 현재 값에서 500으로 애니메이션하는 다른 속성을 시작합니다.  
  
 [!code-csharp[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml.cs#fillbehaviortipstoryboardc1completedhandler)]
 [!code-vb[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/VisualBasic/FillBehaviorTip.xaml.vb#fillbehaviortipstoryboardc1completedhandler)]  
  
 다음은 두 번째를 <xref:System.Windows.Media.Animation.Storyboard> 리소스로 정의하는 태그입니다.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipResources](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipresources)]  
  
 <xref:System.Windows.Media.Animation.Storyboard>을 실행하면 0에서 350으로 <xref:System.Windows.Media.TranslateTransform> 애니메이션되는 속성을 예상한 <xref:System.Windows.Media.Animation.FillBehavior> <xref:System.Windows.Media.TranslateTransform.X%2A> 다음 완료된 후 0으로 되돌린 다음(설정이 <xref:System.Windows.Media.Animation.FillBehavior.Stop>있기 때문에) 0에서 500으로 애니메이션될 수 있습니다. 대신 0에서 350으로 <xref:System.Windows.Media.TranslateTransform> 애니메이션한 다음 500으로 애니메이션합니다.  
  
 이는 WPF가 이벤트를 발생시키는 순서와 속성 값이 캐시되고 속성이 무효화되지 않는 한 다시 계산되지 않기 때문입니다. 이벤트는 <xref:System.Windows.Media.Animation.Timeline.Completed> 루트 타임라인(첫 번째)에 <xref:System.Windows.Media.Animation.Storyboard>의해 트리거되었기 때문에 먼저 처리됩니다. 현재 속성은 <xref:System.Windows.Media.TranslateTransform.X%2A> 아직 무효화되지 않았므로 애니메이션된 값을 반환합니다. 두 <xref:System.Windows.Media.Animation.Storyboard> 번째 값은 캐시된 값을 시작 값으로 사용하고 애니메이션을 시작합니다.  
  
<a name="performancesection"></a>
## <a name="performance"></a>성능  
  
### <a name="animations-continue-to-run-after-navigating-away-from-a-page"></a>페이지 외부로 이동한 후에도 애니메이션이 계속 실행됨  
 실행 중인 애니메이션이 <xref:System.Windows.Controls.Page> 포함된 에서 벗어나면 해당 <xref:System.Windows.Controls.Page> 애니메이션이 가비지 수집될 때까지 계속 재생됩니다. 사용 중인 탐색 시스템에 따라, 빠져 나간 페이지가 제한 없는 시간 동안 메모리에 남아 있으며 해당 애니메이션을 재생하느라 리소스를 계속 사용할 수 있습니다. 페이지에 계속 실행되는("주변") 애니메이션이 포함되어 있을 때 이러한 상황이 가장 두드러지게 나타납니다.  
  
 따라서 <xref:System.Windows.FrameworkElement.Unloaded> 페이지에서 멀리 이동할 때 이벤트를 사용하여 애니메이션을 제거하는 것이 좋습니다.  
  
 애니메이션을 제거하는 방법에는 여러 가지가 있습니다. 다음 기술을 사용하여 <xref:System.Windows.Media.Animation.Storyboard>에 속하는 애니메이션을 제거할 수 있습니다.  
  
- 이벤트 트리거로 시작한 것을 <xref:System.Windows.Media.Animation.Storyboard> 제거하려면 [스토리보드 제거 방법: 스토리보드 제거 를 참조하세요.](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms749412(v=vs.90))  
  
- 코드를 사용하여 을 <xref:System.Windows.Media.Animation.Storyboard>제거하려면 <xref:System.Windows.Media.Animation.Storyboard.Remove%2A> 메서드를 참조하십시오.  
  
 애니메이션이 시작된 방법에 관계없이 다음 기법을 사용할 수 있습니다.  
  
- 특정 속성에서 애니메이션을 제거하려면 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> 메서드를 사용합니다. 첫 번째 매개 변수로 애니메이션 효과가 적용 되는 속성을 지정 하 고 `null` 두 번째입니다. 이렇게 하면 해당 속성에서 모든 애니메이션 클록이 제거됩니다.  
  
 속성을 애니메이션하는 다양한 방법에 대한 자세한 내용은 [속성 애니메이션 기술 개요를](property-animation-techniques-overview.md)참조하십시오.  
  
### <a name="using-the-compose-handoffbehavior-consumes-system-resources"></a>Compose HandoffBehavior를 사용하여 시스템 리소스 소비  
 적용 하는 경우는 <xref:System.Windows.Media.Animation.Storyboard>, <xref:System.Windows.Media.Animation.AnimationTimeline>, 또는 <xref:System.Windows.Media.Animation.AnimationClock> 사용 하 여 속성을 <xref:System.Windows.Media.Animation.HandoffBehavior.Compose><xref:System.Windows.Media.Animation.HandoffBehavior>모든 <xref:System.Windows.Media.Animation.Clock> 타이밍 시스템 것입니다; 속성을 사용 하 여 이전에 연결 된 개체를 계속 시스템 리소스를 사용 하 자동으로 이러한 클록을 제거 합니다.  
  
 많은 수의 시계를 사용 하 여 적용 하는 경우 성능 문제를 방지 하려면 <xref:System.Windows.Media.Animation.HandoffBehavior.Compose>를 완성 한 후 애니메이션된 속성에서 구성 중인 클록을 제거 해야 합니다. 여러 가지 방법으로 클록을 제거할 수 있습니다.  
  
- 속성에서 모든 클록을 제거 하려면 사용 합니다 <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationClock%29> 또는 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> 애니메이션된 개체의 메서드. 첫 번째 매개 변수로 애니메이션 효과가 적용 되는 속성을 지정 하 고 `null` 두 번째입니다. 이렇게 하면 해당 속성에서 모든 애니메이션 클록이 제거됩니다.  
  
- 특정 제거할 <xref:System.Windows.Media.Animation.AnimationClock> 클록 목록에서 사용 하 여는 <xref:System.Windows.Media.Animation.Clock.Controller%2A> 의 속성을 <xref:System.Windows.Media.Animation.AnimationClock> 검색할를 <xref:System.Windows.Media.Animation.ClockController>, 호출를 <xref:System.Windows.Media.Animation.ClockController.Remove%2A> 메서드의 <xref:System.Windows.Media.Animation.ClockController>합니다. 이 일반적으로 수행 된 <xref:System.Windows.Media.Animation.Clock.Completed> 클록에 대 한 이벤트 처리기입니다. 루트 클록만 하 여 제어 될 수는 <xref:System.Windows.Media.Animation.ClockController>; <xref:System.Windows.Media.Animation.Clock.Controller%2A> 자식 클록의 속성은 반환 `null`합니다. 또한는 <xref:System.Windows.Media.Animation.Clock.Completed> 클록의 유효 기간 무제한 인 경우 이벤트가 호출 되지 것입니다.  호출 시기를 결정 하는 사용자가 해야 하는 경우 <xref:System.Windows.Media.Animation.ClockController.Remove%2A>합니다.  
  
 이것은 주로 수명이 긴 개체에 대한 애니메이션에서 문제가 됩니다.  개체가 가비지 수집될 경우 해당 클록도 연결이 끊어지고 가비지가 수집됩니다.  
  
 시계 객체에 대한 자세한 내용은 [애니메이션 및 타이밍 시스템 개요를](animation-and-timing-system-overview.md)참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- [애니메이션 개요](animation-overview.md)
