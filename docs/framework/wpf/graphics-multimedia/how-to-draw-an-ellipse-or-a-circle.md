---
title: '방법: 타원 또는 원 그리기'
ms.date: 03/30/2017
helpviewer_keywords:
- ellipses [WPF], drawing
- circles [WPF], drawing
- drawing circles [WPF]
- drawing ellipses [WPF]
- graphics [WPF], drawing circles
- graphics [WPF], drawing ellipses
ms.assetid: 99763b8c-bfc8-44be-8231-8a70daf5481a
ms.openlocfilehash: 5f17615da4907cba6e25b68f2f934602c2f8a390
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452924"
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a><span data-ttu-id="b0472-102">방법: 타원 또는 원 그리기</span><span class="sxs-lookup"><span data-stu-id="b0472-102">How to: Draw an Ellipse or a Circle</span></span>
<span data-ttu-id="b0472-103">이 예제에서는 <xref:System.Windows.Shapes.Ellipse> 요소를 사용 하 여 타원과 원을 그리는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b0472-103">This example shows how to draw ellipses and circles by using the <xref:System.Windows.Shapes.Ellipse> element.</span></span> <span data-ttu-id="b0472-104">타원을 그리려면 <xref:System.Windows.Shapes.Ellipse> 요소를 만들고 해당 <xref:System.Windows.FrameworkElement.Width%2A>를 지정 하 고 <xref:System.Windows.FrameworkElement.Height%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="b0472-104">To draw an ellipse, create an <xref:System.Windows.Shapes.Ellipse> element and specify its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="b0472-105"><xref:System.Windows.Shapes.Shape.Fill%2A> 속성을 사용 하 여 타원의 내부를 그리는 데 사용 되는 <xref:System.Windows.Media.Brush>를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0472-105">Use its <xref:System.Windows.Shapes.Shape.Fill%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the interior of the ellipse.</span></span> <span data-ttu-id="b0472-106"><xref:System.Windows.Shapes.Shape.Stroke%2A> 속성을 사용 하 여 타원의 윤곽선을 그리는 데 사용 되는 <xref:System.Windows.Media.Brush>를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0472-106">Use its <xref:System.Windows.Shapes.Shape.Stroke%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the outline of the ellipse.</span></span> <span data-ttu-id="b0472-107"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 속성은 타원 윤곽선의 두께를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0472-107">The <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> property specifies the thickness of the ellipse outline.</span></span>  
  
 <span data-ttu-id="b0472-108">원을 그리려면 <xref:System.Windows.Shapes.Ellipse> 요소의 <xref:System.Windows.FrameworkElement.Width%2A>와 <xref:System.Windows.FrameworkElement.Height%2A>를 서로 동일 하 게 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0472-108">To draw a circle, make the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> of the <xref:System.Windows.Shapes.Ellipse> element equal to each other.</span></span>  
  
 <span data-ttu-id="b0472-109">다음 예제에서는 <xref:System.Windows.Controls.Canvas>내에 4 개의 <xref:System.Windows.Shapes.Ellipse> 요소를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="b0472-109">The following example draws four <xref:System.Windows.Shapes.Ellipse> elements within a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0472-110">예제</span><span class="sxs-lookup"><span data-stu-id="b0472-110">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 <span data-ttu-id="b0472-111">이 예제에서는 <xref:System.Windows.Controls.Canvas> 사용 하 여 줄임표를 포함 하지만 텍스트가 아닌 콘텐츠를 지 원하는 <xref:System.Windows.Controls.Panel> 나 <xref:System.Windows.Controls.Control>와 함께 타원 요소 (및 다른 모든 셰이프 요소)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0472-111">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the ellipses, you can use ellipse elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="b0472-112">이 예제는 더 큰 샘플의 일부입니다. 전체 샘플은 [셰이프 요소 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b0472-112">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0472-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b0472-113">See also</span></span>

- <xref:System.Windows.Shapes.Ellipse>
- <xref:System.Windows.Shapes.Shape>
- [<span data-ttu-id="b0472-114">셰이프 요소 샘플</span><span class="sxs-lookup"><span data-stu-id="b0472-114">Shape Elements Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
