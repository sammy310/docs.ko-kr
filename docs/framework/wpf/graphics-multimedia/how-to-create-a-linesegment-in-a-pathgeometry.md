---
title: '방법: PathGeometry에 LineSegment 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- line segments [WPF], creating
- graphics [WPF], line segments
ms.assetid: 0155ed47-a20d-49a7-a306-186d8e07fbc4
ms.openlocfilehash: a50c98ccc3f6d517e0917cb774af4d49d2bfa7a3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054551"
---
# <a name="how-to-create-a-linesegment-in-a-pathgeometry"></a><span data-ttu-id="b3a50-102">방법: PathGeometry에 LineSegment 만들기</span><span class="sxs-lookup"><span data-stu-id="b3a50-102">How to: Create a LineSegment in a PathGeometry</span></span>

<span data-ttu-id="b3a50-103">이 예제에서는 선분을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b3a50-103">This example shows how to create a line segment.</span></span> <span data-ttu-id="b3a50-104">선 세그먼트를 만들려면 사용 합니다 <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, 및 <xref:System.Windows.Media.LineSegment> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b3a50-104">To create a line segment, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.LineSegment> classes.</span></span>

## <a name="example"></a><span data-ttu-id="b3a50-105">예제</span><span class="sxs-lookup"><span data-stu-id="b3a50-105">Example</span></span>

<span data-ttu-id="b3a50-106">다음 예제에서는 그리기를 <xref:System.Windows.Media.LineSegment> 에서 (10, 50)를 (200, 70).</span><span class="sxs-lookup"><span data-stu-id="b3a50-106">The following examples draw a <xref:System.Windows.Media.LineSegment> from (10, 50) to (200, 70).</span></span> <span data-ttu-id="b3a50-107">다음 그림에서는 결과 <xref:System.Windows.Media.LineSegment>; 좌표계를 표시 하도록 그리드 배경이 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a50-107">The following illustration shows the resulting <xref:System.Windows.Media.LineSegment>; a grid background was added to show the coordinate system.</span></span>

<span data-ttu-id="b3a50-108">![PathFigure의 LineSegment](./media/graphicsmm-pathgeometrylinesegment.png "graphicsmm_pathgeometrylinesegment") (10, 50)에서 (200, 70)까지 그린는 LineSegment</span><span class="sxs-lookup"><span data-stu-id="b3a50-108">![A LineSegment in a PathFigure](./media/graphicsmm-pathgeometrylinesegment.png "graphicsmm_pathgeometrylinesegment") A LineSegment drawn from (10,50) to (200,70)</span></span>

<span data-ttu-id="b3a50-109">[xaml]</span><span class="sxs-lookup"><span data-stu-id="b3a50-109">[xaml]</span></span>

<span data-ttu-id="b3a50-110">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서는 특성 구문을 사용하여 경로를 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a50-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may use attribute syntax to describe a path.</span></span>

```xaml
<Path Stroke="Black" StrokeThickness="1"
  Data="M 10,50 L 200,70" />
```

<span data-ttu-id="b3a50-111">[xaml]</span><span class="sxs-lookup"><span data-stu-id="b3a50-111">[xaml]</span></span>

<span data-ttu-id="b3a50-112">(이 특성 구문은 실제로 만들어지는 참고를 <xref:System.Windows.Media.StreamGeometry>, 가벼운 버전의는 <xref:System.Windows.Media.PathGeometry>합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a50-112">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="b3a50-113">자세한 내용은 [경로 태그 구문](path-markup-syntax.md) 페이지를 참조하세요.)</span><span class="sxs-lookup"><span data-stu-id="b3a50-113">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>

<span data-ttu-id="b3a50-114">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서는 개체 요소 구문을 사용하여 선분을 그릴 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a50-114">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you may also draw a line segment by using object element syntax.</span></span> <span data-ttu-id="b3a50-115">다음 예제는 이전 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 예제와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a50-115">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>

```xaml
<Path Stroke="Black" StrokeThickness="1">
  <Path.Data>
    <PathGeometry>
      <PathFigure StartPoint="10,50">
        <LineSegment Point="200,70" />
      </PathFigure>
    </PathGeometry>
  </Path.Data>
</Path>
```

```csharp
PathFigure myPathFigure = new PathFigure();
myPathFigure.StartPoint = new Point(10, 50);

LineSegment myLineSegment = new LineSegment();
myLineSegment.Point = new Point(200, 70);

PathSegmentCollection myPathSegmentCollection = new PathSegmentCollection();
myPathSegmentCollection.Add(myLineSegment);

myPathFigure.Segments = myPathSegmentCollection;

PathFigureCollection myPathFigureCollection = new PathFigureCollection();
myPathFigureCollection.Add(myPathFigure);

PathGeometry myPathGeometry = new PathGeometry();
myPathGeometry.Figures = myPathFigureCollection;

Path myPath = new Path();
myPath.Stroke = Brushes.Black;
myPath.StrokeThickness = 1;
myPath.Data = myPathGeometry;
```

```vb
Dim myPathFigure As New PathFigure()
myPathFigure.StartPoint = New Point(10, 50)

Dim myLineSegment As New LineSegment()
myLineSegment.Point = New Point(200, 70)

Dim myPathSegmentCollection As New PathSegmentCollection()
myPathSegmentCollection.Add(myLineSegment)

myPathFigure.Segments = myPathSegmentCollection

Dim myPathFigureCollection As New PathFigureCollection()
myPathFigureCollection.Add(myPathFigure)

Dim myPathGeometry As New PathGeometry()
myPathGeometry.Figures = myPathFigureCollection

Dim myPath As New Path()
myPath.Stroke = Brushes.Black
myPath.StrokeThickness = 1
myPath.Data = myPathGeometry
```

<span data-ttu-id="b3a50-116">이 예제는 더 큰 샘플에 속합니다. 전체 샘플을 보려면 [기하 도형 샘플](https://go.microsoft.com/fwlink/?LinkID=159989)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3a50-116">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>

## <a name="see-also"></a><span data-ttu-id="b3a50-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="b3a50-117">See also</span></span>

- <xref:System.Windows.Media.PathFigure>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.GeometryDrawing>
- <xref:System.Windows.Shapes.Path>
- [<span data-ttu-id="b3a50-118">Geometry 개요</span><span class="sxs-lookup"><span data-stu-id="b3a50-118">Geometry Overview</span></span>](geometry-overview.md)
