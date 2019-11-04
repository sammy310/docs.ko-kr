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
ms.openlocfilehash: d4527c331308ff6cd517705212e09428216d2378
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459738"
---
# <a name="drawing-objects-overview"></a>Drawing 개체 개요
이 항목에서는 <xref:System.Windows.Media.Drawing> 개체를 소개 하 고이를 사용 하 여 도형, 비트맵, 텍스트 및 미디어를 효율적으로 그리는 방법을 설명 합니다. <xref:System.Windows.Media.Drawing> 개체를 사용 하 여 클립 아트를 만들거나 <xref:System.Windows.Media.DrawingBrush>를 그리거나 <xref:System.Windows.Media.Visual> 개체를 사용할 수 있습니다.  

<a name="whatisadrawingsection"></a>   
## <a name="what-is-a-drawing-object"></a>그리기 개체란?  
 <xref:System.Windows.Media.Drawing> 개체는 모양, 비트맵, 비디오 또는 텍스트 줄과 같은 표시 되는 콘텐츠를 설명 합니다. 그리기 형식마다 다른 콘텐츠 형식을 설명합니다. 다음은 여러 그리기 개체 형식을 보여 주는 목록입니다.  
  
- <xref:System.Windows.Media.GeometryDrawing> – 도형을 그립니다.  
  
- <xref:System.Windows.Media.ImageDrawing> – 이미지를 그립니다.  
  
- <xref:System.Windows.Media.GlyphRunDrawing> – 텍스트를 그립니다.  
  
- <xref:System.Windows.Media.VideoDrawing> – 오디오 또는 비디오 파일을 재생 합니다.  
  
- <xref:System.Windows.Media.DrawingGroup> – 다른 그리기를 그립니다. 다른 그리기를 단일 합성 그리기로 결합하려면 그리기 그룹을 사용합니다.  
  
 <xref:System.Windows.Media.Drawing> 개체는 다양 합니다. 여러 가지 방법으로 <xref:System.Windows.Media.Drawing> 개체를 사용할 수 있습니다.  
  
- <xref:System.Windows.Media.DrawingImage> 및 <xref:System.Windows.Controls.Image> 컨트롤을 사용 하 여 이미지를 이미지로 표시할 수 있습니다.  
  
- <xref:System.Windows.Media.DrawingBrush>와 함께 사용 하 여 <xref:System.Windows.Controls.Page><xref:System.Windows.Controls.Page.Background%2A>와 같은 개체를 그릴 수 있습니다.  
  
- 이를 사용 하 여 <xref:System.Windows.Media.DrawingVisual>모양을 설명할 수 있습니다.  
  
- 이를 사용 하 여 <xref:System.Windows.Media.Visual>의 내용을 열거할 수 있습니다.  
  
 WPF는 도형, 비트맵, 텍스트 및 미디어를 그릴 수 있는 다른 형식의 개체를 제공합니다. 예를 들어 <xref:System.Windows.Shapes.Shape> 개체를 사용 하 여 도형을 그릴 수 있으며, <xref:System.Windows.Controls.MediaElement> 컨트롤은 응용 프로그램에 비디오를 추가 하는 또 다른 방법을 제공 합니다. <xref:System.Windows.Media.Drawing> 개체를 사용 해야 하는 경우는 언제 인가요? 성능 이점을 얻기 위해 프레임 워크 수준 기능을 저하 시킬 수 있는 경우 또는 <xref:System.Windows.Freezable> 기능이 필요한 경우 <xref:System.Windows.Media.Drawing> 개체는 [레이아웃](../advanced/layout.md), 입력 및 포커스에 대 한 지원을 제공 하지 않기 때문에 배경, 클립 아트 및 <xref:System.Windows.Media.Visual> 개체를 사용 하는 하위 수준 그리기를 설명 하는 데 적합 한 성능상의 이점을 제공 합니다.  
  
 개체는 형식 <xref:System.Windows.Freezable> 개체 이기 때문에 <xref:System.Windows.Media.Drawing> 개체는 다음을 포함 하는 몇 가지 특수 기능을 제공 합니다 .이는 [리소스로](../../../desktop-wpf/fundamentals/xaml-resources-define.md)선언 하 고, 여러 개체 간에 공유 하 고, 읽기 전용으로 설정 하 여 성능을 향상 시키고 복제할 수 있습니다. 스레드로부터 안전 합니다. 제공 하는 다른 기능에 대 한 자세한 <xref:System.Windows.Freezable> 개체를 참조 합니다 [Freezable 개체 개요](../advanced/freezable-objects-overview.md)합니다.  
  
<a name="drawinggeometriessection"></a>   
## <a name="draw-a-shape"></a>도형 그리기  
 셰이프를 그리려면 <xref:System.Windows.Media.GeometryDrawing>를 사용 합니다. Geometry drawing의 <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> 속성은 그릴 셰이프를 설명 하 고, 해당 <xref:System.Windows.Media.GeometryDrawing.Brush%2A> 속성은 도형의 내부를 칠하는 방법을 설명 하며, 해당 <xref:System.Windows.Media.GeometryDrawing.Pen%2A> 속성은 윤곽선을 그리는 방법을 설명 합니다.  
  
 다음 예에서는 <xref:System.Windows.Media.GeometryDrawing>를 사용 하 여 도형을 그립니다. 셰이프는 <xref:System.Windows.Media.GeometryGroup>와 <xref:System.Windows.Media.EllipseGeometry> 개체 두 개로 설명 됩니다. 도형의 내부가 <xref:System.Windows.Media.LinearGradientBrush>으로 그려지고 <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>를 사용 하 여 윤곽선을 그립니다.  
  
 이 예에서는 다음과 같은 <xref:System.Windows.Media.GeometryDrawing>를 만듭니다.  
  
 ![타원 두 개의 GeometryDrawing](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexampleinline)]  
  
 전체 예제를 보려면 [GeometryDrawing 만들기](how-to-create-a-geometrydrawing.md)를 참조하세요.  
  
 <xref:System.Windows.Media.PathGeometry>와 같은 다른 <xref:System.Windows.Media.Geometry> 클래스를 사용 하 여 곡선 및 원호를 만들어 보다 복잡 한 도형을 만들 수 있습니다. <xref:System.Windows.Media.Geometry> 개체에 대 한 자세한 내용은 [Geometry 개요](geometry-overview.md)를 참조 하세요.  
  
 <xref:System.Windows.Media.Drawing> 개체를 사용 하지 않는 도형을 그리는 다른 방법에 대 한 자세한 내용은 [WPF의 도형 및 기본 그리기 개요](shapes-and-basic-drawing-in-wpf-overview.md)를 참조 하세요.  
  
<a name="drawingimagessection"></a>   
## <a name="draw-an-image"></a>이미지 그리기  
 이미지를 그리려면 <xref:System.Windows.Media.ImageDrawing>를 사용 합니다. <xref:System.Windows.Media.ImageDrawing> 개체의 <xref:System.Windows.Media.ImageDrawing.ImageSource%2A> 속성은 그릴 이미지를 설명 하 고 해당 <xref:System.Windows.Media.ImageDrawing.Rect%2A> 속성은 이미지가 그려지는 영역을 정의 합니다.  
  
 다음 예제에서는 (75,75)에 있는 사각형에 100 x 100픽셀 이미지를 그립니다. 다음 그림에서는 예제에서 만든 <xref:System.Windows.Media.ImageDrawing> 보여 줍니다. <xref:System.Windows.Media.ImageDrawing>범위를 표시 하는 회색 테두리가 추가 되었습니다.  
  
 ![&#40;75,75&#41;에 그려진 100 x 100 ImageDrawing](./media/graphicsmm-simple-imagedrawing-offset.png "graphicsmm_simple_imagedrawing_offset")  
100 x 100 ImageDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawing100by100inline)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawing100by100inline)]  
  
 이미지에 대한 자세한 내용은 [이미징 개요](imaging-overview.md)를 참조하세요.  
  
<a name="playmedia"></a>   
## <a name="play-media-code-only"></a>미디어 재생(코드만 해당)  
  
> [!NOTE]
> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 <xref:System.Windows.Media.VideoDrawing>을 선언할 수 있지만 코드를 사용 하 여 미디어를 로드 하 고 재생할 수 있습니다. [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]비디오를 재생 하려면 대신 <xref:System.Windows.Controls.MediaElement>를 사용 합니다.  
  
 오디오 또는 비디오 파일을 재생 하려면 <xref:System.Windows.Media.VideoDrawing>와 <xref:System.Windows.Media.MediaPlayer>를 사용 합니다. 미디어를 로드하고 재생하는 방법에는 다음 두 가지가 있습니다. 첫 번째 방법은 <xref:System.Windows.Media.MediaPlayer>와 <xref:System.Windows.Media.VideoDrawing>를 직접 사용 하는 것이 고, 두 번째 방법은 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing>에서 사용할 고유한 <xref:System.Windows.Media.MediaTimeline>를 만드는 것입니다.  
  
> [!NOTE]
> 애플리케이션을 사용하여 미디어를 배포하는 경우 이미지의 경우처럼 미디어 파일을 프로젝트 리소스로 사용할 수 없습니다. 대신 프로젝트 파일에서 미디어 형식을 `Content`로 설정하고 `CopyToOutputDirectory`를 `PreserveNewest` 또는 `Always`로 설정해야 합니다.  
  
 사용자 고유의 <xref:System.Windows.Media.MediaTimeline>를 만들지 않고 미디어를 재생 하려면 다음 단계를 수행 합니다.  
  
1. <xref:System.Windows.Media.MediaPlayer> 개체를 만듭니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline1)]  
  
2. <xref:System.Windows.Media.MediaPlayer.Open%2A> 메서드를 사용 하 여 미디어 파일을 로드 합니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline2)]  
  
3. <xref:System.Windows.Media.VideoDrawing>를 만듭니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline3)]  
  
4. <xref:System.Windows.Media.VideoDrawing>의 <xref:System.Windows.Media.VideoDrawing.Rect%2A> 속성을 설정 하 여 미디어를 그릴 크기와 위치를 지정 합니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline4)]  
  
5. 사용자가 만든 <xref:System.Windows.Media.MediaPlayer> <xref:System.Windows.Media.VideoDrawing>의 <xref:System.Windows.Media.VideoDrawing.Player%2A> 속성을 설정 합니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline5](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline5)]  
  
6. <xref:System.Windows.Media.MediaPlayer>의 <xref:System.Windows.Media.MediaPlayer.Play%2A> 메서드를 사용 하 여 미디어 재생을 시작할 수 있습니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline6](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline6)]  
  
 다음 예제에서는 <xref:System.Windows.Media.VideoDrawing> 및 <xref:System.Windows.Media.MediaPlayer>를 사용 하 여 한 번 비디오 파일을 재생 합니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 미디어에 대 한 추가 타이밍 제어를 얻으려면 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing> 개체에 <xref:System.Windows.Media.MediaTimeline>를 사용 합니다. <xref:System.Windows.Media.MediaTimeline>를 사용 하 여 비디오를 반복할지 여부를 지정할 수 있습니다. <xref:System.Windows.Media.VideoDrawing>에서 <xref:System.Windows.Media.MediaTimeline>를 사용 하려면 다음 단계를 수행 합니다.  
  
1. <xref:System.Windows.Media.MediaTimeline>를 선언 하 고 해당 타이밍 동작을 설정 합니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline1)]  
  
2. <xref:System.Windows.Media.MediaTimeline>에서 <xref:System.Windows.Media.MediaClock>를 만듭니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline2)]  
  
3. <xref:System.Windows.Media.MediaPlayer>를 만들고 <xref:System.Windows.Media.MediaClock>를 사용 하 여 <xref:System.Windows.Media.MediaPlayer.Clock%2A> 속성을 설정 합니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline3)]  
  
4. <xref:System.Windows.Media.VideoDrawing>를 만들고 <xref:System.Windows.Media.MediaPlayer>를 <xref:System.Windows.Media.VideoDrawing>의 <xref:System.Windows.Media.VideoDrawing.Player%2A> 속성에 할당 합니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline4)]  
  
 다음 예제에서는 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing>를 사용 하 여 <xref:System.Windows.Media.MediaTimeline>를 사용 하 여 비디오를 반복 해 서 재생 합니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 <xref:System.Windows.Media.MediaTimeline>사용 하는 경우 <xref:System.Windows.Media.MediaClock>의 <xref:System.Windows.Media.Animation.Clock.Controller%2A> 속성에서 반환 되는 대화형 <xref:System.Windows.Media.Animation.ClockController>를 사용 하 여 <xref:System.Windows.Media.MediaPlayer>의 대화형 방법 대신 미디어 재생을 제어 합니다.  
  
<a name="drawtext"></a>   
## <a name="draw-text"></a>텍스트 그리기  
 텍스트를 그리려면 <xref:System.Windows.Media.GlyphRunDrawing>와 <xref:System.Windows.Media.GlyphRun>를 사용 합니다. 다음 예에서는 <xref:System.Windows.Media.GlyphRunDrawing>를 사용 하 여 "Hello World" 텍스트를 그립니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GlyphRunDrawingExample.cs#glyphrundrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GlyphRunExample.xaml#glyphrundrawingexampleinline)]  
  
 <xref:System.Windows.Media.GlyphRun>은 고정 형식 문서 프레젠테이션 및 인쇄 시나리오에서 사용 하기 위한 하위 수준 개체입니다. 텍스트를 화면에 그리는 더 간단한 방법은 <xref:System.Windows.Controls.Label> 또는 <xref:System.Windows.Controls.TextBlock>를 사용 하는 것입니다. <xref:System.Windows.Media.GlyphRun>에 대 한 자세한 내용은 [GlyphRun 개체 및 Glyphs 요소 개요 소개](../advanced/introduction-to-the-glyphrun-object-and-glyphs-element.md) 를 참조 하세요.  
  
<a name="compositedrawingssection"></a>   
## <a name="composite-drawings"></a>합성 그리기  
 <xref:System.Windows.Media.DrawingGroup>를 사용 하 여 여러 그리기를 단일 복합 그리기로 결합할 수 있습니다. <xref:System.Windows.Media.DrawingGroup>를 사용 하 여 도형, 이미지 및 텍스트를 단일 <xref:System.Windows.Media.Drawing> 개체로 결합할 수 있습니다.  
  
 다음 예에서는 <xref:System.Windows.Media.DrawingGroup>를 사용 하 여 두 <xref:System.Windows.Media.GeometryDrawing> 개체와 <xref:System.Windows.Media.ImageDrawing> 개체를 결합 합니다. 이 예제의 결과는 다음과 같습니다.  
  
 ![여러 개의 그리기가 있는 DrawingGroup](./media/graphicsmm-simple.jpg "graphicsmm_simple")  
합성 그리기  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 또한 <xref:System.Windows.Media.DrawingGroup>를 사용 하면 불투명 마스크, 변환, 비트맵 효과 및 기타 작업을 해당 내용에 적용할 수 있습니다. <xref:System.Windows.Media.DrawingGroup> 작업은 <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>, 다음 순서로 적용 됩니다.  
  
 다음 그림에서는 <xref:System.Windows.Media.DrawingGroup> 작업이 적용 되는 순서를 보여 줍니다.  
  
 ![DrawingGroup 작업의 순서](./media/graphcismm-drawinggroup-order.png "graphcismm_drawinggroup_order")  
DrawingGroup 작업의 순서  
  
 다음 표에서는 <xref:System.Windows.Media.DrawingGroup> 개체의 콘텐츠를 조작 하는 데 사용할 수 있는 속성에 대해 설명 합니다.  
  
|속성|설명|그림|  
|--------------|-----------------|------------------|  
|<xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>|<xref:System.Windows.Media.DrawingGroup> 내용에서 선택 된 부분의 불투명도를 변경 합니다. 예제를 보려면 [방법: 그리기의 불투명도 제어](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748242(v=vs.90))를 참조하세요.|![불투명 마스크를 사용 하는 DrawingGroup](./media/graphicsmm-opmask.png "graphicsmm_opmask")|  
|<xref:System.Windows.Media.DrawingGroup.Opacity%2A>|<xref:System.Windows.Media.DrawingGroup> 내용의 불투명도를 균일 하 게 변경 합니다. <xref:System.Windows.Media.Drawing> 투명 하거나 부분적으로 투명 하 게 하려면이 속성을 사용 합니다. 예제를 보려면 [방법: 도면에 불투명 마스크 적용](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms753195(v=vs.90))을 참조하세요.|![다른 불투명도 설정을 사용 하는 DrawingGroups](./media/graphicsmm-opacity.png "graphicsmm_opacity")|  
|<xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>|<xref:System.Windows.Media.DrawingGroup> 내용에 <xref:System.Windows.Media.Effects.BitmapEffect>을 적용 합니다. 예제를 보려면 [방법: 그리기에 BitmapEffect 적용](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752341(v=vs.90))을 참조하세요.|![DrawingGroup BlurBitmapEffect](./media/graphicsmm-bitmap.png "graphicsmm_bitmap")|  
|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|<xref:System.Windows.Media.Geometry>를 사용 하 여 설명 하는 영역에 <xref:System.Windows.Media.DrawingGroup> 콘텐츠를 클리핑 합니다. 예제를 보려면 [방법: 그림 자르기](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms743068(v=vs.90))를 참조하세요.|![정의 된 클립 영역이 있는 DrawingGroup](./media/graphicsmm-clipgeom.png "graphicsmm_clipgeom")|  
|<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>|지정된 지침에 따라 디바이스 독립적 픽셀을 디바이스 픽셀에 맞춥니다. 이 속성은 매우 세부적인 그래픽이 낮은 DPI 디스플레이에 선명하게 렌더링되도록 하는 데 유용합니다. 예제를 보려면 [Drawing에 GuidelineSet 적용](how-to-apply-a-guidelineset-to-a-drawing.md)을 참조하세요.|![가이드 Lineset를 사용 하거나 사용 하지 않는 DrawingGroup](./media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")|  
|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|<xref:System.Windows.Media.DrawingGroup> 내용을 변환 합니다. 예제를 보려면 [방법: 그리기에 변환 적용](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms742304(v=vs.90))을 참조하세요.|![회전 된 DrawingGroup](./media/graphicsmm-rotate.png "graphicsmm_rotate")|  
  
<a name="usingimagedrawing"></a>   
## <a name="display-a-drawing-as-an-image"></a>그리기를 이미지로 표시  
 <xref:System.Windows.Controls.Image> 컨트롤을 사용 하 여 <xref:System.Windows.Media.Drawing>를 표시 하려면 <xref:System.Windows.Controls.Image> 컨트롤의 <xref:System.Windows.Controls.Image.Source%2A> <xref:System.Windows.Media.DrawingImage> 사용 하 고 <xref:System.Windows.Media.DrawingImage> 개체의 <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> 속성을 표시 하려는 그리기로 설정 합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.DrawingImage>와 <xref:System.Windows.Controls.Image> 컨트롤을 사용 하 여 <xref:System.Windows.Media.GeometryDrawing>를 표시 합니다. 이 예제의 결과는 다음과 같습니다.  
  
 ![타원 두 개의 GeometryDrawing](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
<a name="renderingwithdrawingbrushsection"></a>   
## <a name="paint-an-object-with-a-drawing"></a>Drawing으로 개체 그리기  
 <xref:System.Windows.Media.DrawingBrush>는 그리기 개체를 사용 하 여 영역을 그리는 브러시의 유형입니다. 그리기 기능으로 거의 모든 그래픽 개체를 그리는 데 사용할 수 있습니다. <xref:System.Windows.Media.DrawingBrush>의 <xref:System.Windows.Media.Drawing> 속성은 해당 <xref:System.Windows.Media.DrawingBrush.Drawing%2A>을 설명 합니다. <xref:System.Windows.Media.DrawingBrush>를 사용 하 여 <xref:System.Windows.Media.Drawing> 렌더링 하려면 브러시의 <xref:System.Windows.Media.Drawing> 속성을 사용 하 여 브러시에 브러시를 추가 하 고 브러시를 사용 하 여 컨트롤 또는 패널과 같은 그래픽 개체를 그립니다.  
  
 다음 예에서는 <xref:System.Windows.Media.DrawingBrush>를 사용 하 여 <xref:System.Windows.Media.GeometryDrawing>에서 생성 된 패턴을 사용 하 여 <xref:System.Windows.Shapes.Rectangle> <xref:System.Windows.Shapes.Shape.Fill%2A>를 그립니다. 이 예제의 결과는 다음과 같습니다.  
  
 ![바둑판식으로 배열된 DrawingBrush](./media/graphicsmm-drawingbrush-geometrydrawing.png "graphicsmm_drawingbrush_geometrydrawing")  
DrawingBrush에 GeometryDrawing 사용  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 <xref:System.Windows.Media.DrawingBrush> 클래스는 콘텐츠를 확장 하 고 바둑판식으로 배열 하는 다양 한 옵션을 제공 합니다. <xref:System.Windows.Media.DrawingBrush>에 대 한 자세한 내용은 [이미지, 그림 및 시각적 개체](painting-with-images-drawings-and-visuals.md) 에 대 한 그리기 개요를 참조 하세요.  
  
<a name="renderingwithvisualsection"></a>   
## <a name="render-a-drawing-with-a-visual"></a>시각적 표시로 그림 렌더링  
 <xref:System.Windows.Media.DrawingVisual>는 그리기를 렌더링 하도록 디자인 된 시각적 개체의 형식입니다. 시각적 계층에서 직접 작업하는 방식은 고도로 사용자 지정된 그래픽 환경을 구축하려는 개발자를 위한 옵션이지만 이 개요에서는 설명되지 않습니다. 자세한 내용은 [DrawingVisual 개체 사용](using-drawingvisual-objects.md)을 참조하세요.  
  
<a name="drawingcontextobjects"></a>   
## <a name="drawingcontext-objects"></a>DrawingContext 개체  
 <xref:System.Windows.Media.DrawingContext> 클래스를 사용 하 여 <xref:System.Windows.Media.Visual> 또는 <xref:System.Windows.Media.Drawing>를 시각적 콘텐츠로 채울 수 있습니다. 이러한 하위 수준 그래픽 개체는 대부분 그래픽 콘텐츠를 매우 효율적으로 설명 하기 때문에 <xref:System.Windows.Media.DrawingContext>를 사용 합니다.  
  
 <xref:System.Windows.Media.DrawingContext> 그리기 메서드는 <xref:System.Drawing.Graphics?displayProperty=nameWithType> 형식의 그리기 메서드와 비슷하게 보이지만 실제로는 매우 다릅니다. <xref:System.Windows.Media.DrawingContext>는 유지 모드 그래픽 시스템에서 사용 되는 반면, <xref:System.Drawing.Graphics?displayProperty=nameWithType> 유형은 유지 모드 그래픽 시스템에서 사용 됩니다. <xref:System.Windows.Media.DrawingContext> 개체의 그리기 명령을 사용하는 경우 실제로 나중에 그래픽 시스템에서 사용될 렌더링 명령 집합을 저장하게 되며 (정확한 스토리지 메커니즘은 <xref:System.Windows.Media.DrawingContext>를 제공하는 개체의 형식에 따라 다름) 실시간으로 화면에 그리지 않습니다. WPF (Windows Presentation Foundation) 그래픽 시스템의 작동 방식에 대 한 자세한 내용은 [Wpf 그래픽 렌더링 개요](wpf-graphics-rendering-overview.md)를 참조 하세요.  
  
 <xref:System.Windows.Media.DrawingContext>를 직접 인스턴스화하지 않습니다. 그러나 <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=nameWithType> 및 <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=nameWithType>같은 특정 메서드에서 그리기 컨텍스트를 가져올 수 있습니다.  
  
<a name="enumeratevisualcontents"></a>   
## <a name="enumerate-the-contents-of-a-visual"></a>시각적 개체의 콘텐츠 열거  
 <xref:System.Windows.Media.Drawing> 개체는 다른 용도 외에도 <xref:System.Windows.Media.Visual>콘텐츠를 열거 하기 위한 개체 모델을 제공 합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> 메서드를 사용 하 여 <xref:System.Windows.Media.Visual>의 <xref:System.Windows.Media.DrawingGroup> 값을 검색 하 고이를 열거 합니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Media.Drawing>
- <xref:System.Windows.Media.DrawingGroup>
- [2차원 그래픽 및 이미징](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [이미지, 그림 및 시각적 표시로 그리기](painting-with-images-drawings-and-visuals.md)
- [Geometry 개요](geometry-overview.md)
- [WPF에서 Shape 및 기본 그리기 개요](shapes-and-basic-drawing-in-wpf-overview.md)
- [WPF 그래픽 렌더링 개요](wpf-graphics-rendering-overview.md)
- [Freezable 개체 개요](../advanced/freezable-objects-overview.md)
- [방법 항목](drawings-how-to-topics.md)
