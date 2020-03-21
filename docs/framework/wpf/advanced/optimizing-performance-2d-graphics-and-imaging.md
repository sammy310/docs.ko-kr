---
title: '성능 최적화: 2D 그래픽 및 이미징'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], performance
- drawing [WPF], optimizing performance
- imaging [WPF], optimizing performance
- shapes [WPF], optimizing performance
- 2D graphics [WPF]
- images [WPF], optimizing performance
ms.assetid: e335601e-28c8-4d64-ba27-778fffd55f72
ms.openlocfilehash: 59ac7a5aa8b0591c51cdb6ee0d6435649e22fade
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111220"
---
# <a name="optimizing-performance-2d-graphics-and-imaging"></a>성능 최적화: 2D 그래픽 및 이미징
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 애플리케이션 요구 사항에 맞게 최적화할 수 있는 다양한 범위의 2D 그래픽 및 이미징 기능을 제공합니다. 이 항목에서는 이러한 영역의 성능 최적화에 대한 정보를 제공합니다.  

<a name="Drawing_and_Shapes"></a>
## <a name="drawing-and-shapes"></a>그리기 및 도형  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]은 <xref:System.Windows.Media.Drawing> 그래픽 <xref:System.Windows.Shapes.Shape> 드로잉 컨텐더를 나타내는 객체와 객체를 모두 제공합니다. 그러나 <xref:System.Windows.Media.Drawing> 개체는 개체보다 <xref:System.Windows.Shapes.Shape> 더 간단하고 성능 특성을 더 잘 제공합니다.  
  
 A를 <xref:System.Windows.Shapes.Shape> 사용하면 화면에 그래픽 모양을 그릴 수 있습니다. <xref:System.Windows.FrameworkElement> 클래스에서 파생되므로 <xref:System.Windows.Shapes.Shape> 개체를 패널 및 대부분의 컨트롤 내에서 사용할 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 그래픽 및 렌더링 서비스에 대한 여러 계층의 액세스를 제공합니다. 최상위 계층에서 <xref:System.Windows.Shapes.Shape> 개체는 사용하기 쉽고 레이아웃 및 이벤트 처리와 같은 많은 유용한 기능을 제공합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 바로 사용할 수 있는 여러 도형 개체를 제공합니다. 모든 셰이프 개체는 클래스에서 상속됩니다. <xref:System.Windows.Shapes.Shape> 사용 가능한 <xref:System.Windows.Shapes.Ellipse>셰이프 개체에는 " <xref:System.Windows.Shapes.Line>및 <xref:System.Windows.Shapes.Path> <xref:System.Windows.Shapes.Polygon> <xref:System.Windows.Shapes.Polyline> <xref:System.Windows.Shapes.Rectangle>.  
  
 <xref:System.Windows.Media.Drawing>반면에 개체는 <xref:System.Windows.FrameworkElement> 클래스에서 파생되지 않으며 셰이프, 이미지 및 텍스트를 렌더링하기 위한 더 가벼운 구현을 제공합니다.  
  
 개체에는 네 <xref:System.Windows.Media.Drawing> 가지 유형이 있습니다.  
  
- <xref:System.Windows.Media.GeometryDrawing>셰이프를 그립니다.  
  
- <xref:System.Windows.Media.ImageDrawing>이미지를 그립니다.  
  
- <xref:System.Windows.Media.GlyphRunDrawing>텍스트를 그립니다.  
  
- <xref:System.Windows.Media.DrawingGroup>다른 도면을 그립니다. 다른 그리기를 단일 합성 그리기로 결합하려면 그리기 그룹을 사용합니다.  
  
 오브젝트는 <xref:System.Windows.Media.GeometryDrawing> 형상 컨텐더를 렌더링하는 데 사용됩니다. <xref:System.Windows.Media.Geometry> 클래스 및 이 클래스에서 파생되는 구체적인 클래스(예: <xref:System.Windows.Media.CombinedGeometry>" <xref:System.Windows.Media.EllipseGeometry>및 <xref:System.Windows.Media.PathGeometry>)는 2D 그래픽을 렌더링하고 적중 테스트 및 클리핑 지원을 제공하는 수단을 제공합니다. 기하 도형 개체를 사용하면 컨트롤 영역을 정의하거나 이미지에 적용할 클립 영역을 정의하는 등의 작업을 수행할 수 있습니다. 기하 도형 개체는 사각형 및 원과 같은 단순 영역 또는 둘 이상의 기하 도형 개체에서 만들어진 복합 영역이 될 수 있습니다. 보다 복잡한 기하학적 영역은 <xref:System.Windows.Media.PathSegment>에서 와 같은 <xref:System.Windows.Media.ArcSegment> <xref:System.Windows.Media.BezierSegment>파생 객체를 <xref:System.Windows.Media.QuadraticBezierSegment>결합하여 작성할 수 있습니다.  
  
 표면으로, <xref:System.Windows.Media.Geometry> 클래스와 <xref:System.Windows.Shapes.Shape> 클래스는 매우 유사하다. 둘 다 2D 그래픽의 렌더링에 사용되며 둘 다 예를 들어 <xref:System.Windows.Media.EllipseGeometry> 에서 <xref:System.Windows.Shapes.Ellipse>파생되는 유사한 콘크리트 클래스를 가지고 있습니다. 그러나 두 클래스 집합 사이에는 중요한 차이점이 있습니다. 하나는 <xref:System.Windows.Media.Geometry> 클래스자체를 그릴 수 있는 기능과 <xref:System.Windows.Shapes.Shape> 같은 클래스의 기능이 부족합니다. 기하 도형 개체를 그리려면 DrawingContext, Drawing 또는 Path(Path가 Shape라는 것에 주의)와 같은 또 다른 클래스를 사용하여 그리기 작업을 수행해야 합니다. 채우기, 스트로크 및 스트로크 두께와 같은 렌더링 속성이 기하 도형 개체를 그리는 클래스에 있는 반면, 도형 개체는 이러한 속성을 포함합니다. 이 차이를 보여 주는 한 가지 예로, 기하 도형 개체는 원과 같은 영역을 정의하지만, 도형 개체는 영역을 정의하고 영역 채우기 및 윤곽선 그리기 방법을 정의하며 레이아웃 시스템에 참여할 수 있습니다.  
  
 개체는 클래스에서 파생되므로 <xref:System.Windows.Shapes.Shape> 개체를 <xref:System.Windows.FrameworkElement> 사용하면 응용 프로그램에서 메모리 소비가 훨씬 더 늘어질 수 있습니다. 그래픽 콘텐츠에 <xref:System.Windows.FrameworkElement> 대한 기능이 실제로 필요하지 않은 경우 경량 <xref:System.Windows.Media.Drawing> 객체를 사용하는 것이 좋습니다.  
  
 객체에 대한 <xref:System.Windows.Media.Drawing> 자세한 내용은 [객체 그리기 개요를](../graphics-multimedia/drawing-objects-overview.md)참조하십시오.  
  
<a name="StreamGeometry_Objects"></a>
## <a name="streamgeometry-objects"></a>StreamGeometry 개체  
 오브젝트는 <xref:System.Windows.Media.StreamGeometry> 기하학적 <xref:System.Windows.Media.PathGeometry> 모양을 만들기 위한 가벼운 대안입니다. 복잡한 <xref:System.Windows.Media.StreamGeometry> 형상을 설명해야 하는 경우를 사용합니다. <xref:System.Windows.Media.StreamGeometry>많은 <xref:System.Windows.Media.PathGeometry> 개체를 처리하는 데 최적화되어 있으며 많은 <xref:System.Windows.Media.PathGeometry> 개별 개체를 사용하는 것과 비교할 때 더 나은 성능을 발휘합니다.  
  
 다음 예제에서는 특성 구문을 사용하여 <xref:System.Windows.Media.StreamGeometry> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 삼각형을 만듭니다.  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 객체에 대한 <xref:System.Windows.Media.StreamGeometry> 자세한 내용은 [스트림 지오메트리를 사용하여 셰이프 만들기](../graphics-multimedia/how-to-create-a-shape-using-a-streamgeometry.md)를 참조하십시오.  
  
<a name="DrawingVisual_Objects"></a>
## <a name="drawingvisual-objects"></a>DrawingVisual 개체  
 개체는 <xref:System.Windows.Media.DrawingVisual> 셰이프, 이미지 또는 텍스트를 렌더링하는 데 사용되는 경량 그리기 클래스입니다. 이 클래스는 성능을 향상시키는 레이아웃이나 이벤트 처리를 제공하지 않으므로 간단한 클래스로 간주됩니다. 이러한 이유 때문에 그리기는 배경 및 클립 아트에 적합합니다. 자세한 내용은 [DrawingVisual 개체 사용](../graphics-multimedia/using-drawingvisual-objects.md)을 참조하세요.  
  
<a name="Images"></a>
## <a name="images"></a>이미지  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]이미징은 이전 버전의 Windows에서 이미징 기능을 크게 향상시고 있습니다. 비트맵을 표시하거나 공용 컨트롤에 이미지를 사용하는 등의 이미징 기능은 원래 주로 Microsoft Windows GDI(그래픽 디바이스 인터페이스) 또는 Microsoft Windows GDI+ API(응용 프로그래밍 인터페이스)에 의해 처리되었습니다. 이러한 API는 기준 이미징 기능은 제공했지만 코덱 확장성 및 고품질 이미지 지원 등과 같은 기능이 없었습니다. WPF 이미징 API는 GDI 및 GDI+의 단점을 보완하고 애플리케이션 내에서 이미지를 표시 및 사용하기 위한 새로운 API 집합을 제공하도록 다시 디자인되었습니다.  
  
 이미지를 사용할 경우 더 나은 성능을 얻으려면 다음 권장 사항을 고려하세요.  
  
- 애플리케이션에서 썸네일 이미지를 표시해야 할 경우 크기를 줄인 버전의 이미지를 만듭니다. 기본적으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 이미지를 로드하여 전체 크기로 디코딩합니다. 썸네일 버전의 이미지만 필요한 경우 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 이미지를 전체 크기로 디코딩한 다음 썸네일 크기로 배율을 조정하는 것은 불필요한 작업입니다. 이러한 불필요한 오버헤드를 방지하려면 이미지를 썸네일 크기로 디코딩하도록 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 요청하거나 썸네일 크기 이미지를 로드하도록 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 요청하면 됩니다.  
  
- 이미지를 항상 기본 크기가 아니라 원하는 크기로 디코딩합니다. 위에 언급한 것처럼 이미지를 기본 전체 크기가 아니라 원하는 크기로 디코딩하도록 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 요청합니다. 이렇게 하면 애플리케이션의 작업 집합이 줄어들 뿐만 아니라 실행 속도가 빨라집니다.  
  
- 가능한 경우 여러 이미지로 구성된 필름 스트립과 같은 단일 이미지로 이미지를 결합합니다.  
  
- 자세한 내용은 [이미징 개요를](../graphics-multimedia/imaging-overview.md)참조하십시오.  
  
### <a name="bitmapscalingmode"></a>BitmapScalingMode  
 비트맵의 배율에 애니메이션 효과를 주면 기본 고품질 이미지 샘플 다시 만들기 알고리즘에 시스템 리소스가 많이 사용되므로 프레임 속도가 떨어지고 애니메이션이 끊길 수 있습니다. 개체의 <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A> 속성을 설정하여 <xref:System.Windows.Media.BitmapScalingMode.LowQuality> 비트맵의 크기를 조정할 때 더 부드러운 애니메이션을 만들 수 있습니다. <xref:System.Windows.Media.RenderOptions> <xref:System.Windows.Media.BitmapScalingMode.LowQuality>모드는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 렌더링 엔진이 이미지를 처리할 때 품질에 최적화된 알고리즘에서 속도에 최적화된 알고리즘으로 전환하도록 지시합니다.  
  
 다음 예제에서는 설정 하는 방법의 <xref:System.Windows.Media.BitmapScalingMode> 이미지 개체에 대 한 합니다.  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet2)]
 [!code-vb[RenderOptions#RenderOptionsSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet2)]  
  
### <a name="cachinghint"></a>CachingHint  
 기본적으로 <xref:System.Windows.Media.DrawingBrush> 및 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 와 <xref:System.Windows.Media.VisualBrush>같은 개체의 <xref:System.Windows.Media.TileBrush> 렌더링된 내용을 캐시하지 않습니다. 장면의 <xref:System.Windows.Media.TileBrush> 내용이나 사용이 변경되지 않는 정적 시나리오에서는 비디오 메모리를 절약하므로 의미가 있습니다. 정적 콘텐츠가 비정적 방식으로 <xref:System.Windows.Media.TileBrush> 사용되는 경우(예: 정적 <xref:System.Windows.Media.DrawingBrush> 또는 <xref:System.Windows.Media.VisualBrush> 회전하는 3D 오브젝트의 표면에 매핑되는 경우)는 별로 의미가 없습니다. 기본 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 동작은 콘텐츠가 변경되지 않더라도 <xref:System.Windows.Media.DrawingBrush> 또는 <xref:System.Windows.Media.VisualBrush> 모든 프레임에 대한 전체 콘텐츠를 다시 렌더링하는 것입니다.  
  
 <xref:System.Windows.Media.RenderOptions> <xref:System.Windows.Media.CachingHint.Cache> 개체의 <xref:System.Windows.Media.RenderOptions.CachingHint%2A> 속성을 설정하면 타일브러시 오브젝트의 캐시된 버전을 사용하여 성능을 높일 수 있습니다.  
  
 <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A> 및 <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> 속성 값은 시기를 결정 하는 상대 크기 값을 <xref:System.Windows.Media.TileBrush> 확장의 변경으로 인해 개체를 다시 생성 해야 합니다. 설정 하 여 예를 들어, 합니다 <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> 속성을 2.0으로 캐시를 <xref:System.Windows.Media.TileBrush> 만 크기로 현재 캐시의 크기 두 배를 초과 하는 경우 다시 생성 해야 합니다.  
  
 다음 예제에 대 한 캐싱 힌트 옵션을 사용 하는 방법을 보여 줍니다는 <xref:System.Windows.Media.DrawingBrush>합니다.  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet3)]
 [!code-vb[RenderOptions#RenderOptionsSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet3)]  
  
## <a name="see-also"></a>참고 항목

- [WPF 애플리케이션 성능 최적화](optimizing-wpf-application-performance.md)
- [애플리케이션 성능 계획](planning-for-application-performance.md)
- [하드웨어 활용](optimizing-performance-taking-advantage-of-hardware.md)
- [레이아웃 및 디자인](optimizing-performance-layout-and-design.md)
- [개체 동작](optimizing-performance-object-behavior.md)
- [응용 프로그램 리소스](optimizing-performance-application-resources.md)
- [텍스트](optimizing-performance-text.md)
- [데이터 바인딩](optimizing-performance-data-binding.md)
- [기타 성능 추천 사항](optimizing-performance-other-recommendations.md)
- [애니메이션에 대한 유용한 정보](../graphics-multimedia/animation-tips-and-tricks.md)
