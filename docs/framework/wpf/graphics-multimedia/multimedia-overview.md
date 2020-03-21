---
title: 멀티미디어 개요
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF]
- media [WPF]
ms.assetid: feb25b15-d741-4ac3-818f-1b19f63a3562
ms.openlocfilehash: d4abf4d9fd324ffbf2737dc686c02e50ca1a8a5a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181881"
---
# <a name="multimedia-overview"></a>멀티미디어 개요
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]의 멀티미디어 기능을 통해 오디오 및 비디오를 애플리케이션에 통합하여 사용자 환경을 개선할 수 있습니다. 이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 멀티미디어 기능을 소개합니다.  

<a name="mediaapi"></a>
## <a name="media-api"></a>미디어 API  
 <xref:System.Windows.Controls.MediaElement> 및 <xref:System.Windows.Media.MediaPlayer> 클래스는 오디오 또는 비디오 콘텐츠를 표시하는 데 사용됩니다. 이러한 클래스는 대화형으로 또는 클록을 통해 제어할 수 있습니다. 이러한 클래스는 미디어 재생을 위한 Microsoft Windows 미디어 플레이어 10 컨트롤에서 사용할 수 있습니다. 사용하는 클래스는 시나리오에 따라 달라집니다.  
  
 <xref:System.Windows.Controls.MediaElement><xref:System.Windows.UIElement> 는 [레이아웃에서](../advanced/layout.md) 지원되며 많은 컨트롤의 콘텐츠로 사용할 수 있습니다. 코드 뿐만 아니라 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서도 사용할 수 있습니다. <xref:System.Windows.Media.MediaPlayer>반면에 개체용으로 <xref:System.Windows.Media.Drawing> 설계되었으며 레이아웃 지원이 부족합니다. 를 <xref:System.Windows.Media.MediaPlayer> 사용하여 로드된 미디어는 <xref:System.Windows.Media.VideoDrawing> 를 사용하여 또는 에 <xref:System.Windows.Media.DrawingContext>직접 상호 작용하여 제시할 수 있습니다. <xref:System.Windows.Media.MediaPlayer>XAML에서는 사용할 수 없습니다.  
  
 Drawing 개체 및 그리기 컨텍스트에 대한 자세한 내용은 [Drawing 개체 개요](drawing-objects-overview.md)를 참조하세요.  
  
> [!NOTE]
> 애플리케이션을 사용하여 미디어를 배포하는 경우 미디어 파일을 프로젝트 리소스로 사용할 수 없습니다. 대신 프로젝트 파일에서 미디어 형식을 `Content`로 설정하고 `CopyToOutputDirectory`를 `PreserveNewest` 또는 `Always`로 설정해야 합니다.  
  
<a name="mediaplaybackmodes"></a>
## <a name="media-playback-modes"></a>미디어 재생 모드  
  
> [!NOTE]
> 둘 <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Media.MediaPlayer> 다 비슷한 멤버를 가지고 있습니다. 이 섹션의 링크는 <xref:System.Windows.Controls.MediaElement> 반원들을 참조한다. 구체적으로 언급하지 않는 한, <xref:System.Windows.Controls.MediaElement> 수업에 연결된 구성원도 <xref:System.Windows.Media.MediaPlayer> 수업에서 찾을 수 있다.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 미디어 재생을 이해하려면 미디어를 재생할 수 있는 여러 다른 모드를 이해해야 합니다. 둘 <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Media.MediaPlayer> 다 두 개의 서로 다른 미디어 모드, 독립 모드 및 클럭 모드에서 사용할 수 있습니다. 미디어 모드는 속성에 <xref:System.Windows.Controls.MediaElement.Clock%2A> 의해 결정됩니다. 있는 <xref:System.Windows.Controls.MediaElement.Clock%2A> `null`경우 미디어 개체가 독립 모드에 있습니다. null이 <xref:System.Windows.Controls.MediaElement.Clock%2A> 아닌 경우 미디어 개체가 시계 모드에 있습니다. 기본적으로 미디어 개체는 독립 모드입니다.  
  
### <a name="independent-mode"></a>독립 모드  
 독립 모드에서 미디어 콘텐츠는 미디어 재생을 주도합니다. 독립 모드에서는 다음과 같은 옵션을 사용할 수 있습니다.  
  
- 미디어를 직접 <xref:System.Uri> 지정할 수 있습니다.  
  
- 미디어 재생을 직접 제어할 수 있습니다.  
  
- 미디어 <xref:System.Windows.Controls.MediaElement.Position%2A> 및 <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> 속성을 수정할 수 있습니다.  
  
 미디어는 <xref:System.Windows.Controls.MediaElement> 개체의 <xref:System.Windows.Controls.MediaElement.Source%2A> 속성을 설정하거나 개체의 <xref:System.Windows.Media.MediaPlayer> <xref:System.Windows.Media.MediaPlayer.Open%2A> 메서드를 호출하여 로드됩니다.  
  
 독립 모드에서 미디어 재생을 제어하려면 미디어 개체의 컨트롤 메서드를 사용할 수 있습니다. 사용 가능한 제어 <xref:System.Windows.Controls.MediaElement.Play%2A> <xref:System.Windows.Controls.MediaElement.Pause%2A>방법은 <xref:System.Windows.Controls.MediaElement.Close%2A>" <xref:System.Windows.Controls.MediaElement.Stop%2A>및 의 <xref:System.Windows.Controls.MediaElement>경우 이러한 메서드를 사용하는 대화형 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 컨트롤은 <xref:System.Windows.Controls.MediaState.Manual>을 로 설정된 경우에만 사용할 수 있습니다. 이러한 메서드는 미디어 개체가 클록 모드에 있을 때는 사용할 수 없습니다.  
  
 독립 모드의 예제를 보려면 [MediaElement 제어(재생, 일시 중지, 정지, 볼륨 및 속도)](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)를 참조하세요.  
  
### <a name="clock-mode"></a>클록 모드  
 클럭 모드에서는 <xref:System.Windows.Media.MediaTimeline> 미디어 재생을 구동합니다. 클록 모드에는 다음과 같은 특징이 있습니다.  
  
- 미디어는 을 <xref:System.Uri> 통해 간접적으로 <xref:System.Windows.Media.MediaTimeline>설정됩니다.  
  
- 미디어 재생을 클록으로 제어할 수 있습니다. 미디어 개체의 컨트롤 메서드를 사용할 수 없습니다.  
  
- 미디어는 <xref:System.Windows.Media.MediaTimeline> 개체의 <xref:System.Windows.Media.MediaTimeline.Source%2A> 속성을 설정하고, 타임라인에서 시계를 만들고, 시계를 미디어 개체에 할당하여 로드됩니다. <xref:System.Windows.Media.MediaTimeline> 내부가 <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Controls.MediaElement>을 대상으로 할 때 미디어도 이 방식으로 로드됩니다.  
  
 시계 모드에서 미디어 재생을 <xref:System.Windows.Media.Animation.ClockController> 제어하려면 제어 방법을 사용해야 합니다. A는 <xref:System.Windows.Media.Animation.ClockController> <xref:System.Windows.Media.Animation.ClockController> <xref:System.Windows.Media.MediaClock>의 속성에서 가져옵니다. 시계 모드에서 a <xref:System.Windows.Controls.MediaElement> 또는 <xref:System.Windows.Media.MediaPlayer> 개체의 제어 메서드를 사용하려고 <xref:System.InvalidOperationException> 하면 a가 throw됩니다.  
  
 클록 및 타임라인에 대한 자세한 내용은 [애니메이션 개요](animation-overview.md)를 참조하세요.  
  
 클록 모드 예제를 보려면 [Storyboard를 사용하여 MediaElement 제어](how-to-control-a-mediaelement-by-using-a-storyboard.md)를 참조하세요.  
  
<a name="mediaelement"></a>
## <a name="mediaelement-class"></a>MediaElement 클래스  
 응용 프로그램에 미디어를 추가하는 것은 응용 <xref:System.Windows.Controls.MediaElement> [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 프로그램에 컨트롤을 추가하고 포함하려는 미디어에 제공하는 <xref:System.Uri> 것만큼 간단합니다. 마이크로소프트 윈도 미디어 플레이어에 의해 지원 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]되는 모든 미디어 유형 10에서 지원 됩니다. 다음 예제에서는 <xref:System.Windows.Controls.MediaElement> 에서 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]의 간단한 사용을 보여 주며 있습니다.  
  
 [!code-xaml[MediaElement_snip#SimpleMediaElementUsageWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaElement_snip/CSharp/SimpleUsage.xaml#simplemediaelementusagewholepage)]  
  
 이 샘플에서는 미디어가 로드되는 즉시 자동으로 재생됩니다. 미디어 재생이 완료되면 미디어가 닫히고 모든 미디어 리소스(비디오 메모리 포함)는 해제됩니다. 이것은 <xref:System.Windows.Controls.MediaElement> 개체의 기본 동작이며 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 및 <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> 속성에 의해 제어됩니다.  
  
### <a name="controlling-a-mediaelement"></a>MediaElement 제어  
 및 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> 속성은 각각 의 <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.FrameworkElement.IsLoaded%2A> 동작을 `false`제어합니다. `true` 속성은 <xref:System.Windows.Controls.MediaState> 미디어 재생 동작에 영향을 주도록 설정됩니다. 예를 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 들어 기본값은 <xref:System.Windows.Controls.MediaState.Play> <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> <xref:System.Windows.Controls.MediaState.Close>입니다. 즉, <xref:System.Windows.Controls.MediaElement> 로드되자마자 프리롤이 완성되면 미디어가 재생되기 시작합니다. 재생이 완료되면 미디어가 닫히고 모든 미디어 리소스가 해제됩니다.  
  
 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 및 <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> 속성이 미디어 재생을 제어하는 유일한 방법은 아닙니다. 클럭 모드에서는 클럭이 <xref:System.Windows.Controls.MediaElement> 제어할 수 있고 대화형 제어 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> <xref:System.Windows.Controls.MediaState.Manual>메서드는 을 제어할 수 있습니다. <xref:System.Windows.Controls.MediaElement>다음과 같은 우선 순위를 평가하여 제어를 위한 이 경쟁을 처리합니다.  
  
1. <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>. 미디어가 언로드될 때 적용됩니다. 이렇게 하면 의 <xref:System.Windows.Media.MediaClock> <xref:System.Windows.Controls.MediaElement>가 와 연결되어 있는 경우에도 모든 미디어 리소스가 기본적으로 해제됩니다.  
  
2. <xref:System.Windows.Media.MediaClock>. 미디어에 <xref:System.Windows.Controls.MediaElement.Clock%2A>가 있는 경우 . 미디어가 언로드된 <xref:System.Windows.Media.MediaClock> 경우. <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> <xref:System.Windows.Controls.MediaState.Manual> 클럭 모드는 항상 의 로드된 동작을 재정의합니다. <xref:System.Windows.Controls.MediaElement>  
  
3. <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>. 미디어가 로드될 때 적용됩니다.  
  
4. 대화형 컨트롤 메서드. 장소에 있을 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> <xref:System.Windows.Controls.MediaState.Manual>때입니다. 사용 가능한 제어 <xref:System.Windows.Controls.MediaElement.Play%2A> <xref:System.Windows.Controls.MediaElement.Pause%2A>방법은 <xref:System.Windows.Controls.MediaElement.Close%2A>" <xref:System.Windows.Controls.MediaElement.Stop%2A>및  
  
### <a name="displaying-a-mediaelement"></a>MediaElement 표시  
 를 <xref:System.Windows.Controls.MediaElement> 표시하려면 렌더링할 콘텐츠가 있어야 하며 <xref:System.Windows.FrameworkElement.ActualWidth%2A> <xref:System.Windows.FrameworkElement.ActualHeight%2A> 콘텐츠가 로드될 때까지 해당 및 속성이 0으로 설정됩니다. 오디오 전용 콘텐츠의 경우 이러한 속성은 항상 0입니다. 비디오 콘텐츠의 <xref:System.Windows.Controls.MediaElement.MediaOpened> 경우 이벤트가 발생하면 <xref:System.Windows.FrameworkElement.ActualWidth%2A> <xref:System.Windows.FrameworkElement.ActualHeight%2A> 로드된 미디어의 크기를 보고합니다. 즉, <xref:System.Windows.Controls.MediaElement> 미디어가 로드될 때까지 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] <xref:System.Windows.FrameworkElement.Width%2A> 또는 <xref:System.Windows.FrameworkElement.Height%2A> 속성이 설정되지 않는 한 미디어가 실제 공간을 차지하지 않습니다.  
  
 및 속성을 모두 설정하면 미디어에 제공된 영역을 채우기 위해 미디어가 늘어나게 됩니다. <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> 미디어의 원래 가로 세로 비율을 유지하려면 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> 또는 속성을 설정해야 하지만 둘 다 설정하지는 않습니다. <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 모두 설정하면 미디어가 바람직하지 않을 수 있는 고정 요소 크기로 표시됩니다.  
  
 고정 크기 요소를 유지하지 못하게 하기 위해 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 미디어를 미리 받을 수 있습니다. 이 작업은 을 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 로 <xref:System.Windows.Controls.MediaState.Play> 설정하거나 <xref:System.Windows.Controls.MediaState.Pause>. <xref:System.Windows.Controls.MediaState.Pause> 상태에서 미디어는 프리롤되고 첫 번째 프레임을 표시합니다. <xref:System.Windows.Controls.MediaState.Play> 상태에서 미디어는 프리롤하고 재생하기 시작합니다.  
  
<a name="mediaplayer"></a>
## <a name="mediaplayer-class"></a>MediaPlayer 클래스  
 클래스가 <xref:System.Windows.Controls.MediaElement> 프레임워크 요소인 경우 <xref:System.Windows.Media.MediaPlayer> 클래스는 개체에서 <xref:System.Windows.Media.Drawing> 사용할 수 있도록 설계되었습니다. 그리기 객체는 성능 이점을 얻기 위해 프레임워크 수준 피쳐를 희생할 수 있거나 피쳐가 필요할 <xref:System.Windows.Freezable> 때 사용됩니다. <xref:System.Windows.Media.MediaPlayer>응용 프로그램에서 미디어 콘텐츠를 제공하면서 이러한 기능을 활용할 수 있습니다. 와 <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.Media.MediaPlayer> 같이 독립적 인 또는 클럭 모드에서 사용할 <xref:System.Windows.Controls.MediaElement> 수 있지만 개체의 언로드 및로드 된 상태가 없습니다. 이렇게 하면 의 재생 제어 <xref:System.Windows.Media.MediaPlayer>복잡성이 줄어듭니다.  
  
### <a name="controlling-mediaplayer"></a>MediaPlayer 제어  
 상태 <xref:System.Windows.Media.MediaPlayer> 비수기이기 때문에 미디어 재생을 제어하는 방법은 두 가지뿐입니다.  
  
1. 대화형 컨트롤 메서드. 장소에서 독립적 인 모드`null` <xref:System.Windows.Media.MediaPlayer.Clock%2A> (속성)에있을 때.  
  
2. <xref:System.Windows.Media.MediaClock>. 미디어에 <xref:System.Windows.Media.MediaPlayer.Clock%2A>가 있는 경우 .  
  
### <a name="displaying-a-mediaplayer"></a>MediaPlayer 표시  
 기술적으로 물리적 <xref:System.Windows.Media.MediaPlayer> 표현이 없으므로 표시할 수 없습니다. 그러나, <xref:System.Windows.Media.Drawing> <xref:System.Windows.Media.VideoDrawing> 클래스를 사용하여 미디어를 제시하는 데 사용할 수 있다. 다음 예제에서는 미디어를 표시하는 <xref:System.Windows.Media.VideoDrawing> a의 사용을 보여 줍니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 객체에 대한 자세한 내용은 [도면 객체 개요를](drawing-objects-overview.md) <xref:System.Windows.Media.Drawing> 참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Media.DrawingGroup>
- [레이아웃](../advanced/layout.md)
- [방법 주제](audio-and-video-how-to-topics.md)
