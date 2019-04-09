---
title: GDI+의 다각형
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- polygons
- drawing [Windows Forms], polygons
- GDI+, polygons
ms.assetid: a72213d2-d69a-4c2b-a75c-be7b20390c13
ms.openlocfilehash: 2b1e3d387e4d056d9187c54dcef560544206c370
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132628"
---
# <a name="polygons-in-gdi"></a><span data-ttu-id="2d426-102">GDI+의 다각형</span><span class="sxs-lookup"><span data-stu-id="2d426-102">Polygons in GDI+</span></span>
<span data-ttu-id="2d426-103">다각형은 3 개 이상의 직선 면을 사용 하 여 닫힌된 도형입니다.</span><span class="sxs-lookup"><span data-stu-id="2d426-103">A polygon is a closed shape with three or more straight sides.</span></span> <span data-ttu-id="2d426-104">예를 들어 삼각형 세 변을 사용 하 여 다각형, 사각형은 네 면을 사용 하 여 다각형 이며 오각형 5 면을 사용 하 여 다각형입니다.</span><span class="sxs-lookup"><span data-stu-id="2d426-104">For example, a triangle is a polygon with three sides, a rectangle is a polygon with four sides, and a pentagon is a polygon with five sides.</span></span> <span data-ttu-id="2d426-105">다음 그림에서는 여러 다각형을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2d426-105">The following illustration shows several polygons.</span></span>  
  
 <span data-ttu-id="2d426-106">![다각형](./media/aboutgdip02-art07.gif "Aboutgdip02_art07")</span><span class="sxs-lookup"><span data-stu-id="2d426-106">![Polygons](./media/aboutgdip02-art07.gif "Aboutgdip02_art07")</span></span>  
  
## <a name="drawing-a-polygon"></a><span data-ttu-id="2d426-107">다각형을 그리기</span><span class="sxs-lookup"><span data-stu-id="2d426-107">Drawing a Polygon</span></span>  
 <span data-ttu-id="2d426-108">다각형을 그리려면 하려면를 <xref:System.Drawing.Graphics> 개체를 <xref:System.Drawing.Pen> 개체 및 배열을 <xref:System.Drawing.Point> (또는 <xref:System.Drawing.PointF>) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2d426-108">To draw a polygon, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Pen> object, and an array of <xref:System.Drawing.Point> (or <xref:System.Drawing.PointF>) objects.</span></span> <span data-ttu-id="2d426-109">합니다 <xref:System.Drawing.Graphics> 개체는 제공 된 <xref:System.Drawing.Graphics.DrawPolygon%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="2d426-109">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawPolygon%2A> method.</span></span> <span data-ttu-id="2d426-110">합니다 <xref:System.Drawing.Pen> 개체의 배열과 다각형을 렌더링 하는 데 사용 되는 선의 색과 두께 같은 특성이 저장 <xref:System.Drawing.Point> 직선으로 연결 포인트를 저장 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2d426-110">The <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the polygon, and the array of <xref:System.Drawing.Point> objects stores the points to be connected by straight lines.</span></span> <span data-ttu-id="2d426-111">합니다 <xref:System.Drawing.Pen> 개체 및 배열을 <xref:System.Drawing.Point> 개체에 대 한 인수로 전달 되는 <xref:System.Drawing.Graphics.DrawPolygon%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="2d426-111">The <xref:System.Drawing.Pen> object and the array of <xref:System.Drawing.Point> objects are passed as arguments to the <xref:System.Drawing.Graphics.DrawPolygon%2A> method.</span></span> <span data-ttu-id="2d426-112">다음 예제에서는 3 면 다각형을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="2d426-112">The following example draws a three-sided polygon.</span></span> <span data-ttu-id="2d426-113">만 세 지점에는 `myPointArray`: (0, 0), (50, 30) 및 (30, 60).</span><span class="sxs-lookup"><span data-stu-id="2d426-113">Note that there are only three points in `myPointArray`: (0, 0), (50, 30), and (30, 60).</span></span> <span data-ttu-id="2d426-114"><xref:System.Drawing.Graphics.DrawPolygon%2A> 메서드는 자동으로 다각형에서 선을 그려 닫습니다 (30, 60) 시작 지점 (0, 0)으로 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d426-114">The <xref:System.Drawing.Graphics.DrawPolygon%2A> method automatically closes the polygon by drawing a line from (30, 60) back to the starting point (0, 0).</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#111](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#111)]
 [!code-vb[LinesCurvesAndShapes#111](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#111)]  
  
 <span data-ttu-id="2d426-115">다음 그림은 다각형을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2d426-115">The following illustration shows the polygon.</span></span>  
  
 <span data-ttu-id="2d426-116">![Polygon](./media/aboutgdip02-art08.gif "Aboutgdip02_art08")</span><span class="sxs-lookup"><span data-stu-id="2d426-116">![Polygon](./media/aboutgdip02-art08.gif "Aboutgdip02_art08")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d426-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="2d426-117">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [<span data-ttu-id="2d426-118">선, 곡선 및 도형</span><span class="sxs-lookup"><span data-stu-id="2d426-118">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="2d426-119">방법: 펜 만들기</span><span class="sxs-lookup"><span data-stu-id="2d426-119">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
