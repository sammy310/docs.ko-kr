---
title: 속성 애니메이션 기술 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- animation [WPF], properties [WPF], methods for
- properties [WPF], methods for animating
ms.assetid: 74f61413-f8c0-4e75-bf04-951886426c8b
ms.openlocfilehash: 0b4bf6d4963f32ad83f762fce73c805197ff9c9b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181838"
---
# <a name="property-animation-techniques-overview"></a>속성 애니메이션 기술 개요
이 항목에서는 storyboard, 로컬 애니메이션, 클록 및 프레임당 애니메이션 등, 속성에 애니메이션 효과를 주는 다양한 접근 방법을 설명합니다.  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>전제 조건  
 이 항목을 이해하려면 [애니메이션 개요](animation-overview.md)에 설명된 기본 애니메이션 기능에 대해 잘 알고 있어야 합니다.  
  
<a name="summary"></a>
## <a name="different-ways-to-animate"></a>애니메이션 효과를 주는 다양한 방법  
 속성에 애니메이션 효과를 주는 다양한 시나리오가 있으므로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 속성에 애니메이션 효과를 주는 몇 가지 접근 방법을 제공합니다.  
  
 각 접근 방법에 대해 다음 표에는 인스턴스별로, 스타일, 컨트롤 템플릿 또는 데이터 템플릿에서 사용할 수 있는지, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 사용할 수 있는지 여부 및 해당 접근 방식을 사용하여 애니메이션을 대화형으로 제어할 수 있는지가 나와 있습니다.  "인스턴스별"은 스타일, 컨트롤 템플릿 또는 데이터 템플릿이 아닌 개체의 인스턴스에 직접 애니메이션 또는 storyboard를 적용하는 기술을 나타냅니다.  
  
|애니메이션 기술|시나리오|XAML 지원|대화형으로 제어 가능|  
|-------------------------|---------------|-------------------|--------------------------------|  
|Storyboard 애니메이션|인스턴스별, <xref:System.Windows.Style>" <xref:System.Windows.Controls.ControlTemplate><xref:System.Windows.DataTemplate>|yes|yes|  
|로컬 애니메이션|인스턴스별|예|예|  
|클록 애니메이션|인스턴스별|예|yes|  
|프레임당 애니메이션|인스턴스별|예|해당 없음|  
  
<a name="storyboard_animations"></a>
## <a name="storyboard-animations"></a>Storyboard 애니메이션  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 <xref:System.Windows.Media.Animation.Storyboard> 애니메이션을 정의하고 적용하려는 경우 를 사용하여 애니메이션이 시작된 후 대화식으로 애니메이션을 제어하거나, 복잡한 애니메이션 <xref:System.Windows.Style>트리를 만들거나, <xref:System.Windows.Controls.ControlTemplate> 에 애니메이션을 애니메이션하거나. <xref:System.Windows.DataTemplate> 에 의해 <xref:System.Windows.Media.Animation.Storyboard>애니메이션되는 개체의 경우 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>또는 또는 를 설정하는 <xref:System.Windows.FrameworkElement> 데 <xref:System.Windows.FrameworkContentElement>사용해야 합니다. 자세한 내용은 [Storyboard 개요](storyboards-overview.md)를 참조하세요.  
  
 A는 <xref:System.Windows.Media.Animation.Storyboard> 포함된 애니메이션에 <xref:System.Windows.Media.Animation.Timeline> 대한 대상 정보를 제공하는 특수 한 유형의 컨테이너입니다. <xref:System.Windows.Media.Animation.Storyboard>을 사용하여 애니메이션하려면 다음 세 단계를 완료합니다.  
  
1. 하나 <xref:System.Windows.Media.Animation.Storyboard> 이상의 애니메이션을 선언합니다.  
  
2. <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 첨부된 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> 속성과 연결된 속성을 사용하여 각 애니메이션의 대상 오브젝트 및 속성을 지정합니다.  
  
3. (코드만) 에 <xref:System.Windows.NameScope> 대한 <xref:System.Windows.FrameworkElement> 정의 <xref:System.Windows.FrameworkContentElement>a. 애니메이션할 개체의 이름을 <xref:System.Windows.FrameworkElement> 등록하거나 <xref:System.Windows.FrameworkContentElement>.  
  
4. 을 <xref:System.Windows.Media.Animation.Storyboard>시작합니다.  
  
 시작은 <xref:System.Windows.Media.Animation.Storyboard> 애니메이션을 적용하고 시작하는 속성에 애니메이션을 적용합니다. 두 가지 방법으로 를 <xref:System.Windows.Media.Animation.Storyboard>시작할 수 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 있습니다: 클래스에서 제공 하는 메서드를 <xref:System.Windows.Media.Animation.Storyboard> 사용 하거나 <xref:System.Windows.Media.Animation.BeginStoryboard> 작업을 사용할 수 있습니다. 애니메이션을 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 사용하는 유일한 방법은 작업을 사용하는 <xref:System.Windows.Media.Animation.BeginStoryboard> 것입니다. 작업은 <xref:System.Windows.Media.Animation.BeginStoryboard> <xref:System.Windows.EventTrigger>에서 사용할 수 있습니다. <xref:System.Windows.Trigger> <xref:System.Windows.DataTrigger>  
  
 다음 표에서는 인스턴스별, <xref:System.Windows.Media.Animation.Storyboard> 스타일, 제어 템플릿 및 데이터 템플릿과 같은 각 시작 기술이 지원되는 여러 위치를 보여 둡습니다.  
  
|storyboard 시작 방법...|인스턴스별|Style|컨트롤 템플릿|데이터 템플릿|예제|  
|--------------------------------|-------------------|-----------|----------------------|-------------------|-------------|  
|<xref:System.Windows.Media.Animation.BeginStoryboard>그리고<xref:System.Windows.EventTrigger>|yes|yes|yes|yes|[Storyboard를 사용하여 속성에 애니메이션 효과 주기](how-to-animate-a-property-by-using-a-storyboard.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard>및 속성<xref:System.Windows.Trigger>|예|yes|yes|yes|[속성 값이 변경될 때 애니메이션 트리거](how-to-trigger-an-animation-when-a-property-value-changes.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard>그리고<xref:System.Windows.DataTrigger>|예|yes|yes|yes|[방법: 데이터가 변경될 때 애니메이션 트리거Changes](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa970679(v=vs.90))|  
|<xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드|yes|예|예|예|[Storyboard를 사용하여 속성에 애니메이션 효과 주기](how-to-animate-a-property-by-using-a-storyboard.md)|  
  
 개체에 대한 <xref:System.Windows.Media.Animation.Storyboard> 자세한 내용은 [스토리보드 개요](storyboards-overview.md)를 참조하십시오.  
  
## <a name="local-animations"></a>로컬 애니메이션  
 로컬 애니메이션은 모든 <xref:System.Windows.Media.Animation.Animatable> 개체의 종속성 속성을 애니메이션하는 편리한 방법을 제공합니다. 속성에 단일 애니메이션을 적용하며 애니메이션이 시작된 후에 대화형으로 제어할 필요가 없으면 로컬 애니메이션을 사용합니다. 애니메이션과 <xref:System.Windows.Media.Animation.Storyboard> 달리 로컬 애니메이션은 <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement>a 또는 a와 연결되지 않은 오브젝트에 애니메이션을 만들 수 있습니다. 또한 이러한 유형의 애니메이션에 <xref:System.Windows.NameScope> 대해 a를 정의할 필요가 없습니다.  
  
 로컬 애니메이션은 코드에만 사용할 수 있으며, 스타일, 컨트롤 템플릿 또는 데이터 템플릿에는 정의할 수 없습니다. 로컬 애니메이션은 시작된 후에 대화형으로 제어할 수 없습니다.  
  
 로컬 애니메이션을 사용하여 애니메이션 효과를 주려면 다음 단계를 완료합니다.  
  
1. 개체를 <xref:System.Windows.Media.Animation.AnimationTimeline> 만듭니다.  
  
2. 애니메이션할 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 오브젝트의 메서드를 사용하여 지정한 속성에 <xref:System.Windows.Media.Animation.AnimationTimeline> 적용합니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.Button>의 너비와 배경 색을 애니메이션하는 방법을 보여 주며.  
  
 [!code-cpp[animateproperty#11](~/samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](~/samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
## <a name="clock-animations"></a>클록 애니메이션  
 <xref:System.Windows.Media.MediaPlayer.Clock%2A> 를 사용하지 <xref:System.Windows.Media.Animation.Storyboard> 않고 애니메이션을 만들고 복잡한 타이밍 트리를 만들거나 애니메이션이 시작된 후 대화형으로 제어하려는 경우 개체를 사용합니다. Clock 개체를 사용하여 모든 개체의 종속성 속성을 <xref:System.Windows.Media.Animation.Animatable> 애니메이션할 수 있습니다.  
  
 객체를 <xref:System.Windows.Media.Animation.Clock> 사용하여 스타일, 컨트롤 템플릿 또는 데이터 템플릿에 직접 애니메이션할 수 없습니다. 애니메이션 및 타이밍 시스템은 실제로 <xref:System.Windows.Media.Animation.Clock> 객체를 사용하여 스타일, 컨트롤 템플릿 및 데이터 템플릿에 애니메이션을 <xref:System.Windows.Media.Animation.Clock> 제공하지만 <xref:System.Windows.Media.Animation.Storyboard>에서 해당 개체를 만들어야 합니다. 오브젝트와 <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Clock> 오브젝트 간의 관계에 대한 자세한 내용은 [애니메이션 및 타이밍 시스템 개요를](animation-and-timing-system-overview.md)참조하십시오.  
  
 속성에 단일을 <xref:System.Windows.Media.Animation.Clock> 적용하려면 다음 단계를 완료합니다.  
  
1. 개체를 <xref:System.Windows.Media.Animation.AnimationTimeline> 만듭니다.  
  
2. 의 <xref:System.Windows.Media.Animation.AnimationTimeline.CreateClock%2A> <xref:System.Windows.Media.Animation.AnimationTimeline> 메서드를 사용하여 <xref:System.Windows.Media.Animation.AnimationClock>을 만듭니다.  
  
3. 애니메이션할 <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A> 오브젝트의 메서드를 사용하여 지정한 속성에 <xref:System.Windows.Media.Animation.AnimationClock> 적용합니다.  
  
 다음 예제에서는 를 <xref:System.Windows.Media.Animation.AnimationClock> 만들고 두 개의 유사한 속성에 적용하는 방법을 보여 주십습니다.  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 타이밍 트리를 만들고 속성에 애니메이션 효과를 주는 데 사용하려면 다음 단계를 완료합니다.  
  
1. 타이밍 <xref:System.Windows.Media.Animation.ParallelTimeline> <xref:System.Windows.Media.Animation.AnimationTimeline> 트리를 만들기 위해 및 개체를 사용합니다.  
  
2. <xref:System.Windows.Media.Animation.TimelineGroup.CreateClock%2A> 루트를 <xref:System.Windows.Media.Animation.ParallelTimeline> 사용하여 <xref:System.Windows.Media.Animation.ClockGroup>를 만듭니다.  
  
3. <xref:System.Windows.Media.Animation.ClockGroup.Children%2A> 의 를 <xref:System.Windows.Media.Animation.ClockGroup> 반복하고 자식 <xref:System.Windows.Media.Animation.Clock> 객체를 적용합니다. 각 <xref:System.Windows.Media.Animation.AnimationClock> 자식에 <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A> 대해 애니메이션할 개체의 메서드를 사용하여 지정한 속성에 적용합니다. <xref:System.Windows.Media.Animation.AnimationClock>  
  
 클록 개체에 대한 자세한 내용은 [애니메이션 및 타이밍 시스템 개요](animation-and-timing-system-overview.md)를 참조하세요.  
  
## <a name="per-frame-animation-bypass-the-animation-and-timing-system"></a>프레임당 애니메이션: 애니메이션 및 타이밍 시스템 무시  
 이 접근 방법은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애니메이션 시스템을 완전히 무시해야 할 때 사용합니다. 이 방법에 대한 한 가지 시나리오는 애니메이션의 각 단계에서 개체 상호 작용의 마지막 집합에 따라 개체가 다시 계산되어야 하는 물리학 애니메이션입니다.  
  
 스타일, 컨트롤 템플릿 또는 데이터 템플릿 내부에서는 프레임당 애니메이션을 정의할 수 없습니다.  
  
 프레임별로 애니메이션을 지정하려면 애니메이션할 오브젝트가 <xref:System.Windows.Media.CompositionTarget.Rendering> 포함된 개체의 이벤트에 등록합니다. 이 이벤트 처리기 메서드는 프레임마다 한 번씩 호출됩니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]가 시각적 트리의 지속되는 렌더링 데이터를 컴퍼지션 트리로 마샬링할 때마다 이벤트 처리기 메서드가 호출됩니다.  
  
 이벤트 처리기에서 애니메이션 효과에 필요한 계산을 수행하고 이러한 값을 사용하여 애니메이션 효과를 적용하려는 개체의 속성을 설정합니다.  
  
 현재 프레임에 대한 프레젠테이션 시간을 <xref:System.EventArgs> 얻으려면 이 이벤트와 연결된 <xref:System.Windows.Media.RenderingEventArgs>을 로 <xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A> 캐스팅할 수 있으며, 이 로 캐스팅하여 현재 프레임의 렌더링 시간을 가져오는 데 사용할 수 있는 속성을 제공합니다.  
  
 자세한 내용은 <xref:System.Windows.Media.CompositionTarget.Rendering> 페이지를 참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- [애니메이션 개요](animation-overview.md)
- [Storyboard 개요](storyboards-overview.md)
- [애니메이션 및 타이밍 시스템 개요](animation-and-timing-system-overview.md)
- [종속성 속성 개요](../advanced/dependency-properties-overview.md)
