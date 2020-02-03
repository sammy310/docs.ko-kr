---
title: 도형 및 기본 그리기 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- shapes [WPF], about shapes
- basic drawing [WPF]
- vector drawing [WPF], overview
- vectors [WPF], drawing
- Shape objects [WPF]
ms.assetid: 66d7a6d6-e3b6-47bc-8dfe-8a1b26f7d901
ms.openlocfilehash: dfdbf67d35cbb13e80d0c5184f165b0cc660e2ef
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731629"
---
# <a name="shapes-and-basic-drawing-in-wpf-overview"></a>WPF에서 Shape 및 기본 그리기 개요
이 항목에서는 <xref:System.Windows.Shapes.Shape> 개체로 그리는 방법에 대 한 개요를 제공 합니다. <xref:System.Windows.Shapes.Shape>는 화면에 모양을 그릴 수 있는 <xref:System.Windows.UIElement>의 유형입니다. 이러한 요소는 UI 요소 이기 때문에 <xref:System.Windows.Controls.Panel> 요소와 대부분의 컨트롤 내에서 <xref:System.Windows.Shapes.Shape> 개체를 사용할 수 있습니다.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]는 그래픽 및 렌더링 서비스에 대한 여러 계층의 액세스를 제공합니다. 최상위 계층에서 <xref:System.Windows.Shapes.Shape> 개체는 쉽게 사용할 수 있으며 레이아웃 및 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 이벤트 시스템 참여와 같은 많은 유용한 기능을 제공 합니다.  

<a name="shapes"></a>   
## <a name="shape-objects"></a>Shape 개체  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 사용할 수 있는 다양 한 <xref:System.Windows.Shapes.Shape> 개체를 제공 합니다.  모든 shape 개체는 <xref:System.Windows.Shapes.Shape> 클래스에서 상속 합니다. 사용 가능한 shape 개체에는 <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>및 <xref:System.Windows.Shapes.Rectangle>가 포함 됩니다. <xref:System.Windows.Shapes.Shape> 개체는 다음과 같은 공용 속성을 공유 합니다.  
  
- <xref:System.Windows.Shapes.Shape.Stroke%2A>: 도형의 윤곽선을 그리는 방법을 설명 합니다.  
  
- <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: 셰이프 윤곽선의 두께를 설명 합니다.  
  
- <xref:System.Windows.Shapes.Shape.Fill%2A>: 도형의 내부를 칠하는 방법을 설명 합니다.  
  
- 디바이스 독립적 픽셀 단위로 측정된 좌표 및 꼭지점을 지정하는 데이터 속성입니다.  
  
 <xref:System.Windows.UIElement>에서 파생 되므로 패널 및 대부분의 컨트롤 내에서 shape 개체를 사용할 수 있습니다. <xref:System.Windows.Controls.Canvas> 패널은 자식 개체의 절대 위치 지정을 지원 하기 때문에 복잡 한 그리기를 만드는 데 특히 적합 합니다.  
  
 <xref:System.Windows.Shapes.Line> 클래스를 사용 하면 두 요소 사이에 선을 그릴 수 있습니다. 다음 예제에서는 선 좌표 및 스트로크 속성을 지정하는 여러 방법을 보여 줍니다.  
  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 다음 이미지는 렌더링 된 <xref:System.Windows.Shapes.Line>를 보여 줍니다.  
  
 ![선 그림](./media/shape-ovw-line2.gif "shape_ovw_line2")  
  
 <xref:System.Windows.Shapes.Line> 클래스는 <xref:System.Windows.Shapes.Shape.Fill%2A> 속성을 제공 하지만 <xref:System.Windows.Shapes.Line>에 영역이 없으므로이 속성을 설정 해도 아무런 효과가 없습니다.  
  
 또 다른 일반적인 셰이프는 <xref:System.Windows.Shapes.Ellipse>입니다.  셰이프의 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 정의 하 여 <xref:System.Windows.Shapes.Ellipse>를 만듭니다. 원을 그리려면 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 값이 같은 <xref:System.Windows.Shapes.Ellipse>를 지정 합니다.  
  
 [!code-xaml[ShapeOverviews#ShapesOVW1](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 다음 그림은 렌더링 된 <xref:System.Windows.Shapes.Ellipse>의 예를 보여 줍니다.  
  
 ![타원 그림](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")  
  
<a name="paths"></a>   
## <a name="using-paths-and-geometries"></a>경로 및 기하 도형 사용  
 <xref:System.Windows.Shapes.Path> 클래스를 사용 하 여 곡선 및 복잡 한 도형을 그릴 수 있습니다. 이러한 곡선 및 도형은 <xref:System.Windows.Media.Geometry> 개체를 사용 하 여 설명 됩니다. <xref:System.Windows.Shapes.Path>를 사용 하려면 <xref:System.Windows.Media.Geometry>를 만든 후이를 사용 하 여 <xref:System.Windows.Shapes.Path> 개체의 <xref:System.Windows.Shapes.Path.Data%2A> 속성을 설정 합니다.  
  
 선택할 수 있는 다양 한 <xref:System.Windows.Media.Geometry> 개체가 있습니다. <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>및 <xref:System.Windows.Media.EllipseGeometry> 클래스는 상대적으로 간단한 도형을 설명 합니다. 더 복잡 한 도형을 만들거나 곡선을 만들려면 <xref:System.Windows.Media.PathGeometry>를 사용 합니다.  
  
<a name="pathgeometry"></a>   
### <a name="pathgeometry-and-pathsegments"></a>PathGeometry 및 PathSegments  
 <xref:System.Windows.Media.PathGeometry> 개체는 하나 이상의 <xref:System.Windows.Media.PathFigure> 개체로 구성 됩니다. 각 <xref:System.Windows.Media.PathFigure>는 다른 "그림" 또는 도형을 나타냅니다. 각 <xref:System.Windows.Media.PathFigure>은 각각 그림 또는 모양의 연결 된 부분을 나타내는 하나 이상의 <xref:System.Windows.Media.PathSegment> 개체로 구성 됩니다. 세그먼트 형식은 <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.BezierSegment>및 <xref:System.Windows.Media.ArcSegment>를 포함 합니다.  
  
 다음 예에서는 <xref:System.Windows.Shapes.Path>를 사용 하 여 정방형 3 차원 곡선을 그립니다.  
  
 [!code-xaml[geometrysample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 다음 그림에서는 렌더링된 도형을 보여 줍니다.  
  
 ![경로 그림](./media/shape-ovw-path2.gif "shape_ovw_path2")  
  
 <xref:System.Windows.Media.PathGeometry> 및 기타 <xref:System.Windows.Media.Geometry> 클래스에 대 한 자세한 내용은 [Geometry 개요](geometry-overview.md)를 참조 하세요.  
  
<a name="pathdatastring"></a>   
### <a name="xaml-abbreviated-syntax"></a>XAML 약식 구문  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 특수 한 약어 구문을 사용 하 여 <xref:System.Windows.Shapes.Path>를 설명할 수도 있습니다. 다음 예제에서는 약식 구문이 복잡한 도형을 그리는 데 사용됩니다.  
  
```xaml  
      <Path Stroke="DarkGoldenRod" StrokeThickness="3"   
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 다음 이미지는 렌더링 된 <xref:System.Windows.Shapes.Path>를 보여 줍니다.  
  
 ![경로 그림](./media/shape-ovw-path.PNG "shape_ovw_path")  
  
 <xref:System.Windows.Shapes.Path.Data%2A> 특성 문자열은 M으로 표시 되는 "moveto" 명령으로 시작 하며,이 명령은 <xref:System.Windows.Controls.Canvas>의 좌표계에서 경로에 대 한 시작점을 설정 합니다. <xref:System.Windows.Shapes.Path> 데이터 매개 변수는 대/소문자를 구분 합니다. 대문자 M은 새 현재 점의 절대 위치를 나타냅니다. 소문자 m은 상대 좌표를 나타냅니다. 첫 번째 세그먼트는 2개의 제어점 (100,25) 및 (400,350)을 사용하여 그린, (100,200)에서 시작하고 (400,175)에서 끝나는 입방형 3차원 곡선입니다. 이 세그먼트는 <xref:System.Windows.Shapes.Path.Data%2A> 특성 문자열에서 C 명령으로 표시 됩니다. 마찬가지로 대문자 C는 절대 경로를 나타내고 소문자 c는 상대 경로를 나타냅니다.  
  
 두 번째 세그먼트는 절대 가로 "lineto" 명령 H로 시작합니다. 이 명령은 이전 하위 경로의 엔드포인트(400,175)에서 새 엔드포인트(280,175)까지 그리는 선을 지정합니다. 이는 가로 "lineto" 명령 이므로 지정 된 값은 *x*좌표입니다.  
  
 전체 경로 구문은 <xref:System.Windows.Shapes.Path.Data%2A> 참조 및 [PathGeometry를 사용 하 여 도형 만들기](how-to-create-a-shape-by-using-a-pathgeometry.md)를 참조 하세요.  
  
<a name="fillpaint"></a>   
## <a name="painting-shapes"></a>도형 그리기  
 <xref:System.Windows.Media.Brush> 개체는 셰이프의 <xref:System.Windows.Shapes.Shape.Stroke%2A> 및 <xref:System.Windows.Shapes.Shape.Fill%2A>을 그리는 데 사용 됩니다. 다음 예제에서는 <xref:System.Windows.Shapes.Ellipse>의 스트로크와 채우기를 지정 합니다. 브러시 속성에 대한 유효한 입력은 키워드 또는 16진수 색 값일 수 있습니다. 사용 가능한 색 키워드에 대 한 자세한 내용은 <xref:System.Windows.Media> 네임 스페이스의 <xref:System.Windows.Media.Colors> 클래스 속성을 참조 하세요.  
  
```xaml
<Canvas Background="LightGray">   
   <Ellipse  
      Canvas.Top="50"  
      Canvas.Left="50"  
      Fill="#FFFFFF00"  
      Height="75"  
      Width="75"  
      StrokeThickness="5"  
      Stroke="#FF0000FF"/>  
</Canvas>  
```  
  
 다음 이미지는 렌더링 된 <xref:System.Windows.Shapes.Ellipse>를 보여 줍니다.  
  
 ![타원](./media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")  
  
 또는 속성 요소 구문을 사용 하 여 <xref:System.Windows.Media.SolidColorBrush> 개체를 명시적으로 만들어 단색으로 도형을 그릴 수 있습니다.  
  
```xaml
<!-- This polygon shape uses pre-defined color values for its Stroke and  
     Fill properties.   
     The SolidColorBrush's Opacity property affects the fill color in   
     this case by making it slightly transparent (opacity of 0.4) so   
     that it blends with any underlying color. -->  
  
<Polygon  
    Points="300,200 400,125 400,275 300,200"  
    Stroke="Purple"   
    StrokeThickness="2">  
    <Polygon.Fill>  
       <SolidColorBrush Color="Blue" Opacity="0.4"/>  
    </Polygon.Fill>  
</Polygon>  
```  
  
 다음 그림은 렌더링된 도형을 보여 줍니다.  
  
 ![System.windows.media.solidcolorbrush> 그림](./media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")  
  
 그라데이션, 이미지, 패턴 등으로 도형의 스트로크나 채우기를 그릴 수도 있습니다. 자세한 내용은 [단색 및 그라데이션을 사용한 그리기 개요](painting-with-solid-colors-and-gradients-overview.md)를 참조 하세요.  
  
<a name="stretchableshapessection"></a>   
## <a name="stretchable-shapes"></a>확장 가능한 도형  
 <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>및 <xref:System.Windows.Shapes.Rectangle> 클래스에는 모두 <xref:System.Windows.Shapes.Shape.Stretch%2A> 속성이 있습니다. 이 속성은 <xref:System.Windows.Shapes.Shape> 개체의 레이아웃 공간을 채우도록 <xref:System.Windows.Shapes.Shape> 개체의 콘텐츠 (그릴 도형)를 늘이는 방법을 결정 합니다. <xref:System.Windows.Shapes.Shape> 개체의 레이아웃 공간은 명시적 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 설정 또는 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 및 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 설정으로 인해 레이아웃 시스템에서 <xref:System.Windows.Shapes.Shape> 할당 하는 공간 크기입니다. Windows Presentation Foundation의 레이아웃에 대 한 자세한 내용은 [레이아웃](../advanced/layout.md) 개요를 참조 하세요.  
  
 Stretch 속성은 다음 값 중 하나를 사용합니다.  
  
- <xref:System.Windows.Media.Stretch.None>: <xref:System.Windows.Shapes.Shape> 개체의 내용이 늘어나지 않습니다.  
  
- <xref:System.Windows.Media.Stretch.Fill>: <xref:System.Windows.Shapes.Shape> 개체의 콘텐츠가 레이아웃 공간을 채우도록 늘어납니다.  가로 세로 비율은 유지되지 않습니다.  
  
- <xref:System.Windows.Media.Stretch.Uniform>: <xref:System.Windows.Shapes.Shape> 개체의 내용이 원래 가로 세로 비율을 유지 하면서 레이아웃 공간을 채울 수 있는 만큼 늘어납니다.  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>: <xref:System.Windows.Shapes.Shape> 개체의 내용이 원래의 가로 세로 비율을 유지 하면서 레이아웃 공간을 완전히 채우도록 확장 됩니다.  
  
 <xref:System.Windows.Shapes.Shape> 개체의 내용이 늘어나는 경우 스트레치 후 <xref:System.Windows.Shapes.Shape> 개체의 윤곽선이 그려집니다.  
  
 다음 예제에서 <xref:System.Windows.Shapes.Polygon>는 (0, 0)에서 (0, 1) (1, 1)까지 매우 작은 삼각형을 그리는 데 사용 됩니다. <xref:System.Windows.Shapes.Polygon> 개체의 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A>는 100로 설정 되 고 해당 stretch 속성은 Fill로 설정 됩니다. 따라서 <xref:System.Windows.Shapes.Polygon> 개체의 내용 (삼각형)이 더 큰 공간을 채우도록 늘어납니다.  
  
```xaml
<Polygon  
  Points="0,0 0,1 1,1"  
  Fill="Blue"  
  Width="100"  
  Height="100"  
  Stretch="Fill"  
  Stroke="Black"  
  StrokeThickness="2" />  
```

```csharp
PointCollection myPointCollection = new PointCollection();  
myPointCollection.Add(new Point(0,0));  
myPointCollection.Add(new Point(0,1));  
myPointCollection.Add(new Point(1,1));  
  
Polygon myPolygon = new Polygon();  
myPolygon.Points = myPointCollection;  
myPolygon.Fill = Brushes.Blue;  
myPolygon.Width = 100;  
myPolygon.Height = 100;  
myPolygon.Stretch = Stretch.Fill;  
myPolygon.Stroke = Brushes.Black;  
myPolygon.StrokeThickness = 2;  
```

<a name="transforms"></a>   
## <a name="transforming-shapes"></a>도형 변환  
 <xref:System.Windows.Media.Transform> 클래스는 2 차원 평면의 셰이프를 변환 하는 방법을 제공 합니다.  다양 한 유형의 변환에는 회전 (<xref:System.Windows.Media.RotateTransform>), 크기 조정 (<xref:System.Windows.Media.ScaleTransform>), 기울이기 (<xref:System.Windows.Media.SkewTransform>) 및 변환 (<xref:System.Windows.Media.TranslateTransform>)이 포함 됩니다.  
  
 도형에 적용하는 일반적인 변환은 회전입니다.  도형을 회전 하려면 <xref:System.Windows.Media.RotateTransform> 만들고 해당 <xref:System.Windows.Media.RotateTransform.Angle%2A>를 지정 합니다. 45의 <xref:System.Windows.Media.RotateTransform.Angle%2A>는 요소를 45도 시계 방향으로 회전 합니다. 90의 각도는 요소를 90도 시계 방향으로 회전 합니다. 합니다. 요소가 회전 되는 지점을 제어 하려면 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 및 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 속성을 설정 합니다. 이러한 속성 값은 변환할 요소의 좌표 공간으로 표현됩니다. <xref:System.Windows.Media.RotateTransform.CenterX%2A> 및 <xref:System.Windows.Media.RotateTransform.CenterY%2A>의 기본값은 0입니다. 마지막으로 요소에 <xref:System.Windows.Media.RotateTransform>을 적용 합니다. 변환이 레이아웃에 영향을 주지 않도록 하려면 셰이프의 <xref:System.Windows.UIElement.RenderTransform%2A> 속성을 설정 합니다.  
  
 다음 예제에서 <xref:System.Windows.Media.RotateTransform>은 셰이프의 왼쪽 위 모퉁이 (0, 0)에 대 한 도형 45 각도를 회전 하는 데 사용 됩니다.  
  
 [!code-xaml[transformssample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 다음 예제에서는 다른 모양이 45도 회전되지만 이번에는 점 (25,50)을 기준으로 회전됩니다.  
  
 [!code-xaml[transformssample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 다음 그림에서는 두 변환을 적용한 결과를 보여 줍니다.  
  
 ![여러 중심점을 사용한 45도 회전](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")  
  
 이전 예제에서는 각 도형 개체에 단일 변환이 적용되었습니다. 도형 또는 다른 UI 요소에 여러 변환을 적용 하려면 <xref:System.Windows.Media.TransformGroup>을 사용 합니다.  
  
## <a name="see-also"></a>참고 항목

- [2차원 그래픽 및 이미징](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [단색 및 그라데이션을 사용한 그리기 개요](painting-with-solid-colors-and-gradients-overview.md)
- [Geometry 개요](geometry-overview.md)
- [연습: 내 첫 WPF 데스크톱 애플리케이션](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
- [애니메이션 개요](animation-overview.md)
