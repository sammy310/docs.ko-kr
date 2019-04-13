---
title: 멀티미디어 개요
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF]
- media [WPF]
ms.assetid: feb25b15-d741-4ac3-818f-1b19f63a3562
ms.openlocfilehash: 66cb28fce9485898711b9029baf8a17dd9b2c011
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59340492"
---
# <a name="multimedia-overview"></a>멀티미디어 개요
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]의 멀티미디어 기능을 통해 오디오 및 비디오를 응용 프로그램에 통합하여 사용자 환경을 개선할 수 있습니다. 이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 멀티미디어 기능을 소개합니다.  

<a name="mediaapi"></a>   
## <a name="media-api"></a>미디어 API  
 합니다 <xref:System.Windows.Controls.MediaElement> 고 <xref:System.Windows.Media.MediaPlayer> 클래스는 오디오 또는 비디오 콘텐츠를 제공 하는 데 사용 됩니다. 이러한 클래스는 대화형으로 또는 클록을 통해 제어할 수 있습니다. 이러한 클래스는 미디어 재생을 위한 [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 10 컨트롤에서 사용할 수 있습니다. 사용하는 클래스는 시나리오에 따라 달라집니다.  
  
 <xref:System.Windows.Controls.MediaElement> <xref:System.Windows.UIElement> 에서 지는 [레이아웃](../advanced/layout.md) 많은 컨트롤의 내용으로 사용 될 수 있습니다. 코드 뿐만 아니라 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서도 사용할 수 있습니다. <xref:System.Windows.Media.MediaPlayer>를 위한 다른 한편으로 <xref:System.Windows.Media.Drawing> 개체 및 레이아웃 지원 하지 않습니다. 사용 하 여 로드 된 미디어는 <xref:System.Windows.Media.MediaPlayer> 를 사용 하 여 표시할 수만 <xref:System.Windows.Media.VideoDrawing> 또는 직접 상호 작용 하 여를 <xref:System.Windows.Media.DrawingContext>입니다. <xref:System.Windows.Media.MediaPlayer> XAML에서 사용할 수 없습니다.  
  
 Drawing 개체 및 그리기 컨텍스트에 대한 자세한 내용은 [Drawing 개체 개요](drawing-objects-overview.md)를 참조하세요.  
  
> [!NOTE]
>  애플리케이션을 사용하여 미디어를 배포하는 경우 미디어 파일을 프로젝트 리소스로 사용할 수 없습니다. 대신 프로젝트 파일에서 미디어 형식을 `Content`로 설정하고 `CopyToOutputDirectory`를 `PreserveNewest` 또는 `Always`로 설정해야 합니다.  
  
<a name="mediaplaybackmodes"></a>   
## <a name="media-playback-modes"></a>미디어 재생 모드  
  
> [!NOTE]
>  둘 다 <xref:System.Windows.Controls.MediaElement> 및 <xref:System.Windows.Media.MediaPlayer> 는 유사한 멤버가 있습니다. 이 섹션의 링크를 참조 합니다 <xref:System.Windows.Controls.MediaElement> 클래스 멤버입니다. 구체적으로 언급 하지 않는 한 멤버 연결에 <xref:System.Windows.Controls.MediaElement> 클래스에서 찾을 수 있습니다는 <xref:System.Windows.Media.MediaPlayer> 클래스입니다.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 미디어 재생을 이해하려면 미디어를 재생할 수 있는 여러 다른 모드를 이해해야 합니다. 둘 다 <xref:System.Windows.Controls.MediaElement> 고 <xref:System.Windows.Media.MediaPlayer> 두 가지 다른 미디어 모드, 독립 모드와 클록 모드에서 사용할 수 있습니다. 미디어 모드에 의해 결정 됩니다는 <xref:System.Windows.Controls.MediaElement.Clock%2A> 속성입니다. 때 <xref:System.Windows.Controls.MediaElement.Clock%2A> 는 `null`, 미디어 개체는 독립 모드입니다. 경우는 <xref:System.Windows.Controls.MediaElement.Clock%2A> 는 null이 아닌 미디어 개체가 클록 모드에서입니다. 기본적으로 미디어 개체는 독립 모드입니다.  
  
### <a name="independent-mode"></a>독립 모드  
 독립 모드에서 미디어 콘텐츠는 미디어 재생을 주도합니다. 독립 모드에서는 다음과 같은 옵션을 사용할 수 있습니다.  
  
-   미디어의 <xref:System.Uri> 직접 지정할 수 있습니다.  
  
-   미디어 재생을 직접 제어할 수 있습니다.  
  
-   미디어 <xref:System.Windows.Controls.MediaElement.Position%2A> 고 <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> 속성을 수정할 수 있습니다.  
  
 설정 하거나 미디어를 로드 합니다 <xref:System.Windows.Controls.MediaElement> 개체의 <xref:System.Windows.Controls.MediaElement.Source%2A> 속성 또는 전화 800-659-3579 합니다 <xref:System.Windows.Media.MediaPlayer> 개체의 <xref:System.Windows.Media.MediaPlayer.Open%2A> 메서드.  
  
 독립 모드에서 미디어 재생을 제어하려면 미디어 개체의 컨트롤 메서드를 사용할 수 있습니다. 사용할 수 있는 컨트롤 메서드는 <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>를 <xref:System.Windows.Controls.MediaElement.Close%2A>, 및 <xref:System.Windows.Controls.MediaElement.Stop%2A>합니다. 에 대 한 <xref:System.Windows.Controls.MediaElement>, 이러한 메서드를 사용 하 여 대화형 컨트롤 에서만 사용 가능 시기를 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 로 설정 된 <xref:System.Windows.Controls.MediaState.Manual>합니다. 이러한 메서드는 미디어 개체가 클록 모드에 있을 때는 사용할 수 없습니다.  
  
 독립 모드의 예제를 보려면 [MediaElement 제어(재생, 일시 중지, 정지, 볼륨 및 속도)](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)를 참조하세요.  
  
### <a name="clock-mode"></a>클록 모드  
 클록 모드에서는 <xref:System.Windows.Media.MediaTimeline> 이 미디어를 재생 합니다. 클록 모드에는 다음과 같은 특징이 있습니다.  
  
-   미디어의 <xref:System.Uri> 를 통해 간접적으로 설정 된 <xref:System.Windows.Media.MediaTimeline>합니다.  
  
-   미디어 재생을 클록으로 제어할 수 있습니다. 미디어 개체의 컨트롤 메서드를 사용할 수 없습니다.  
  
-   미디어를 설정 하 여 로드를 <xref:System.Windows.Media.MediaTimeline> 개체의 <xref:System.Windows.Media.MediaTimeline.Source%2A> 속성, 타임 라인에서 클록을 만들고 클록을 미디어 개체에 할당 합니다. 미디어 이러한 방식으로 로드 됩니다 때를 <xref:System.Windows.Media.MediaTimeline> 내부를 <xref:System.Windows.Media.Animation.Storyboard> 대상은 <xref:System.Windows.Controls.MediaElement>합니다.  
  
 클록 모드에서 미디어 재생을 제어 하는 <xref:System.Windows.Media.Animation.ClockController> 제어 메서드를 사용 해야 합니다. <xref:System.Windows.Media.Animation.ClockController> 에서 가져온 합니다 <xref:System.Windows.Media.Animation.ClockController> 의 속성을 <xref:System.Windows.Media.MediaClock>입니다. 컨트롤 메서드를 사용 하려는 경우는 <xref:System.Windows.Controls.MediaElement> 또는 <xref:System.Windows.Media.MediaPlayer> 클록 모드에서 개체를 <xref:System.InvalidOperationException> throw 됩니다.  
  
 클록 및 타임라인에 대한 자세한 내용은 [애니메이션 개요](animation-overview.md)를 참조하세요.  
  
 클록 모드 예제를 보려면 [Storyboard를 사용하여 MediaElement 제어](how-to-control-a-mediaelement-by-using-a-storyboard.md)를 참조하세요.  
  
<a name="mediaelement"></a>   
## <a name="mediaelement-class"></a>MediaElement 클래스  
 응용 프로그램에 미디어를 추가 하는 것은 추가 하기만 <xref:System.Windows.Controls.MediaElement> 컨트롤을 합니다 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 응용 프로그램의 제공을 <xref:System.Uri> 포함 하려는 미디어에. [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 10에서 지원하는 모든 미디어 형식이 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 지원됩니다. 다음 예제에서는 사용 하는 간단한 합니다 <xref:System.Windows.Controls.MediaElement> 에서 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]합니다.  
  
 [!code-xaml[MediaElement_snip#SimpleMediaElementUsageWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaElement_snip/CSharp/SimpleUsage.xaml#simplemediaelementusagewholepage)]  
  
 이 샘플에서는 미디어가 로드되는 즉시 자동으로 재생됩니다. 미디어 재생이 완료되면 미디어가 닫히고 모든 미디어 리소스(비디오 메모리 포함)는 해제됩니다. 기본 동작은이 <xref:System.Windows.Controls.MediaElement> 개체를 통해 제어 됩니다 합니다 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 및 <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> 속성입니다.  
  
### <a name="controlling-a-mediaelement"></a>MediaElement 제어  
 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 및 <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> 속성의 동작을 제어 합니다 <xref:System.Windows.Controls.MediaElement> 때 <xref:System.Windows.FrameworkElement.IsLoaded%2A> 됩니다 `true` 또는 `false`각각. <xref:System.Windows.Controls.MediaState> 속성이 미디어 재생 동작에 영향을 주도록 설정 됩니다. 예를 들어, 기본 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 됩니다 <xref:System.Windows.Controls.MediaState.Play> 기본 <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> 는 <xref:System.Windows.Controls.MediaState.Close>합니다. 즉, 즉시는 <xref:System.Windows.Controls.MediaElement> 로드 하 고 미리 받기가 완료 되 면 미디어 재생 되기 시작 합니다. 재생이 완료되면 미디어가 닫히고 모든 미디어 리소스가 해제됩니다.  
  
 합니다 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 고 <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> 속성은 미디어 재생을 제어 하는 유일한 방법은 없습니다. 클록 모드에서 클록 제어할 수는 <xref:System.Windows.Controls.MediaElement> 대화형 컨트롤 메서드를 제어할 때 및 합니다 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 는 <xref:System.Windows.Controls.MediaState.Manual>합니다. <xref:System.Windows.Controls.MediaElement> 다음과 같은 우선 순위를 평가 하 여 컨트롤에 대 한이 경합을 처리 합니다.  
  
1. <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>. 미디어가 언로드될 때 적용됩니다. 이렇게 하면 기본적으로 모든 미디어 리소스가 해제 되는 경우에을 <xref:System.Windows.Media.MediaClock> 연관 된는 <xref:System.Windows.Controls.MediaElement>합니다.  
  
2. <xref:System.Windows.Media.MediaClock>. 미디어에 때 적용에서 된 <xref:System.Windows.Controls.MediaElement.Clock%2A>합니다. 미디어가 언로드될 경우는 <xref:System.Windows.Media.MediaClock> 으로 적용 합니다 <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> 는 <xref:System.Windows.Controls.MediaState.Manual>합니다. 클록 모드의 로드 동작을 항상 재정의 <xref:System.Windows.Controls.MediaElement>합니다.  
  
3. <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>. 미디어가 로드될 때 적용됩니다.  
  
4. 대화형 컨트롤 메서드. 경우를 배치할 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 는 <xref:System.Windows.Controls.MediaState.Manual>합니다. 사용할 수 있는 컨트롤 메서드는 <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>를 <xref:System.Windows.Controls.MediaElement.Close%2A>, 및 <xref:System.Windows.Controls.MediaElement.Stop%2A>합니다.  
  
### <a name="displaying-a-mediaelement"></a>MediaElement 표시  
 표시 하는 <xref:System.Windows.Controls.MediaElement> 렌더링할 콘텐츠가 있어야 하 고 더 해당 <xref:System.Windows.FrameworkElement.ActualWidth%2A> 및 <xref:System.Windows.FrameworkElement.ActualHeight%2A> 속성 콘텐츠가 로드 될 때까지 0으로 설정 합니다. 오디오 전용 콘텐츠의 경우 이러한 속성은 항상 0입니다. 비디오 콘텐츠의 경우에 대 한는 <xref:System.Windows.Controls.MediaElement.MediaOpened> 이벤트가 발생 합니다 <xref:System.Windows.FrameworkElement.ActualWidth%2A> 및 <xref:System.Windows.FrameworkElement.ActualHeight%2A> 가 로드 된 미디어의 크기를 보고 합니다. 즉, 미디어가 로드 될 때까지 합니다 <xref:System.Windows.Controls.MediaElement> 의 실제 공간을 차지 하지 것입니다는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 하지 않는 한를 <xref:System.Windows.FrameworkElement.Width%2A> 또는 <xref:System.Windows.FrameworkElement.Height%2A> 속성이 설정 됩니다.  
  
 모두 설정 합니다 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 제공 하는 영역을 채우도록 확장 미디어 하면는 <xref:System.Windows.Controls.MediaElement>합니다. 하거나 미디어의 원래 가로 세로 비율을 유지 하는 <xref:System.Windows.FrameworkElement.Width%2A> 또는 <xref:System.Windows.FrameworkElement.Height%2A> 속성 하나만 설정 해야 합니다. 모두 설정 합니다 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성에는 미디어에는 바람직하지 않이 고정된 요소 크기로 제공 하면 합니다.  
  
 고정 크기 요소를 유지하지 못하게 하기 위해 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 미디어를 미리 받을 수 있습니다. 이렇게 설정 하면 됩니다는 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 하나로 <xref:System.Windows.Controls.MediaState.Play> 또는 <xref:System.Windows.Controls.MediaState.Pause>. 에 <xref:System.Windows.Controls.MediaState.Pause> 상태에서 미디어를 미리 받고 첫 번째 프레임에 표시 됩니다. 에 <xref:System.Windows.Controls.MediaState.Play> 상태에서 미디어는 미리 받은 후 재생을 시작 합니다.  
  
<a name="mediaplayer"></a>   
## <a name="mediaplayer-class"></a>MediaPlayer 클래스  
 여기서는 <xref:System.Windows.Controls.MediaElement> 클래스는 프레임 워크 요소를 <xref:System.Windows.Media.MediaPlayer> 클래스에서 사용 하도록 합니다. <xref:System.Windows.Media.Drawing> 개체입니다. 성능 이점을 얻을 수 있는 프레임 워크 수준 기능 저하를 감수 해야 하거나 필요한 경우 drawing 개체가 사용 됩니다 <xref:System.Windows.Freezable> 기능입니다. <xref:System.Windows.Media.MediaPlayer> 응용 프로그램에서 미디어 콘텐츠를 제공 하면서 이러한 기능을 활용할 수 있습니다. 와 같은 <xref:System.Windows.Controls.MediaElement>, <xref:System.Windows.Media.MediaPlayer> 관계 없이 사용할 수 있습니다 또는 모드 않습니다 하지 클록가 <xref:System.Windows.Controls.MediaElement> 개체의 언로드 및 상태를 로드 합니다. 재생 컨트롤 복잡성이 감소는 <xref:System.Windows.Media.MediaPlayer>합니다.  
  
### <a name="controlling-mediaplayer"></a>MediaPlayer 제어  
 때문에 <xref:System.Windows.Media.MediaPlayer> 는 상태 비저장만 두 가지 미디어 재생을 제어할 수 있습니다.  
  
1. 대화형 컨트롤 메서드. 독립 모드에서 작업 하는 경우 준비에서 (`null`<xref:System.Windows.Media.MediaPlayer.Clock%2A> 속성).  
  
2. <xref:System.Windows.Media.MediaClock>. 미디어에 때 적용에서 된 <xref:System.Windows.Media.MediaPlayer.Clock%2A>합니다.  
  
### <a name="displaying-a-mediaplayer"></a>MediaPlayer 표시  
 기술적으로 <xref:System.Windows.Media.MediaPlayer> 물리적 표현이 없기 때문에 표시할 수 없습니다. 그러나에서 미디어를 제공 하 사용할 수는 <xref:System.Windows.Media.Drawing> 를 사용 하 여를 <xref:System.Windows.Media.VideoDrawing> 클래스입니다. 다음 예제에서는 사용을 <xref:System.Windows.Media.VideoDrawing> 미디어를 표시 합니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 참조 된 [Drawing 개체 개요](drawing-objects-overview.md) 에 대 한 자세한 내용은 <xref:System.Windows.Media.Drawing> 개체입니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Media.DrawingGroup>
- [레이아웃](../advanced/layout.md)
- [방법 항목](audio-and-video-how-to-topics.md)
