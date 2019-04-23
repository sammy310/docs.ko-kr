---
title: GDI+의 개곡선 및 폐곡선
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- curves [Windows Forms], filling
- GDI+, curves
- curves [Windows Forms], drawing
- curves
ms.assetid: 08d2cc9a-dc9d-4eed-bcbb-2c8e2ca5d3ae
ms.openlocfilehash: 33a8954296a7e63637ad5e210fb30fba1a3fdd53
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59165115"
---
# <a name="open-and-closed-curves-in-gdi"></a><span data-ttu-id="68987-102">GDI+의 개곡선 및 폐곡선</span><span class="sxs-lookup"><span data-stu-id="68987-102">Open and Closed Curves in GDI+</span></span>
<span data-ttu-id="68987-103">다음 그림에서는 두 곡선으로 분할: 개곡선 및 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="68987-103">The following illustration shows two curves: one open and one closed.</span></span>  
  
 <span data-ttu-id="68987-104">![개곡선 및 폐곡선](./media/aboutgdip02-art24.gif "Aboutgdip02_art24")</span><span class="sxs-lookup"><span data-stu-id="68987-104">![Open & Closed curves](./media/aboutgdip02-art24.gif "Aboutgdip02_art24")</span></span>  
  
## <a name="managed-interface-for-curves"></a><span data-ttu-id="68987-105">곡선에 대 한 관리 되는 인터페이스</span><span class="sxs-lookup"><span data-stu-id="68987-105">Managed Interface for Curves</span></span>  
 <span data-ttu-id="68987-106">닫힌된 곡선 내부 있고 브러시를 사용 하 여 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68987-106">Closed curves have an interior and therefore can be filled with a brush.</span></span> <span data-ttu-id="68987-107"><xref:System.Drawing.Graphics> 클래스의 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 닫힌된 도형 및 곡선을 채우기 위한 메서드를 제공: <xref:System.Drawing.Graphics.FillRectangle%2A>, <xref:System.Drawing.Graphics.FillEllipse%2A>, <xref:System.Drawing.Graphics.FillPie%2A>를 <xref:System.Drawing.Graphics.FillPolygon%2A>, <xref:System.Drawing.Graphics.FillClosedCurve%2A>를 <xref:System.Drawing.Graphics.FillPath%2A>, 및 <xref:System.Drawing.Graphics.FillRegion%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="68987-107">The <xref:System.Drawing.Graphics> class in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] provides the following methods for filling closed shapes and curves: <xref:System.Drawing.Graphics.FillRectangle%2A>, <xref:System.Drawing.Graphics.FillEllipse%2A>, <xref:System.Drawing.Graphics.FillPie%2A>, <xref:System.Drawing.Graphics.FillPolygon%2A>, <xref:System.Drawing.Graphics.FillClosedCurve%2A>, <xref:System.Drawing.Graphics.FillPath%2A>, and <xref:System.Drawing.Graphics.FillRegion%2A>.</span></span> <span data-ttu-id="68987-108">다음이 방법 중 하나를 호출할 때마다 특정 브러시 형식 중 하나를 전달 해야 합니다 있습니다 (<xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>를 <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, 또는 <xref:System.Drawing.Drawing2D.PathGradientBrush>) 인수로 합니다.</span><span class="sxs-lookup"><span data-stu-id="68987-108">Whenever you call one of these methods, you must pass one of the specific brush types (<xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, or <xref:System.Drawing.Drawing2D.PathGradientBrush>) as an argument.</span></span>  
  
 <span data-ttu-id="68987-109"><xref:System.Drawing.Graphics.FillPie%2A> 메서드를 함께 제공 되는 <xref:System.Drawing.Graphics.DrawArc%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="68987-109">The <xref:System.Drawing.Graphics.FillPie%2A> method is a companion to the <xref:System.Drawing.Graphics.DrawArc%2A> method.</span></span> <span data-ttu-id="68987-110">처럼 합니다 <xref:System.Drawing.Graphics.DrawArc%2A> 메서드는 타원 윤곽선의 부분을 그리는 <xref:System.Drawing.Graphics.FillPie%2A> 메서드는 타원의 내부를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="68987-110">Just as the <xref:System.Drawing.Graphics.DrawArc%2A> method draws a portion of the outline of an ellipse, the <xref:System.Drawing.Graphics.FillPie%2A> method fills a portion of the interior of an ellipse.</span></span> <span data-ttu-id="68987-111">다음 예제에서는 원호를 그리는 데 및 타원의 내부의 해당 부분을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="68987-111">The following example draws an arc and fills the corresponding portion of the interior of the ellipse:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#21](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#21)]
 [!code-vb[LinesCurvesAndShapes#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#21)]  
  
 <span data-ttu-id="68987-112">다음 그림은 원호 및 채워진된 원형 차트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="68987-112">The following illustration shows the arc and the filled pie.</span></span>  
  
 <span data-ttu-id="68987-113">![개곡선 및 폐곡선](./media/aboutgdip02-art25.gif "Aboutgdip02_art25")</span><span class="sxs-lookup"><span data-stu-id="68987-113">![Open & Closed curves](./media/aboutgdip02-art25.gif "Aboutgdip02_art25")</span></span>  
  
 <span data-ttu-id="68987-114"><xref:System.Drawing.Graphics.FillClosedCurve%2A> 메서드를 함께 제공 되는 <xref:System.Drawing.Graphics.DrawClosedCurve%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="68987-114">The <xref:System.Drawing.Graphics.FillClosedCurve%2A> method is a companion to the <xref:System.Drawing.Graphics.DrawClosedCurve%2A> method.</span></span> <span data-ttu-id="68987-115">두 메서드는 자동으로 끝점 시작 지점에 연결 하 여 곡선을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="68987-115">Both methods automatically close the curve by connecting the ending point to the starting point.</span></span> <span data-ttu-id="68987-116">다음 예제에서는 통과 하는 곡선을 그리는 데 (0, 0), (60, 20) 및 (40, 50).</span><span class="sxs-lookup"><span data-stu-id="68987-116">The following example draws a curve that passes through (0, 0), (60, 20), and (40, 50).</span></span> <span data-ttu-id="68987-117">그런 다음 곡선을 자동으로 연결 닫힙니다 (40, 50) 시작 지점 (0, 0) 및 내부 단색으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="68987-117">Then, the curve is automatically closed by connecting (40, 50) to the starting point (0, 0), and the interior is filled with a solid color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#22](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#22)]
 [!code-vb[LinesCurvesAndShapes#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#22)]  
  
 <span data-ttu-id="68987-118"><xref:System.Drawing.Graphics.FillPath%2A> 메서드는 별도 경로 가지의 내부를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="68987-118">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the interiors of the separate pieces of a path.</span></span> <span data-ttu-id="68987-119">닫힌된 곡선 또는 셰이프, 부분 경로 형성 하지 않으면 경우는 <xref:System.Drawing.Graphics.FillPath%2A> 메서드 채우기 전에 경로의 일부를 자동으로 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="68987-119">If a piece of a path doesn't form a closed curve or shape, the <xref:System.Drawing.Graphics.FillPath%2A> method automatically closes that piece of the path before filling it.</span></span> <span data-ttu-id="68987-120">다음 예제에서는 그리고 호, 카디널 스플라인을, 문자열 및 원형 구성 되는 경로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="68987-120">The following example draws and fills a path that consists of an arc, a cardinal spline, a string, and a pie:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#23](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#23)]
 [!code-vb[LinesCurvesAndShapes#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#23)]  
  
 <span data-ttu-id="68987-121">다음 그림은 단색 하지 않고 사용 하 여 경로 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="68987-121">The following illustration shows the path with and without the solid fill.</span></span> <span data-ttu-id="68987-122">문자열의 텍스트 윤곽선은 있지만 채워지지를 여는 <xref:System.Drawing.Graphics.DrawPath%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="68987-122">Note that the text in the string is outlined, but not filled, by the <xref:System.Drawing.Graphics.DrawPath%2A> method.</span></span> <span data-ttu-id="68987-123">것은 <xref:System.Drawing.Graphics.FillPath%2A> 내부 문자열의 문자를 색칠 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="68987-123">It is the <xref:System.Drawing.Graphics.FillPath%2A> method that paints the interiors of the characters in the string.</span></span>  
  
 <span data-ttu-id="68987-124">![경로 문자열](./media/aboutgdip02-art26.gif "Aboutgdip02_art26")</span><span class="sxs-lookup"><span data-stu-id="68987-124">![String in a path](./media/aboutgdip02-art26.gif "Aboutgdip02_art26")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68987-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="68987-125">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- [<span data-ttu-id="68987-126">선, 곡선 및 도형</span><span class="sxs-lookup"><span data-stu-id="68987-126">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="68987-127">방법: 그리는 데 필요한 그래픽 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="68987-127">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="68987-128">경로 구성 및 그리기</span><span class="sxs-lookup"><span data-stu-id="68987-128">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
