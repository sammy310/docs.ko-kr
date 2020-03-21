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
ms.openlocfilehash: 7a5d00eb2fb7c66e5e42d40893806e13717e1d2e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186530"
---
# <a name="drawing-objects-overview"></a>Drawing 개체 개요
이 항목에서는 <xref:System.Windows.Media.Drawing> 개체를 소개하고 이를 사용하여 셰이프, 비트맵, 텍스트 및 미디어를 효율적으로 그리는 방법을 설명합니다. 클립 <xref:System.Windows.Media.Drawing> 아트를 만들 거나, 을 <xref:System.Windows.Media.DrawingBrush>사용하여 <xref:System.Windows.Media.Visual> 페인트하거나, 객체를 사용할 때 오브젝트를 사용합니다.  

<a name="whatisadrawingsection"></a>
## <a name="what-is-a-drawing-object"></a>그리기 개체란?  
 개체는 <xref:System.Windows.Media.Drawing> 셰이프, 비트맵, 비디오 또는 텍스트 줄과 같은 표시되는 콘텐츠를 설명합니다. 그리기 형식마다 다른 콘텐츠 형식을 설명합니다. 다음은 여러 그리기 개체 형식을 보여 주는 목록입니다.  
  
- <xref:System.Windows.Media.GeometryDrawing>- 모양을 그립니다.  
  
- <xref:System.Windows.Media.ImageDrawing>– 이미지를 그립니다.  
  
- <xref:System.Windows.Media.GlyphRunDrawing>– 텍스트를 그립니다.  
  
- <xref:System.Windows.Media.VideoDrawing>- 오디오 또는 비디오 파일을 재생합니다.  
  
- <xref:System.Windows.Media.DrawingGroup>– 다른 도면을 그립니다. 다른 그리기를 단일 합성 그리기로 결합하려면 그리기 그룹을 사용합니다.  
  
 <xref:System.Windows.Media.Drawing>개체는 다재다능합니다. 개체를 사용할 수 있는 <xref:System.Windows.Media.Drawing> 방법에는 여러 가지가 있습니다.  
  
- 컨트롤과 <xref:System.Windows.Media.DrawingImage> <xref:System.Windows.Controls.Image> 컨트롤을 사용하여 이미지로 표시할 수 있습니다.  
  
- a와 <xref:System.Windows.Media.DrawingBrush> 함께 사용하여 <xref:System.Windows.Controls.Page.Background%2A> <xref:System.Windows.Controls.Page>의 와 같은 객체를 페인트할 수 있습니다.  
  
- 의 모양을 설명하는 데 사용할 <xref:System.Windows.Media.DrawingVisual>수 있습니다.  
  
- 의 내용을 열거하는 데 사용할 수 <xref:System.Windows.Media.Visual>있습니다.  
  
 WPF는 도형, 비트맵, 텍스트 및 미디어를 그릴 수 있는 다른 형식의 개체를 제공합니다. 예를 들어 개체를 <xref:System.Windows.Shapes.Shape> 사용하여 셰이프를 그릴 <xref:System.Windows.Controls.MediaElement> 수도 있으며 컨트롤은 응용 프로그램에 비디오를 추가하는 또 다른 방법을 제공합니다. 그렇다면 언제 객체를 사용해야 <xref:System.Windows.Media.Drawing> 합니까? 프레임워크 수준 기능을 희생하여 성능 이점을 얻거나 기능이 필요할 <xref:System.Windows.Freezable> 때 수행할 수 있는 경우 개체는 [레이아웃,](../advanced/layout.md)입력 및 포커스에 대한 지원이 부족하기 때문에 <xref:System.Windows.Media.Visual> <xref:System.Windows.Media.Drawing> 배경, 클립 아트 및 개체가 있는 로우 레벨 드로잉에 이상적인 성능 이점을 제공합니다.  
  
 형식 <xref:System.Windows.Freezable> 개체이기 때문에 <xref:System.Windows.Media.Drawing> 개체는 [리소스로](../../../desktop-wpf/fundamentals/xaml-resources-define.md)선언하고, 여러 개체 간에 공유되고, 성능을 향상시키기 위해 읽기 전용으로 만들고, 복제하고, 스레드를 안전하게 만들 수 있습니다. 제공 하는 다른 기능에 대 한 자세한 <xref:System.Windows.Freezable> 개체를 참조 합니다 [Freezable 개체 개요](../advanced/freezable-objects-overview.md)합니다.  
  
<a name="drawinggeometriessection"></a>
## <a name="draw-a-shape"></a>도형 그리기  
 셰이프를 그리려면 <xref:System.Windows.Media.GeometryDrawing>을 사용합니다. 지오메트리 드로잉의 <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> 속성은 그릴 모양을 설명하고, 해당 <xref:System.Windows.Media.GeometryDrawing.Brush%2A> 속성은 셰이프의 내부를 페인팅하는 방법을 설명하고, 해당 속성은 <xref:System.Windows.Media.GeometryDrawing.Pen%2A> 윤곽선을 그리는 방법을 설명합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.GeometryDrawing> a를 사용하여 셰이프를 그립니다. 셰이프는 a와 <xref:System.Windows.Media.GeometryGroup> 두 <xref:System.Windows.Media.EllipseGeometry> 개의 개체에 의해 설명됩니다. 모양의 내부는 a로 <xref:System.Windows.Media.LinearGradientBrush> 그려지고 윤곽선은 <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>로 그려집니다.  
  
 이 예제는 <xref:System.Windows.Media.GeometryDrawing>다음을 만듭니다.  
  
 ![타원 두 개의 GeometryDrawing](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexampleinline)]  
  
 전체 예제를 보려면 [GeometryDrawing 만들기](how-to-create-a-geometrydrawing.md)를 참조하세요.  
  
 곡선과 <xref:System.Windows.Media.Geometry> 호를 <xref:System.Windows.Media.PathGeometry> 작성하여 더 복잡한 모양을 만들 수 있습니다. 객체에 대한 <xref:System.Windows.Media.Geometry> 자세한 내용은 [지오메트리 개요](geometry-overview.md)를 참조하십시오.  
  
 객체를 사용하지 <xref:System.Windows.Media.Drawing> 않는 셰이프를 그리는 다른 방법에 대한 자세한 내용은 [WPF 개요에서 셰이프 및 기본 그리기를](shapes-and-basic-drawing-in-wpf-overview.md)참조하십시오.  
  
<a name="drawingimagessection"></a>
## <a name="draw-an-image"></a>이미지 그리기  
 이미지를 그리려면 <xref:System.Windows.Media.ImageDrawing>을 사용합니다. 오브젝트의 <xref:System.Windows.Media.ImageDrawing> <xref:System.Windows.Media.ImageDrawing.ImageSource%2A> 속성은 그릴 이미지를 설명하고 해당 <xref:System.Windows.Media.ImageDrawing.Rect%2A> 속성은 이미지가 그려지는 영역을 정의합니다.  
  
 다음 예제에서는 (75,75)에 있는 사각형에 100 x 100픽셀 이미지를 그립니다. 다음 그림에서는 <xref:System.Windows.Media.ImageDrawing> 예제에서 만든 것을 보여 주시고 있습니다. <xref:System.Windows.Media.ImageDrawing>의 경계를 표시하기 위해 회색 테두리가 추가되었습니다.  
  
 ![&#40;75,75&#41;에 그려진 100 x 100 ImageDrawing](./media/graphicsmm-simple-imagedrawing-offset.png "graphicsmm_simple_imagedrawing_offset")  
100 x 100 ImageDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawing100by100inline)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawing100by100inline)]  
  
 이미지에 대한 자세한 내용은 [이미징 개요](imaging-overview.md)를 참조하세요.  
  
<a name="playmedia"></a>
## <a name="play-media-code-only"></a>미디어 재생(코드만 해당)  
  
> [!NOTE]
> <xref:System.Windows.Media.VideoDrawing> 을 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]선언할 수는 있지만 코드를 사용하여 해당 미디어를 로드하고 재생할 수만 있습니다. 에서 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]비디오를 재생하려면 <xref:System.Windows.Controls.MediaElement> 대신 을 사용합니다.  
  
 오디오 또는 비디오 파일을 재생하려면 <xref:System.Windows.Media.VideoDrawing> 및 <xref:System.Windows.Media.MediaPlayer>를 사용합니다. 미디어를 로드하고 재생하는 방법에는 다음 두 가지가 있습니다. 첫 번째는 a와 <xref:System.Windows.Media.MediaPlayer> <xref:System.Windows.Media.VideoDrawing> a를 단독으로 사용하는 것이고, 두 번째 <xref:System.Windows.Media.MediaTimeline> 방법은 을 <xref:System.Windows.Media.MediaPlayer> 사용하여 <xref:System.Windows.Media.VideoDrawing>사용할 자신을 만드는 것입니다.  
  
> [!NOTE]
> 애플리케이션을 사용하여 미디어를 배포하는 경우 이미지의 경우처럼 미디어 파일을 프로젝트 리소스로 사용할 수 없습니다. 대신 프로젝트 파일에서 미디어 형식을 `Content`로 설정하고 `CopyToOutputDirectory`를 `PreserveNewest` 또는 `Always`로 설정해야 합니다.  
  
 직접 <xref:System.Windows.Media.MediaTimeline>만들지 않고 미디어를 재생하려면 다음 단계를 수행합니다.  
  
1. <xref:System.Windows.Media.MediaPlayer> 개체를 만듭니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline1)]  
  
2. 메서드를 <xref:System.Windows.Media.MediaPlayer.Open%2A> 사용하여 미디어 파일을 로드합니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline2)]  
  
3. <xref:System.Windows.Media.VideoDrawing>를 만듭니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline3)]  
  
4. <xref:System.Windows.Media.VideoDrawing>의 <xref:System.Windows.Media.VideoDrawing.Rect%2A> 속성을 설정하여 미디어를 그릴 크기와 위치를 지정합니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline4)]  
  
5. <xref:System.Windows.Media.VideoDrawing.Player%2A> 만든 <xref:System.Windows.Media.VideoDrawing> 을 가진 속성을 <xref:System.Windows.Media.MediaPlayer> 설정합니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline5](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline5)]  
  
6. 미디어 <xref:System.Windows.Media.MediaPlayer.Play%2A> 재생을 <xref:System.Windows.Media.MediaPlayer> 시작하려면 의 메서드를 사용합니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline6](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline6)]  
  
 다음 예제에서는 <xref:System.Windows.Media.VideoDrawing> a와 <xref:System.Windows.Media.MediaPlayer> a를 사용하여 비디오 파일을 한 번 재생합니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 미디어에 대한 추가 타이밍 제어를 얻으려면 <xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing> 개체와 함께 를 사용합니다. 을 <xref:System.Windows.Media.MediaTimeline> 사용하면 비디오를 반복할지 여부를 지정할 수 있습니다. <xref:System.Windows.Media.VideoDrawing>을 <xref:System.Windows.Media.MediaTimeline> 사용하여 를 사용하려면 다음 단계를 수행합니다.  
  
1. 을 <xref:System.Windows.Media.MediaTimeline> 선언하고 타이밍 동작을 설정합니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline1)]  
  
2. 에서 <xref:System.Windows.Media.MediaClock> 를 <xref:System.Windows.Media.MediaTimeline>만듭니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline2)]  
  
3. 를 <xref:System.Windows.Media.MediaPlayer> 만들고 을 <xref:System.Windows.Media.MediaClock> 사용하여 <xref:System.Windows.Media.MediaPlayer.Clock%2A> 해당 속성을 설정합니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline3)]  
  
4. 을 <xref:System.Windows.Media.VideoDrawing> 만들고 을 <xref:System.Windows.Media.MediaPlayer> 의 <xref:System.Windows.Media.VideoDrawing.Player%2A> 속성에 <xref:System.Windows.Media.VideoDrawing>할당합니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline4)]  
  
 다음 예제에서는 <xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.MediaPlayer> a와 a를 <xref:System.Windows.Media.VideoDrawing> 사용하여 비디오를 반복적으로 재생합니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 <xref:System.Windows.Media.MediaTimeline>을 사용하는 경우 <xref:System.Windows.Media.Animation.ClockController> 의 <xref:System.Windows.Media.Animation.Clock.Controller%2A> 속성에서 반환된 대화형 대화형 <xref:System.Windows.Media.MediaClock> 을 사용하여 <xref:System.Windows.Media.MediaPlayer>의 대화형 메서드 대신 미디어 재생을 제어합니다.  
  
<a name="drawtext"></a>
## <a name="draw-text"></a>텍스트 그리기  
 텍스트를 그리려면 <xref:System.Windows.Media.GlyphRunDrawing> 및 를 <xref:System.Windows.Media.GlyphRun>사용합니다. 다음 예제에서는 <xref:System.Windows.Media.GlyphRunDrawing> "Hello World" 텍스트를 그립니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GlyphRunDrawingExample.cs#glyphrundrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GlyphRunExample.xaml#glyphrundrawingexampleinline)]  
  
 <xref:System.Windows.Media.GlyphRun> 고정 형식 문서 프레젠테이션과 인쇄 시나리오를 사용 하 여 사용 하기 위한 것 하위 수준 개체입니다. 화면에 텍스트를 그리는 더 간단한 방법을 사용 하는 것을 <xref:System.Windows.Controls.Label> 또는 <xref:System.Windows.Controls.TextBlock>합니다. 에 대 한 자세한 내용은 <xref:System.Windows.Media.GlyphRun>를 참조 합니다 [GlyphRun 개체 및 Glyphs 요소 소개](../advanced/introduction-to-the-glyphrun-object-and-glyphs-element.md) 개요.  
  
<a name="compositedrawingssection"></a>
## <a name="composite-drawings"></a>합성 그리기  
 A를 <xref:System.Windows.Media.DrawingGroup> 사용하면 여러 도면을 단일 복합 도면으로 결합할 수 있습니다. 을 <xref:System.Windows.Media.DrawingGroup>사용하여 셰이프, 이미지 및 텍스트를 단일 <xref:System.Windows.Media.Drawing> 개체로 결합할 수 있습니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.DrawingGroup> a를 <xref:System.Windows.Media.GeometryDrawing> 사용하여 두 <xref:System.Windows.Media.ImageDrawing> 개체와 개체를 결합합니다. 이 예제의 결과는 다음과 같습니다.  
  
 ![여러 개의 그리기가 있는 DrawingGroup](./media/graphicsmm-simple.jpg "graphicsmm_simple")  
합성 그리기  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 또한 <xref:System.Windows.Media.DrawingGroup> A를 사용하면 불투명 도 마스크, 변환, 비트맵 효과 및 기타 작업을 해당 내용에 적용할 수 있습니다. <xref:System.Windows.Media.DrawingGroup>작업은 <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>다음 순서로 <xref:System.Windows.Media.DrawingGroup.Opacity%2A> <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A> <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A> <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> <xref:System.Windows.Media.DrawingGroup.Transform%2A>적용됩니다.  
  
 다음 그림에서는 <xref:System.Windows.Media.DrawingGroup> 작업이 적용되는 순서를 보여 주며 있습니다.  
  
 ![DrawingGroup 작업의 순서](./media/graphcismm-drawinggroup-order.png "graphcismm_drawinggroup_order")  
DrawingGroup 작업의 순서  
  
 다음 표에서는 <xref:System.Windows.Media.DrawingGroup> 개체의 내용을 조작하는 데 사용할 수 있는 속성에 대해 설명합니다.  
  
|속성|Description|그림|  
|--------------|-----------------|------------------|  
|<xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>|내용의 선택한 부분의 불투명도를 <xref:System.Windows.Media.DrawingGroup> 변경합니다. 예제를 보려면 [방법: 그리기의 불투명도 제어](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748242(v=vs.90))를 참조하세요.|![불투명도 마스크가 있는 도면 그룹](./media/graphicsmm-opmask.png "graphicsmm_opmask")|  
|<xref:System.Windows.Media.DrawingGroup.Opacity%2A>|내용의 불투명도를 <xref:System.Windows.Media.DrawingGroup> 균일하게 변경합니다. 이 속성을 사용하여 <xref:System.Windows.Media.Drawing> 투명하거나 부분적으로 투명하게 만듭니다. 예제를 보려면 [방법: 도면에 불투명 마스크 적용](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms753195(v=vs.90))을 참조하세요.|![여러 불투명도 설정의 DrawingGroup](./media/graphicsmm-opacity.png "graphicsmm_opacity")|  
|<xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>|내용에 <xref:System.Windows.Media.Effects.BitmapEffect> a를 <xref:System.Windows.Media.DrawingGroup> 적용합니다. 예제를 보려면 [방법: 그리기에 BitmapEffect 적용](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752341(v=vs.90))을 참조하세요.|![BlurBitmapEffect가 적용된 DrawingGroup](./media/graphicsmm-bitmap.png "graphicsmm_bitmap")|  
|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|<xref:System.Windows.Media.DrawingGroup> 을 사용하여 설명하는 영역에 내용을 클립합니다. <xref:System.Windows.Media.Geometry> 예제를 보려면 [방법: 그림 자르기](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms743068(v=vs.90))를 참조하세요.|![정의된 클립 영역이 있는 DrawingGroup](./media/graphicsmm-clipgeom.png "graphicsmm_clipgeom")|  
|<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>|지정된 지침에 따라 디바이스 독립적 픽셀을 디바이스 픽셀에 맞춥니다. 이 속성은 매우 세부적인 그래픽이 낮은 DPI 디스플레이에 선명하게 렌더링되도록 하는 데 유용합니다. 예제를 보려면 [Drawing에 GuidelineSet 적용](how-to-apply-a-guidelineset-to-a-drawing.md)을 참조하세요.|![GuidelineSet이 있는 DrawingGroup과 없는 DrawingGroup](./media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")|  
|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|<xref:System.Windows.Media.DrawingGroup> 내용을 변환합니다. 예제를 보려면 [방법: 그리기에 변환 적용](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms742304(v=vs.90))을 참조하세요.|![회전된 DrawingGroup](./media/graphicsmm-rotate.png "graphicsmm_rotate")|  
  
<a name="usingimagedrawing"></a>
## <a name="display-a-drawing-as-an-image"></a>그리기를 이미지로 표시  
 <xref:System.Windows.Media.Drawing> 컨트롤을 <xref:System.Windows.Controls.Image> 사용하여 를 표시하려면 <xref:System.Windows.Media.DrawingImage> <xref:System.Windows.Controls.Image> 컨트롤로 <xref:System.Windows.Controls.Image.Source%2A> 를 사용하고 <xref:System.Windows.Media.DrawingImage> 표시할 <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> 도면에 오브젝트의 속성을 설정합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.DrawingImage> a <xref:System.Windows.Controls.Image> 및 컨트롤을 <xref:System.Windows.Media.GeometryDrawing>사용하여 을 표시합니다. 이 예제의 결과는 다음과 같습니다.  
  
 ![타원 두 개의 GeometryDrawing](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
<a name="renderingwithdrawingbrushsection"></a>
## <a name="paint-an-object-with-a-drawing"></a>Drawing으로 개체 그리기  
 A는 <xref:System.Windows.Media.DrawingBrush> 드로잉 객체로 영역을 그리는 브러시 유형입니다. 그리기 기능으로 거의 모든 그래픽 개체를 그리는 데 사용할 수 있습니다. a의 <xref:System.Windows.Media.Drawing> <xref:System.Windows.Media.DrawingBrush> 속성은 을 <xref:System.Windows.Media.DrawingBrush.Drawing%2A>설명합니다. 을 <xref:System.Windows.Media.Drawing> 사용하여 <xref:System.Windows.Media.DrawingBrush>렌더링하려면 브러시의 <xref:System.Windows.Media.Drawing> 속성을 사용하여 브러시에 추가하고 브러시를 사용하여 컨트롤 또는 패널과 같은 그래픽 오브젝트를 페인칠합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.DrawingBrush> a를 사용하여 <xref:System.Windows.Shapes.Shape.Fill%2A> 에서 <xref:System.Windows.Shapes.Rectangle> 만든 패턴으로 <xref:System.Windows.Media.GeometryDrawing>를 페인트합니다. 이 예제의 결과는 다음과 같습니다.  
  
 ![바둑판식으로 배열된 DrawingBrush](./media/graphicsmm-drawingbrush-geometrydrawing.png "graphicsmm_drawingbrush_geometrydrawing")  
DrawingBrush에 GeometryDrawing 사용  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 클래스는 <xref:System.Windows.Media.DrawingBrush> 내용을 늘리고 바둑판식 배열을 위한 다양한 옵션을 제공합니다. 자세한 <xref:System.Windows.Media.DrawingBrush>내용은 [이미지, 도면 및 시각적 개체가 있는 페인팅 개요를](painting-with-images-drawings-and-visuals.md) 참조하십시오.  
  
<a name="renderingwithvisualsection"></a>
## <a name="render-a-drawing-with-a-visual"></a>시각적 표시로 그림 렌더링  
 A는 <xref:System.Windows.Media.DrawingVisual> 도면을 렌더링하도록 설계된 시각적 개체의 유형입니다. 시각적 계층에서 직접 작업하는 방식은 고도로 사용자 지정된 그래픽 환경을 구축하려는 개발자를 위한 옵션이지만 이 개요에서는 설명되지 않습니다. 자세한 내용은 [DrawingVisual 개체 사용](using-drawingvisual-objects.md)을 참조하세요.  
  
<a name="drawingcontextobjects"></a>
## <a name="drawingcontext-objects"></a>DrawingContext 개체  
 클래스를 <xref:System.Windows.Media.DrawingContext> 사용하면 시각적 콘텐츠로 <xref:System.Windows.Media.Drawing> 또는 a를 <xref:System.Windows.Media.Visual> 채울 수 있습니다. 이러한 하위 수준 그래픽 개체는 그래픽 콘텐츠를 매우 효율적으로 설명하기 때문에 a를 <xref:System.Windows.Media.DrawingContext> 사용합니다.  
  
 그리기 <xref:System.Windows.Media.DrawingContext> 메서드는 <xref:System.Drawing.Graphics?displayProperty=nameWithType> 형식의 그리기 메서드와 비슷하게 보이지만 실제로는 매우 다릅니다. <xref:System.Windows.Media.DrawingContext><xref:System.Drawing.Graphics?displayProperty=nameWithType> 유형이 즉각적인 모드 그래픽 시스템과 함께 사용되는 동안 유지 모드 그래픽 시스템과 함께 사용됩니다. <xref:System.Windows.Media.DrawingContext> 개체의 그리기 명령을 사용하는 경우 실제로 나중에 그래픽 시스템에서 사용될 렌더링 명령 집합을 저장하게 되며 (정확한 스토리지 메커니즘은 <xref:System.Windows.Media.DrawingContext>를 제공하는 개체의 형식에 따라 다름) 실시간으로 화면에 그리지 않습니다. Windows 프레젠테이션 파운데이션(WPF) 그래픽 시스템의 작동 방식에 대한 자세한 내용은 [WPF 그래픽 렌더링 개요를](wpf-graphics-rendering-overview.md)참조하십시오.  
  
 절대로 직접 인스턴스화하지 <xref:System.Windows.Media.DrawingContext>않습니다. 그러나 및 <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=nameWithType> 와 <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=nameWithType>같은 특정 메서드에서 드로잉 컨텍스트를 획득할 수 있습니다.  
  
<a name="enumeratevisualcontents"></a>
## <a name="enumerate-the-contents-of-a-visual"></a>시각적 개체의 콘텐츠 열거  
 <xref:System.Windows.Media.Drawing> 다른 용도 외에도 개체는 <xref:System.Windows.Media.Visual>의 내용을 등록하기 위한 개체 모델을 제공합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> 메서드를 사용하여 <xref:System.Windows.Media.DrawingGroup> a의 <xref:System.Windows.Media.Visual> 값을 검색하고 등록합니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Media.Drawing>
- <xref:System.Windows.Media.DrawingGroup>
- [2D 그래픽 및 이미징](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [이미지, 그림 및 시각적 표시로 그리기](painting-with-images-drawings-and-visuals.md)
- [Geometry 개요](geometry-overview.md)
- [WPF에서 Shape 및 기본 그리기 개요](shapes-and-basic-drawing-in-wpf-overview.md)
- [WPF 그래픽 렌더링 개요](wpf-graphics-rendering-overview.md)
- [Freezable 개체 개요](../advanced/freezable-objects-overview.md)
- [방법 주제](drawings-how-to-topics.md)
