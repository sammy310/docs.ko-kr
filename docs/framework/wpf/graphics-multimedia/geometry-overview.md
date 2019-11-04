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
ms.openlocfilehash: f45c13e1af9bc2d1f75da11b13a2c03936b136c1
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73455016"
---
# <a name="geometry-overview"></a>Geometry 개요
이 개요에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Media.Geometry> 클래스를 사용 하 여 도형을 설명 하는 방법을 설명 합니다. 이 항목에서는 <xref:System.Windows.Media.Geometry> 개체와 <xref:System.Windows.Shapes.Shape> 요소 간의 차이점도 대조 합니다.  

<a name="wcpsdk_graphics_geometry_introduction"></a>   
## <a name="what-is-a-geometry"></a>기하 도형이란?  
 <xref:System.Windows.Media.Geometry> 클래스와이 클래스에서 파생 되는 클래스 (예: <xref:System.Windows.Media.EllipseGeometry>, <xref:System.Windows.Media.PathGeometry>및 <xref:System.Windows.Media.CombinedGeometry>)를 사용 하 여 2 차원 도형의 기 하 도형을 설명할 수 있습니다. 이러한 기하학적 설명은 화면에 그릴 도형 정의 또는 적중 테스트 및 클립 영역을 정의와 같은 다양한 용도로 사용됩니다. 애니메이션 경로를 정의하는 데도 기하 도형을 사용할 수 있습니다.  
  
 <xref:System.Windows.Media.Geometry> 개체는 사각형 및 원과 같은 단순 하거나 둘 이상의 geometry 개체에서 만든 복합 일 수 있습니다.  호와 곡선을 설명 하는 데 사용할 수 있는 <xref:System.Windows.Media.PathGeometry> 및 <xref:System.Windows.Media.StreamGeometry> 클래스를 사용 하 여 더 복잡 한 기 하 도형을 만들 수 있습니다.  
  
 <xref:System.Windows.Media.Geometry>는 <xref:System.Windows.Freezable>형식 이므로 <xref:System.Windows.Media.Geometry> 개체는 여러 가지 특수 기능을 제공 합니다. [즉, 여러](../../../desktop-wpf/fundamentals/xaml-resources-define.md)개체 간에 공유 되 고, 여러 개체 간에 공유 되 고, 성능을 향상 시키고, 복제 되 고, 스레드로부터 안전 하 게 보호 하기 위해 읽기 전용으로 설정 될 수 있습니다. 제공 하는 다른 기능에 대 한 자세한 <xref:System.Windows.Freezable> 개체를 참조 합니다 [Freezable 개체 개요](../advanced/freezable-objects-overview.md)합니다.  
  
<a name="wcpsdk_graphics_geometry_geometryandshapes"></a>   
## <a name="geometries-vs-shapes"></a>기 하 도형 및 모양  
 <xref:System.Windows.Media.Geometry> 및 <xref:System.Windows.Shapes.Shape> 클래스는 2 차원 셰이프를 설명 하는 것 처럼 보이지만 (예: <xref:System.Windows.Shapes.Ellipse> <xref:System.Windows.Media.EllipseGeometry> 비교) 중요 한 차이점이 있습니다.  
  
 하나의 경우 <xref:System.Windows.Media.Geometry> 클래스는 <xref:System.Windows.Shapes.Shape> 클래스가 <xref:System.Windows.FrameworkElement>에서 상속 하는 동안 <xref:System.Windows.Freezable> 클래스에서 상속 됩니다. 요소 이기 때문에 <xref:System.Windows.Shapes.Shape> 개체는 자신을 렌더링 하 고 레이아웃 시스템에 참여할 수 있지만 <xref:System.Windows.Media.Geometry> 개체는 그렇지 않습니다.  
  
 <xref:System.Windows.Shapes.Shape> 개체는 <xref:System.Windows.Media.Geometry> 개체 보다 더 쉽게 사용할 수 있지만 <xref:System.Windows.Media.Geometry> 개체는 더 다양 합니다. <xref:System.Windows.Shapes.Shape> 개체를 사용 하 여 2 차원 그래픽을 렌더링 하는 동안 <xref:System.Windows.Media.Geometry> 개체를 사용 하 여 2 차원 그래픽의 기하학적 영역을 정의 하거나, 클리핑 영역을 정의 하거나, 적중 테스트를 위한 영역을 정의할 수 있습니다 (예:).  
  
### <a name="the-path-shape"></a>경로 도형  
 <xref:System.Windows.Shapes.Path> 클래스 <xref:System.Windows.Shapes.Shape>하나는 실제로 <xref:System.Windows.Media.Geometry>를 사용 하 여 해당 내용을 설명 합니다. <xref:System.Windows.Media.Geometry>를 사용 하 여 <xref:System.Windows.Shapes.Path>의 <xref:System.Windows.Shapes.Path.Data%2A> 속성을 설정 하 고 <xref:System.Windows.Shapes.Shape.Fill%2A> 및 <xref:System.Windows.Shapes.Shape.Stroke%2A> 속성을 설정 하 여 <xref:System.Windows.Media.Geometry>를 렌더링할 수 있습니다.  
  
<a name="commonproperties"></a>   
## <a name="common-properties-that-take-a-geometry"></a>Geometry를 사용하는 공용 속성  
 이전 섹션에서는 Geometry 개체를 도형 그리기, 애니메이션 효과 적용, 클리핑 등의 다양한 용도로 다른 개체와 함께 사용할 수 있다는 사실을 설명했습니다. 다음 표에서는 <xref:System.Windows.Media.Geometry> 개체를 사용 하는 속성을 포함 하는 여러 클래스를 보여 줍니다.  
  
|Type|속성|  
|----------|--------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>|  
|<xref:System.Windows.Media.DrawingGroup>|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|  
|<xref:System.Windows.Media.GeometryDrawing>|<xref:System.Windows.Media.GeometryDrawing.Geometry%2A>|  
|<xref:System.Windows.Shapes.Path>|<xref:System.Windows.Shapes.Path.Data%2A>|  
|<xref:System.Windows.UIElement>|<xref:System.Windows.UIElement.Clip%2A>|  
  
<a name="wcpsdk_graphics_geometry_geometrytypes"></a>   
## <a name="simple-geometry-types"></a>단순 기하 도형 형식  
 모든 기 하 도형의 기본 클래스는 <xref:System.Windows.Media.Geometry>추상 클래스입니다.  <xref:System.Windows.Media.Geometry> 클래스에서 파생 되는 클래스는 대략적으로 단순 기 하 도형, 경로 기 하 도형 및 복합 기 하 도형 등의 세 가지 범주로 그룹화 할 수 있습니다.  
  
 간단한 기 하 도형 클래스는 <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>및 <xref:System.Windows.Media.EllipseGeometry>를 포함 하며 선, 사각형 및 원과 같은 기본 기하학적 모양을 만드는 데 사용 됩니다.  
  
- <xref:System.Windows.Media.LineGeometry>는 선의 시작점과 끝점을 지정 하 여 정의 됩니다.  
  
- <xref:System.Windows.Media.RectangleGeometry>는 상대 위치와 높이 및 너비를 지정 하는 <xref:System.Windows.Rect> 구조체로 정의 됩니다. <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> 및 <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> 속성을 설정 하 여 모퉁이가 둥근 사각형을 만들 수 있습니다.  
  
- <xref:System.Windows.Media.EllipseGeometry>은 중심점, x 반지름 및 y 반지름에 의해 정의 됩니다.  다음 예제에서는 렌더링 및 클리핑을 위한 단순 기하 도형을 만드는 방법을 보여 줍니다.  
  
 <xref:System.Windows.Media.PathGeometry>를 사용 하거나 기 하 도형 개체를 결합 하 여 이러한 동일한 셰이프를 만들 수 있지만 이러한 클래스를 사용 하면 이러한 기본 기하학적 셰이프를 보다 간단 하 게 만들 수 있습니다.  
  
 다음 예에서는 <xref:System.Windows.Media.LineGeometry>를 만들고 렌더링 하는 방법을 보여 줍니다.  앞에서 설명한 것 처럼 <xref:System.Windows.Media.Geometry> 개체는 자신을 그릴 수 없기 때문에이 예제에서는 <xref:System.Windows.Shapes.Path> 셰이프를 사용 하 여 선을 렌더링 합니다.  줄에 영역이 없으므로 <xref:System.Windows.Shapes.Path>의 <xref:System.Windows.Shapes.Shape.Fill%2A> 속성을 설정 해도 아무런 효과가 없습니다. 대신 <xref:System.Windows.Shapes.Shape.Stroke%2A> 및 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 속성만 지정 됩니다. 다음 그림에서는 예제의 출력을 보여 줍니다.  
  
 ![LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")  
(10,20)부터 (100,130)까지 그린 LineGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 다음 예제에서는 <xref:System.Windows.Media.EllipseGeometry>를 만들고 렌더링 하는 방법을 보여 줍니다.  이 예에서는 point `50,50`로 설정 된 <xref:System.Windows.Media.EllipseGeometry>의 <xref:System.Windows.Media.EllipseGeometry.Center%2A>를 설정 하 고, x 반지름 및 y 반지름을 모두 `50`설정 하 여 지름이 100 인 원을 만듭니다.  타원의 내부는 Path 요소의 Fill 속성에 값을 할당 하 여 그려집니다 (이 경우 <xref:System.Windows.Media.Brushes.Gold%2A>. 다음 그림에서는 예제의 출력을 보여 줍니다.  
  
 ![EllipseGeometry](./media/graphicsmm-ellipse.gif "graphicsmm_ellipse")  
(50,50)에 그린 EllipseGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmellipsegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmellipsegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmellipsegeometryexample)]  
  
 다음 예에서는 <xref:System.Windows.Media.RectangleGeometry>를 만들고 렌더링 하는 방법을 보여 줍니다.  사각형의 위치와 크기는 <xref:System.Windows.Rect> 구조체로 정의 됩니다. 위치는 `50,50`이고 높이 및 너비 둘 다 `25`이므로 정사각형을 만듭니다. 다음 그림에서는 예제의 출력을 보여 줍니다.  
  
 ![RectangleGeometry](./media/graphicsmm-rectangle.gif "graphicsmm_rectangle")  
50,50에 그린 RectangleGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 다음 예에서는 <xref:System.Windows.Media.EllipseGeometry>를 이미지의 클립 영역으로 사용 하는 방법을 보여 줍니다.  <xref:System.Windows.Controls.Image> 개체는 200의 <xref:System.Windows.FrameworkElement.Width%2A> 및 150 <xref:System.Windows.FrameworkElement.Height%2A>으로 정의 됩니다.  <xref:System.Windows.Media.EllipseGeometry.RadiusX%2A> 값이 100이 고 <xref:System.Windows.Media.EllipseGeometry.RadiusY%2A> 값이 75 이며 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 값이 100 인 <xref:System.Windows.Media.EllipseGeometry>는 이미지의 <xref:System.Windows.UIElement.Clip%2A> 속성으로 설정 됩니다.  타원 영역 내의 이미지 부분만 표시됩니다. 다음 그림에서는 예제의 출력을 보여 줍니다.  
  
 ![클리핑이 있는 이미지와 없는 이미지](./media/graphicsmm-clipexample.png "graphicsmm_clipexample")  
Image 컨트롤 클리핑에 사용되는 EllipseGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmimageclipgeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmimageclipgeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmimageclipgeometryexample)]  
  
<a name="wcpsdk_graphics_geometry_pathgeometry"></a>   
## <a name="path-geometries"></a>경로 기하 도형  
 <xref:System.Windows.Media.PathGeometry> 클래스와 그에 해당 하는 경량의 <xref:System.Windows.Media.StreamGeometry> 클래스는 원호, 곡선 및 선으로 구성 된 여러 복잡 한 그림을 설명 하는 수단을 제공 합니다.  
  
 <xref:System.Windows.Media.PathGeometry>의 핵심은 <xref:System.Windows.Media.PathFigure> 개체의 컬렉션 이므로 각 그림은 <xref:System.Windows.Media.PathGeometry>의 불연속 셰이프를 설명 하기 때문에 이름이 지정 됩니다. 각 <xref:System.Windows.Media.PathFigure>은 각각 그림의 세그먼트를 설명 하는 하나 이상의 <xref:System.Windows.Media.PathSegment> 개체로 구성 됩니다.  
  
 세그먼트 형식은 다양합니다.  
  
|세그먼트 형식|설명|예제|  
|------------------|-----------------|-------------|  
|<xref:System.Windows.Media.ArcSegment>|두 점 사이에 타원형 호를 만듭니다.|[타원형 원호 만들기](how-to-create-an-elliptical-arc.md).|  
|<xref:System.Windows.Media.BezierSegment>|두 점 사이에 입방형 3차원 곡선을 만듭니다.|[입방형 3차원 곡선 만들기](how-to-create-a-cubic-bezier-curve.md).|  
|<xref:System.Windows.Media.LineSegment>|두 점 사이에 선을 만듭니다.|[PathGeometry에 LineSegment 만들기](how-to-create-a-linesegment-in-a-pathgeometry.md)|  
|<xref:System.Windows.Media.PolyBezierSegment>|일련의 입방형 3차원 곡선을 만듭니다.|<xref:System.Windows.Media.PolyBezierSegment> 형식 페이지를 참조 하세요.|  
|<xref:System.Windows.Media.PolyLineSegment>|일련의 줄을 만듭니다.|<xref:System.Windows.Media.PolyLineSegment> 형식 페이지를 참조 하세요.|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|일련의 정방형 3차원 곡선을 만듭니다.|<xref:System.Windows.Media.PolyQuadraticBezierSegment> 페이지를 참조 하세요.|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|정방형 3차원 곡선을 만듭니다.|[정방형 3차원 곡선 만들기](how-to-create-a-quadratic-bezier-curve.md).|  
  
 <xref:System.Windows.Media.PathFigure> 내의 세그먼트는 각 세그먼트의 끝점이 다음 세그먼트의 시작점 인 단일 기 하 도형으로 결합 됩니다. <xref:System.Windows.Media.PathFigure>의 <xref:System.Windows.Media.PathFigure.StartPoint%2A> 속성은 첫 번째 세그먼트를 그릴 지점을 지정 합니다. 각 후속 세그먼트는 이전 세그먼트의 끝점에서 시작합니다. 예를 들어 <xref:System.Windows.Media.PathFigure.StartPoint%2A> 속성을 `10,50`로 설정 하 고 <xref:System.Windows.Media.LineSegment>의 <xref:System.Windows.Media.LineSegment.Point%2A> 속성 설정을 사용 하 여 `10,150`를 만들어 `10,50` `10,150`의 세로줄을 정의할 수 있습니다.  
  
 다음 예에서는 <xref:System.Windows.Media.LineSegment>를 사용 하 여 단일 <xref:System.Windows.Media.PathFigure> 구성 된 간단한 <xref:System.Windows.Media.PathGeometry>을 만들고 <xref:System.Windows.Shapes.Path> 요소를 사용 하 여 표시 합니다. <xref:System.Windows.Media.PathFigure> 개체의 <xref:System.Windows.Media.PathFigure.StartPoint%2A> `10,20`으로 설정 되 고 <xref:System.Windows.Media.LineSegment>는 `100,130`끝점으로 정의 됩니다. 다음 그림에서는이 예제에서 만든 <xref:System.Windows.Media.PathGeometry> 보여 줍니다.  
  
 ![LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")  
단일 LineSegment를 포함하는 PathGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrylineexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrylineexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrylineexample)]  
  
 위의 <xref:System.Windows.Media.LineGeometry> 예제를 사용 하 여이 예제를 대비 하는 것이 좋습니다.  <xref:System.Windows.Media.PathGeometry>에 사용 되는 구문은 간단한 <xref:System.Windows.Media.LineGeometry>에 사용 되는 것 보다 더 자세한 정보를 표시 하 고,이 경우 <xref:System.Windows.Media.LineGeometry> 클래스를 사용 하는 것이 더 적합할 수 있지만 <xref:System.Windows.Media.PathGeometry>의 자세한 구문에서는 매우 복잡 하 고 복잡 한 기하학적 영역을 허용 합니다.  
  
 <xref:System.Windows.Media.PathSegment> 개체의 조합을 사용 하 여 더 복잡 한 기 하 도형을 만들 수 있습니다.  
  
 다음 예에서는 <xref:System.Windows.Media.BezierSegment>, <xref:System.Windows.Media.LineSegment>및 <xref:System.Windows.Media.ArcSegment> 사용 하 여 셰이프를 만듭니다. 이 예에서는 먼저 4 개 지점을 정의 합니다. 시작점은 이전 세그먼트의 끝점, 끝점 (<xref:System.Windows.Media.BezierSegment.Point3%2A>) 및 두 개의 제어점 (<xref:System.Windows.Media.BezierSegment.Point1%2A> 및 <xref:System.Windows.Media.BezierSegment.Point2%2A>)입니다.  입방형 3차원 곡선의 두 제어점은 자석처럼 동작하여 서로를 향해서 직선 방향에 놓일 부분을 잡아당겨 곡선을 형성합니다. 첫 번째 제어점 인 <xref:System.Windows.Media.BezierSegment.Point1%2A>은 곡선의 시작 부분에 영향을 줍니다. 두 번째 제어점 인 <xref:System.Windows.Media.BezierSegment.Point2%2A>은 곡선의 끝 부분에 영향을 줍니다.  
  
 그런 다음이 예제에서는 이전 <xref:System.Windows.Media.BezierSegment>의 끝점 사이에 그려진 <xref:System.Windows.Media.LineSegment>를 <xref:System.Windows.Media.LineSegment> 속성에 지정 된 지점에 추가 합니다.  
  
 그런 다음이 예제에서는 이전 <xref:System.Windows.Media.LineSegment>의 끝점에서 <xref:System.Windows.Media.ArcSegment.Point%2A> 속성에 지정 된 지점으로 그려지는 <xref:System.Windows.Media.ArcSegment>를 추가 합니다. 또한 원호의 x 및 y 반지름 (<xref:System.Windows.Media.ArcSegment.Size%2A>), 회전 각도 (<xref:System.Windows.Media.ArcSegment.RotationAngle%2A>), 결과 호의 각도 (<xref:System.Windows.Media.ArcSegment.IsLargeArc%2A>)를 나타내는 플래그, 호가 그려지는 방향 (<xref:System.Windows.Media.ArcSegment.SweepDirection%2A>)을 나타내는 값 등을 지정 합니다. 다음 그림은 이 예제에서 만들어지는 도형을 보여 줍니다.  
  
 ![PathGeometry](./media/graphicsmm-path2.gif "graphicsmm_path2")  
PathGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexexample)]  
  
 <xref:System.Windows.Media.PathGeometry>내에서 여러 <xref:System.Windows.Media.PathFigure> 개체를 사용 하 여 더 복잡 한 기 하 도형을 만들 수 있습니다.  
  
 다음 예에서는 각각 여러 개의 <xref:System.Windows.Media.PathSegment> 개체를 포함 하는 두 개의 <xref:System.Windows.Media.PathFigure> 개체를 사용 하 여 <xref:System.Windows.Media.PathGeometry>를 만듭니다.  위의 예제에서 <xref:System.Windows.Media.PathFigure> <xref:System.Windows.Media.PolyLineSegment> 및 <xref:System.Windows.Media.QuadraticBezierSegment> 사용 되는 <xref:System.Windows.Media.PathFigure>입니다.  <xref:System.Windows.Media.PolyLineSegment>는 점 배열을 사용 하 여 정의 되 고 <xref:System.Windows.Media.QuadraticBezierSegment>는 제어점과 끝점으로 정의 됩니다. 다음 그림은 이 예제에서 만들어지는 도형을 보여 줍니다.  
  
 ![PathGeometry](./media/graphicsmm-path.gif "graphicsmm_path")  
여러 그림이 있는 PathGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexmultiexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexmultiexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexmultiexample)]  
  
### <a name="streamgeometry"></a>StreamGeometry  
 <xref:System.Windows.Media.PathGeometry> 클래스와 마찬가지로 <xref:System.Windows.Media.StreamGeometry>는 곡선, 원호 및 선을 포함할 수 있는 복잡 한 기 하 도형을 정의 합니다. <xref:System.Windows.Media.PathGeometry>와 달리 <xref:System.Windows.Media.StreamGeometry> 내용은 데이터 바인딩, 애니메이션 또는 수정을 지원 하지 않습니다. 복잡 한 기 하 도형을 설명 해야 하지만 데이터 바인딩, 애니메이션 또는 수정을 지원 하기 위한 오버 헤드를 원하지 않는 경우 <xref:System.Windows.Media.StreamGeometry>를 사용 합니다. 효율성 때문에 <xref:System.Windows.Media.StreamGeometry> 클래스는 표시기를 설명 하는 데 적합 합니다.  
  
 예제를 보려면 [StreamGeometry를 사용하여 도형 만들기](how-to-create-a-shape-using-a-streamgeometry.md)를 참조하세요.  
  
### <a name="path-markup-syntax"></a>경로 태그 구문  
 <xref:System.Windows.Media.PathGeometry> 및 <xref:System.Windows.Media.StreamGeometry> 형식은 특수 한 일련의 이동 및 그리기 명령을 사용 하 여 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 특성 구문을 지원 합니다. 자세한 내용은 [경로 태그 구문](path-markup-syntax.md)을 참조하세요.  
  
<a name="wcpsdk_graphics_geometry_introduction2"></a>   
## <a name="composite-geometries"></a>복합 기하 도형  
 복합 geometry 개체는 <xref:System.Windows.Media.GeometryGroup>, <xref:System.Windows.Media.CombinedGeometry>를 사용 하거나 정적 <xref:System.Windows.Media.Geometry> 메서드 <xref:System.Windows.Media.Geometry.Combine%2A>를 호출 하 여 만들 수 있습니다.  
  
- <xref:System.Windows.Media.CombinedGeometry> 개체 및 <xref:System.Windows.Media.Geometry.Combine%2A> 메서드는 부울 연산을 수행 하 여 두 기 하 도형으로 정의 된 영역을 결합 합니다. 영역이 없는 <xref:System.Windows.Media.Geometry> 개체는 삭제 됩니다. 두 개의 <xref:System.Windows.Media.Geometry> 개체만 결합할 수 있습니다. 단, 이러한 두 기 하 도형은 복합 기 하 도형 일 수도 있습니다.  
  
- <xref:System.Windows.Media.GeometryGroup> 클래스는 영역을 결합 하지 않고 포함 된 <xref:System.Windows.Media.Geometry> 개체의 amalgamation을 만듭니다. <xref:System.Windows.Media.GeometryGroup>에는 원하는 수의 <xref:System.Windows.Media.Geometry> 개체를 추가할 수 있습니다. 예제를 보려면 [복합 도형 만들기](how-to-create-a-composite-shape.md)를 참조하세요.  
  
 결합 작업을 수행 하지 않기 때문에 <xref:System.Windows.Media.GeometryGroup> 개체를 사용 하면 <xref:System.Windows.Media.CombinedGeometry> 개체 또는 <xref:System.Windows.Media.Geometry.Combine%2A> 메서드를 사용 하는 것 보다 성능상의 이점이 있습니다.  
  
<a name="combindgeometriessection"></a>   
## <a name="combined-geometries"></a>결합된 기하 도형  
 이전 단원에서는 <xref:System.Windows.Media.CombinedGeometry> 개체 및 <xref:System.Windows.Media.Geometry.Combine%2A> 메서드에 포함 된 기 하 도형으로 정의 된 영역을 결합 합니다. <xref:System.Windows.Media.GeometryCombineMode> 열거형은 기 하 도형을 결합 하는 방법을 지정 합니다. <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> 속성에 사용할 수 있는 값은 <xref:System.Windows.Media.GeometryCombineMode.Union>, <xref:System.Windows.Media.GeometryCombineMode.Intersect>, <xref:System.Windows.Media.GeometryCombineMode.Exclude>및 <xref:System.Windows.Media.GeometryCombineMode.Xor>입니다.  
  
 다음 예제에서는 Union의 조합 모드를 사용 하 여 <xref:System.Windows.Media.CombinedGeometry>을 정의 합니다.  <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>와 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A>는 모두 동일한 반지름의 원으로 정의 되지만 센터가 50로 오프셋 됩니다.  
  
 [!code-xaml[GeometrySample#23](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Union 결합 모드의 결과](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")  
  
 다음 예에서는 <xref:System.Windows.Media.CombinedGeometry> <xref:System.Windows.Media.GeometryCombineMode.Xor>결합 모드로 정의 됩니다.  <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>와 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A>는 모두 동일한 반지름의 원으로 정의 되지만 센터가 50로 오프셋 됩니다.  
  
 [!code-xaml[GeometrySample#24](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Xor 결합 모드의 결과](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")  
  
 추가 예제를 보려면 [복합 도형 만들기](how-to-create-a-composite-shape.md) 및 [결합된 기하 도형 만들기](how-to-create-a-combined-geometry.md)를 참조하세요.  
  
<a name="freezable_features"></a>   
## <a name="freezable-features"></a>Freezable 기능  
 <xref:System.Windows.Freezable> 클래스에서 상속 하기 때문에 <xref:System.Windows.Media.Geometry> 클래스는 몇 가지 특수 기능을 제공 합니다. <xref:System.Windows.Media.Geometry> 개체를 [XAML 리소스로](../../../desktop-wpf/fundamentals/xaml-resources-define.md)선언 하 고, 여러 개체 간에 공유 하 고, 성능을 향상 시키기 위해 읽기 전용으로 만들 수 있습니다. 스레드로부터 안전 합니다. 제공 하는 다른 기능에 대 한 자세한 <xref:System.Windows.Freezable> 개체를 참조 합니다 [Freezable 개체 개요](../advanced/freezable-objects-overview.md)합니다.  
  
<a name="othergeometryfeatures"></a>   
## <a name="other-geometry-features"></a>기타 기하 도형 기능  
 또한 <xref:System.Windows.Media.Geometry> 클래스는 다음과 같은 유용한 유틸리티 메서드를 제공 합니다.  
  
- <xref:System.Windows.Media.Geometry.GetArea%2A>-<xref:System.Windows.Media.Geometry>영역을 가져옵니다.  
  
- <xref:System.Windows.Media.Geometry.FillContains%2A>-기 하 도형에 다른 <xref:System.Windows.Media.Geometry>포함 되어 있는지 여부를 확인 합니다.  
  
- <xref:System.Windows.Media.Geometry.StrokeContains%2A>-<xref:System.Windows.Media.Geometry>의 스트로크에 지정 된 지점이 들어 있는지 여부를 확인 합니다.  
  
 메서드의 전체 목록은 <xref:System.Windows.Media.Geometry> 클래스를 참조 하세요.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Media.Geometry>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [2차원 그래픽 및 이미징](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [경로 태그 구문](path-markup-syntax.md)
- [방법 항목](geometries-how-to-topics.md)
- [애니메이션 개요](animation-overview.md)
- [WPF에서 Shape 및 기본 그리기 개요](shapes-and-basic-drawing-in-wpf-overview.md)
- [Drawing 개체 개요](drawing-objects-overview.md)
