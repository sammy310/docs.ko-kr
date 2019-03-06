---
title: '방법: PathGeometry를 사용하여 도형 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
ms.openlocfilehash: ce84f2509116207afa200ddf83dcdc1f8101da13
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356227"
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a><span data-ttu-id="f5f22-102">방법: PathGeometry를 사용하여 도형 만들기</span><span class="sxs-lookup"><span data-stu-id="f5f22-102">How to: Create a Shape by Using a PathGeometry</span></span>
<span data-ttu-id="f5f22-103">사용 하 여 도형을 만드는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.PathGeometry> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="f5f22-103">This example shows how to create a shape using the <xref:System.Windows.Media.PathGeometry> class.</span></span> <span data-ttu-id="f5f22-104"><xref:System.Windows.Media.PathGeometry> 개체는 하나 이상의 구성 됩니다 <xref:System.Windows.Media.PathFigure> 객체; 각 <xref:System.Windows.Media.PathFigure> 다른 "그림" 또는 도형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f5f22-104"><xref:System.Windows.Media.PathGeometry> objects are composed of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="f5f22-105">각 <xref:System.Windows.Media.PathFigure> 자체는 하나 이상의 구성 <xref:System.Windows.Media.PathSegment> 각각이 그림 또는 도형의 연결 된 부분을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f5f22-105">Each <xref:System.Windows.Media.PathFigure> is itself composed of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="f5f22-106">세그먼트 형식 포함 <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, 및 <xref:System.Windows.Media.BezierSegment>합니다.</span><span class="sxs-lookup"><span data-stu-id="f5f22-106">Segment types include <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, and <xref:System.Windows.Media.BezierSegment>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5f22-107">예제</span><span class="sxs-lookup"><span data-stu-id="f5f22-107">Example</span></span>  
 <span data-ttu-id="f5f22-108">다음 예제에서는 <xref:System.Windows.Media.PathGeometry> 삼각형이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5f22-108">The following example uses a <xref:System.Windows.Media.PathGeometry> to create a triangle.</span></span> <span data-ttu-id="f5f22-109">합니다 <xref:System.Windows.Media.PathGeometry> 를 사용 하 여 표시 되는 <xref:System.Windows.Shapes.Path> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f5f22-109">The  <xref:System.Windows.Media.PathGeometry> is displayed using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 [!code-xaml[GeometrySample#49](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 <span data-ttu-id="f5f22-110">다음 그림은 이전 예제에서 만든 도형을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f5f22-110">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="f5f22-111">![PathGeometry](./media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span><span class="sxs-lookup"><span data-stu-id="f5f22-111">![A PathGeometry](./media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span></span>  
<span data-ttu-id="f5f22-112">PathGeometry를 사용 하 여 만든 삼각형</span><span class="sxs-lookup"><span data-stu-id="f5f22-112">A triangle created with a PathGeometry</span></span>  
  
 <span data-ttu-id="f5f22-113">이전 예제에는 비교적 간단한 도형을, 삼각형을 만드는 방법을 보여 주었습니다.</span><span class="sxs-lookup"><span data-stu-id="f5f22-113">The previous example showed how to create a relatively simple shape, a triangle.</span></span> <span data-ttu-id="f5f22-114"><xref:System.Windows.Media.PathGeometry> 호와 곡선을 포함 하 여 더 복잡 한 도형을 만들고를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5f22-114">A <xref:System.Windows.Media.PathGeometry> can also be used to create more complex shapes, including arcs and curves.</span></span> <span data-ttu-id="f5f22-115">예제를 보려면 [타원형 원호 만들기](how-to-create-an-elliptical-arc.md)를 [입방 형 3 차원 곡선을 만듭니다](how-to-create-a-cubic-bezier-curve.md), 및 [정방형 베 지 어 곡선 만들기](how-to-create-a-quadratic-bezier-curve.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f5f22-115">For examples, see [Create an Elliptical Arc](how-to-create-an-elliptical-arc.md), [Create a Cubic Bezier Curve](how-to-create-a-cubic-bezier-curve.md), and [Create a Quadratic Bezier Curve](how-to-create-a-quadratic-bezier-curve.md).</span></span>  
  
 <span data-ttu-id="f5f22-116">이 예제는 더 큰 샘플에 속합니다. 전체 샘플을 보려면 [기하 도형 샘플](https://go.microsoft.com/fwlink/?LinkID=159989)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5f22-116">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5f22-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="f5f22-117">See also</span></span>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [<span data-ttu-id="f5f22-118">Geometry 개요</span><span class="sxs-lookup"><span data-stu-id="f5f22-118">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="f5f22-119">기 하 도형 샘플</span><span class="sxs-lookup"><span data-stu-id="f5f22-119">Geometries Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159989)
