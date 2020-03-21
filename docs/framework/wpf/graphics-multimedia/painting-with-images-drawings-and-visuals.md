---
title: 이미지, 그림 및 시각적 표시로 그리기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with drawings
- painting [WPF], with drawings
- painting [WPF], with images
- painting with visuals [WPF]
- brushes [WPF], painting with images
- brushes [WPF], painting with visuals
ms.assetid: 779aac3f-8d41-49d8-8130-768244aa2240
ms.openlocfilehash: e0e5e386b32425c87502d18a24e758193c14a5b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186915"
---
# <a name="painting-with-images-drawings-and-visuals"></a>이미지, 그림 및 시각적 표시로 그리기
이 항목에서는 <xref:System.Windows.Media.ImageBrush>에서 <xref:System.Windows.Media.DrawingBrush>를 사용하는 <xref:System.Windows.Media.VisualBrush> 방법과 및 개체를 사용하여 <xref:System.Windows.Media.Drawing>이미지, <xref:System.Windows.Media.Visual>에 또는 을 사용하여 영역을 페인그하는 방법에 대해 설명합니다.  

<a name="prereqs"></a>
## <a name="prerequisites"></a>전제 조건  
 이 항목을 이해하려면 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 제공하는 다양한 형식의 브러시와 해당 기본 기능에 대해 잘 알고 있어야 합니다. 소개 내용을 보려면 [WPF 브러시 개요](wpf-brushes-overview.md)를 참조하세요.  
  
<a name="image"></a>
## <a name="paint-an-area-with-an-image"></a>이미지로 영역 그리기  
 <xref:System.Windows.Media.ImageBrush> 영역을 그립니다는 <xref:System.Windows.Media.ImageSource>합니다. 가장 일반적인 유형의 <xref:System.Windows.Media.ImageSource> 를 사용 하는 <xref:System.Windows.Media.ImageBrush> 는 <xref:System.Windows.Media.Imaging.BitmapImage>, 비트맵 그래픽을 설명 하는 합니다. 사용할 수는 <xref:System.Windows.Media.DrawingImage> 를 사용 하 여 그릴를 <xref:System.Windows.Media.Drawing> 개체 이며 간단 하 게 사용을 <xref:System.Windows.Media.DrawingBrush> 대신 합니다. 개체에 대한 <xref:System.Windows.Media.ImageSource> 자세한 내용은 [이미징 개요를](imaging-overview.md)참조하십시오.  
  
 <xref:System.Windows.Media.ImageBrush>을 사용하여 페인트하려면 <xref:System.Windows.Media.Imaging.BitmapImage> 을 만들고 이를 사용하여 비트맵 콘텐츠를 로드합니다. 그런 다음 <xref:System.Windows.Media.Imaging.BitmapImage> 을 사용하여 <xref:System.Windows.Media.ImageBrush.ImageSource%2A> 의 <xref:System.Windows.Media.ImageBrush>속성을 설정합니다. 마지막으로 <xref:System.Windows.Media.ImageBrush> 페인트할 오브젝트에 적용합니다.  에서 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]로드할 <xref:System.Windows.Media.ImageBrush.ImageSource%2A> 이미지 의 경로를 <xref:System.Windows.Media.ImageBrush> 사용하여 의 속성을 설정할 수도 있습니다.  
  
 모든 <xref:System.Windows.Media.Brush> 오브젝트와 <xref:System.Windows.Media.ImageBrush> 마찬가지로 a를 사용하여 모양, 패널, 컨트롤 및 텍스트와 같은 오브젝트를 페인칠할 수 있습니다. 다음 그림에서는 <xref:System.Windows.Media.ImageBrush>을 통해 달성할 수 있는 몇 가지 효과를 보여 주며 있습니다.  
  
 ![ImageBrush 출력 예제](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
ImageBrush로 그린 개체  
  
 기본적으로 페인팅되는 <xref:System.Windows.Media.ImageBrush> 영역을 완전히 채우기 위해 이미지를 늘이면 페인팅된 영역이 이미지와 다른 가로 세로 비율이 있는 경우 이미지가 왜곡될 수 있습니다. 의 기본값에서 로 <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성을 변경하여 이 <xref:System.Windows.Media.Stretch.Fill> <xref:System.Windows.Media.Stretch.None>동작을 <xref:System.Windows.Media.Stretch.Uniform> <xref:System.Windows.Media.Stretch.UniformToFill>변경할 수 있습니다. 의 <xref:System.Windows.Media.ImageBrush> 유형이기 <xref:System.Windows.Media.TileBrush>때문에 이미지 브러시가 출력 영역을 채우고 패턴을 만드는 방법을 정확하게 지정할 수 있습니다. 고급 <xref:System.Windows.Media.TileBrush> 기능에 대한 자세한 내용은 [타일브러시 개요를](tilebrush-overview.md)참조하십시오.  
  
<a name="fillingpanelwithimage"></a>
## <a name="example-paint-an-object-with-a-bitmap-image"></a>예제: 비트맵 이미지로 개체 그리기  
 다음 예제에서는 <xref:System.Windows.Media.ImageBrush> 을 사용하여 <xref:System.Windows.Controls.Panel.Background%2A> 을 <xref:System.Windows.Controls.Canvas>페인트합니다.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/ImageBrushExample.xaml#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/ImageBrushExample.cs#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/imagebrushexample.vb#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
<a name="drawingbrushintro"></a>
## <a name="paint-an-area-with-a-drawing"></a>Drawing으로 영역 그리기  
 A를 <xref:System.Windows.Media.DrawingBrush> 사용하면 모양, 텍스트, 이미지 및 비디오가 있는 영역을 페인칠할 수 있습니다. 드로잉 브러시 내부의 셰이프는 단색, 그라데이션, 이미지 또는 <xref:System.Windows.Media.DrawingBrush>다른 모양으로 칠할 수 있습니다. 다음 그림에서는 <xref:System.Windows.Media.DrawingBrush>의 일부 용도를 보여 줍니다.  
  
 ![DrawingBrush 출력 예제](./media/wcpsdk-mmgraphics-drawingbrushexamples.png "wcpsdk_mmgraphics_drawingbrushexamples")  
DrawingBrush로 그린 개체  
  
 A는 <xref:System.Windows.Media.DrawingBrush> 객체가 있는 <xref:System.Windows.Media.Drawing> 영역을 그립니다. 개체는 <xref:System.Windows.Media.Drawing> 셰이프, 비트맵, 비디오 또는 텍스트 줄과 같은 표시되는 콘텐츠를 설명합니다. 그리기 형식마다 다른 콘텐츠 형식을 설명합니다. 다음은 여러 그리기 개체 형식을 보여 주는 목록입니다.  
  
- <xref:System.Windows.Media.GeometryDrawing>- 모양을 그립니다.  
  
- <xref:System.Windows.Media.ImageDrawing>– 이미지를 그립니다.  
  
- <xref:System.Windows.Media.GlyphRunDrawing>– 텍스트를 그립니다.  
  
- <xref:System.Windows.Media.VideoDrawing>- 오디오 또는 비디오 파일을 재생합니다.  
  
- <xref:System.Windows.Media.DrawingGroup>– 다른 도면을 그립니다. 다른 그리기를 단일 합성 그리기로 결합하려면 그리기 그룹을 사용합니다.  
  
 객체에 대한 <xref:System.Windows.Media.Drawing> 자세한 내용은 [도면 객체 개요를](drawing-objects-overview.md)참조하십시오.  
  
 <xref:System.Windows.Media.ImageBrush>처럼, 출력 <xref:System.Windows.Media.DrawingBrush> 영역을 채우기 위해 그것의 <xref:System.Windows.Media.DrawingBrush.Drawing%2A> 스트레칭. 의 기본 설정에서 <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성을 변경하여 이 동작을 재정의할 <xref:System.Windows.Media.Stretch.Fill>수 있습니다. 자세한 내용은 <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성을 참조하세요.  
  
<a name="fillingareawithdrawingbrushexample"></a>
## <a name="example-paint-an-object-with-a-drawing"></a>예제: Drawing으로 개체 그리기  
 다음 예제에서는 3개의 타원 그림으로 개체를 그리는 방법을 보여 줍니다. A는 <xref:System.Windows.Media.GeometryDrawing> 타원을 설명하는 데 사용됩니다.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/DrawingBrushExample.xaml#graphicsmmdrawingbrushasbuttonbackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/DrawingBrushExample.cs#graphicsmmdrawingbrushasbuttonbackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/drawingbrushexample.vb#graphicsmmdrawingbrushasbuttonbackgroundexample1)]  
  
<a name="visualbrushsection"></a>
## <a name="paint-an-area-with-a-visual"></a>시각적 표시로 영역 그리기  
 모든 브러쉬 중에서 가장 다재다능하고 강력한 브러시로 <xref:System.Windows.Media.Visual>영역을 <xref:System.Windows.Media.VisualBrush> 페인트합니다. A는 <xref:System.Windows.Media.Visual> 많은 유용한 그래픽 구성 요소의 조상 역할을 하는 하위 수준의 그래픽 형식입니다. <xref:System.Windows.Window>예를 들어, <xref:System.Windows.FrameworkElement>의 <xref:System.Windows.Controls.Control> 는 의 및 <xref:System.Windows.Media.Visual> 클래스는 모든 유형의 개체입니다. 을 <xref:System.Windows.Media.VisualBrush>사용하면 거의 모든 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 그래픽 오브젝트가 있는 영역을 페인트할 수 있습니다.  
  
> [!NOTE]
> 개체의 <xref:System.Windows.Media.VisualBrush> <xref:System.Windows.Freezable> 형식이지만 <xref:System.Windows.Media.VisualBrush.Visual%2A> 속성이 가 아닌 `null`값으로 설정되어 있을 때 고정(읽기 전용으로 만)할 수 없습니다.  
  
 두 가지 방법으로 지정할 수는 <xref:System.Windows.Media.VisualBrush.Visual%2A> 의 콘텐츠는 <xref:System.Windows.Media.VisualBrush>합니다.  
  
- 새 <xref:System.Windows.Media.Visual> 를 설정 하는 데 사용 합니다 <xref:System.Windows.Media.VisualBrush.Visual%2A> 의 속성을 <xref:System.Windows.Media.VisualBrush>합니다. 예제를 보려면 다음에 나오는 [예제: 시각적 개체로 개체 그리기](#examplevisualbrush1)를 참조하세요.  
  
- 기존 항목 사용 <xref:System.Windows.Media.Visual>, 대상의 중복 이미지를 만드는 <xref:System.Windows.Media.Visual>합니다. 사용할 수 있습니다는 <xref:System.Windows.Media.VisualBrush> 리플렉션 및 확대와 같은 흥미로운 효과 만들 수 있습니다. 예제를 보려면 [예제: 리플렉션 만들기](#examplevisualbrush2) 섹션을 참조하세요.  
  
 정의 하는 경우 새 <xref:System.Windows.Media.VisualBrush.Visual%2A> 에 대 한는 <xref:System.Windows.Media.VisualBrush> 하 고 <xref:System.Windows.Media.Visual> 는 <xref:System.Windows.UIElement> (예: 패널 또는 컨트롤)에서 실행 되는 레이아웃 시스템을 <xref:System.Windows.UIElement> 와 해당 자식 요소 때를 <xref:System.Windows.Media.VisualBrush.AutoLayoutContent%2A> 속성이 `true`. 그러나 루트는 <xref:System.Windows.UIElement> 기본적으로 시스템의 나머지 부분과 격리되어 스타일이며 외부 레이아웃은 이 경계에 침투할 수 없습니다. 루트의 크기를 명시적으로 지정 해야 하므로 <xref:System.Windows.UIElement>만 부모 이기 때문은 <xref:System.Windows.Media.VisualBrush> 하므로 해당 수 없습니다. 자동으로 크기가 조정 자체 그려지는 영역 및 합니다. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]의 레이아웃에 대한 자세한 내용은 [레이아웃](../advanced/layout.md)을 참조하세요.  
  
 좋아요 <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Media.DrawingBrush>및, <xref:System.Windows.Media.VisualBrush> 출력 영역을 채우기 위해 해당 내용을 늘입니다. 의 기본 설정에서 <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성을 변경하여 이 동작을 재정의할 <xref:System.Windows.Media.Stretch.Fill>수 있습니다. 자세한 내용은 <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성을 참조하세요.  
  
<a name="examplevisualbrush1"></a>
## <a name="example-paint-an-object-with-a-visual"></a>예제: 시각적 개체로 개체 그리기  
 다음 예제에서는 여러 컨트롤과 패널을 사용해서 사각형을 그립니다.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/VisualBrushExample.xaml#graphicsmmvisualbrushasrectanglebackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/VisualBrushExample.cs#graphicsmmvisualbrushasrectanglebackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/visualbrushexample.vb#graphicsmmvisualbrushasrectanglebackgroundexample1)]  
  
<a name="examplevisualbrush2"></a>
## <a name="example-create-a-reflection"></a>예제: 리플렉션 만들기  
 앞의 예제에서는 배경으로 사용할 <xref:System.Windows.Media.Visual> 새 새를 만드는 방법을 보여 주어 도있습니다. 를 <xref:System.Windows.Media.VisualBrush> 사용하여 기존 시각적 개체를 표시할 수도 있습니다. 이 기능을 사용하면 반사 및 배율과 같은 흥미로운 시각 효과를 생성할 수 있습니다. 다음 예제에서는 <xref:System.Windows.Media.VisualBrush> a를 사용하여 여러 <xref:System.Windows.Controls.Border> 요소가 포함된 a의 반사를 만듭니다. 다음 그림에서는 이 예제가 생성하는 출력을 보여 줍니다.  
  
 ![반사된 표시 개체](./media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")  
반사된 표시 개체  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 화면의 일부를 확대하는 방법 및 리플렉션을 만드는 방법을 보여 주는 추가 예제를 보려면 [VisualBrush 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush)을 참조하세요.  
  
<a name="tilebrush"></a>
## <a name="tilebrush-features"></a>TileBrush 기능  
 <xref:System.Windows.Media.ImageBrush>및 <xref:System.Windows.Media.DrawingBrush> <xref:System.Windows.Media.VisualBrush> 개체 유형입니다. <xref:System.Windows.Media.TileBrush> <xref:System.Windows.Media.TileBrush>개체는 영역이 이미지, 드로잉 또는 시각적 으로 페인팅되는 방식을 크게 제어할 수 있습니다. 예를 들어 늘어난 이미지만으로 영역을 그리기보다, 패턴을 만드는 일련의 이미지 타일을 사용하여 영역을 그릴 수 있습니다.  
  
 A에는 <xref:System.Windows.Media.TileBrush> 콘텐츠, 타일 및 출력 영역의 세 가지 기본 구성 요소가 있습니다.  
  
 ![TileBrush 구성 요소](./media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk_mmgraphics_defaultcontentprojection2")  
단일 타일이 있는 TileBrush의 구성 요소  
  
 ![바둑판식으로 배열된 TileBrush의 구성 요소](./media/graphicsmm-tiledprojection.png "graphicsmm_tiledprojection")  
여러 타일이 있는 TileBrush의 구성 요소  
  
 개체의 <xref:System.Windows.Media.TileBrush> 타일링 기능에 대한 자세한 내용은 [타일 브러시 개요를](tilebrush-overview.md)참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Media.ImageBrush>
- <xref:System.Windows.Media.DrawingBrush>
- <xref:System.Windows.Media.VisualBrush>
- <xref:System.Windows.Media.TileBrush>
- [TileBrush 개요](tilebrush-overview.md)
- [WPF 브러시 개요](wpf-brushes-overview.md)
- [이미징 개요](imaging-overview.md)
- [Drawing 개체 개요](drawing-objects-overview.md)
- [불투명 마스크 개요](opacity-masks-overview.md)
- [WPF 그래픽 렌더링 개요](wpf-graphics-rendering-overview.md)
- [ImageBrush 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)
- [VisualBrush 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush)
