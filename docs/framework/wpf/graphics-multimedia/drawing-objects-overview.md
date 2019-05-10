---
title: Drawing 개체 개요
ms.date: 03/30/2017
helpviewer_keywords:
- ImageDrawing objects [WPF]
- GlyphRunDrawing objects [WPF]
- GeometryDrawing objects [WPF]
- drawings [WPF], about drawings
- Drawing objects [WPF]
- DrawingGroup objects [WPF]
ms.assetid: 9b5ce5c0-e204-4320-a7a8-0b2210d62f88
ms.openlocfilehash: b09fed48912a9175ff34d5be4f783bdb06abf936
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64615430"
---
# <a name="drawing-objects-overview"></a>Drawing 개체 개요
이 항목에서는 소개 <xref:System.Windows.Media.Drawing> 개체 및 도형, 비트맵, 텍스트 및 미디어를 효율적으로 그리는 데 사용 하는 방법에 설명 합니다. 사용 하 여 <xref:System.Windows.Media.Drawing> 클립 아트를 만들 때 개체를 사용 하 여 그리는 <xref:System.Windows.Media.DrawingBrush>를 사용 하 여 또는 <xref:System.Windows.Media.Visual> 개체.  

<a name="whatisadrawingsection"></a>   
## <a name="what-is-a-drawing-object"></a>그리기 개체란?  
 <xref:System.Windows.Media.Drawing> 도형, 비트맵, 비디오 또는 텍스트 줄 같은 보이는 콘텐츠를 설명 하는 개체입니다. 그리기 형식마다 다른 콘텐츠 형식을 설명합니다. 다음은 여러 그리기 개체 형식을 보여 주는 목록입니다.  
  
- <xref:System.Windows.Media.GeometryDrawing> -도형을 그립니다.  
  
- <xref:System.Windows.Media.ImageDrawing> – 이미지를 그립니다.  
  
- <xref:System.Windows.Media.GlyphRunDrawing> – 텍스트를 그립니다.  
  
- <xref:System.Windows.Media.VideoDrawing> – 오디오 또는 비디오 파일을 재생합니다.  
  
- <xref:System.Windows.Media.DrawingGroup> -다른 그리기를 그립니다. 다른 그리기를 단일 합성 그리기로 결합하려면 그리기 그룹을 사용합니다.  
  
 <xref:System.Windows.Media.Drawing> 개체는 다목적입니다. 여러 가지 방법으로 사용할 수는 <xref:System.Windows.Media.Drawing> 개체입니다.  
  
- 사용 하 여 이미지로 표시할 수 있습니다는 <xref:System.Windows.Media.DrawingImage> 및 <xref:System.Windows.Controls.Image> 제어 합니다.  
  
- 와 함께 사용할 수 있습니다는 <xref:System.Windows.Media.DrawingBrush> 와 같은 개체를 그릴 합니다 <xref:System.Windows.Controls.Page.Background%2A> 의 <xref:System.Windows.Controls.Page>합니다.  
  
- 모양을 설명 하는 데 사용할 수 있습니다는 <xref:System.Windows.Media.DrawingVisual>합니다.  
  
- 콘텐츠를 열거 하는 데 사용할 수 있습니다는 <xref:System.Windows.Media.Visual>합니다.  
  
 WPF는 도형, 비트맵, 텍스트 및 미디어를 그릴 수 있는 다른 형식의 개체를 제공합니다. 예를 들어 사용할 수도 있습니다 <xref:System.Windows.Shapes.Shape> 도형을 그릴 개체 및 <xref:System.Windows.Controls.MediaElement> 컨트롤은 응용 프로그램에 비디오를 추가 하는 또 다른 방법은 제공 합니다. 따라서 사용 해야 <xref:System.Windows.Media.Drawing> 개체? 성능 이점을 얻을 수 있는 프레임 워크 수준 기능 저하를 감수 해야 하거나 필요한 경우 <xref:System.Windows.Freezable> 기능입니다. 때문에 <xref:System.Windows.Media.Drawing> 개체에 대 한 지원 부족 [레이아웃](../advanced/layout.md), 입력 및 포커스를 성능을 제공 하므로 사용 하 여 하위 수준 그리기 및 배경, 클립 아트를 설명 하는 데 적합 <xref:System.Windows.Media.Visual> 개체입니다.  
  
 형식 이므로 <xref:System.Windows.Freezable> 개체를 <xref:System.Windows.Media.Drawing> 개체에는 다음을 포함 하는 몇 가지 특별 한 기능을 얻을 수:로 선언할 수 있습니다 [리소스](../advanced/xaml-resources.md)개선 하기 위해 읽기 전용으로, 여러 개체 간에 공유 성능, 복제 하 고 스레드로부터 안전 합니다. 제공 하는 다른 기능에 대 한 자세한 <xref:System.Windows.Freezable> 개체를 참조 합니다 [Freezable 개체 개요](../advanced/freezable-objects-overview.md)합니다.  
  
<a name="drawinggeometriessection"></a>   
## <a name="draw-a-shape"></a>도형 그리기  
 도형 그리기, 사용 하는 <xref:System.Windows.Media.GeometryDrawing>합니다. 기 하 도형 그리기의 <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> 속성을 그릴 도형을 설명 해당 <xref:System.Windows.Media.GeometryDrawing.Brush%2A> 도형의 내부를 그려야 하는 방법, 하는 속성에 설명 합니다 및 해당 <xref:System.Windows.Media.GeometryDrawing.Pen%2A> 속성의 윤곽을 그리는 방법을 설명 합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.GeometryDrawing> 도형을 그릴 수 있습니다. 설명 됩니다는 <xref:System.Windows.Media.GeometryGroup> 두 개의 <xref:System.Windows.Media.EllipseGeometry> 개체입니다. 사용 하 여 도형의 내부가 그려지는 <xref:System.Windows.Media.LinearGradientBrush> 윤곽선을 그릴 때 사용 하 고는 <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>합니다.  
  
 이 예제에서는 다음 항목을 만듭니다 <xref:System.Windows.Media.GeometryDrawing>합니다.  
  
 ![타원 두 개의 GeometryDrawing](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexampleinline)]  
  
 전체 예제를 보려면 [GeometryDrawing 만들기](how-to-create-a-geometrydrawing.md)를 참조하세요.  
  
 다른 <xref:System.Windows.Media.Geometry> 와 같은 클래스 <xref:System.Windows.Media.PathGeometry> 곡선 및 호를 만들어 더 복잡 한 도형을 만드는 데 사용할 수 있습니다. 에 대 한 자세한 내용은 <xref:System.Windows.Media.Geometry> 개체를 참조 합니다 [기 하 도형 개요](geometry-overview.md)합니다.  
  
 사용 하지 않는 도형을 그리는 다른 방법에 대 한 자세한 내용은 <xref:System.Windows.Media.Drawing> 개체를 참조 하세요 [에서 Shape 및 기본 그리기 개요 WPF](shapes-and-basic-drawing-in-wpf-overview.md)합니다.  
  
<a name="drawingimagessection"></a>   
## <a name="draw-an-image"></a>이미지 그리기  
 사용할 이미지를 그릴는 <xref:System.Windows.Media.ImageDrawing>합니다. <xref:System.Windows.Media.ImageDrawing> 개체의 <xref:System.Windows.Media.ImageDrawing.ImageSource%2A> 그릴 이미지를 설명 하는 속성 및 해당 <xref:System.Windows.Media.ImageDrawing.Rect%2A> 속성 이미지를 그릴 영역을 정의 합니다.  
  
 다음 예제에서는 (75,75)에 있는 사각형에 100 x 100픽셀 이미지를 그립니다. 다음 그림에 표시 된 <xref:System.Windows.Media.ImageDrawing> 예제에서 만든 합니다. 경계를 표시 하는 회색 테두리가 추가 되었습니다는 <xref:System.Windows.Media.ImageDrawing>합니다.  
  
 ![100 여 100 ImageDrawing 그립니다 &#40;75, 75&#41;](./media/graphicsmm-simple-imagedrawing-offset.png "graphicsmm_simple_imagedrawing_offset")  
100 x 100 ImageDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawing100by100inline)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawing100by100inline)]  
  
 이미지에 대한 자세한 내용은 [이미징 개요](imaging-overview.md)를 참조하세요.  
  
<a name="playmedia"></a>   
## <a name="play-media-code-only"></a>미디어 재생(코드만 해당)  
  
> [!NOTE]
>  선언할 수는 있지만 <xref:System.Windows.Media.VideoDrawing> 에서 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]를 할 수 있습니다 로드 하 고 코드를 사용 하 여 해당 미디어를 재생 합니다. 비디오를 재생할 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]를 사용 하 여를 <xref:System.Windows.Controls.MediaElement> 대신 합니다.  
  
 오디오 또는 비디오 파일을 재생 하려면 사용 하는 <xref:System.Windows.Media.VideoDrawing> 및 <xref:System.Windows.Media.MediaPlayer>합니다. 미디어를 로드하고 재생하는 방법에는 다음 두 가지가 있습니다. 첫 번째 사용 하는 것을 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing> 고 두 번째 방법은 직접 만들어보십시오 <xref:System.Windows.Media.MediaTimeline> 를 사용 하는 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing>합니다.  
  
> [!NOTE]
>  애플리케이션을 사용하여 미디어를 배포하는 경우 이미지의 경우처럼 미디어 파일을 프로젝트 리소스로 사용할 수 없습니다. 대신 프로젝트 파일에서 미디어 형식을 `Content`로 설정하고 `CopyToOutputDirectory`를 `PreserveNewest` 또는 `Always`로 설정해야 합니다.  
  
 직접 만들지 않고 미디어를 재생 하려면 <xref:System.Windows.Media.MediaTimeline>, 다음 단계를 수행 합니다.  
  
1. <xref:System.Windows.Media.MediaPlayer> 개체를 만듭니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline1)]  
  
2. 사용 된 <xref:System.Windows.Media.MediaPlayer.Open%2A> 미디어 파일을 로드 하는 방법입니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline2)]  
  
3. <xref:System.Windows.Media.VideoDrawing>를 만듭니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline3)]  
  
4. 크기 및 설정 하 여 미디어를 그릴 위치를 지정 합니다 <xref:System.Windows.Media.VideoDrawing.Rect%2A> 의 속성을 <xref:System.Windows.Media.VideoDrawing>입니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline4)]  
  
5. 설정 합니다 <xref:System.Windows.Media.VideoDrawing.Player%2A> 의 속성을 <xref:System.Windows.Media.VideoDrawing> 사용 하 여를 <xref:System.Windows.Media.MediaPlayer> 만든.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline5](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline5)]  
  
6. 사용 하 여는 <xref:System.Windows.Media.MediaPlayer.Play%2A> 메서드의 <xref:System.Windows.Media.MediaPlayer> 미디어 재생을 시작 합니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline6](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline6)]  
  
 다음 예제에서는 한 <xref:System.Windows.Media.VideoDrawing> 및 <xref:System.Windows.Media.MediaPlayer> 비디오 파일을 한 번 재생 하도록 합니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 미디어에 대해 추가 타이밍 제어 권한을 사용 하 여는 <xref:System.Windows.Media.MediaTimeline> 사용 하 여 합니다 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing> 개체입니다. <xref:System.Windows.Media.MediaTimeline> 여 비디오 반복 여부를 지정할 수 있습니다. 사용 하는 <xref:System.Windows.Media.MediaTimeline> 사용 하 여는 <xref:System.Windows.Media.VideoDrawing>, 다음 단계를 수행:  
  
1. 선언 된 <xref:System.Windows.Media.MediaTimeline> 고 해당 타이밍 동작을 설정 합니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline1)]  
  
2. 만들기는 <xref:System.Windows.Media.MediaClock> 에서 <xref:System.Windows.Media.MediaTimeline>합니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline2)]  
  
3. 만들기를 <xref:System.Windows.Media.MediaPlayer> 사용 하는 <xref:System.Windows.Media.MediaClock> 설정 하려면 해당 <xref:System.Windows.Media.MediaPlayer.Clock%2A> 속성.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline3)]  
  
4. 만들기를 <xref:System.Windows.Media.VideoDrawing> 할당 및는 <xref:System.Windows.Media.MediaPlayer> 에 <xref:System.Windows.Media.VideoDrawing.Player%2A> 의 속성은 <xref:System.Windows.Media.VideoDrawing>합니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline4)]  
  
 다음 예제에서는 <xref:System.Windows.Media.MediaTimeline> 사용 하 여를 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing> 비디오를 반복적으로 재생 합니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 이때 사용 하는 경우를 <xref:System.Windows.Media.MediaTimeline>, 대화형를 사용 하 여 <xref:System.Windows.Media.Animation.ClockController> 에서 반환 된를 <xref:System.Windows.Media.Animation.Clock.Controller%2A> 의 속성을 <xref:System.Windows.Media.MediaClock> 의 대화형 메서드 대신 미디어 재생을 제어 하 <xref:System.Windows.Media.MediaPlayer>.  
  
<a name="drawtext"></a>   
## <a name="draw-text"></a>텍스트 그리기  
 사용할 텍스트를 그리려면를 <xref:System.Windows.Media.GlyphRunDrawing> 및 <xref:System.Windows.Media.GlyphRun>합니다. 다음 예제에서는 <xref:System.Windows.Media.GlyphRunDrawing> "Hello World" 텍스트를 그립니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GlyphRunDrawingExample.cs#glyphrundrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GlyphRunExample.xaml#glyphrundrawingexampleinline)]  
  
 <xref:System.Windows.Media.GlyphRun> 고정 형식 문서 프레젠테이션과 인쇄 시나리오를 사용 하 여 사용 하기 위한 것 하위 수준 개체입니다. 화면에 텍스트를 그리는 더 간단한 방법을 사용 하는 것을 <xref:System.Windows.Controls.Label> 또는 <xref:System.Windows.Controls.TextBlock>합니다. 에 대 한 자세한 내용은 <xref:System.Windows.Media.GlyphRun>를 참조 합니다 [GlyphRun 개체 및 Glyphs 요소 소개](../advanced/introduction-to-the-glyphrun-object-and-glyphs-element.md) 개요.  
  
<a name="compositedrawingssection"></a>   
## <a name="composite-drawings"></a>합성 그리기  
 <xref:System.Windows.Media.DrawingGroup> 여러 그리기를 단일 합성 그리기로 결합할 수 있습니다. 사용 하 여는 <xref:System.Windows.Media.DrawingGroup>를 하나의 도형, 이미지 및 텍스트를 결합할 수 있습니다 <xref:System.Windows.Media.Drawing> 개체입니다.  
  
 다음 예에서는 <xref:System.Windows.Media.DrawingGroup> 두 개의 결합 <xref:System.Windows.Media.GeometryDrawing> 개체 및 <xref:System.Windows.Media.ImageDrawing> 개체입니다. 이 예제의 결과는 다음과 같습니다.  
  
 ![여러 있는 DrawingGroup](./media/graphicsmm-simple.jpg "graphicsmm_simple")  
합성 그리기  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 <xref:System.Windows.Media.DrawingGroup> 내용이에 불투명 마스크, 변환, 비트맵 효과 및 기타 작업을 적용할 수 있습니다. <xref:System.Windows.Media.DrawingGroup> 작업이 아래 순서 대로 적용 됩니다: <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A>를 <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>를 <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>를 차례로 <xref:System.Windows.Media.DrawingGroup.Transform%2A>합니다.  
  
 다음 그림에서는 순서는 <xref:System.Windows.Media.DrawingGroup> 작업이 적용 됩니다.  
  
 ![DrawingGroup 작업의 순서](./media/graphcismm-drawinggroup-order.png "graphcismm_drawinggroup_order")  
DrawingGroup 작업의 순서  
  
 다음 표에서 조작 하는 데 사용할 수 속성을 <xref:System.Windows.Media.DrawingGroup> 개체의 콘텐츠입니다.  
  
|속성|설명|그림|  
|--------------|-----------------|------------------|  
|<xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>|선택한 부분의 불투명도 변경 합니다 <xref:System.Windows.Media.DrawingGroup> 내용입니다. 예는 [방법: 그리기의 불투명도 제어](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748242(v=vs.90))입니다.|![불투명도 마스크가 있는 DrawingGroup](./media/graphicsmm-opmask.png "graphicsmm_opmask")|  
|<xref:System.Windows.Media.DrawingGroup.Opacity%2A>|불투명도 균일 하 게 변경 합니다 <xref:System.Windows.Media.DrawingGroup> 내용입니다. 이 속성을 사용 하 여 확인을 <xref:System.Windows.Media.Drawing> 투명 하거나 부분적으로 투명 합니다. 예는 [방법: 그리기에서 불투명 마스크 적용할](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms753195(v=vs.90))합니다.|![여러 불투명도 설정의 DrawingGroup](./media/graphicsmm-opacity.png "graphicsmm_opacity")|  
|<xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>|적용을 <xref:System.Windows.Media.Effects.BitmapEffect> 에 <xref:System.Windows.Media.DrawingGroup> 콘텐츠입니다. 예는 [방법: 그리기에 BitmapEffect 적용](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752341(v=vs.90))합니다.|![BlurBitmapEffect가 적용된 DrawingGroup](./media/graphicsmm-bitmap.png "graphicsmm_bitmap")|  
|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|클립 합니다 <xref:System.Windows.Media.DrawingGroup> 사용을 설명 영역에 콘텐츠를 <xref:System.Windows.Media.Geometry>입니다. 예는 [방법: 그림 자르기](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms743068(v=vs.90)) 합니다.|![정의된 클립 영역이 있는 DrawingGroup](./media/graphicsmm-clipgeom.png "graphicsmm_clipgeom")|  
|<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>|지정된 지침에 따라 디바이스 독립적 픽셀을 디바이스 픽셀에 맞춥니다. 이 속성은 매우 세부적인 그래픽이 낮은 DPI 디스플레이에 선명하게 렌더링되도록 하는 데 유용합니다. 예제를 보려면 [Drawing에 GuidelineSet 적용](how-to-apply-a-guidelineset-to-a-drawing.md)을 참조하세요.|![GuidelineSet이 있는 DrawingGroup과 없는 DrawingGroup](./media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")|  
|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|변환 된 <xref:System.Windows.Media.DrawingGroup> 내용입니다. 예는 [방법: 그리기에 변환 적용](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms742304(v=vs.90))합니다.|![회전된 DrawingGroup](./media/graphicsmm-rotate.png "graphicsmm_rotate")|  
  
<a name="usingimagedrawing"></a>   
## <a name="display-a-drawing-as-an-image"></a>그리기를 이미지로 표시  
 표시할를 <xref:System.Windows.Media.Drawing> 사용 하 여는 <xref:System.Windows.Controls.Image> 컨트롤을 사용 하 여를 <xref:System.Windows.Media.DrawingImage> 으로 <xref:System.Windows.Controls.Image> 컨트롤의 <xref:System.Windows.Controls.Image.Source%2A> 설정 합니다 <xref:System.Windows.Media.DrawingImage> 개체의 <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> 속성을 표시 하려는 그리기.  
  
 다음 예제에서는 <xref:System.Windows.Media.DrawingImage> 와 <xref:System.Windows.Controls.Image> 표시할 컨트롤을 <xref:System.Windows.Media.GeometryDrawing>입니다. 이 예제의 결과는 다음과 같습니다.  
  
 ![타원 두 개의 GeometryDrawing](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
<a name="renderingwithdrawingbrushsection"></a>   
## <a name="paint-an-object-with-a-drawing"></a>Drawing으로 개체 그리기  
 <xref:System.Windows.Media.DrawingBrush> 그리기 개체를 사용 하 여 영역을 그리는 브러시의 형식입니다. 그리기 기능으로 거의 모든 그래픽 개체를 그리는 데 사용할 수 있습니다. <xref:System.Windows.Media.Drawing> 의 속성을 <xref:System.Windows.Media.DrawingBrush> 설명 해당 <xref:System.Windows.Media.DrawingBrush.Drawing%2A>합니다. 렌더링 하는 <xref:System.Windows.Media.Drawing> 사용 하 여는 <xref:System.Windows.Media.DrawingBrush>, 브러시를 사용 하 여 브러시에 추가 <xref:System.Windows.Media.Drawing> 속성을 사용 하 여 그래픽을 그리는 브러시를 패널 또는 컨트롤 같은 개체입니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.DrawingBrush> 그릴 합니다 <xref:System.Windows.Shapes.Shape.Fill%2A> 의 <xref:System.Windows.Shapes.Rectangle> 로 만든 패턴을 사용 하 여를 <xref:System.Windows.Media.GeometryDrawing>입니다. 이 예제의 결과는 다음과 같습니다.  
  
 ![DrawingBrush 바둑판식](./media/graphicsmm-drawingbrush-geometrydrawing.png "graphicsmm_drawingbrush_geometrydrawing")  
DrawingBrush에 GeometryDrawing 사용  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 <xref:System.Windows.Media.DrawingBrush> 클래스는 여러 가지를 확장 하 고 해당 콘텐츠를 바둑판식으로 배열에 대 한 옵션을 제공 합니다. 에 대 한 자세한 내용은 <xref:System.Windows.Media.DrawingBrush>를 참조 합니다 [이미지, 그림 및 시각적 표시로 그리기](painting-with-images-drawings-and-visuals.md) 개요.  
  
<a name="renderingwithvisualsection"></a>   
## <a name="render-a-drawing-with-a-visual"></a>시각적 표시로 그림 렌더링  
 <xref:System.Windows.Media.DrawingVisual> 그림을 렌더링 하도록 디자인 된 시각적 개체의 형식입니다. 시각적 계층에서 직접 작업하는 방식은 고도로 사용자 지정된 그래픽 환경을 구축하려는 개발자를 위한 옵션이지만 이 개요에서는 설명되지 않습니다. 자세한 내용은 [DrawingVisual 개체 사용](using-drawingvisual-objects.md)을 참조하세요.  
  
<a name="drawingcontextobjects"></a>   
## <a name="drawingcontext-objects"></a>DrawingContext 개체  
 <xref:System.Windows.Media.DrawingContext> 클래스를 사용 하면를 채울 수는 <xref:System.Windows.Media.Visual> 또는 <xref:System.Windows.Media.Drawing> 시각적 콘텐츠를 사용 하 여 합니다. 이러한 많은 하위 수준 그래픽 개체 사용을 <xref:System.Windows.Media.DrawingContext> 그래픽 콘텐츠 매우 효율적으로 설명 하므로 합니다.  
  
 하지만 합니다 <xref:System.Windows.Media.DrawingContext> 그리기 메서드 그리기 메서드와 유사는 <xref:System.Drawing.Graphics?displayProperty=nameWithType> 실제로 매우 다른 지는 형식입니다. <xref:System.Windows.Media.DrawingContext> 유지 모드 그래픽 시스템을 사용 하 여 사용 된 <xref:System.Drawing.Graphics?displayProperty=nameWithType> 은 직접 실행 모드 그래픽 시스템 형식이 사용 되었습니다. <xref:System.Windows.Media.DrawingContext> 개체의 그리기 명령을 사용하는 경우 실제로 나중에 그래픽 시스템에서 사용될 렌더링 명령 집합을 저장하게 되며 (정확한 스토리지 메커니즘은 <xref:System.Windows.Media.DrawingContext>를 제공하는 개체의 형식에 따라 다름) 실시간으로 화면에 그리지 않습니다. Windows Presentation Foundation (WPF) 그래픽 시스템의 작동 방식에 대 한 자세한 내용은 참조는 [WPF 그래픽 렌더링 개요](wpf-graphics-rendering-overview.md)합니다.  
  
 절대 직접 인스턴스화하지를 <xref:System.Windows.Media.DrawingContext>; 얻을 수 있습니다, 있지만 특정 메서드에서 그리기 컨텍스트 등 <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=nameWithType> 고 <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=nameWithType>입니다.  
  
<a name="enumeratevisualcontents"></a>   
## <a name="enumerate-the-contents-of-a-visual"></a>시각적 개체의 콘텐츠 열거  
 기타 다른 용도 외에도 <xref:System.Windows.Media.Drawing> 개체는 또한 개체 모델의 콘텐츠를 열거 하는 것에 대 한 제공을 <xref:System.Windows.Media.Visual>입니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> 검색 하는 메서드를 <xref:System.Windows.Media.DrawingGroup> 값을 <xref:System.Windows.Media.Visual> 열거 합니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Media.Drawing>
- <xref:System.Windows.Media.DrawingGroup>
- [2차원 그래픽 및 이미징](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [이미지, 그림 및 시각적 표시로 그리기](painting-with-images-drawings-and-visuals.md)
- [Geometry 개요](geometry-overview.md)
- [WPF에서 Shape 및 기본 그리기 개요](shapes-and-basic-drawing-in-wpf-overview.md)
- [WPF 그래픽 렌더링 개요](wpf-graphics-rendering-overview.md)
- [Freezable 개체 개요](../advanced/freezable-objects-overview.md)
- [방법 항목](drawings-how-to-topics.md)
