---
title: '방법: 줄 또는 세그먼트 끝에서 끝 모양 수정'
ms.date: 03/30/2017
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
ms.openlocfilehash: 5f755d7b4d1682755ea461121f91c0666d450ad1
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452781"
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a><span data-ttu-id="a4c97-102">방법: 줄 또는 세그먼트 끝에서 끝 모양 수정</span><span class="sxs-lookup"><span data-stu-id="a4c97-102">How to: Modify the Cap at the End of a Line or Segment</span></span>
<span data-ttu-id="a4c97-103">이 예제에서는 열린 <xref:System.Windows.Shapes.Shape> 요소의 시작 또는 끝에 있는 셰이프를 수정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a4c97-103">This example shows how to modify the shape at the start or end of an open <xref:System.Windows.Shapes.Shape> element.</span></span> <span data-ttu-id="a4c97-104">열린 <xref:System.Windows.Shapes.Shape>의 시작 부분에 있는 캡을 변경 하려면 해당 <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c97-104">To change the cap at the beginning of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> property.</span></span> <span data-ttu-id="a4c97-105">열린 <xref:System.Windows.Shapes.Shape>끝에 있는 캡을 변경 하려면 해당 <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c97-105">To change the cap at the end of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> property.</span></span> <span data-ttu-id="a4c97-106">사용 가능한 선 끝 모양을 보려면 <xref:System.Windows.Media.PenLineCap> 열거를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4c97-106">To view the available line caps, see the <xref:System.Windows.Media.PenLineCap> enumeration.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a4c97-107">이 속성은 <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Polyline>또는 열린 <xref:System.Windows.Shapes.Path> 요소와 같은 열린 도형에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a4c97-107">This property only affects an open shape, such as a <xref:System.Windows.Shapes.Line>, a <xref:System.Windows.Shapes.Polyline>, or an open <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 <span data-ttu-id="a4c97-108">다음 예제에서는 4 개의 <xref:System.Windows.Shapes.Polyline> 요소를 그린 다음 각의 끝에 서로 다른 모양 집합을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c97-108">The following example draws four <xref:System.Windows.Shapes.Polyline> elements and uses a different set of shapes on the ends of each.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4c97-109">예제</span><span class="sxs-lookup"><span data-stu-id="a4c97-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 <span data-ttu-id="a4c97-110">이 예제는 더 큰 샘플의 일부입니다. 전체 샘플은 [셰이프 요소 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4c97-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4c97-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a4c97-111">See also</span></span>

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Media.PenLineCap>
