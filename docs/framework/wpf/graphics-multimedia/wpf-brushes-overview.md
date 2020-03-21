---
title: 브러쉬 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], about brushes
ms.assetid: ecea1955-420b-45c6-bf43-c1404c072c41
ms.openlocfilehash: 7a9474b392052900952f5b677ad94b16025de8dd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186573"
---
# <a name="wpf-brushes-overview"></a>WPF 브러시 개요
화면에 표시되는 모든 것은 브러시로 그려졌기 때문에 표시됩니다. 예를 들어 브러시는 단추의 배경, 텍스트의 전경 및 셰이프 의 채우기를 설명하는 데 사용됩니다. 이 항목에서는 브러시로 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 페인팅의 개념을 소개하고 예제를 제공합니다. 브러시를 사용하여 간단한 단색부터 복잡한 패턴 및 이미지 집합에 이르는 모든 방식으로 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 개체를 그릴 수 있습니다.  
  
<a name="paintingwithbrush"></a>
## <a name="painting-with-a-brush"></a>브러시로 페인팅  
 출력이 <xref:System.Windows.Media.Brush> 있는 영역을 "페인트"합니다. 다른 브러시는 다른 유형의 출력 합니다. 일부 브러시 그라데이션, 패턴, 이미지 또는 드로잉을 사용 하 여 다른 단색으로 영역을 그립니다. 다음 그림에서는 각 유형의 예제를 보여 주며 <xref:System.Windows.Media.Brush> 있습니다.  
  
 ![브러시 형식](./media/graphicsmm-brushtypes.jpg "graphicsmm_brushtypes")  
브러시 예제  
  
 대부분의 시각적 개체를 사용하면 페인팅 방법을 지정할 수 있습니다. 다음 표에는 을 사용할 수 있는 몇 <xref:System.Windows.Media.Brush>가지 일반적인 개체 및 속성이 나열되어 있습니다.  
  
|클래스|브러시 속성|  
|-----------|----------------------|  
|<xref:System.Windows.Controls.Border>|<xref:System.Windows.Controls.Border.BorderBrush%2A>, <xref:System.Windows.Controls.Border.Background%2A>|  
|<xref:System.Windows.Controls.Control>|<xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>|  
|<xref:System.Windows.Controls.Panel>|<xref:System.Windows.Controls.Panel.Background%2A>|  
|<xref:System.Windows.Media.Pen>|<xref:System.Windows.Media.Pen.Brush%2A>|  
|<xref:System.Windows.Shapes.Shape>|<xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>|  
|<xref:System.Windows.Controls.TextBlock>|<xref:System.Windows.Controls.TextBlock.Background%2A>|  
  
 다음 섹션에서는 서로 <xref:System.Windows.Media.Brush> 다른 형식을 설명하고 각각의 예제를 제공합니다.  
  
<a name="paintwithsolidcolorbrush"></a>
## <a name="paint-with-a-solid-color"></a>단색으로 페인트  
 a는 <xref:System.Windows.Media.SolidColorBrush> 솔리드로 <xref:System.Windows.Media.Color>영역을 페인트합니다. : 를 지정하는 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 다양한 방법이 있습니다 : 예를 들어, 알파, 빨간색, 파란색 및 녹색 채널을 지정하거나 <xref:System.Windows.Media.Colors> 클래스에서 제공하는 미리 정의 된 색상 중 하나를 사용할 수 있습니다. <xref:System.Windows.Media.SolidColorBrush>  
  
 다음 예제에서는 <xref:System.Windows.Media.SolidColorBrush> a를 <xref:System.Windows.Shapes.Shape.Fill%2A> 사용하여 <xref:System.Windows.Shapes.Rectangle>을 페인트합니다. 다음 그림에서는 페인팅된 사각형을 보여 주습니다.  
  
 ![SolidColorBrush를 사용하여 그린 사각형](./media/graphicsmm-brush-ovw-solidcolorbrush.png "graphicsmm_brush_ovw_solidcolorbrush")  
솔리드컬러 브러시를 사용하여 그린 직사각형  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmsolidcolorbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmsolidcolorbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmsolidcolorbrushexampleinline)]  
  
 클래스에 <xref:System.Windows.Media.SolidColorBrush> 대한 자세한 내용은 [단색 및 그라데이션 개요를 가진 페인팅을](painting-with-solid-colors-and-gradients-overview.md)참조하십시오.  
  
<a name="paintwithlineargradientbrush"></a>
## <a name="paint-with-a-linear-gradient"></a>선형 그라데이션으로 페인트  
 <xref:System.Windows.Media.LinearGradientBrush> 선형 그라데이션으로 영역을 그립니다. 선형 그라데이션은 그라데이션 축인 선에 두 개 이상의 색상을 혼합합니다. 객체를 <xref:System.Windows.Media.GradientStop> 사용하여 그라데이션의 색상과 해당 위치를 지정합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.LinearGradientBrush> a를 <xref:System.Windows.Shapes.Shape.Fill%2A> 사용하여 <xref:System.Windows.Shapes.Rectangle>을 페인트합니다. 다음 그림에서는 페인팅된 사각형을 보여 주습니다.  
  
 ![LinearGradientBrush를 사용하여 그린 사각형](./media/graphicsmm-brush-ovw-lineargradientbrush.jpg "graphicsmm_brush_ovw_lineargradientbrush")  
선형 그라데이션 브러시를 사용하여 그린 사각형  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmlineargradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmlineargradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmlineargradientbrushexampleinline)]  
  
 클래스에 <xref:System.Windows.Media.LinearGradientBrush> 대한 자세한 내용은 [단색 및 그라데이션 개요를 가진 페인팅을](painting-with-solid-colors-and-gradients-overview.md)참조하십시오.  
  
<a name="paintwithradialgradientbrush"></a>
## <a name="paint-with-a-radial-gradient"></a>방사형 그라데이션으로 페인트  
 방사형 <xref:System.Windows.Media.RadialGradientBrush> 그라데이션이 있는 영역을 페인트합니다. 방사형 그라데이션은 둘 이상의 색상을 원 에 걸쳐 혼합합니다. 클래스와 <xref:System.Windows.Media.LinearGradientBrush> 마찬가지로 객체를 <xref:System.Windows.Media.GradientStop> 사용하여 그라데이션의 색상과 위치를 지정합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.RadialGradientBrush> a를 <xref:System.Windows.Shapes.Shape.Fill%2A> 사용하여 <xref:System.Windows.Shapes.Rectangle>을 페인트합니다. 다음 그림에서는 페인팅된 사각형을 보여 주습니다.  
  
 ![RadialGradientBrush를 사용하여 그린 사각형](./media/graphicsmm-brush-ovw-radialgradientbrush.jpg "graphicsmm_brush_ovw_radialgradientbrush")  
방사형 그라데이션 브러시를 사용하여 그린 직사각형  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmradialgradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmradialgradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmradialgradientbrushexampleinline)]  
  
 클래스에 <xref:System.Windows.Media.RadialGradientBrush> 대한 자세한 내용은 [단색 및 그라데이션 개요를 가진 페인팅을](painting-with-solid-colors-and-gradients-overview.md)참조하십시오.  
  
<a name="paintwithimage"></a>
## <a name="paint-with-an-image"></a>이미지로 페인트  
 영역을 <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Media.ImageSource>페인트합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.ImageBrush> 을 사용하여 <xref:System.Windows.Shapes.Shape.Fill%2A> 을 <xref:System.Windows.Shapes.Rectangle>페인트합니다. 다음 그림에서는 페인팅된 사각형을 보여 주습니다.  
  
 ![ImageBrush로 그린 사각형](./media/graphicsmm-brush-ovw-imagebrush.jpg "graphicsmm_brush_ovw_imagebrush")  
이미지를 사용하여 페인팅된 사각형  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmimagebrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmimagebrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmimagebrushexampleinline)]  
  
 클래스에 <xref:System.Windows.Media.ImageBrush> 대한 자세한 내용은 [이미지, 도면 및 시각적 개체로 페인팅을](painting-with-images-drawings-and-visuals.md)참조하십시오.  
  
<a name="paintwithdrawing"></a>
## <a name="paint-with-a-drawing"></a>그림과 페인트  
 a는 <xref:System.Windows.Media.DrawingBrush> 영역을 페인트합니다. <xref:System.Windows.Media.Drawing> A에는 <xref:System.Windows.Media.Drawing> 모양, 이미지, 텍스트 및 미디어가 포함될 수 있습니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.DrawingBrush> a를 <xref:System.Windows.Shapes.Shape.Fill%2A> 사용하여 <xref:System.Windows.Shapes.Rectangle>을 페인트합니다. 다음 그림에서는 페인팅된 사각형을 보여 주습니다.  
  
 ![DrawingBrush를 사용하여 그린 사각형](./media/graphicsmm-brush-ovw-drawingbrush.jpg "graphicsmm_brush_ovw_drawingbrush")  
드로잉 브러시를 사용하여 그린 사각형  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmdrawingbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmdrawingbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmdrawingbrushexampleinline)]  
  
 클래스에 <xref:System.Windows.Media.DrawingBrush> 대한 자세한 내용은 [이미지, 도면 및 시각적 개체로 페인팅을](painting-with-images-drawings-and-visuals.md)참조하십시오.  
  
<a name="paintwithvisual"></a>
## <a name="paint-with-a-visual"></a>비주얼페인트  
 A는 <xref:System.Windows.Media.VisualBrush> 객체가 있는 <xref:System.Windows.Media.Visual> 영역을 그립니다. 시각적 개체의 예로는 <xref:System.Windows.Controls.Page>에서 <xref:System.Windows.Controls.MediaElement>를 포함합니다. <xref:System.Windows.Controls.Button> 또한 <xref:System.Windows.Media.VisualBrush> A를 사용하면 응용 프로그램의 한 부분에서 다른 영역으로 콘텐츠를 투영할 수 있습니다. 반사 효과를 만들고 화면의 부분을 확대하는 데 매우 유용합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.VisualBrush> a를 <xref:System.Windows.Shapes.Shape.Fill%2A> 사용하여 <xref:System.Windows.Shapes.Rectangle>을 페인트합니다. 다음 그림에서는 페인팅된 사각형을 보여 주습니다.  
  
 ![VisualBrush를 사용하여 그린 사각형](./media/graphicsmm-brush-ovw-visualbrush.jpg "graphicsmm_brush_ovw_visualbrush")  
비주얼 브러시를 사용하여 그린 사각형  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmvisualbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmvisualbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmvisualbrushexampleinline)]  
  
 클래스에 <xref:System.Windows.Media.VisualBrush> 대한 자세한 내용은 [이미지, 도면 및 시각적 개체로 페인팅을](painting-with-images-drawings-and-visuals.md)참조하십시오.  
  
<a name="paintwithpredefinedbrushesandsystemcolors"></a>
## <a name="paint-using-predefined-and-system-brushes"></a>미리 정의된 시스템 브러시를 사용하여 페인트  
 편의를 위해 WPF(Windows 프레젠테이션 파운데이션)는 미리 정의된 시스템 브러시 세트를 제공하여 개체를 페인팅하는 데 사용할 수 있습니다.  
  
- 사용 가능한 미리 정의된 브러시 목록은 <xref:System.Windows.Media.Brushes> 클래스를 참조하십시오. 미리 정의된 브러시를 사용하는 방법을 보여 주려면 [단색으로 영역 페인트](how-to-paint-an-area-with-a-solid-color.md)를 참조하십시오.  
  
- 사용 가능한 시스템 브러시 목록은 클래스를 <xref:System.Windows.SystemColors> 참조하십시오. 예를 들어 [시스템 브러시로 영역 페인트](how-to-paint-an-area-with-a-system-brush.md)를 참조하십시오.  
  
<a name="commonbrushfeatures"></a>
## <a name="common-brush-features"></a>일반적인 브러시 특징  
 <xref:System.Windows.Media.Brush>개체는 <xref:System.Windows.Media.Brush.Opacity%2A> 브러시를 투명하거나 부분적으로 투명하게 만드는 데 사용할 수 있는 속성을 제공합니다. 값이 <xref:System.Windows.Media.Brush.Opacity%2A> 0이면 브러시가 완전히 투명해지며 <xref:System.Windows.Media.Brush.Opacity%2A> 값 1은 브러시를 완전히 불투명하게 만듭니다. 다음 예제에서는 <xref:System.Windows.Media.Brush.Opacity%2A> 속성을 사용하여 <xref:System.Windows.Media.SolidColorBrush> 25% 불투명을 만듭니다.  
  
 [!code-xaml[BrushOverviewExamples_snip#OpacityExample1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/OpacityExample.xaml#opacityexample1xaml)]  
  
 [!code-csharp[BrushOverviewExamples_snip#OpacityExample1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/OpacityExample.cs#opacityexample1csharp)]  
  
 브러시에 부분적으로 투명한 색상이 포함된 경우 색상의 불투명도 값은 곱셈을 통해 브러시의 불투명도 값과 결합됩니다. 예를 들어 브러시의 불투명도 값이 0.5이고 브러시에 사용된 색상도 불투명도 값이 0.5인 경우 출력 색상은 불투명도 값이 0.25입니다.  
  
> [!NOTE]
> 브러시의 불투명도 값을 변경하는 것이 <xref:System.Windows.UIElement.Opacity%2A?displayProperty=nameWithType> 속성을 사용하여 전체 요소의 불투명도를 변경하는 것보다 더 효율적입니다.  
  
 브러시 <xref:System.Windows.Media.Brush.Transform%2A> 또는 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 속성을 사용하여 브러시의 내용을 회전, 배율 조정, 기울이기 및 변환할 수 있습니다. 자세한 내용은 [브러시 변환 개요를](brush-transformation-overview.md)참조하십시오.  
  
 개체이기 <xref:System.Windows.Media.Animation.Animatable> 때문에 <xref:System.Windows.Media.Brush> 오브젝트를 애니메이션할 수 있습니다. 자세한 내용은 [애니메이션 개요를](animation-overview.md)참조하십시오.  
  
<a name="freezable_features"></a>
### <a name="freezable-features"></a>Freezable 기능  
 클래스에서 상속하기 때문에 클래스는 여러 가지 <xref:System.Windows.Media.Brush> 특수 기능을 제공합니다: 개체를 [리소스로](../../../desktop-wpf/fundamentals/xaml-resources-define.md)선언하고, 여러 개체 간에 공유및 복제할 수 있습니다. <xref:System.Windows.Freezable> <xref:System.Windows.Media.Brush> 또한 성능을 향상시키기 <xref:System.Windows.Media.Brush> 위해 <xref:System.Windows.Media.VisualBrush> 읽기 전용으로 만들 수 있는 모든 형식을 사용할 수 있으며 스레드가 안전합니다.  
  
 제공 하는 다른 기능에 대 한 자세한 내용은 <xref:System.Windows.Freezable> 개체를 참조 하세요 [Freezable 개체 개요](../advanced/freezable-objects-overview.md)합니다.  
  
 개체를 고정할 <xref:System.Windows.Media.VisualBrush> 수 없는 이유에 <xref:System.Windows.Media.VisualBrush> 대한 자세한 내용은 형식 페이지를 참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Media.Brush>
- <xref:System.Windows.Media.Brushes>
- [단색 및 그라데이션을 사용한 그리기 개요](painting-with-solid-colors-and-gradients-overview.md)
- [이미지, 그림 및 시각적 표시로 그리기](painting-with-images-drawings-and-visuals.md)
- [Freezable 개체 개요](../advanced/freezable-objects-overview.md)
- [브러시 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)
- [ImageBrush 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)
- [VisualBrush 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush)
- [방법 주제](brushes-how-to-topics.md)
- [기타 성능 추천 사항](../advanced/optimizing-performance-other-recommendations.md)
