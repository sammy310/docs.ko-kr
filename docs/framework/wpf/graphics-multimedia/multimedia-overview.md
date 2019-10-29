---
title: 멀티미디어 개요
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF]
- media [WPF]
ms.assetid: feb25b15-d741-4ac3-818f-1b19f63a3562
ms.openlocfilehash: 42d0d388e859b556d23b7fc81931cd61470ba541
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039798"
---
# <a name="multimedia-overview"></a>멀티미디어 개요
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]의 멀티미디어 기능을 통해 오디오 및 비디오를 애플리케이션에 통합하여 사용자 환경을 개선할 수 있습니다. 이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 멀티미디어 기능을 소개합니다.  

<a name="mediaapi"></a>   
## <a name="media-api"></a>미디어 API  
 <xref:System.Windows.Controls.MediaElement> 및 <xref:System.Windows.Media.MediaPlayer> 클래스는 오디오 또는 비디오 콘텐츠를 표시 하는 데 사용 됩니다. 이러한 클래스는 대화형으로 또는 클록을 통해 제어할 수 있습니다. 이러한 클래스는 미디어 재생을 위해 Microsoft Windows Media Player 10 컨트롤에서 사용할 수 있습니다. 사용하는 클래스는 시나리오에 따라 달라집니다.  
  
 <xref:System.Windows.Controls.MediaElement>는 [레이아웃](../advanced/layout.md) 에서 지원 되며 많은 컨트롤의 콘텐츠로 사용 될 수 있는 <xref:System.Windows.UIElement>입니다. 코드 뿐만 아니라 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서도 사용할 수 있습니다. 반면 <xref:System.Windows.Media.MediaPlayer>은 <xref:System.Windows.Media.Drawing> 개체를 위해 디자인 되었으며 레이아웃 지원이 부족 합니다. <xref:System.Windows.Media.MediaPlayer>를 사용 하 여 로드 된 미디어는 <xref:System.Windows.Media.VideoDrawing> 사용 하거나 <xref:System.Windows.Media.DrawingContext>와 직접 상호 작용 하 여 제공할 수 있습니다. <xref:System.Windows.Media.MediaPlayer>는 XAML에서 사용할 수 없습니다.  
  
 Drawing 개체 및 그리기 컨텍스트에 대한 자세한 내용은 [Drawing 개체 개요](drawing-objects-overview.md)를 참조하세요.  
  
> [!NOTE]
> 애플리케이션을 사용하여 미디어를 배포하는 경우 미디어 파일을 프로젝트 리소스로 사용할 수 없습니다. 대신 프로젝트 파일에서 미디어 형식을 `Content`로 설정하고 `CopyToOutputDirectory`를 `PreserveNewest` 또는 `Always`로 설정해야 합니다.  
  
<a name="mediaplaybackmodes"></a>   
## <a name="media-playback-modes"></a>미디어 재생 모드  
  
> [!NOTE]
> <xref:System.Windows.Controls.MediaElement>와 <xref:System.Windows.Media.MediaPlayer>는 모두 유사한 멤버를 가집니다. 이 섹션의 링크는 <xref:System.Windows.Controls.MediaElement> 클래스 멤버를 참조 합니다. 구체적으로 언급 하지 않는 한 <xref:System.Windows.Controls.MediaElement> 클래스의에 연결 된 멤버는 <xref:System.Windows.Media.MediaPlayer> 클래스 에서도 찾을 수 있습니다.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 미디어 재생을 이해하려면 미디어를 재생할 수 있는 여러 다른 모드를 이해해야 합니다. 두 개의 다른 미디어 모드, 즉 독립 모드와 클록 모드에서 <xref:System.Windows.Controls.MediaElement>와 <xref:System.Windows.Media.MediaPlayer>를 모두 사용할 수 있습니다. 미디어 모드는 <xref:System.Windows.Controls.MediaElement.Clock%2A> 속성에 의해 결정 됩니다. <xref:System.Windows.Controls.MediaElement.Clock%2A> `null`된 경우 미디어 개체는 독립 모드입니다. <xref:System.Windows.Controls.MediaElement.Clock%2A> null이 아닌 경우 미디어 개체는 클록 모드입니다. 기본적으로 미디어 개체는 독립 모드입니다.  
  
### <a name="independent-mode"></a>독립 모드  
 독립 모드에서 미디어 콘텐츠는 미디어 재생을 주도합니다. 독립 모드에서는 다음과 같은 옵션을 사용할 수 있습니다.  
  
- 미디어의 <xref:System.Uri> 직접 지정할 수 있습니다.  
  
- 미디어 재생을 직접 제어할 수 있습니다.  
  
- 미디어의 <xref:System.Windows.Controls.MediaElement.Position%2A> 및 <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> 속성을 수정할 수 있습니다.  
  
 미디어는 <xref:System.Windows.Controls.MediaElement> 개체의 <xref:System.Windows.Controls.MediaElement.Source%2A> 속성을 설정 하거나 <xref:System.Windows.Media.MediaPlayer> 개체의 <xref:System.Windows.Media.MediaPlayer.Open%2A> 메서드를 호출 하 여 로드 됩니다.  
  
 독립 모드에서 미디어 재생을 제어하려면 미디어 개체의 컨트롤 메서드를 사용할 수 있습니다. 사용할 수 있는 컨트롤 메서드는 <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A>및 <xref:System.Windows.Controls.MediaElement.Stop%2A>입니다. <xref:System.Windows.Controls.MediaElement>의 경우 이러한 메서드를 사용 하는 대화형 컨트롤은 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> <xref:System.Windows.Controls.MediaState.Manual>으로 설정 된 경우에만 사용할 수 있습니다. 이러한 메서드는 미디어 개체가 클록 모드에 있을 때는 사용할 수 없습니다.  
  
 독립 모드의 예제를 보려면 [MediaElement 제어(재생, 일시 중지, 정지, 볼륨 및 속도)](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)를 참조하세요.  
  
### <a name="clock-mode"></a>클록 모드  
 클록 모드에서 <xref:System.Windows.Media.MediaTimeline>는 미디어 재생을 구동 합니다. 클록 모드에는 다음과 같은 특징이 있습니다.  
  
- 미디어의 <xref:System.Uri> <xref:System.Windows.Media.MediaTimeline>를 통해 간접적으로 설정 됩니다.  
  
- 미디어 재생을 클록으로 제어할 수 있습니다. 미디어 개체의 컨트롤 메서드를 사용할 수 없습니다.  
  
- 미디어는 <xref:System.Windows.Media.MediaTimeline> 개체의 <xref:System.Windows.Media.MediaTimeline.Source%2A> 속성을 설정 하 고, 타임 라인에서 시계를 만들고, 미디어 개체에 시계를 할당 하 여 로드 됩니다. <xref:System.Windows.Media.Animation.Storyboard> 내의 <xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Controls.MediaElement>를 대상으로 하는 경우에도 미디어가 로드 됩니다.  
  
 클록 모드에서 미디어 재생을 제어 하려면 <xref:System.Windows.Media.Animation.ClockController> 컨트롤 메서드를 사용 해야 합니다. <xref:System.Windows.Media.Animation.ClockController>는 <xref:System.Windows.Media.MediaClock>의 <xref:System.Windows.Media.Animation.ClockController> 속성에서 가져옵니다. 클록 모드에서 <xref:System.Windows.Controls.MediaElement> 또는 <xref:System.Windows.Media.MediaPlayer> 개체의 control 메서드를 사용 하려고 하면 <xref:System.InvalidOperationException>이 throw 됩니다.  
  
 클록 및 타임라인에 대한 자세한 내용은 [애니메이션 개요](animation-overview.md)를 참조하세요.  
  
 클록 모드 예제를 보려면 [Storyboard를 사용하여 MediaElement 제어](how-to-control-a-mediaelement-by-using-a-storyboard.md)를 참조하세요.  
  
<a name="mediaelement"></a>   
## <a name="mediaelement-class"></a>MediaElement 클래스  
 응용 프로그램에 미디어를 추가 하는 것은 응용 프로그램의 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]에 <xref:System.Windows.Controls.MediaElement> 컨트롤을 추가 하 고 포함 하려는 미디어에 <xref:System.Uri>를 제공 하는 것 만큼 간단 합니다. Microsoft Windows Media Player 10에서 지 원하는 모든 미디어 유형은 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 지원 됩니다. 다음 예에서는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 <xref:System.Windows.Controls.MediaElement>를 간단히 사용 하는 방법을 보여 줍니다.  
  
 [!code-xaml[MediaElement_snip#SimpleMediaElementUsageWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaElement_snip/CSharp/SimpleUsage.xaml#simplemediaelementusagewholepage)]  
  
 이 샘플에서는 미디어가 로드되는 즉시 자동으로 재생됩니다. 미디어 재생이 완료되면 미디어가 닫히고 모든 미디어 리소스(비디오 메모리 포함)는 해제됩니다. <xref:System.Windows.Controls.MediaElement> 개체의 기본 동작이 며 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 및 <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> 속성에 의해 제어 됩니다.  
  
### <a name="controlling-a-mediaelement"></a>MediaElement 제어  
 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 및 <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> 속성은 각각 <xref:System.Windows.FrameworkElement.IsLoaded%2A> `true` 또는 `false`될 때 <xref:System.Windows.Controls.MediaElement>의 동작을 제어 합니다. 미디어 재생 동작에 영향을 주는 속성 <xref:System.Windows.Controls.MediaState> 설정 됩니다. 예를 들어 기본 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> <xref:System.Windows.Controls.MediaState.Play> 되 고 기본 <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> <xref:System.Windows.Controls.MediaState.Close>됩니다. 즉, <xref:System.Windows.Controls.MediaElement> 로드 되 고 미리 받기가 완료 되 면 미디어가 재생 되기 시작 합니다. 재생이 완료되면 미디어가 닫히고 모든 미디어 리소스가 해제됩니다.  
  
 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 및 <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> 속성은 미디어 재생을 제어 하는 유일한 방법이 아닙니다. 클록 모드에서 clock은 <xref:System.Windows.Controls.MediaElement>를 제어할 수 있으며 대화형 컨트롤 메서드는 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> <xref:System.Windows.Controls.MediaState.Manual>때 제어 합니다. <xref:System.Windows.Controls.MediaElement>는 다음과 같은 우선 순위를 평가 하 여 제어에 대 한 경쟁을 처리 합니다.  
  
1. <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> 미디어가 언로드될 때 적용됩니다. 이렇게 하면 <xref:System.Windows.Media.MediaClock> <xref:System.Windows.Controls.MediaElement>에 연결 된 경우에도 모든 미디어 리소스가 기본적으로 해제 됩니다.  
  
2. <xref:System.Windows.Media.MediaClock> 미디어에 <xref:System.Windows.Controls.MediaElement.Clock%2A>있을 때 발생 합니다. 미디어를 언로드하면 <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> <xref:System.Windows.Controls.MediaState.Manual>되는 동안 <xref:System.Windows.Media.MediaClock> 적용 됩니다. 클록 모드는 항상 <xref:System.Windows.Controls.MediaElement>의 로드 된 동작을 재정의 합니다.  
  
3. <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 미디어가 로드될 때 적용됩니다.  
  
4. 대화형 컨트롤 메서드. <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>이 <xref:System.Windows.Controls.MediaState.Manual>경우 적용 됩니다. 사용할 수 있는 컨트롤 메서드는 <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A>및 <xref:System.Windows.Controls.MediaElement.Stop%2A>입니다.  
  
### <a name="displaying-a-mediaelement"></a>MediaElement 표시  
 <xref:System.Windows.Controls.MediaElement> 표시 하려면 렌더링할 콘텐츠가 있어야 하 고, 콘텐츠가 로드 될 때까지 <xref:System.Windows.FrameworkElement.ActualWidth%2A> 및 <xref:System.Windows.FrameworkElement.ActualHeight%2A> 속성이 0으로 설정 됩니다. 오디오 전용 콘텐츠의 경우 이러한 속성은 항상 0입니다. 비디오 콘텐츠의 경우 <xref:System.Windows.Controls.MediaElement.MediaOpened> 이벤트가 발생 하면 <xref:System.Windows.FrameworkElement.ActualWidth%2A> <xref:System.Windows.FrameworkElement.ActualHeight%2A> 로드 된 미디어의 크기를 보고 합니다. 즉, <xref:System.Windows.FrameworkElement.Width%2A> 또는 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 설정 하지 않는 한, 미디어를 로드할 때까지 <xref:System.Windows.Controls.MediaElement>는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]의 실제 공간을 차지 하지 않습니다.  
  
 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 둘 다 설정 하면 미디어를 늘려 <xref:System.Windows.Controls.MediaElement>에 제공 된 영역을 채웁니다. 미디어의 원래 가로 세로 비율을 유지 하려면 <xref:System.Windows.FrameworkElement.Width%2A> 또는 <xref:System.Windows.FrameworkElement.Height%2A> 속성 중 하나만 설정 해야 합니다. <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 둘 다 설정 하면 미디어가 고정 요소 크기에 표시 되므로 바람직하지 않을 수 있습니다.  
  
 고정 크기 요소를 유지하지 못하게 하기 위해 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 미디어를 미리 받을 수 있습니다. 이 작업을 수행 하려면 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> <xref:System.Windows.Controls.MediaState.Play> 또는 <xref:System.Windows.Controls.MediaState.Pause>로 설정 합니다. <xref:System.Windows.Controls.MediaState.Pause> 상태에서 미디어는 미리 받고 첫 번째 프레임을 표시 합니다. <xref:System.Windows.Controls.MediaState.Play> 상태에서 미디어는 미리 받고 재생을 시작 합니다.  
  
<a name="mediaplayer"></a>   
## <a name="mediaplayer-class"></a>MediaPlayer 클래스  
 <xref:System.Windows.Controls.MediaElement> 클래스가 프레임 워크 요소인 경우 <xref:System.Windows.Media.MediaPlayer> 클래스는 <xref:System.Windows.Media.Drawing> 개체에서 사용 하도록 설계 되었습니다. Drawing 개체는 성능 이점을 얻기 위해 프레임 워크 수준 기능을 저하 시킬 수 있거나 <xref:System.Windows.Freezable> 기능이 필요할 때 사용 됩니다. <xref:System.Windows.Media.MediaPlayer>를 사용 하면 응용 프로그램에서 미디어 콘텐츠를 제공 하는 동시에 이러한 기능을 활용할 수 있습니다. <xref:System.Windows.Controls.MediaElement>와 마찬가지로 <xref:System.Windows.Media.MediaPlayer> 독립 모드나 클록 모드에서 사용할 수 있지만 <xref:System.Windows.Controls.MediaElement> 개체의 언로드 및 로드 됨 상태는 없습니다. 이렇게 하면 <xref:System.Windows.Media.MediaPlayer>의 재생 제어 복잡성이 줄어듭니다.  
  
### <a name="controlling-mediaplayer"></a>MediaPlayer 제어  
 <xref:System.Windows.Media.MediaPlayer>은 상태 비저장 이므로 미디어 재생을 제어 하는 방법은 두 가지 뿐입니다.  
  
1. 대화형 컨트롤 메서드. 독립 모드 (`null`<xref:System.Windows.Media.MediaPlayer.Clock%2A> 속성)를 사용할 때 적용 됩니다.  
  
2. <xref:System.Windows.Media.MediaClock> 미디어에 <xref:System.Windows.Media.MediaPlayer.Clock%2A>있을 때 발생 합니다.  
  
### <a name="displaying-a-mediaplayer"></a>MediaPlayer 표시  
 기술적으로는 물리적 표현이 없기 때문에 <xref:System.Windows.Media.MediaPlayer>를 표시할 수 없습니다. 그러나 <xref:System.Windows.Media.VideoDrawing> 클래스를 사용 하 여 <xref:System.Windows.Media.Drawing>에 미디어를 표시 하는 데 사용할 수 있습니다. 다음 예에서는 <xref:System.Windows.Media.VideoDrawing>를 사용 하 여 미디어를 표시 하는 방법을 보여 줍니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 <xref:System.Windows.Media.Drawing> 개체에 대 한 자세한 내용은 [Drawing 개체 개요](drawing-objects-overview.md) 를 참조 하세요.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Media.DrawingGroup>
- [레이아웃](../advanced/layout.md)
- [방법 항목](audio-and-video-how-to-topics.md)
