---
title: 경로 애니메이션 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], paths
- path animations [WPF]
ms.assetid: 979c732c-df74-47a6-be96-8e07b3707d53
ms.openlocfilehash: 07628d26c8222c7c01f58826a36a15e13dc31ff4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181874"
---
# <a name="path-animations-overview"></a>경로 애니메이션 개요
<a name="introduction"></a> 이 항목에서는 기하학적 경로를 사용하여 출력 값을 생성할 수 있도록 하는 경로 애니메이션을 소개합니다. 경로 애니메이션은 복잡한 경로를 따라 개체를 이동하고 회전하는 데 유용합니다.  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>전제 조건  
 이 항목을 이해하려면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애니메이션 기능에 대해 잘 알고 있어야 합니다. 애니메이션 기능에 대한 소개는 [애니메이션 개요를](animation-overview.md)참조하십시오.  
  
 오브젝트를 <xref:System.Windows.Media.PathGeometry> 사용하여 경로 애니메이션을 정의하기 때문에 다양한 <xref:System.Windows.Media.PathGeometry> 유형의 <xref:System.Windows.Media.PathSegment> 오브젝트도 잘 알고 있어야 합니다. 자세한 내용은 [지오메트리 개요](geometry-overview.md)를 참조하십시오.  
  
<a name="what_is_a_path_animation"></a>
## <a name="what-is-a-path-animation"></a>경로 애니메이션이란?  
 경로 애니메이션은 a를 <xref:System.Windows.Media.Animation.AnimationTimeline> <xref:System.Windows.Media.PathGeometry> 입력으로 사용하는 유형입니다. 시작, 시작 또는 By 속성을 설정하거나(시작/받는/별 애니메이션에 대해 수행하는 것처럼) 키 프레임을 사용하는 대신(키 프레임 애니메이션에 사용할 때) 기하학적 경로를 정의하고 이를 사용하여 경로 애니메이션의 `PathGeometry` 속성을 설정합니다. 경로 애니메이션은 진행되면서 경로에서 x, y 및 각도 정보를 읽고 해당 정보로 출력을 생성합니다.  
  
 경로 애니메이션은 복잡한 경로를 따라 개체에 애니메이션 효과를 주는 데 매우 유용합니다. 경로를 따라 객체를 이동하는 한 가지 <xref:System.Windows.Media.MatrixTransform> 방법은 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> a와 a를 사용하여 복잡한 경로를 따라 객체를 변환하는 것입니다. 다음 예제에서는 개체를 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 사용하여 <xref:System.Windows.Media.MatrixTransform.Matrix%2A> <xref:System.Windows.Media.MatrixTransform>의 속성을 애니메이션하여 이 기술을 보여 줍니다. 는 <xref:System.Windows.Media.MatrixTransform> 단추에 적용되고 곡선 된 경로를 따라 이동합니다. 속성이 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> 설정되므로 `true`사각형이 패스의 접선을 따라 회전합니다.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 예제에서 사용되는 경로 구문에 대한 자세한 내용은 [경로 마크업 구문](path-markup-syntax.md) 개요를 참조하세요. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 전체 샘플은 [경로 애니메이션 샘플을](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)참조하십시오.  
  
 in 및 코드를 사용하거나 코드에서 메서드를 사용하여 속성에 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 경로 애니메이션을 적용할 수 있습니다. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <xref:System.Windows.Media.Animation.Storyboard> 경로 애니메이션을 사용하여 하나 이상의 <xref:System.Windows.Media.Animation.AnimationClock> 속성에 만들고 적용할 수도 있습니다. 애니메이션 적용 방법에 대한 자세한 내용은 속성 [애니메이션 기술 개요를](property-animation-techniques-overview.md)참조하십시오.  
  
<a name="animation_types"></a>
## <a name="path-animation-types"></a>경로 애니메이션 형식  
 애니메이션은 속성 값을 생성하므로 속성 형식이 다르면 애니메이션 형식도 다릅니다. <xref:System.Double> (예: a의 <xref:System.Windows.Media.TranslateTransform.X%2A> <xref:System.Windows.Media.TranslateTransform>속성)을 사용하는 속성을 애니메이션하려면 값을 생성하는 애니메이션을 <xref:System.Double> 사용합니다. <xref:System.Windows.Point>을 사용하는 속성을 애니메이션하려면 <xref:System.Windows.Point> 값을 생성하는 애니메이션 등을 사용합니다.  
  
 경로 애니메이션 클래스는 <xref:System.Windows.Media.Animation> 네임스페이스에 속하며 다음 명명 규칙을 사용합니다.  
  
 * \<유형>*`AnimationUsingPath`  
  
 유형>클래스가 애니메이션하는 값의 유형입니다. * \<*  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 다음 경로 애니메이션 클래스를 제공합니다.  
  
|속성 형식|해당 경로 애니메이션 클래스|예제|  
|-------------------|----------------------------------------|-------------|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|[경로를 따라 개체에 애니메이션 효과 주기(Double 애니메이션)](how-to-animate-an-object-along-a-path-double-animation.md)|  
|<xref:System.Windows.Media.Matrix>|<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>|[경로를 따라 개체에 애니메이션 효과 주기(Matrix 애니메이션)](how-to-animate-an-object-along-a-path-matrix-animation.md)|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|[경로를 따라 개체에 애니메이션 효과 주기(포인트 애니메이션)](how-to-animate-an-object-along-a-path-point-animation.md)|  
  
 A는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> <xref:System.Windows.Media.Matrix> 에서 값을 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.PathGeometry%2A>생성합니다. 을 <xref:System.Windows.Media.MatrixTransform>사용하여 사용할 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 경우 패스를 따라 개체를 이동할 수 있습니다. 의 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> 속성을 설정하면 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 패스의 곡선을 따라 오브젝트도 회전합니다. `true`  
  
 A는 <xref:System.Windows.Media.Animation.PointAnimationUsingPath> <xref:System.Windows.Point> <xref:System.Windows.Media.Animation.PointAnimationUsingPath.PathGeometry%2A>의 x- 및 y 좌표에서 값을 생성합니다. 을 <xref:System.Windows.Media.Animation.PointAnimationUsingPath> 사용하여 값을 사용하는 <xref:System.Windows.Point> 속성에 애니메이션을 사용하면 경로를 따라 개체를 이동할 수 있습니다. A는 <xref:System.Windows.Media.Animation.PointAnimationUsingPath> 객체를 회전할 수 없습니다.  
  
 A는 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> <xref:System.Double> 에서 값을 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>생성합니다. <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.Source%2A> 속성을 설정하여 x 좌표, <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> y 좌표 또는 경로각도를 출력으로 사용할지 여부를 지정할 수 있습니다. 를 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 사용하여 오브젝트를 회전하거나 x축 또는 y축을 따라 이동할 수 있습니다.  
  
<a name="pathanimationinput"></a>
## <a name="path-animation-input"></a>경로 애니메이션 입력  
 각 경로 애니메이션 <xref:System.Windows.Media.PathGeometry> 클래스는 입력을 지정하는 속성을 제공합니다. 경로 애니메이션은 <xref:System.Windows.Media.PathGeometry> 을 사용하여 출력 값을 생성합니다. 클래스를 <xref:System.Windows.Media.PathGeometry> 사용하면 호, 곡선 및 선으로 구성된 여러 복잡한 그림을 설명할 수 있습니다.  
  
 a의 <xref:System.Windows.Media.PathGeometry> 중심에는 개체컬렉션이 <xref:System.Windows.Media.PathFigure> 있습니다. 각 그림은 <xref:System.Windows.Media.PathGeometry>에서 불연속 모양을 설명하기 때문에 이러한 개체의 이름이 지정됩니다. 각각은 <xref:System.Windows.Media.PathFigure> 하나 이상의 <xref:System.Windows.Media.PathSegment> 개체로 구성되며, 각 개체는 그림의 세그먼트를 설명합니다.  
  
 세그먼트 형식은 다양합니다.  
  
|세그먼트 형식|Description|  
|------------------|-----------------|  
|<xref:System.Windows.Media.ArcSegment>|두 점 사이에 타원형 호를 만듭니다.|  
|<xref:System.Windows.Media.BezierSegment>|두 점 사이에 입방형 3차원 곡선을 만듭니다.|  
|<xref:System.Windows.Media.LineSegment>|두 점 사이에 선을 만듭니다.|  
|<xref:System.Windows.Media.PolyBezierSegment>|일련의 입방형 3차원 곡선을 만듭니다.|  
|<xref:System.Windows.Media.PolyLineSegment>|일련의 줄을 만듭니다.|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|일련의 정방형 3차원 곡선을 만듭니다.|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|정방형 3차원 곡선을 만듭니다.|  
  
 세그먼트의 <xref:System.Windows.Media.PathFigure> 세그먼트는 세그먼트의 끝점을 다음 세그먼트의 시작점으로 사용하는 단일 기하학적 모양으로 결합됩니다. 속성은 <xref:System.Windows.Media.PathFigure.StartPoint%2A> <xref:System.Windows.Media.PathFigure> 첫 번째 세그먼트가 그려지는 점을 지정합니다. 각 후속 세그먼트는 이전 세그먼트의 끝점에서 시작합니다. 예를 `10,50` 들어 에서 세로 `10,150` 선은 <xref:System.Windows.Media.PathFigure.StartPoint%2A> 속성을 `10,50` 로 설정하고 <xref:System.Windows.Media.LineSegment> <xref:System.Windows.Media.LineSegment.Point%2A> `10,150`의 속성 설정을 사용하여 만들면 정의할 수 있습니다.  
  
 객체에 대한 <xref:System.Windows.Media.PathGeometry> 자세한 내용은 [지오메트리 개요](geometry-overview.md)를 참조하십시오.  
  
 에서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]특수 약어 구문을 사용하여 <xref:System.Windows.Media.PathGeometry.Figures%2A> <xref:System.Windows.Media.PathGeometry>의 속성을 설정할 수도 있습니다. 자세한 내용은 [경로 마크업 구문](path-markup-syntax.md) 개요를 참조하세요.  
  
 예제에서 사용되는 경로 구문에 대한 자세한 내용은 [경로 마크업 구문](path-markup-syntax.md) 개요를 참조하세요. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [경로 애니메이션 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [경로 태그 구문](path-markup-syntax.md)
- [경로 애니메이션 방법 항목](path-animation-how-to-topics.md)
- [애니메이션 개요](animation-overview.md)
- [속성 애니메이션 기술 개요](property-animation-techniques-overview.md)
