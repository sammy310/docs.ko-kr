---
title: '방법: Polygon 요소를 사용하여 닫힌 도형 그리기'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], Polygon elements
- closed shapes [WPF], drawing with Polygon elements
- Polygon elements [WPF]
- drawing [WPF], closed shapes with Polygon elements
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
ms.openlocfilehash: 533c341e2fae528ec896bf38bafa13974af1d127
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360041"
---
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a><span data-ttu-id="9c28f-102">방법: Polygon 요소를 사용하여 닫힌 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="9c28f-102">How to: Draw a Closed Shape by Using the Polygon Element</span></span>
<span data-ttu-id="9c28f-103">이 예제에서는 사용 하 여 닫힌된 도형 그리기를 <xref:System.Windows.Shapes.Polygon> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9c28f-103">This example shows how to draw a closed shape by using the <xref:System.Windows.Shapes.Polygon> element.</span></span> <span data-ttu-id="9c28f-104">닫힌된 도형 그리기, 만들려면를 <xref:System.Windows.Shapes.Polygon> 요소 및 사용 하 여 해당 <xref:System.Windows.Shapes.Polygon.Points%2A> 도형의 꼭지점을 지정 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="9c28f-104">To draw a closed shape, create a <xref:System.Windows.Shapes.Polygon> element and use its <xref:System.Windows.Shapes.Polygon.Points%2A> property to specify the vertices of a shape.</span></span> <span data-ttu-id="9c28f-105">줄의 첫 번째 및 마지막 지점을 연결 하는 그려집니다 자동으로.</span><span class="sxs-lookup"><span data-stu-id="9c28f-105">A line is automatically drawn that connects the first and last points.</span></span> <span data-ttu-id="9c28f-106">마지막으로, 지정 된 <xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>, 또는 둘 다.</span><span class="sxs-lookup"><span data-stu-id="9c28f-106">Finally, specify a <xref:System.Windows.Shapes.Shape.Fill%2A>, a <xref:System.Windows.Shapes.Shape.Stroke%2A>, or both.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c28f-107">예제</span><span class="sxs-lookup"><span data-stu-id="9c28f-107">Example</span></span>  
 <span data-ttu-id="9c28f-108">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], 지점에 대 한 구문이 공백으로 구분 된 목록 쉼표로 구분 된 x 및 y 좌표 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="9c28f-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 <span data-ttu-id="9c28f-109">이 예제에서는 사용 되지만 <xref:System.Windows.Controls.Canvas> 다각형을 포함 하려면 사용할 수 있습니다 다각형 요소 (및 다른 모든 도형 요소)와 <xref:System.Windows.Controls.Panel> 또는 <xref:System.Windows.Controls.Control> 텍스트가 아닌 콘텐츠를 지 원하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c28f-109">Although the example uses a <xref:System.Windows.Controls.Canvas> to contain the polygons, you can use polygon elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="9c28f-110">이 예제는 더 큰 샘플;의 일부 전체 샘플을 참조 하세요 [도형 요소 샘플](https://go.microsoft.com/fwlink/?LinkID=160037)합니다.</span><span class="sxs-lookup"><span data-stu-id="9c28f-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>
