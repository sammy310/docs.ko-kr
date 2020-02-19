---
title: '방법: 복합 도형 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- shapes [WPF], composite
- composite shapes [WPF]
- graphics [WPF], composite shapes
ms.assetid: 8e5c7ef4-d7ed-4c43-afc9-ca01325c300b
ms.openlocfilehash: c56053f2b07d6055deac5097a68fd7b80ad704ba
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452099"
---
# <a name="how-to-create-a-composite-shape"></a><span data-ttu-id="6ae15-102">방법: 복합 도형 만들기</span><span class="sxs-lookup"><span data-stu-id="6ae15-102">How to: Create a Composite Shape</span></span>
<span data-ttu-id="6ae15-103">이 예제에서는 <xref:System.Windows.Media.Geometry> 개체를 사용 하 여 복합 도형을 만들고 <xref:System.Windows.Shapes.Path> 요소를 사용 하 여 표시 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6ae15-103">This example shows how to create composite shapes using <xref:System.Windows.Media.Geometry> objects and display them using a <xref:System.Windows.Shapes.Path> element.</span></span> <span data-ttu-id="6ae15-104">다음 예에서는 <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>및 <xref:System.Windows.Media.RectangleGeometry>를 <xref:System.Windows.Media.GeometryGroup> 사용 하 여 복합 셰이프를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6ae15-104">In the following example, a <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>, and a <xref:System.Windows.Media.RectangleGeometry> are used with a <xref:System.Windows.Media.GeometryGroup> to create a composite shape.</span></span> <span data-ttu-id="6ae15-105">그런 다음 <xref:System.Windows.Shapes.Path> 요소를 사용 하 여 기 하 도형을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="6ae15-105">The geometries are then drawn using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ae15-106">예제</span><span class="sxs-lookup"><span data-stu-id="6ae15-106">Example</span></span>  
 [!code-xaml[GeometrySample#19](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 <span data-ttu-id="6ae15-107">다음 그림은 이전 예제에서 만든 도형을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6ae15-107">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="6ae15-108">![GeometryGroup를 사용 하 여 만든 복합 기 하 도형](./media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")</span><span class="sxs-lookup"><span data-stu-id="6ae15-108">![A composite geometry created using a GeometryGroup](./media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")</span></span>  
<span data-ttu-id="6ae15-109">복합 기 하 도형</span><span class="sxs-lookup"><span data-stu-id="6ae15-109">Composite Geometry</span></span>  
  
 <span data-ttu-id="6ae15-110">다각형 및 곡선 세그먼트를 포함 하는 도형 같은 보다 복잡 한 셰이프는 <xref:System.Windows.Media.PathGeometry>을 사용 하 여 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae15-110">More complex shapes, such as polygons and shapes with curved segments, may be created using a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="6ae15-111"><xref:System.Windows.Media.PathGeometry>를 사용 하 여 모양을 만드는 방법을 보여 주는 예제는 [PathGeometry를 사용 하 여 도형 만들기](how-to-create-a-shape-by-using-a-pathgeometry.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6ae15-111">For an example showing how to create a shape using a <xref:System.Windows.Media.PathGeometry>, see [Create a Shape by Using a PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span></span>  <span data-ttu-id="6ae15-112">이 예제에서는 <xref:System.Windows.Shapes.Path> 요소를 사용 하 여 도형을 화면에 렌더링 하지만 <xref:System.Windows.Media.Geometry> 개체를 사용 하 여 <xref:System.Windows.Media.GeometryDrawing> 또는 <xref:System.Windows.Media.DrawingContext>의 콘텐츠를 설명할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae15-112">Although this example renders a shape to the screen using a <xref:System.Windows.Shapes.Path> element, <xref:System.Windows.Media.Geometry> objects may also be used to describe the contents of a <xref:System.Windows.Media.GeometryDrawing> or a <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="6ae15-113">클리핑 및 적중 테스트에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae15-113">They may also be used for clipping and hit-testing.</span></span>  
  
 <span data-ttu-id="6ae15-114">이 예제는 더 큰 샘플에 속합니다. 전체 샘플을 보려면 [기하 도형 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ae15-114">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>
