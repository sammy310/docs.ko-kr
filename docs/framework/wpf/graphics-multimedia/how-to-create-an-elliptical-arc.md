---
title: '방법: 타원형 원호 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], elliptical arcs
- elliptical arcs [WPF], creating
- arcs [WPF], elliptical
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
ms.openlocfilehash: aae304b9963f3a8e5833b4d8ba0a54777a750225
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183653"
---
# <a name="how-to-create-an-elliptical-arc"></a><span data-ttu-id="4bd8f-102">방법: 타원형 원호 만들기</span><span class="sxs-lookup"><span data-stu-id="4bd8f-102">How to: Create an Elliptical Arc</span></span>
<span data-ttu-id="4bd8f-103">이 예제에서는 타원형 호를 그리는 방법을 보여 줍니다. 타원형 호를 만들려면 사용 합니다 <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, 및 <xref:System.Windows.Media.ArcSegment> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4bd8f-103">This example shows how to draw an elliptical arc. To create an elliptical arc, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.ArcSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4bd8f-104">예제</span><span class="sxs-lookup"><span data-stu-id="4bd8f-104">Example</span></span>  
 <span data-ttu-id="4bd8f-105">다음 예제에서는 타원형 호가 그려집니다 (10100)에서 (200100).</span><span class="sxs-lookup"><span data-stu-id="4bd8f-105">In the following examples, an elliptical arc is drawn from (10,100) to (200,100).</span></span> <span data-ttu-id="4bd8f-106">호에는 <xref:System.Windows.Media.ArcSegment.Size%2A> 50에서 100 장치 독립적 픽셀을 <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> 45도의 <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> 설정 `true`, 및 <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> 의 <xref:System.Windows.Media.SweepDirection.Counterclockwise>합니다.</span><span class="sxs-lookup"><span data-stu-id="4bd8f-106">The arc has a <xref:System.Windows.Media.ArcSegment.Size%2A> of 100 by 50 device-independent pixels, a <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> of 45 degrees, an <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> setting of `true`, and a <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> of <xref:System.Windows.Media.SweepDirection.Counterclockwise>.</span></span>  
  
 <span data-ttu-id="4bd8f-107">[xaml]</span><span class="sxs-lookup"><span data-stu-id="4bd8f-107">[xaml]</span></span>  
  
 <span data-ttu-id="4bd8f-108">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], 경로를 설명할 특성 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bd8f-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#56](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  
  
 <span data-ttu-id="4bd8f-109">[xaml]</span><span class="sxs-lookup"><span data-stu-id="4bd8f-109">[xaml]</span></span>  
  
 <span data-ttu-id="4bd8f-110">(이 특성 구문은 실제로 만들어지는 참고를 <xref:System.Windows.Media.StreamGeometry>, 가벼운 버전의는 <xref:System.Windows.Media.PathGeometry>합니다.</span><span class="sxs-lookup"><span data-stu-id="4bd8f-110">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="4bd8f-111">자세한 내용은 [경로 태그 구문](path-markup-syntax.md) 페이지를 참조하세요.)</span><span class="sxs-lookup"><span data-stu-id="4bd8f-111">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="4bd8f-112">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]를 명시적으로 object 태그를 사용 하 여 타원형 호를 그릴 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bd8f-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can also draw an elliptical arc by explicitly using object tags.</span></span> <span data-ttu-id="4bd8f-113">다음은 위의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="4bd8f-113">The following is equivalent to the preceding [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 [!code-xaml[GeometrySample#36](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 <span data-ttu-id="4bd8f-114">이 예제는 더 큰 샘플의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="4bd8f-114">This example is part of a larger sample.</span></span> <span data-ttu-id="4bd8f-115">전체 샘플을 참조 하세요. 합니다 [기 하 도형 샘플](https://go.microsoft.com/fwlink/?LinkID=159989)합니다.</span><span class="sxs-lookup"><span data-stu-id="4bd8f-115">For the complete sample, see the [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bd8f-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="4bd8f-116">See also</span></span>

- [<span data-ttu-id="4bd8f-117">정방형 3차원 곡선 만들기</span><span class="sxs-lookup"><span data-stu-id="4bd8f-117">Create a Quadratic Bezier Curve</span></span>](how-to-create-a-quadratic-bezier-curve.md)
- [<span data-ttu-id="4bd8f-118">입방형 3차원 곡선 만들기</span><span class="sxs-lookup"><span data-stu-id="4bd8f-118">Create a Cubic Bezier Curve</span></span>](how-to-create-a-cubic-bezier-curve.md)
