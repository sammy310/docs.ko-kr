---
title: '방법: 선 그리기'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
ms.openlocfilehash: a803c1be01086ca8911ef4cc33bd67697239e2c0
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452950"
---
# <a name="how-to-draw-a-line"></a><span data-ttu-id="7440a-102">방법: 선 그리기</span><span class="sxs-lookup"><span data-stu-id="7440a-102">How to: Draw a Line</span></span>
<span data-ttu-id="7440a-103">이 예제에서는 <xref:System.Windows.Shapes.Line> 요소를 사용 하 여 선을 그리는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7440a-103">This example shows you how to draw lines by using the <xref:System.Windows.Shapes.Line> element.</span></span>  
  
 <span data-ttu-id="7440a-104">선을 그리려면 <xref:System.Windows.Shapes.Line> 요소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7440a-104">To draw a line, create a <xref:System.Windows.Shapes.Line> element.</span></span> <span data-ttu-id="7440a-105">해당 <xref:System.Windows.Shapes.Line.X1%2A> 및 <xref:System.Windows.Shapes.Line.Y1%2A> 속성을 사용 하 여 시작점을 설정 합니다. <xref:System.Windows.Shapes.Line.X2%2A> 및 <xref:System.Windows.Shapes.Line.Y2%2A> 속성을 사용 하 여 끝점을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7440a-105">Use its <xref:System.Windows.Shapes.Line.X1%2A> and <xref:System.Windows.Shapes.Line.Y1%2A> properties to set its start point; and use its <xref:System.Windows.Shapes.Line.X2%2A> and <xref:System.Windows.Shapes.Line.Y2%2A> properties to set its end point.</span></span> <span data-ttu-id="7440a-106">마지막으로, 스트로크가 없는 줄이 보이지 않기 때문에 <xref:System.Windows.Shapes.Shape.Stroke%2A>를 설정 하 고 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="7440a-106">Finally, set its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> because a line without a stroke is invisible.</span></span>  
  
 <span data-ttu-id="7440a-107">선에는 <xref:System.Windows.Shapes.Shape.Fill%2A> 요소를 설정 해도 아무런 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7440a-107">Setting the <xref:System.Windows.Shapes.Shape.Fill%2A> element for a line has no effect, because a line has no interior.</span></span>  
  
 <span data-ttu-id="7440a-108">다음 예제에서는 <xref:System.Windows.Controls.Canvas> 요소 안에 3 개의 줄을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="7440a-108">The following example draws three lines inside a <xref:System.Windows.Controls.Canvas> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7440a-109">예제</span><span class="sxs-lookup"><span data-stu-id="7440a-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 <span data-ttu-id="7440a-110">이 예제는 더 큰 샘플의 일부입니다. 전체 샘플은 [셰이프 요소 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7440a-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7440a-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7440a-111">See also</span></span>

- <xref:System.Windows.Shapes.Line>
- [<span data-ttu-id="7440a-112">셰이프 요소 샘플</span><span class="sxs-lookup"><span data-stu-id="7440a-112">Shape Elements Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
