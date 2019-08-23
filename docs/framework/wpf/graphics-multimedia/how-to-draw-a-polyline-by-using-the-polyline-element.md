---
title: '방법: Polyline 요소를 사용하여 폴리라인 그리기'
ms.date: 03/30/2017
helpviewer_keywords:
- connected lines [WPF]
- polylines [WPF], drawing
- graphics [WPF], polylines
- lines [WPF], connected (see polylines)
- drawing [WPF], polylines
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
ms.openlocfilehash: fb5220082989a9d0a22c4998bb79c0a196067e7e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934958"
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a><span data-ttu-id="1bac8-102">방법: Polyline 요소를 사용하여 폴리라인 그리기</span><span class="sxs-lookup"><span data-stu-id="1bac8-102">How to: Draw a Polyline by Using the Polyline Element</span></span>
<span data-ttu-id="1bac8-103">이 예제에서는 <xref:System.Windows.Shapes.Polyline> 요소를 사용 하 여 일련의 연결 된 선 인 다중선을 그리는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1bac8-103">This example shows how to draw a polyline, which is a series of connected lines, by using the <xref:System.Windows.Shapes.Polyline> element.</span></span>  
  
 <span data-ttu-id="1bac8-104">다중선을 그리려면 요소를 <xref:System.Windows.Shapes.Polyline> 만든 다음 해당 <xref:System.Windows.Shapes.Polyline.Points%2A> 속성을 사용 하 여 도형 꼭 짓 점을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bac8-104">To draw a polyline, create a <xref:System.Windows.Shapes.Polyline> element and use its <xref:System.Windows.Shapes.Polyline.Points%2A> property to specify the shape vertices.</span></span> <span data-ttu-id="1bac8-105">마지막으로 스트로크가 없는 <xref:System.Windows.Shapes.Shape.Stroke%2A> 선이 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 보이지 않기 때문에 및 속성을 사용 하 여 다중선 윤곽선을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bac8-105">Finally, use the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties to describe the polyline outline because a line without a stroke is invisible.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1bac8-106">요소가 닫힌 모양이 아니기 때문에 속성은 <xref:System.Windows.Shapes.Shape.Fill%2A> 모양 윤곽선을 의도적으로 닫는 경우에도 영향을 주지 않습니다. <xref:System.Windows.Shapes.Polyline></span><span class="sxs-lookup"><span data-stu-id="1bac8-106">Because the <xref:System.Windows.Shapes.Polyline> element is not a closed shape, the <xref:System.Windows.Shapes.Shape.Fill%2A> property has no effect, even if you deliberately close the shape outline.</span></span> <span data-ttu-id="1bac8-107">을 사용 하 여 <xref:System.Windows.Shapes.Shape.Fill%2A>닫힌 도형을 만들려면 요소를 <xref:System.Windows.Shapes.Polygon> 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bac8-107">To create a closed shape with a <xref:System.Windows.Shapes.Shape.Fill%2A>, use a <xref:System.Windows.Shapes.Polygon> element.</span></span>  
  
 <span data-ttu-id="1bac8-108">다음 예제에서는 내에 <xref:System.Windows.Shapes.Polyline> 두 개의 요소 <xref:System.Windows.Controls.Canvas>를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="1bac8-108">The following example draws two <xref:System.Windows.Shapes.Polyline> elements inside a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bac8-109">예제</span><span class="sxs-lookup"><span data-stu-id="1bac8-109">Example</span></span>  
 <span data-ttu-id="1bac8-110">에서 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]점의 유효한 구문은 쉼표로 구분 된 x 및 y 좌표 쌍의 공백으로 구분 된 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="1bac8-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 <span data-ttu-id="1bac8-111">이 예제에서는를 <xref:System.Windows.Controls.Canvas> 사용 하 여 폴리라인을 포함 하지만, 텍스트가 아닌 콘텐츠를 지 원하는 <xref:System.Windows.Controls.Panel> 또는 <xref:System.Windows.Controls.Control> 와 함께 폴리라인 요소 (및 다른 모든 셰이프 요소)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bac8-111">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the polylines, you can use polyline elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="1bac8-112">이 예제는 더 큰 샘플의 일부입니다. 전체 샘플은 [셰이프 요소 샘플](https://go.microsoft.com/fwlink/?LinkID=160037)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1bac8-112">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bac8-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="1bac8-113">See also</span></span>

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Shapes.Polygon>
- <xref:System.Windows.Shapes.Shape>
- [<span data-ttu-id="1bac8-114">셰이프 요소 샘플</span><span class="sxs-lookup"><span data-stu-id="1bac8-114">Shape Elements Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160037)
- [<span data-ttu-id="1bac8-115">WPF에서 Shape 및 기본 그리기 개요</span><span class="sxs-lookup"><span data-stu-id="1bac8-115">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
