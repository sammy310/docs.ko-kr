---
title: TileBrush 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TileBrush [WPF]
- brushes [WPF], TileBrush
ms.assetid: aa4a7b7e-d09d-44c2-8d61-310c50e08d68
ms.openlocfilehash: 99bcc8695206030a381d71df2dda495867d3e9c7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187102"
---
# <a name="tilebrush-overview"></a>TileBrush 개요
<xref:System.Windows.Media.TileBrush>개체는 영역이 이미지로 페인팅되는 방식을 크게 제어할 <xref:System.Windows.Media.Drawing>수 <xref:System.Windows.Media.Visual>있습니다. 이 항목에서는 피처를 <xref:System.Windows.Media.TileBrush> 사용하여 영역을 또는 <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Media.DrawingBrush> <xref:System.Windows.Media.VisualBrush> 페인트하는 방법을 보다 세한 제어할 수 있는 방법을 설명합니다.  

<a name="prerequisite"></a>
## <a name="prerequisites"></a>전제 조건  
 이 항목을 이해하려면 <xref:System.Windows.Media.ImageBrush>의 <xref:System.Windows.Media.DrawingBrush> <xref:System.Windows.Media.VisualBrush> 기본 기능을 사용하는 방법을 이해하는 것이 좋습니다. 이러한 유형에 대한 소개는 [이미지, 도면 및 시각적 개체가 있는 페인팅을](painting-with-images-drawings-and-visuals.md)참조하십시오.  
  
<a name="tilebrush"></a>
## <a name="painting-an-area-with-tiles"></a>타일로 영역 그리기  
 <xref:System.Windows.Media.ImageBrush>을 <xref:System.Windows.Media.DrawingBrush>의 <xref:System.Windows.Media.VisualBrush> 하면 <xref:System.Windows.Media.TileBrush> 개체 유형입니다. 타일 브러시는 이미지, 그림 또는 시각적 개체로 영역을 그리는 방법을 강력하게 제어할 수 있도록 합니다. 예를 들어 늘어난 이미지만으로 영역을 그리기보다, 패턴을 만드는 일련의 이미지 타일을 사용하여 영역을 그릴 수 있습니다.  
  
 타일 브러시로 영역을 그리려면 세 가지 구성 요소인, 콘텐츠, 기본 타일 및 출력 영역이 필요합니다.  
  
 ![TileBrush 구성 요소](./media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk_mmgraphics_defaultcontentprojection2")  
단일 타일이 있는 TileBrush의 구성 요소  
  
 ![바둑판식으로 배열된 TileBrush의 구성 요소](./media/graphicsmm-tiledprojection.png "graphicsmm_tiledprojection")  
TileMode가 Tile인 TileBrush의 구성 요소  
  
 출력 <xref:System.Windows.Shapes.Shape.Fill%2A> 영역은 <xref:System.Windows.Shapes.Ellipse> <xref:System.Windows.Controls.Control.Background%2A> <xref:System.Windows.Controls.Button>의 또는 의 와 같이 페인팅되는 영역입니다. 다음 섹션에서는 <xref:System.Windows.Media.TileBrush>의 다른 두 구성 요소에 대해 설명합니다.  
  
<a name="brushcontent"></a>
## <a name="brush-content"></a>브러시 콘텐츠  
 콘텐츠의 다른 유형과 각 페인트의 <xref:System.Windows.Media.TileBrush> 세 가지 유형이 있습니다.  
  
- 브러시가 <xref:System.Windows.Media.ImageBrush>의 경우 이 콘텐츠는 <xref:System.Windows.Media.ImageBrush.ImageSource%2A> 이미지입니다. <xref:System.Windows.Media.ImageBrush>  
  
- 브러시가 a인 <xref:System.Windows.Media.DrawingBrush>경우 이 콘텐츠는 도면입니다. 속성은 <xref:System.Windows.Media.DrawingBrush.Drawing%2A> 의 내용을 <xref:System.Windows.Media.DrawingBrush>지정합니다.  
  
- 브러시가 a인 <xref:System.Windows.Media.VisualBrush>경우 이 콘텐츠는 시각적 개체입니다. 속성은 <xref:System.Windows.Media.VisualBrush.Visual%2A> 의 내용을 지정합니다. <xref:System.Windows.Media.VisualBrush>  
  
 집합을 기본값으로 두는 <xref:System.Windows.Media.TileBrush> 것이 일반적이지만 <xref:System.Windows.Media.TileBrush.Viewbox%2A> 속성을 사용하여 콘텐츠의 위치와 치수를 지정할 수 있습니다. <xref:System.Windows.Media.TileBrush.Viewbox%2A> 기본적으로 <xref:System.Windows.Media.TileBrush.Viewbox%2A> 브러시의 내용을 완전히 포함하도록 구성됩니다. <xref:System.Windows.Controls.Viewbox>구성에 대한 자세한 내용은 <xref:System.Windows.Controls.Viewbox> 속성 페이지를 참조하십시오.  
  
<a name="thebasetile"></a>
## <a name="the-base-tile"></a>기본 타일  
 해당 <xref:System.Windows.Media.TileBrush> 콘텐츠를 기본 타일에 투영합니다. 속성은 <xref:System.Windows.Media.TileBrush.Stretch%2A> 기본 <xref:System.Windows.Media.TileBrush> 타일을 채우기 위해 콘텐츠가 늘어나는 방법을 제어합니다. 속성은 <xref:System.Windows.Media.TileBrush.Stretch%2A> <xref:System.Windows.Media.Stretch> 열거형에 의해 정의된 다음 값을 허용합니다.  
  
- <xref:System.Windows.Media.Stretch.None>: 브러시의 내용물이 타일을 채우기 위해 늘어나지 않습니다.  
  
- <xref:System.Windows.Media.Stretch.Fill>: 브러시의 내용이 타일에 맞게 배율이 조정됩니다. 콘텐츠의 높이 및 너비가 독립적으로 조정되므로 콘텐츠의 원래 가로 세로 비율이 유지되지 않을 수 있습니다. 즉, 출력 타일을 완전히 채우도록 브러시 콘텐츠를 이동해야 할 수 있습니다.  
  
- <xref:System.Windows.Media.Stretch.Uniform>: 브러시의 내용이 타일 에 완전히 맞을 수 있도록 배율이 조정됩니다. 콘텐츠의 가로 세로 비율이 유지됩니다.  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>: 브러시의 내용량이 배율이 조정되어 출력 영역을 완전히 채우는 동시에 콘텐츠의 원래 가로 세로 비율을 유지합니다.  
  
 다음 이미지는 서로 다른 <xref:System.Windows.Media.TileBrush.Stretch%2A> 설정을 보여 줍니다.  
  
 ![여러 TileBrush Stretch 설정](./media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")  
  
 다음 예제에서는 출력 영역을 <xref:System.Windows.Media.ImageBrush> 채우기 위해 늘어나지 않도록 a의 내용이 설정됩니다.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMNoStretchExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/StretchExample.xaml#graphicsmmnostretchexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMNoStretchExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/StretchExample.cs#graphicsmmnostretchexample)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMNoStretchExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/stretchexample.vb#graphicsmmnostretchexample)]  
  
 기본적으로 a는 <xref:System.Windows.Media.TileBrush> 단일 타일(기본 타일)을 생성하고 해당 타일을 확장하여 출력 영역을 완전히 채웁니다. <xref:System.Windows.Media.TileBrush.Viewport%2A> 및 <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 속성을 설정하여 기본 타일의 크기와 위치를 변경할 수 있습니다.  
  
<a name="basetilesize"></a>
### <a name="base-tile-size"></a>기본 타일 크기  
 속성은 <xref:System.Windows.Media.TileBrush.Viewport%2A> 기본 타일의 크기와 위치를 결정하고 <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> <xref:System.Windows.Media.TileBrush.Viewport%2A> 속성은 절대 좌표를 사용하여 지정되는지 또는 상대 좌표를 사용하여 지정되는지 여부를 결정합니다. 상대 좌표인 경우 출력 영역의 크기를 기준으로 합니다. 점 (0,0)은 출력 영역의 왼쪽 위 구석을 나타내고 (1,1)은 출력 영역의 오른쪽 아래 구석을 나타냅니다. 속성에서 <xref:System.Windows.Media.TileBrush.Viewport%2A> 절대 좌표를 사용하도록 지정하려면 <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> <xref:System.Windows.Media.BrushMappingMode.Absolute>속성을 로 설정합니다.  
  
 다음 그림에서는 <xref:System.Windows.Media.TileBrush> 상대와 절대 사이의 출력 <xref:System.Windows.Media.TileBrush.ViewportUnits%2A>차이를 보여 주며. 각 그림은 바둑판식 배열 패턴을 보여 줍니다. 다음 섹션에서는 바둑판식 배열 패턴을 지정하는 방법을 설명합니다.  
  
 ![절대적 및 상대적 뷰포트 단위](./media/absolute-and-relative-viewports.png "absolute_and_relative_viewports")  
  
 다음 예제에서는 이미지를 사용하여 너비 및 높이가 50%인 타일을 만듭니다. 기본 타일은 출력 영역의 (0,0) 위치에 있습니다.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMRelativeViewportUnitsExample1](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileSizeExample.xaml#graphicsmmrelativeviewportunitsexample1)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMRelativeViewportUnitsExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TileSizeExample.cs#graphicsmmrelativeviewportunitsexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMRelativeViewportUnitsExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilesizeexample.vb#graphicsmmrelativeviewportunitsexample1)]  
  
 다음 예제는 25 <xref:System.Windows.Media.ImageBrush> x 25 장치 독립 픽셀의 타일을 설정합니다. <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 절대적이기 때문에 <xref:System.Windows.Media.ImageBrush> 타일은 페인팅되는 영역의 크기에 관계없이 항상 25 x 25 픽셀입니다.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMAbsoluteViewportUnitsExample1](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileSizeExample.xaml#graphicsmmabsoluteviewportunitsexample1)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMAbsoluteViewportUnitsExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TileSizeExample.cs#graphicsmmabsoluteviewportunitsexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMAbsoluteViewportUnitsExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilesizeexample.vb#graphicsmmabsoluteviewportunitsexample1)]  
  
<a name="tilingbehavior"></a>
### <a name="tiling-behavior"></a>바둑판식 배열 동작  
 A는 <xref:System.Windows.Media.TileBrush> 기본 타일이 출력 영역을 완전히 채우지 못하고 타일링 모드가 <xref:System.Windows.Media.TileMode.None> 지정되면 타일패턴이 생성됩니다. 타일 브러시의 타일이 출력 영역을 완전히 채우지 않는 경우 해당 속성은 <xref:System.Windows.Media.TileBrush.TileMode%2A> 출력 영역을 채우기 위해 기본 타일을 복제할지 여부와 경우 기본 타일을 복제하는 방법을 지정합니다. 속성은 <xref:System.Windows.Media.TileBrush.TileMode%2A> <xref:System.Windows.Media.TileMode> 열거형에 의해 정의된 다음 값을 허용합니다.  
  
- <xref:System.Windows.Media.TileMode.None>: 기본 타일만 그려집니다.  
  
- <xref:System.Windows.Media.TileMode.Tile>: 기본 타일이 그려지고 나머지 영역은 한 타일의 오른쪽 가장자리가 다음 타일의 왼쪽 가장자리에 인접하고 아래쪽과 위쪽에 유사하게 기본 타일을 반복하여 채워집니다.  
  
- <xref:System.Windows.Media.TileMode.FlipX>: <xref:System.Windows.Media.TileMode.Tile>와 동일하지만 타일의 대체 열은 가로로 뒤집혀 있습니다.  
  
- <xref:System.Windows.Media.TileMode.FlipY>: 와 <xref:System.Windows.Media.TileMode.Tile>동일하지만 타일의 대체 행은 수직으로 뒤집혀 있습니다.  
  
- <xref:System.Windows.Media.TileMode.FlipXY>: <xref:System.Windows.Media.TileMode.FlipX> 및 <xref:System.Windows.Media.TileMode.FlipY>의 조합 .  
  
 다음 이미지는 여러 다른 바둑판식 배열 모드를 보여 줍니다.  
  
 ![여러 TileBrush TileMode 설정](./media/img-mmgraphics-tilemodes.gif "img_mmgraphics_tilemodes")  
  
 다음 예제에서는 이미지를 사용하여 너비 및 높이가 100x100픽셀인 사각형을 그립니다. 브러시를 <xref:System.Windows.Media.TileBrush.Viewport%2A> 0,0,0.25,0.25로 설정하면 브러시의 기본 타일이 출력 영역의 1/4로 만들어집니다. <xref:System.Windows.Media.TileBrush.TileMode%2A> 브러시가 <xref:System.Windows.Media.TileMode.FlipXY>로 설정됩니다. 이를 통해 타일 행으로 사각형이 채워집니다.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMFlipXYExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TilingExample.xaml#graphicsmmflipxyexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMFlipXYExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TilingExample.cs#graphicsmmflipxyexample)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMFlipXYExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilingexample.vb#graphicsmmflipxyexample)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Media.ImageBrush>
- <xref:System.Windows.Media.DrawingBrush>
- <xref:System.Windows.Media.VisualBrush>
- <xref:System.Windows.Media.TileBrush>
- [이미지, 그림 및 시각적 표시로 그리기](painting-with-images-drawings-and-visuals.md)
- [방법 주제](brushes-how-to-topics.md)
- [Freezable 개체 개요](../advanced/freezable-objects-overview.md)
- [ImageBrush 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)
- [VisualBrush 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush)
