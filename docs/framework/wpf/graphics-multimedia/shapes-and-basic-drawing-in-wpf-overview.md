---
title: 도형 및 기본 도면 개요
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
ms.openlocfilehash: 44104bec478f1fbb10acc0e591af43ea95fecdc5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141330"
---
# <a name="shapes-and-basic-drawing-in-wpf-overview"></a>WPF에서 Shape 및 기본 그리기 개요
이 항목에서는 개체로 <xref:System.Windows.Shapes.Shape> 그리는 방법에 대한 개요를 제공합니다. A는 <xref:System.Windows.Shapes.Shape> 화면에 <xref:System.Windows.UIElement> 셰이프를 그릴 수 있는 유형입니다. UI 요소이므로 <xref:System.Windows.Shapes.Shape> 개체를 요소 내부및 대부분의 컨트롤 내에서 <xref:System.Windows.Controls.Panel> 사용할 수 있습니다.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]는 그래픽 및 렌더링 서비스에 대한 여러 계층의 액세스를 제공합니다. 최상위 계층에서 <xref:System.Windows.Shapes.Shape> 개체는 사용하기 쉽고 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 레이아웃 및 이벤트 시스템 참여와 같은 많은 유용한 기능을 제공합니다.  

<a name="shapes"></a>
## <a name="shape-objects"></a>Shape 개체  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]을 사용하면 바로 사용할 <xref:System.Windows.Shapes.Shape> 수 있는 여러 개체를 제공합니다.  모든 셰이프 개체는 클래스에서 상속됩니다. <xref:System.Windows.Shapes.Shape> 사용 가능한 <xref:System.Windows.Shapes.Ellipse>셰이프 개체에는 " <xref:System.Windows.Shapes.Line>및 <xref:System.Windows.Shapes.Path> <xref:System.Windows.Shapes.Polygon> <xref:System.Windows.Shapes.Polyline> <xref:System.Windows.Shapes.Rectangle>. <xref:System.Windows.Shapes.Shape>개체는 다음과 같은 공통 속성을 공유합니다.  
  
- <xref:System.Windows.Shapes.Shape.Stroke%2A>: 셰이프의 윤곽선이 어떻게 그려지는지 설명합니다.  
  
- <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: 셰이프 윤곽선의 두께를 설명합니다.  
  
- <xref:System.Windows.Shapes.Shape.Fill%2A>: 모양의 내부가 어떻게 그려지는지 설명합니다.  
  
- 디바이스 독립적 픽셀 단위로 측정된 좌표 및 꼭지점을 지정하는 데이터 속성입니다.  
  
 에서 파생되기 <xref:System.Windows.UIElement>때문에 모양 개체는 패널 및 대부분의 컨트롤 내에서 사용할 수 있습니다. 패널은 <xref:System.Windows.Controls.Canvas> 자식 객체의 절대 위치를 지원하기 때문에 복잡한 도면을 작성하는 데 특히 적합합니다.  
  
 클래스를 <xref:System.Windows.Shapes.Line> 사용하면 두 점 사이에 선을 그릴 수 있습니다. 다음 예제에서는 선 좌표 및 스트로크 속성을 지정하는 여러 방법을 보여 줍니다.  
  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 다음 이미지는 렌더링된 <xref:System.Windows.Shapes.Line>을 보여 주며.  
  
 ![선 설명](./media/shape-ovw-line2.gif "shape_ovw_line2")  
  
 클래스는 <xref:System.Windows.Shapes.Line> <xref:System.Windows.Shapes.Shape.Fill%2A> 속성을 제공하지만 a <xref:System.Windows.Shapes.Line> 영역에는 적용되지 않으므로 설정은 영향을 주지 않습니다.  
  
 또 다른 일반적인 <xref:System.Windows.Shapes.Ellipse>모양은 .  셰이프및 <xref:System.Windows.Shapes.Ellipse> <xref:System.Windows.FrameworkElement.Height%2A> 속성을 정의하여 <xref:System.Windows.FrameworkElement.Width%2A> 작성합니다. 원을 그리려면 해당 <xref:System.Windows.Shapes.Ellipse> 및 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> 값이 같을 수를 지정합니다.  
  
 [!code-xaml[ShapeOverviews#ShapesOVW1](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 다음 이미지는 렌더링된 <xref:System.Windows.Shapes.Ellipse>의 예를 보여 주며.  
  
 ![타원 설명](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")  
  
<a name="paths"></a>
## <a name="using-paths-and-geometries"></a>경로 및 기하 도형 사용  
 클래스를 <xref:System.Windows.Shapes.Path> 사용하면 곡선과 복잡한 모양을 그릴 수 있습니다. 이러한 곡선과 모양은 <xref:System.Windows.Media.Geometry> 객체를 사용하여 설명됩니다. 을 <xref:System.Windows.Shapes.Path>사용하여 를 <xref:System.Windows.Media.Geometry> 만들고 이를 사용하여 <xref:System.Windows.Shapes.Path> 개체의 <xref:System.Windows.Shapes.Path.Data%2A> 속성을 설정합니다.  
  
 선택할 수있는 개체의 <xref:System.Windows.Media.Geometry> 다양한있습니다. 의 <xref:System.Windows.Media.LineGeometry> <xref:System.Windows.Media.RectangleGeometry>및 <xref:System.Windows.Media.EllipseGeometry> 클래스는 비교적 간단한 모양을 설명합니다. 더 복잡한 셰이프를 만들거나 곡선을 만들려면 <xref:System.Windows.Media.PathGeometry>을 사용합니다.  
  
<a name="pathgeometry"></a>
### <a name="pathgeometry-and-pathsegments"></a>PathGeometry 및 PathSegments  
 <xref:System.Windows.Media.PathGeometry>개체는 하나 이상의 <xref:System.Windows.Media.PathFigure> 개체로 구성됩니다. 각각다른 <xref:System.Windows.Media.PathFigure> "그림" 또는 모양을 나타냅니다. 각각은 <xref:System.Windows.Media.PathFigure> 하나 이상의 <xref:System.Windows.Media.PathSegment> 개체로 구성되며, 각 개체는 도형 또는 모양의 연결된 부분을 나타냅니다. 세그먼트 유형에는 다음과 <xref:System.Windows.Media.LineSegment> <xref:System.Windows.Media.BezierSegment>같은 <xref:System.Windows.Media.ArcSegment>것이 포함됩니다.  
  
 다음 예제에서는 이차 <xref:System.Windows.Shapes.Path> 베지어 곡선을 그리는 데 사용됩니다.  
  
 [!code-xaml[geometrysample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 다음 그림에서는 렌더링된 도형을 보여 줍니다.  
  
 ![경로 설명](./media/shape-ovw-path2.gif "shape_ovw_path2")  
  
 및 기타 <xref:System.Windows.Media.Geometry> <xref:System.Windows.Media.PathGeometry> 클래스에 대한 자세한 내용은 [지오메트리 개요](geometry-overview.md)를 참조하십시오.  
  
<a name="pathdatastring"></a>
### <a name="xaml-abbreviated-syntax"></a>XAML 약식 구문  
 에서 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 를 설명하는 특수 약어 구문을 사용할 <xref:System.Windows.Shapes.Path>수도 있습니다. 다음 예제에서는 약식 구문이 복잡한 도형을 그리는 데 사용됩니다.  
  
```xaml  
      <Path Stroke="DarkGoldenRod" StrokeThickness="3"
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 다음 이미지는 렌더링된 <xref:System.Windows.Shapes.Path>을 보여 주며.  
  
 ![경로 설명](./media/shape-ovw-path.PNG "shape_ovw_path")  
  
 특성 <xref:System.Windows.Shapes.Path.Data%2A> 문자열은 "moveto" 명령으로 시작되며, M으로 표시되어 <xref:System.Windows.Controls.Canvas>의 좌표계에서 경로에 대한 시작점을 설정합니다. <xref:System.Windows.Shapes.Path>데이터 매개 변수는 대/소문자를 구분합니다. 대문자 M은 새 현재 점에 대한 절대 위치를 나타냅니다. 소문자 m은 상대 좌표를 나타냅니다. 첫 번째 세그먼트는 2개의 제어점 (100,25) 및 (400,350)을 사용하여 그린, (100,200)에서 시작하고 (400,175)에서 끝나는 입방형 3차원 곡선입니다. 이 세그먼트는 <xref:System.Windows.Shapes.Path.Data%2A> 특성 문자열의 C 명령으로 표시됩니다. 마찬가지로 대문자 C는 절대 경로를 나타내고 소문자 c는 상대 경로를 나타냅니다.  
  
 두 번째 세그먼트는 절대 가로 "lineto" 명령 H로 시작합니다. 이 명령은 이전 하위 경로의 엔드포인트(400,175)에서 새 엔드포인트(280,175)까지 그리는 선을 지정합니다. 수평 "lineto" 명령이므로 지정된 값은 *x*좌표입니다.  
  
 전체 경로 구문에 대 <xref:System.Windows.Shapes.Path.Data%2A> 한 참조를 참조 하 고 [경로 지오 메균을 사용 하 여 셰이프 만들기](how-to-create-a-shape-by-using-a-pathgeometry.md)를 참조 합니다.  
  
<a name="fillpaint"></a>
## <a name="painting-shapes"></a>도형 그리기  
 <xref:System.Windows.Media.Brush>오브젝트는 셰이프 및 <xref:System.Windows.Shapes.Shape.Stroke%2A> <xref:System.Windows.Shapes.Shape.Fill%2A>및 을 그리는 데 사용됩니다. 다음 예제에서는 a의 스트로크와 <xref:System.Windows.Shapes.Ellipse> 채우기가 지정됩니다. 브러시 속성에 대한 유효한 입력은 키워드 또는 16진수 색 값일 수 있습니다. 사용 가능한 색상 키워드에 대한 자세한 <xref:System.Windows.Media.Colors> 내용은 <xref:System.Windows.Media> 네임스페이스의 클래스 속성을 참조하세요.  
  
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
  
 다음 이미지는 렌더링된 <xref:System.Windows.Shapes.Ellipse>을 보여 주며.  
  
 ![모든 타원](./media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")  
  
 또는 속성 요소 구문을 사용하여 오브젝트를 <xref:System.Windows.Media.SolidColorBrush> 명시적으로 만들어 단색으로 셰이프를 페인칠할 수 있습니다.  
  
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
  
 ![SolidColorBrush 설명](./media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")  
  
 그라데이션, 이미지, 패턴 등으로 도형의 스트로크나 채우기를 그릴 수도 있습니다. 자세한 내용은 [단색 및 그라데이션이 있는 페인팅 개요를](painting-with-solid-colors-and-gradients-overview.md)참조하십시오.  
  
<a name="stretchableshapessection"></a>
## <a name="stretchable-shapes"></a>확장 가능한 도형  
 의 <xref:System.Windows.Shapes.Line> <xref:System.Windows.Shapes.Path>에 <xref:System.Windows.Shapes.Polygon> <xref:System.Windows.Shapes.Polyline>대한 <xref:System.Windows.Shapes.Rectangle> 및 클래스에는 <xref:System.Windows.Shapes.Shape.Stretch%2A> 모두 속성이 있습니다. 이 속성은 <xref:System.Windows.Shapes.Shape> 오브젝트의 레이아웃 공간을 채우기 <xref:System.Windows.Shapes.Shape> 위해 오브젝트의 내용(그릴 셰이프)을 늘이는 방법을 결정합니다. <xref:System.Windows.Shapes.Shape> 개체의 레이아웃 <xref:System.Windows.Shapes.Shape> 공간은 명시적 <xref:System.Windows.FrameworkElement.Width%2A> 및 설정 또는 해당 <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 설정 및 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 설정으로 인해 레이아웃 시스템에서 할당되는 공간의 양입니다. Windows 프레젠테이션 재단의 레이아웃에 대한 자세한 내용은 [레이아웃](../advanced/layout.md) 개요를 참조하십시오.  
  
 Stretch 속성은 다음 값 중 하나를 사용합니다.  
  
- <xref:System.Windows.Media.Stretch.None>: <xref:System.Windows.Shapes.Shape> 개체의 내용이 늘어나지 않습니다.  
  
- <xref:System.Windows.Media.Stretch.Fill>: <xref:System.Windows.Shapes.Shape> 오브젝트의 내용이 늘어나 레이아웃 공간을 채웁니다.  가로 세로 비율은 유지되지 않습니다.  
  
- <xref:System.Windows.Media.Stretch.Uniform>: <xref:System.Windows.Shapes.Shape> 오브젝트의 내용은 원래 의 가로 세로 비율을 유지하면서 레이아웃 공간을 채우기 위해 가능한 한 많이 늘어납니다.  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>: <xref:System.Windows.Shapes.Shape> 오브젝트의 내용이 늘어나 레이아웃 공간을 완전히 채우고 원래의 가로 세로 비율을 유지합니다.  
  
 <xref:System.Windows.Shapes.Shape> 오브젝트의 내용이 늘어나면 <xref:System.Windows.Shapes.Shape> 스트레칭 후에 오브젝트의 윤곽선이 그려집니다.  
  
 다음 예제에서 a는 <xref:System.Windows.Shapes.Polygon> (0,0)에서 (0,1) ~ (1,1)로 매우 작은 삼각형을 그리는 데 사용됩니다. 개체의 <xref:System.Windows.Shapes.Polygon> <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 100으로 설정되고 스트레치 속성이 채우기로 설정됩니다. 결과적으로 <xref:System.Windows.Shapes.Polygon> 오브젝트의 내용(삼각형)이 늘어나 더 큰 공간을 채웁니다.  
  
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
 클래스는 <xref:System.Windows.Media.Transform> 2차원 평면에서 모양을 변환하는 방법을 제공합니다.  변환의 다른 유형은<xref:System.Windows.Media.RotateTransform>회전 (), 배율 (),<xref:System.Windows.Media.ScaleTransform>기울이기 (),<xref:System.Windows.Media.SkewTransform>및 번역 ()을<xref:System.Windows.Media.TranslateTransform>포함한다.  
  
 도형에 적용하는 일반적인 변환은 회전입니다.  셰이프를 회전하려면 <xref:System.Windows.Media.RotateTransform> 를 만들고 <xref:System.Windows.Media.RotateTransform.Angle%2A>을 지정합니다. 45의 A는 <xref:System.Windows.Media.RotateTransform.Angle%2A> 요소를 시계 방향으로 45도 회전합니다. 90의 각도는 요소를 시계 방향으로 90도 회전합니다. 등등. 요소가 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 회전되는 점을 제어하려면 및 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 속성을 설정합니다. 이러한 속성 값은 변환할 요소의 좌표 공간으로 표현됩니다. <xref:System.Windows.Media.RotateTransform.CenterX%2A><xref:System.Windows.Media.RotateTransform.CenterY%2A> 기본값이 0입니다. 마지막으로 요소에 <xref:System.Windows.Media.RotateTransform> 적용합니다. 변환이 레이아웃에 영향을 주지 않도록 하려면 셰이프의 <xref:System.Windows.UIElement.RenderTransform%2A> 속성을 설정합니다.  
  
 다음 예제에서는 셰이프의 <xref:System.Windows.Media.RotateTransform> 왼쪽 위 모서리(0,0)를 사용하여 셰이프를 45도 회전하는 데 사용됩니다.  
  
 [!code-xaml[transformssample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 다음 예제에서는 다른 모양이 45도 회전되지만 이번에는 점 (25,50)을 기준으로 회전됩니다.  
  
 [!code-xaml[transformssample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 다음 그림에서는 두 변환을 적용한 결과를 보여 줍니다.  
  
 ![여러 중심점을 사용한 45도 회전](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")  
  
 이전 예제에서는 각 도형 개체에 단일 변환이 적용되었습니다. 셰이프(또는 다른 UI 요소)에 여러 변환을 <xref:System.Windows.Media.TransformGroup>적용하려면 을 사용합니다.  
  
## <a name="see-also"></a>참고 항목

- [2D 그래픽 및 이미징](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [단색 및 그라데이션을 사용한 그리기 개요](painting-with-solid-colors-and-gradients-overview.md)
- [Geometry 개요](geometry-overview.md)
- [연습: 첫 번째 WPF 데스크톱 응용 프로그램](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
- [애니메이션 개요](animation-overview.md)
