---
title: '방법: Polyline 요소를 사용하여 다중선 그리기'
ms.date: 03/30/2017
helpviewer_keywords:
- connected lines [WPF]
- polylines [WPF], drawing
- graphics [WPF], polylines
- lines [WPF], connected (see polylines)
- drawing [WPF], polylines
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
ms.openlocfilehash: 35981f6d5a47ea5d5e024efe714b52103938eddf
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378182"
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a><span data-ttu-id="14065-102">방법: Polyline 요소를 사용하여 다중선 그리기</span><span class="sxs-lookup"><span data-stu-id="14065-102">How to: Draw a Polyline by Using the Polyline Element</span></span>
<span data-ttu-id="14065-103">이 예제에서는 사용 하 여 일련의 연결 된 줄은 다중선 그리기를 <xref:System.Windows.Shapes.Polyline> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="14065-103">This example shows how to draw a polyline, which is a series of connected lines, by using the <xref:System.Windows.Shapes.Polyline> element.</span></span>  
  
 <span data-ttu-id="14065-104">다중선 그리기를 만들려면를 <xref:System.Windows.Shapes.Polyline> 요소 및 사용 하 여 해당 <xref:System.Windows.Shapes.Polyline.Points%2A> 셰이프 꼭 짓 점을 지정 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="14065-104">To draw a polyline, create a <xref:System.Windows.Shapes.Polyline> element and use its <xref:System.Windows.Shapes.Polyline.Points%2A> property to specify the shape vertices.</span></span> <span data-ttu-id="14065-105">마지막으로 사용 합니다 <xref:System.Windows.Shapes.Shape.Stroke%2A> 및 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 스트로크 없는 줄에 표시 되지 않으므로 간략하게 설명 하는 다중선을 설명 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="14065-105">Finally, use the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties to describe the polyline outline because a line without a stroke is invisible.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14065-106">때문에 합니다 <xref:System.Windows.Shapes.Polyline> 요소는 닫힌된 셰이프는 <xref:System.Windows.Shapes.Shape.Fill%2A> 모양의 윤곽선을 의도적으로 닫은 경우에 속성에 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14065-106">Because the <xref:System.Windows.Shapes.Polyline> element is not a closed shape, the <xref:System.Windows.Shapes.Shape.Fill%2A> property has no effect, even if you deliberately close the shape outline.</span></span> <span data-ttu-id="14065-107">사용 하 여 닫힌된 도형을 만들어야를 <xref:System.Windows.Shapes.Shape.Fill%2A>를 사용 하 여를 <xref:System.Windows.Shapes.Polygon> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="14065-107">To create a closed shape with a <xref:System.Windows.Shapes.Shape.Fill%2A>, use a <xref:System.Windows.Shapes.Polygon> element.</span></span>  
  
 <span data-ttu-id="14065-108">다음 예제에서는 두 개의 그립니다 <xref:System.Windows.Shapes.Polyline> 내부 요소는 <xref:System.Windows.Controls.Canvas>합니다.</span><span class="sxs-lookup"><span data-stu-id="14065-108">The following example draws two <xref:System.Windows.Shapes.Polyline> elements inside a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14065-109">예제</span><span class="sxs-lookup"><span data-stu-id="14065-109">Example</span></span>  
 <span data-ttu-id="14065-110">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], 지점에 대 한 구문이 공백으로 구분 된 목록 쉼표로 구분 된 x 및 y 좌표 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="14065-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 <span data-ttu-id="14065-111">이 예제에서는 한 <xref:System.Windows.Controls.Canvas> 다중선을 포함 하려면 사용할 수 있습니다 폴리라인 요소 (및 다른 모든 도형 요소)와 <xref:System.Windows.Controls.Panel> 또는 <xref:System.Windows.Controls.Control> 텍스트가 아닌 콘텐츠를 지 원하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="14065-111">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the polylines, you can use polyline elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="14065-112">이 예제는 더 큰 샘플;의 일부 전체 샘플을 참조 하세요 [도형 요소 샘플](https://go.microsoft.com/fwlink/?LinkID=160037)합니다.</span><span class="sxs-lookup"><span data-stu-id="14065-112">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14065-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="14065-113">See also</span></span>
- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Shapes.Polygon>
- <xref:System.Windows.Shapes.Shape>
- [<span data-ttu-id="14065-114">도형 요소 샘플</span><span class="sxs-lookup"><span data-stu-id="14065-114">Shape Elements Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160037)
- [<span data-ttu-id="14065-115">WPF에서 Shape 및 기본 그리기 개요</span><span class="sxs-lookup"><span data-stu-id="14065-115">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
