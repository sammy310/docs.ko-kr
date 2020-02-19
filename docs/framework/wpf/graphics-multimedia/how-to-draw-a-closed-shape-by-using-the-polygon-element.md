---
title: '방법: Polygon 요소를 사용하여 닫힌 도형 그리기'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], Polygon elements
- closed shapes [WPF], drawing with Polygon elements
- Polygon elements [WPF]
- drawing [WPF], closed shapes with Polygon elements
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
ms.openlocfilehash: 324a5623ee658789b8600a43a89ce26cab7cd6cd
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452976"
---
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a><span data-ttu-id="e5512-102">방법: Polygon 요소를 사용하여 닫힌 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="e5512-102">How to: Draw a Closed Shape by Using the Polygon Element</span></span>
<span data-ttu-id="e5512-103">이 예제에서는 <xref:System.Windows.Shapes.Polygon> 요소를 사용 하 여 닫힌 도형을 그리는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e5512-103">This example shows how to draw a closed shape by using the <xref:System.Windows.Shapes.Polygon> element.</span></span> <span data-ttu-id="e5512-104">폐쇄형 셰이프를 그리려면 <xref:System.Windows.Shapes.Polygon> 요소를 만들고 해당 <xref:System.Windows.Shapes.Polygon.Points%2A> 속성을 사용 하 여 도형의 꼭 짓 점을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5512-104">To draw a closed shape, create a <xref:System.Windows.Shapes.Polygon> element and use its <xref:System.Windows.Shapes.Polygon.Points%2A> property to specify the vertices of a shape.</span></span> <span data-ttu-id="e5512-105">첫 번째 및 마지막 요소를 연결 하는 선이 자동으로 그려집니다.</span><span class="sxs-lookup"><span data-stu-id="e5512-105">A line is automatically drawn that connects the first and last points.</span></span> <span data-ttu-id="e5512-106">마지막으로 <xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>또는 둘 다를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5512-106">Finally, specify a <xref:System.Windows.Shapes.Shape.Fill%2A>, a <xref:System.Windows.Shapes.Shape.Stroke%2A>, or both.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5512-107">예제</span><span class="sxs-lookup"><span data-stu-id="e5512-107">Example</span></span>  
 <span data-ttu-id="e5512-108">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 올바른 점에 대 한 구문은 쉼표로 구분 된 x 및 y 좌표 쌍을 공백으로 구분한 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="e5512-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 <span data-ttu-id="e5512-109">예제에서는 <xref:System.Windows.Controls.Canvas> 사용 하 여 다각형을 포함 하지만 텍스트가 아닌 콘텐츠를 지 원하는 <xref:System.Windows.Controls.Panel> 나 <xref:System.Windows.Controls.Control>에 polygon 요소 (및 다른 모든 셰이프 요소)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5512-109">Although the example uses a <xref:System.Windows.Controls.Canvas> to contain the polygons, you can use polygon elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="e5512-110">이 예제는 더 큰 샘플의 일부입니다. 전체 샘플은 [셰이프 요소 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e5512-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>
