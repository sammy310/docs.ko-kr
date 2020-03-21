---
title: Geometry 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometry classes [WPF]
- graphics [WPF], geometry classes
ms.assetid: 9fba8934-98b7-4af6-82f6-f4ef887f963a
ms.openlocfilehash: ff42e59edd9d98b0b52dc3bdd3ace0c35df60878
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112377"
---
# <a name="geometry-overview"></a>Geometry 개요
이 개요는 클래스를 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Media.Geometry> 사용하여 셰이프를 설명하는 방법을 설명합니다. 이 항목에서는 개체와 <xref:System.Windows.Media.Geometry> <xref:System.Windows.Shapes.Shape> 요소 간의 차이점도 대조합니다.  

<a name="wcpsdk_graphics_geometry_introduction"></a>
## <a name="what-is-a-geometry"></a>기하 도형이란?  
 <xref:System.Windows.Media.Geometry> 클래스와 클래스(예: <xref:System.Windows.Media.EllipseGeometry>에서 <xref:System.Windows.Media.PathGeometry>파생되는 클래스)를 <xref:System.Windows.Media.CombinedGeometry>비롯한 및 에서 파생되는 클래스를 사용하면 2D 셰이프의 형상을 설명할 수 있습니다. 이러한 기하학적 설명은 화면에 그릴 도형 정의 또는 적중 테스트 및 클립 영역을 정의와 같은 다양한 용도로 사용됩니다. 애니메이션 경로를 정의하는 데도 기하 도형을 사용할 수 있습니다.  
  
 <xref:System.Windows.Media.Geometry>개체는 둘 이상의 형상 객체에서 작성된 사각형 및 원 또는 복합과 같이 단순할 수 있습니다.  호와 곡선을 설명할 수 <xref:System.Windows.Media.PathGeometry> 있는 <xref:System.Windows.Media.StreamGeometry> 클래스와 클래스를 사용하여 보다 복잡한 형상을 작성할 수 있습니다.  
  
 a는 <xref:System.Windows.Media.Geometry> <xref:System.Windows.Freezable>의 <xref:System.Windows.Media.Geometry> 유형이기 때문에 개체는 몇 가지 특수 기능을 제공합니다: [리소스로](../../../desktop-wpf/fundamentals/xaml-resources-define.md)선언하고, 여러 개체 간에 공유되고, 읽기 전용으로 만들어 성능을 향상시키고, 복제하고, 스레드를 안전하게 만들 수 있습니다. 제공 하는 다른 기능에 대 한 자세한 <xref:System.Windows.Freezable> 개체를 참조 합니다 [Freezable 개체 개요](../advanced/freezable-objects-overview.md)합니다.  
  
<a name="wcpsdk_graphics_geometry_geometryandshapes"></a>
## <a name="geometries-vs-shapes"></a>형상 대 모양  
 <xref:System.Windows.Media.Geometry> 클래스와 <xref:System.Windows.Shapes.Shape> 클래스는 모두 2D 모양(비교 <xref:System.Windows.Media.EllipseGeometry> 및 <xref:System.Windows.Shapes.Ellipse> 예)을 설명한다는 점에서 비슷해 보이지만 중요한 차이점이 있습니다.  
  
 하나에 대 <xref:System.Windows.Media.Geometry> 한 클래스는 <xref:System.Windows.Freezable> 클래스에서 <xref:System.Windows.Shapes.Shape> 상속 하는 <xref:System.Windows.FrameworkElement>동안 클래스에서 상속 합니다. 요소는 요소이므로 <xref:System.Windows.Shapes.Shape> 개체는 자신을 렌더링하고 레이아웃 시스템에 참여할 <xref:System.Windows.Media.Geometry> 수 있지만 개체는 참여할 수 없습니다.  
  
 개체는 개체보다 <xref:System.Windows.Shapes.Shape> <xref:System.Windows.Media.Geometry> 쉽게 사용할 수 <xref:System.Windows.Media.Geometry> 있지만 개체는 더 다양합니다. <xref:System.Windows.Shapes.Shape> 오브젝트가 2D 그래픽을 렌더링하는 <xref:System.Windows.Media.Geometry> 데 사용되는 동안 오브젝트는 2D 그래픽에 대한 형상 영역을 정의하거나, 클리핑을 위한 영역을 정의하거나, 적중 테스트를 위한 영역을 정의하는 데 사용할 수 있습니다.  
  
### <a name="the-path-shape"></a>경로 도형  
 클래스는 <xref:System.Windows.Shapes.Shape> <xref:System.Windows.Shapes.Path> 실제로 a를 <xref:System.Windows.Media.Geometry> 사용하여 내용을 설명합니다. 의 <xref:System.Windows.Shapes.Path.Data%2A> 속성을 <xref:System.Windows.Shapes.Path> 와 서 <xref:System.Windows.Media.Geometry> 설정 하 <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Shape.Stroke%2A> 고 해당 및 <xref:System.Windows.Media.Geometry>속성을 설정 하 여 렌더링할 수 있습니다.  
  
<a name="commonproperties"></a>
## <a name="common-properties-that-take-a-geometry"></a>Geometry를 사용하는 공용 속성  
 이전 섹션에서는 Geometry 개체를 도형 그리기, 애니메이션 효과 적용, 클리핑 등의 다양한 용도로 다른 개체와 함께 사용할 수 있다는 사실을 설명했습니다. 다음 표에는 개체를 수는 속성이 있는 여러 클래스가 나열되어 있습니다. <xref:System.Windows.Media.Geometry>  
  
|Type|속성|  
|----------|--------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>|  
|<xref:System.Windows.Media.DrawingGroup>|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|  
|<xref:System.Windows.Media.GeometryDrawing>|<xref:System.Windows.Media.GeometryDrawing.Geometry%2A>|  
|<xref:System.Windows.Shapes.Path>|<xref:System.Windows.Shapes.Path.Data%2A>|  
|<xref:System.Windows.UIElement>|<xref:System.Windows.UIElement.Clip%2A>|  
  
<a name="wcpsdk_graphics_geometry_geometrytypes"></a>
## <a name="simple-geometry-types"></a>단순 기하 도형 형식  
 모든 형상의 기본 클래스는 추상 클래스입니다. <xref:System.Windows.Media.Geometry>  <xref:System.Windows.Media.Geometry> 클래스에서 파생되는 클래스는 대략 간단한 형상, 경로 형상 및 복합 형상의 세 가지 범주로 그룹화할 수 있습니다.  
  
 단순 형상 클래스에는 <xref:System.Windows.Media.RectangleGeometry>에 <xref:System.Windows.Media.EllipseGeometry> 의한 <xref:System.Windows.Media.LineGeometry>및 선, 사각형 및 원과 같은 기본 기하학적 모양을 작성하는 데 사용됩니다.  
  
- A는 <xref:System.Windows.Media.LineGeometry> 선의 시작점과 끝점을 지정하여 정의됩니다.  
  
- A는 <xref:System.Windows.Media.RectangleGeometry> 상대적 <xref:System.Windows.Rect> 위치와 높이 및 너비를 지정하는 구조로 정의됩니다. <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> 및 <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> 속성을 설정하여 둥근 사각형을 만들 수 있습니다.  
  
- A는 <xref:System.Windows.Media.EllipseGeometry> 중심점, x 반지름 및 y 반지름으로 정의됩니다.  다음 예제에서는 렌더링 및 클리핑을 위한 단순 기하 도형을 만드는 방법을 보여 줍니다.  
  
 이러한 동일한 모양과 더 복잡한 셰이프는 형상 <xref:System.Windows.Media.PathGeometry> 객체를 함께 결합하거나 결합하여 만들 수 있지만 이러한 클래스는 이러한 기본 기하학적 모양을 생성하기 위한 더 간단한 수단을 제공합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.LineGeometry>을 만들고 렌더링하는 방법을 보여 주어집니다.  앞서 설명한 <xref:System.Windows.Media.Geometry> 것처럼 오브젝트는 자체를 그릴 수 없으므로 <xref:System.Windows.Shapes.Path> 예제에서는 셰이프를 사용하여 선을 렌더링합니다.  선에는 영역이 없으므로 의 <xref:System.Windows.Shapes.Shape.Fill%2A> 속성을 <xref:System.Windows.Shapes.Path> 설정하면 효과가 없습니다. 대신 <xref:System.Windows.Shapes.Shape.Stroke%2A> 및 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 속성만 지정됩니다. 다음 그림에서는 예제의 출력을 보여 줍니다.  
  
 ![LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")  
(10,20)부터 (100,130)까지 그린 LineGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 다음 예제에서는 <xref:System.Windows.Media.EllipseGeometry>을 만들고 렌더링하는 방법을 보여 주어집니다.  예제에서는 <xref:System.Windows.Media.EllipseGeometry.Center%2A> <xref:System.Windows.Media.EllipseGeometry> 의 설정이 점으로 `50,50` 설정되고 x 반지름과 y 반지름이 모두 `50`설정되어 지름이 100인 원을 만듭니다.  이 경우 <xref:System.Windows.Media.Brushes.Gold%2A>타원의 내부는 Path 요소의 채우기 속성에 값을 할당하여 페인팅됩니다. 다음 그림에서는 예제의 출력을 보여 줍니다.  
  
 ![EllipseGeometry](./media/graphicsmm-ellipse.gif "graphicsmm_ellipse")  
(50,50)에 그린 EllipseGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmellipsegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmellipsegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmellipsegeometryexample)]  
  
 다음 예제에서는 <xref:System.Windows.Media.RectangleGeometry>을 만들고 렌더링하는 방법을 보여 주어집니다.  사각형의 위치와 치수는 구조체에 <xref:System.Windows.Rect> 의해 정의됩니다. 위치는 `50,50`이고 높이 및 너비 둘 다 `25`이므로 정사각형을 만듭니다. 다음 그림에서는 예제의 출력을 보여 줍니다.  
  
 ![RectangleGeometry](./media/graphicsmm-rectangle.gif "graphicsmm_rectangle")  
50,50에 그린 RectangleGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 다음 예제에서는 이미지에 <xref:System.Windows.Media.EllipseGeometry> 대 한 클립 영역으로 사용 하는 방법을 보여 주어 있습니다.  <xref:System.Windows.Controls.Image> 개체는 200과 <xref:System.Windows.FrameworkElement.Height%2A> 150으로 정의됩니다. <xref:System.Windows.FrameworkElement.Width%2A>  <xref:System.Windows.Media.EllipseGeometry.RadiusX%2A> 값이 <xref:System.Windows.Media.EllipseGeometry.RadiusY%2A> 100이고 값이 75이고 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 값이 100,75인 A는 <xref:System.Windows.UIElement.Clip%2A> <xref:System.Windows.Media.EllipseGeometry> 이미지 의 속성으로 설정됩니다.  타원 영역 내의 이미지 부분만 표시됩니다. 다음 그림에서는 예제의 출력을 보여 줍니다.  
  
 ![클리핑이 있는 이미지와 없는 이미지](./media/graphicsmm-clipexample.png "graphicsmm_clipexample")  
Image 컨트롤 클리핑에 사용되는 EllipseGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmimageclipgeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmimageclipgeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmimageclipgeometryexample)]  
  
<a name="wcpsdk_graphics_geometry_pathgeometry"></a>
## <a name="path-geometries"></a>경로 기하 도형  
 클래스와 해당 경량 <xref:System.Windows.Media.PathGeometry> <xref:System.Windows.Media.StreamGeometry> 등가물 인 클래스는 호, 곡선 및 선으로 구성된 여러 복잡한 그림을 설명하는 수단을 제공합니다.  
  
 a의 <xref:System.Windows.Media.PathGeometry> 중심에는 <xref:System.Windows.Media.PathFigure> 개체 컬렉션이 있으므로 각 그림은 <xref:System.Windows.Media.PathGeometry>에서 개별 모양을 설명하기 때문에 명명됩니다. 각각은 <xref:System.Windows.Media.PathFigure> 하나 이상의 <xref:System.Windows.Media.PathSegment> 개체로 구성되며, 각 개체는 그림의 세그먼트를 설명합니다.  
  
 세그먼트 형식은 다양합니다.  
  
|세그먼트 형식|Description|예제|  
|------------------|-----------------|-------------|  
|<xref:System.Windows.Media.ArcSegment>|두 점 사이에 타원형 호를 만듭니다.|[타원형 호를 만듭니다.](how-to-create-an-elliptical-arc.md)|  
|<xref:System.Windows.Media.BezierSegment>|두 점 사이에 입방형 3차원 곡선을 만듭니다.|[입방 베지어 곡선을 만듭니다.](how-to-create-a-cubic-bezier-curve.md)|  
|<xref:System.Windows.Media.LineSegment>|두 점 사이에 선을 만듭니다.|[PathGeometry에 LineSegment 만들기](how-to-create-a-linesegment-in-a-pathgeometry.md)|  
|<xref:System.Windows.Media.PolyBezierSegment>|일련의 입방형 3차원 곡선을 만듭니다.|<xref:System.Windows.Media.PolyBezierSegment> 입력 페이지를 참조하십시오.|  
|<xref:System.Windows.Media.PolyLineSegment>|일련의 줄을 만듭니다.|<xref:System.Windows.Media.PolyLineSegment> 입력 페이지를 참조하십시오.|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|일련의 정방형 3차원 곡선을 만듭니다.|<xref:System.Windows.Media.PolyQuadraticBezierSegment> 페이지를 참조하십시오.|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|정방형 3차원 곡선을 만듭니다.|[이차 베지어 곡선을 만듭니다.](how-to-create-a-quadratic-bezier-curve.md)|  
  
 a <xref:System.Windows.Media.PathFigure> 내의 세그먼트는 단일 기하학적 모양으로 결합되고 각 세그먼트의 끝점은 다음 세그먼트의 시작점이 됩니다. 속성은 <xref:System.Windows.Media.PathFigure.StartPoint%2A> <xref:System.Windows.Media.PathFigure> 첫 번째 세그먼트가 그려지는 점을 지정합니다. 각 후속 세그먼트는 이전 세그먼트의 끝점에서 시작합니다. 예를 `10,50` 들어 에서 세로 `10,150` 선은 <xref:System.Windows.Media.PathFigure.StartPoint%2A> 속성을 `10,50` 로 설정하고 <xref:System.Windows.Media.LineSegment> <xref:System.Windows.Media.LineSegment.Point%2A> `10,150`의 속성 설정을 사용하여 만들면 정의할 수 있습니다.  
  
 <xref:System.Windows.Media.PathGeometry> 다음 예제는 a를 <xref:System.Windows.Media.PathFigure> <xref:System.Windows.Media.LineSegment> 가진 단일로 구성된 간단한 <xref:System.Windows.Shapes.Path> 을 만들고 요소를 사용하여 표시합니다. 개체가 <xref:System.Windows.Media.PathFigure> 로 <xref:System.Windows.Media.PathFigure.StartPoint%2A> `10,20` 설정되고 a가 <xref:System.Windows.Media.LineSegment> `100,130`끝점으로 정의됩니다. 다음 그림에서는 <xref:System.Windows.Media.PathGeometry> 이 예제에서 만든 것을 보여 주며 있습니다.  
  
 ![LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")  
단일 LineSegment를 포함하는 PathGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrylineexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrylineexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrylineexample)]  
  
 이 예제를 앞의 예제와 <xref:System.Windows.Media.LineGeometry> 대조할 가치가 있습니다.  a에 <xref:System.Windows.Media.PathGeometry> 사용되는 구문은 <xref:System.Windows.Media.LineGeometry>단순에 사용되는 구문보다 훨씬 더 자세한 내용이며 이 <xref:System.Windows.Media.LineGeometry> 경우 클래스를 사용하는 것이 더 합리적일 <xref:System.Windows.Media.PathGeometry> 수 있지만 이 구문은 매우 복잡하고 복잡한 기하학적 영역을 허용합니다.  
  
 객체의 <xref:System.Windows.Media.PathSegment> 조합을 사용하여 보다 복잡한 형상을 작성할 수 있습니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.BezierSegment>에서 <xref:System.Windows.Media.LineSegment>와 를 <xref:System.Windows.Media.ArcSegment> 사용하여 셰이프를 만듭니다. 예는 먼저 입방 베지어 곡선을 만드는 네 개의 점을 정의하여: 이전 세그먼트의 끝점인 시작점,<xref:System.Windows.Media.BezierSegment.Point3%2A><xref:System.Windows.Media.BezierSegment.Point1%2A> 끝점() 및 두 개의 제어점(및 <xref:System.Windows.Media.BezierSegment.Point2%2A>)).  입방형 3차원 곡선의 두 제어점은 자석처럼 동작하여 서로를 향해서 직선 방향에 놓일 부분을 잡아당겨 곡선을 형성합니다. 첫 번째 제어점 <xref:System.Windows.Media.BezierSegment.Point1%2A>, 시작 부분에 영향을 줍니다 곡선의 부분, 두 번째 제어점 <xref:System.Windows.Media.BezierSegment.Point2%2A>, 곡선의 끝 부분에 영향을 줍니다.  
  
 그런 다음 예제에서는 앞에 <xref:System.Windows.Media.LineSegment> <xref:System.Windows.Media.BezierSegment> 오는 끝점 사이에 해당 <xref:System.Windows.Media.LineSegment> 속성에 지정된 점에 그려지는 를 추가합니다.  
  
 그런 다음 예제에서는 이전 <xref:System.Windows.Media.ArcSegment> <xref:System.Windows.Media.LineSegment> 끝점에서 해당 <xref:System.Windows.Media.ArcSegment.Point%2A> 속성에 의해 지정된 점에 그려지는 를 추가합니다. 또한 이 예제에서는 호의<xref:System.Windows.Media.ArcSegment.Size%2A>x-및 y-반경(), 회전<xref:System.Windows.Media.ArcSegment.RotationAngle%2A>각도(), 결과 호의 각도가 얼마나 큰지<xref:System.Windows.Media.ArcSegment.IsLargeArc%2A>나타내는 플래그()와 호가 그려지는<xref:System.Windows.Media.ArcSegment.SweepDirection%2A>방향을 나타내는 값을 지정합니다. 다음 그림은 이 예제에서 만들어지는 도형을 보여 줍니다.  
  
 ![PathGeometry](./media/graphicsmm-path2.gif "graphicsmm_path2")  
PathGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexexample)]  
  
 보다 복잡한 형상은 에 있는 <xref:System.Windows.Media.PathFigure> 여러 객체를 사용하여 작성할 수 있습니다. <xref:System.Windows.Media.PathGeometry>  
  
 다음 예제에서는 <xref:System.Windows.Media.PathGeometry> 두 <xref:System.Windows.Media.PathFigure> 개의 개체가 있는 <xref:System.Windows.Media.PathSegment> a를 만들며, 각 개체에는 여러 개체가 포함됩니다.  상기 <xref:System.Windows.Media.PathFigure> 예에서 <xref:System.Windows.Media.PathFigure> <xref:System.Windows.Media.PolyLineSegment> a와 <xref:System.Windows.Media.QuadraticBezierSegment> a가 사용된다.  A는 <xref:System.Windows.Media.PolyLineSegment> 점 배열로 정의되며, 이 점은 제어점과 끝점으로 <xref:System.Windows.Media.QuadraticBezierSegment> 정의됩니다. 다음 그림은 이 예제에서 만들어지는 도형을 보여 줍니다.  
  
 ![PathGeometry](./media/graphicsmm-path.gif "graphicsmm_path")  
여러 그림이 있는 PathGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexmultiexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexmultiexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexmultiexample)]  
  
### <a name="streamgeometry"></a>StreamGeometry  
 클래스와 <xref:System.Windows.Media.PathGeometry> 마찬가지로 <xref:System.Windows.Media.StreamGeometry> a는 곡선, 호 및 선을 포함할 수 있는 복잡한 기하학적 모양을 정의합니다. 와 <xref:System.Windows.Media.PathGeometry>달리 a의 <xref:System.Windows.Media.StreamGeometry> 내용은 데이터 바인딩, 애니메이션 또는 수정을 지원하지 않습니다. 복잡한 <xref:System.Windows.Media.StreamGeometry> 형상을 설명해야 하지만 데이터 바인딩, 애니메이션 또는 수정을 지원하는 오버헤드를 원하지 않는 경우를 사용합니다. 그 효율성 때문에, <xref:System.Windows.Media.StreamGeometry> 클래스는 장식기를 설명하기위한 좋은 선택입니다.  
  
 예제를 보려면 [StreamGeometry를 사용하여 도형 만들기](how-to-create-a-shape-using-a-streamgeometry.md)를 참조하세요.  
  
### <a name="path-markup-syntax"></a>경로 태그 구문  
 및 <xref:System.Windows.Media.PathGeometry> <xref:System.Windows.Media.StreamGeometry> 형식은 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 특수 일련의 이동 및 그리기 명령을 사용하여 특성 구문을 지원합니다. 자세한 내용은 [경로 태그 구문](path-markup-syntax.md)을 참조하세요.  
  
<a name="wcpsdk_graphics_geometry_introduction2"></a>
## <a name="composite-geometries"></a>복합 기하 도형  
 사용 하 여 복합 기 하 도형 개체를 만들 수 있습니다는 <xref:System.Windows.Media.GeometryGroup>, <xref:System.Windows.Media.CombinedGeometry>, 또는 정적 호출 하 여 <xref:System.Windows.Media.Geometry> 메서드 <xref:System.Windows.Media.Geometry.Combine%2A>합니다.  
  
- 개체와 <xref:System.Windows.Media.CombinedGeometry> <xref:System.Windows.Media.Geometry.Combine%2A> 메서드는 두 형상으로 정의된 영역을 결합하기 위해 부울 작업을 수행합니다. <xref:System.Windows.Media.Geometry>영역이 없는 객체는 삭제됩니다. 두 <xref:System.Windows.Media.Geometry> 오브젝트만 결합할 수 있습니다(이 두 형상은 복합 형상일 수도 있음).  
  
- 클래스는 <xref:System.Windows.Media.GeometryGroup> 해당 영역을 결합하지 <xref:System.Windows.Media.Geometry> 않고 포함된 개체의 통합을 만듭니다. 에 임의의 수의 <xref:System.Windows.Media.Geometry> 개체를 <xref:System.Windows.Media.GeometryGroup>추가할 수 있습니다. 예제를 보려면 [복합 도형 만들기](how-to-create-a-composite-shape.md)를 참조하세요.  
  
 결합 작업을 수행 하지 않으므로 <xref:System.Windows.Media.GeometryGroup> 개체를 사용 하 <xref:System.Windows.Media.CombinedGeometry> 여 <xref:System.Windows.Media.Geometry.Combine%2A> 개체 또는 메서드를 사용 하 여 성능 이점을 제공 합니다.  
  
<a name="combindgeometriessection"></a>
## <a name="combined-geometries"></a>결합된 기하 도형  
 앞의 단면에서 <xref:System.Windows.Media.CombinedGeometry> 언급한 <xref:System.Windows.Media.Geometry.Combine%2A> 객체와 메서드는 해당 객체에 포함된 형상으로 정의된 영역을 결합합니다. 열거형은 <xref:System.Windows.Media.GeometryCombineMode> 형상이 결합되는 방법을 지정합니다. <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> 속성에 대 한 가능한 <xref:System.Windows.Media.GeometryCombineMode.Union> <xref:System.Windows.Media.GeometryCombineMode.Intersect>값은 <xref:System.Windows.Media.GeometryCombineMode.Xor>: 및 <xref:System.Windows.Media.GeometryCombineMode.Exclude>  
  
 다음 예제에서 a는 <xref:System.Windows.Media.CombinedGeometry> Union의 결합 모드로 정의됩니다.  둘 <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> 다 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 같은 반지름의 원으로 정의되지만 중심은 50으로 간격띄우기됩니다.  
  
 [!code-xaml[GeometrySample#23](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Union 결합 모드의 결과](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")  
  
 다음 예제에서 a는 <xref:System.Windows.Media.CombinedGeometry> <xref:System.Windows.Media.GeometryCombineMode.Xor>의 결합 모드로 정의됩니다.  둘 <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> 다 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 같은 반지름의 원으로 정의되지만 중심은 50으로 간격띄우기됩니다.  
  
 [!code-xaml[GeometrySample#24](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Xor 결합 모드의 결과](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")  
  
 추가 예제를 보려면 [복합 도형 만들기](how-to-create-a-composite-shape.md) 및 [결합된 기하 도형 만들기](how-to-create-a-combined-geometry.md)를 참조하세요.  
  
<a name="freezable_features"></a>
## <a name="freezable-features"></a>Freezable 기능  
 <xref:System.Windows.Freezable> 클래스에서 상속되기 때문에 클래스는 <xref:System.Windows.Media.Geometry> 여러 <xref:System.Windows.Media.Geometry> 개체 간에 공유되고, 성능을 향상시키기 위해 읽기 전용으로 만든 [XAML 리소스로](../../../desktop-wpf/fundamentals/xaml-resources-define.md)선언할 수 있으며, 복제되고 스레드가 안전하도록 만들 수 있습니다. 제공 하는 다른 기능에 대 한 자세한 <xref:System.Windows.Freezable> 개체를 참조 합니다 [Freezable 개체 개요](../advanced/freezable-objects-overview.md)합니다.  
  
<a name="othergeometryfeatures"></a>
## <a name="other-geometry-features"></a>기타 기하 도형 기능  
 클래스는 <xref:System.Windows.Media.Geometry> 다음과 같은 유용한 유틸리티 메서드도 제공합니다.  
  
- <xref:System.Windows.Media.Geometry.GetArea%2A>- 의 영역을 <xref:System.Windows.Media.Geometry>가져옵니다.  
  
- <xref:System.Windows.Media.Geometry.FillContains%2A>- 지오메트리에 다른 <xref:System.Windows.Media.Geometry>.  
  
- <xref:System.Windows.Media.Geometry.StrokeContains%2A>- a의 <xref:System.Windows.Media.Geometry> 스트로크에 지정된 점이 포함되어 있는지 여부를 결정합니다.  
  
 해당 <xref:System.Windows.Media.Geometry> 메서드의 전체 목록은 클래스를 참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Media.Geometry>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [2D 그래픽 및 이미징](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [경로 태그 구문](path-markup-syntax.md)
- [방법 주제](geometries-how-to-topics.md)
- [애니메이션 개요](animation-overview.md)
- [WPF에서 Shape 및 기본 그리기 개요](shapes-and-basic-drawing-in-wpf-overview.md)
- [Drawing 개체 개요](drawing-objects-overview.md)
