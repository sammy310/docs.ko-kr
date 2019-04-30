---
title: '방법: 사각형 그리기'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], rectangles
- graphics [WPF], rectangles
- rectangles [WPF], drawing
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
ms.openlocfilehash: 261026b994b432565928b38ff1657115ff7cbe4e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947630"
---
# <a name="how-to-draw-a-rectangle"></a><span data-ttu-id="13d0c-102">방법: 사각형 그리기</span><span class="sxs-lookup"><span data-stu-id="13d0c-102">How to: Draw a Rectangle</span></span>
<span data-ttu-id="13d0c-103">사용 하 여 사각형을 그리는 방법을 보여 주는이 예제는 <xref:System.Windows.Shapes.Rectangle> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="13d0c-103">This example shows how to draw a rectangle by using the <xref:System.Windows.Shapes.Rectangle> element.</span></span>  
  
 <span data-ttu-id="13d0c-104">사각형을 그리려면 만들려면를 <xref:System.Windows.Shapes.Rectangle> 요소를 지정 하 고 해당 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="13d0c-104">To draw a rectangle, create a <xref:System.Windows.Shapes.Rectangle> element and specify its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="13d0c-105">사각형의 내부 그릴 설정 해당 <xref:System.Windows.Shapes.Shape.Fill%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="13d0c-105">To paint the inside of the rectangle, set its <xref:System.Windows.Shapes.Shape.Fill%2A>.</span></span> <span data-ttu-id="13d0c-106">사각형 윤곽선을 제공 하려면 사용 하 여 해당 <xref:System.Windows.Shapes.Shape.Stroke%2A> 고 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="13d0c-106">To give the rectangle an outline, use its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties.</span></span>  
  
 <span data-ttu-id="13d0c-107">모서리가 둥근 사각형, 선택적으로 지정할 <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> 고 <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="13d0c-107">To give the rectangle rounded corners, specify the optional <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties.</span></span> <span data-ttu-id="13d0c-108">합니다 <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> 및 <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> 속성 사각형의 모퉁이 둥글게 하는 데 사용 되는 타원의 x 축과 y 반지름을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="13d0c-108">The <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties set the x-axis and y-axis radii of the ellipse that is used to round the corners of the rectangle.</span></span>  
  
 <span data-ttu-id="13d0c-109">다음 예제에서는 두 개의 <xref:System.Windows.Shapes.Rectangle> 요소를 그립니다는 <xref:System.Windows.Controls.Canvas>합니다.</span><span class="sxs-lookup"><span data-stu-id="13d0c-109">In the following example, two <xref:System.Windows.Shapes.Rectangle> elements are drawn in a <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="13d0c-110">첫 번째 사각형에는 <xref:System.Windows.Media.Brushes.Blue%2A> 내부.</span><span class="sxs-lookup"><span data-stu-id="13d0c-110">The first rectangle has a <xref:System.Windows.Media.Brushes.Blue%2A> interior.</span></span> <span data-ttu-id="13d0c-111">두 번째 사각형에는 <xref:System.Windows.Media.Brushes.Blue%2A> 내부에 <xref:System.Windows.Media.Brushes.Black%2A> 윤곽선 및 모서리가 둥근된 합니다.</span><span class="sxs-lookup"><span data-stu-id="13d0c-111">The second rectangle has a <xref:System.Windows.Media.Brushes.Blue%2A> interior, a <xref:System.Windows.Media.Brushes.Black%2A> outline, and rounded corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13d0c-112">예제</span><span class="sxs-lookup"><span data-stu-id="13d0c-112">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#Rectangle1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 <span data-ttu-id="13d0c-113">이 예제에서는 한 <xref:System.Windows.Controls.Canvas> 사각형을 포함 하려면 사용할 수 있습니다 사각형 요소 (및 다른 모든 도형 요소)와 <xref:System.Windows.Controls.Panel> 또는 <xref:System.Windows.Controls.Control> 텍스트가 아닌 콘텐츠를 지 원하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="13d0c-113">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the rectangles, you can use rectangle elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span> <span data-ttu-id="13d0c-114">사각형의 일부에 대 한 배경을 제공 하는 데 특히 유용은 사실 <xref:System.Windows.Controls.Grid> 패널입니다.</span><span class="sxs-lookup"><span data-stu-id="13d0c-114">In fact, rectangles are particularly useful for providing backgrounds for portions of <xref:System.Windows.Controls.Grid> panels.</span></span> <span data-ttu-id="13d0c-115">예를 들어 참조 된 [테이블 개요](../advanced/table-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="13d0c-115">For an example, see the [Table Overview](../advanced/table-overview.md).</span></span>  
  
 <span data-ttu-id="13d0c-116">이 예제는 더 큰 샘플;의 일부 전체 샘플을 참조 하세요 [도형 요소 샘플](https://go.microsoft.com/fwlink/?LinkID=160037)합니다.</span><span class="sxs-lookup"><span data-stu-id="13d0c-116">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13d0c-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="13d0c-117">See also</span></span>

- <xref:System.Windows.Shapes.Rectangle>
- [<span data-ttu-id="13d0c-118">도형 요소 샘플</span><span class="sxs-lookup"><span data-stu-id="13d0c-118">Shape Elements Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160037)
- [<span data-ttu-id="13d0c-119">WPF에서 Shape 및 기본 그리기 개요</span><span class="sxs-lookup"><span data-stu-id="13d0c-119">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="13d0c-120">테이블 개요</span><span class="sxs-lookup"><span data-stu-id="13d0c-120">Table Overview</span></span>](../advanced/table-overview.md)
