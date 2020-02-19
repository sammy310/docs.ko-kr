---
title: '방법: PathGeometry를 사용하여 도형 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
ms.openlocfilehash: bdf3c937bfff1780a72e8743bc86a3c3dad2558d
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452047"
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a><span data-ttu-id="d0368-102">방법: PathGeometry를 사용하여 도형 만들기</span><span class="sxs-lookup"><span data-stu-id="d0368-102">How to: Create a Shape by Using a PathGeometry</span></span>
<span data-ttu-id="d0368-103">이 예제에서는 <xref:System.Windows.Media.PathGeometry> 클래스를 사용 하 여 모양을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0368-103">This example shows how to create a shape using the <xref:System.Windows.Media.PathGeometry> class.</span></span> <span data-ttu-id="d0368-104"><xref:System.Windows.Media.PathGeometry> 개체는 하나 이상의 <xref:System.Windows.Media.PathFigure> 개체로 구성 됩니다. 각 <xref:System.Windows.Media.PathFigure>는 다른 "그림" 또는 도형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d0368-104"><xref:System.Windows.Media.PathGeometry> objects are composed of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="d0368-105">각 <xref:System.Windows.Media.PathFigure>는 각각 그림 또는 모양의 연결 된 부분을 나타내는 하나 이상의 <xref:System.Windows.Media.PathSegment> 개체로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0368-105">Each <xref:System.Windows.Media.PathFigure> is itself composed of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="d0368-106">세그먼트 형식은 <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>및 <xref:System.Windows.Media.BezierSegment>를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0368-106">Segment types include <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, and <xref:System.Windows.Media.BezierSegment>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0368-107">예제</span><span class="sxs-lookup"><span data-stu-id="d0368-107">Example</span></span>  
 <span data-ttu-id="d0368-108">다음 예에서는 <xref:System.Windows.Media.PathGeometry>를 사용 하 여 삼각형을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d0368-108">The following example uses a <xref:System.Windows.Media.PathGeometry> to create a triangle.</span></span> <span data-ttu-id="d0368-109"><xref:System.Windows.Shapes.Path> 요소를 사용 하 여 <xref:System.Windows.Media.PathGeometry> 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0368-109">The  <xref:System.Windows.Media.PathGeometry> is displayed using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 [!code-xaml[GeometrySample#49](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 <span data-ttu-id="d0368-110">다음 그림은 이전 예제에서 만든 도형을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0368-110">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="d0368-111">![PathGeometry](./media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span><span class="sxs-lookup"><span data-stu-id="d0368-111">![A PathGeometry](./media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span></span>  
<span data-ttu-id="d0368-112">PathGeometry를 사용 하 여 만든 삼각형입니다.</span><span class="sxs-lookup"><span data-stu-id="d0368-112">A triangle created with a PathGeometry</span></span>  
  
 <span data-ttu-id="d0368-113">앞의 예제에서는 비교적 간단한 모양의 삼각형을 만드는 방법을 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="d0368-113">The previous example showed how to create a relatively simple shape, a triangle.</span></span> <span data-ttu-id="d0368-114"><xref:System.Windows.Media.PathGeometry>를 사용 하 여 호와 곡선을 포함 하 여 더 복잡 한 도형을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0368-114">A <xref:System.Windows.Media.PathGeometry> can also be used to create more complex shapes, including arcs and curves.</span></span> <span data-ttu-id="d0368-115">예제는 [타원형 원호 만들기](how-to-create-an-elliptical-arc.md), [입방 형 3 차원 곡선 만들기](how-to-create-a-cubic-bezier-curve.md)및 [정방형 3 차원 곡선 만들기](how-to-create-a-quadratic-bezier-curve.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d0368-115">For examples, see [Create an Elliptical Arc](how-to-create-an-elliptical-arc.md), [Create a Cubic Bezier Curve](how-to-create-a-cubic-bezier-curve.md), and [Create a Quadratic Bezier Curve](how-to-create-a-quadratic-bezier-curve.md).</span></span>  
  
 <span data-ttu-id="d0368-116">이 예제는 더 큰 샘플에 속합니다. 전체 샘플을 보려면 [기하 도형 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d0368-116">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0368-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d0368-117">See also</span></span>

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [<span data-ttu-id="d0368-118">Geometry 개요</span><span class="sxs-lookup"><span data-stu-id="d0368-118">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="d0368-119">기 하 도형 샘플</span><span class="sxs-lookup"><span data-stu-id="d0368-119">Geometries Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)
