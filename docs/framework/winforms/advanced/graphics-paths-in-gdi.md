---
title: GDI+의 그래픽 경로
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], paths
- GDI+, drawing paths
- paths [Windows Forms], drawing
- drawing [Windows Forms], paths
ms.assetid: a5500dec-666c-41fd-9da3-2169dd89c5eb
ms.openlocfilehash: c9a43065210f5ef0fffcae01cc7eb88349696b6b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938169"
---
# <a name="graphics-paths-in-gdi"></a><span data-ttu-id="db3f7-102">GDI+의 그래픽 경로</span><span class="sxs-lookup"><span data-stu-id="db3f7-102">Graphics Paths in GDI+</span></span>
<span data-ttu-id="db3f7-103">경로 선, 사각형 및 간단한 곡선을 결합 하 여 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db3f7-103">Paths are formed by combining lines, rectangles, and simple curves.</span></span> <span data-ttu-id="db3f7-104">설명한 대로 합니다 [벡터 그래픽 개요](vector-graphics-overview.md) 기본 구성 요소는 다음 그림을 그리기 위한 가장 유용한 것으로 입증는:</span><span class="sxs-lookup"><span data-stu-id="db3f7-104">Recall from the [Vector Graphics Overview](vector-graphics-overview.md) that the following basic building blocks have proven to be the most useful for drawing pictures:</span></span>  
  
- <span data-ttu-id="db3f7-105">선</span><span class="sxs-lookup"><span data-stu-id="db3f7-105">Lines</span></span>  
  
- <span data-ttu-id="db3f7-106">사각형</span><span class="sxs-lookup"><span data-stu-id="db3f7-106">Rectangles</span></span>  
  
- <span data-ttu-id="db3f7-107">줄임표</span><span class="sxs-lookup"><span data-stu-id="db3f7-107">Ellipses</span></span>  
  
- <span data-ttu-id="db3f7-108">원호</span><span class="sxs-lookup"><span data-stu-id="db3f7-108">Arcs</span></span>  
  
- <span data-ttu-id="db3f7-109">다각형</span><span class="sxs-lookup"><span data-stu-id="db3f7-109">Polygons</span></span>  
  
- <span data-ttu-id="db3f7-110">카디널 스플라인</span><span class="sxs-lookup"><span data-stu-id="db3f7-110">Cardinal splines</span></span>  
  
- <span data-ttu-id="db3f7-111">3 차원 곡선 스플라인</span><span class="sxs-lookup"><span data-stu-id="db3f7-111">Bézier splines</span></span>  
  
 <span data-ttu-id="db3f7-112">GDI +에서 <xref:System.Drawing.Drawing2D.GraphicsPath> 개체를 사용 하면 단일 단위로 이러한 빌딩 블록의 시퀀스를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db3f7-112">In GDI+, the <xref:System.Drawing.Drawing2D.GraphicsPath> object allows you to collect a sequence of these building blocks into a single unit.</span></span> <span data-ttu-id="db3f7-113">선, 사각형, 다각형 및 곡선의 전체 시퀀스를 한 번 호출을 사용 하 여 그릴 수 있습니다 합니다 <xref:System.Drawing.Graphics.DrawPath%2A> 메서드는 <xref:System.Drawing.Graphics> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="db3f7-113">The entire sequence of lines, rectangles, polygons, and curves can then be drawn with one call to the <xref:System.Drawing.Graphics.DrawPath%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="db3f7-114">다음 그림에서는 줄, 호, 3 차원 곡선 스플라인, 및 카디널 스플라인 결합 하 여 만든 경로 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="db3f7-114">The following illustration shows a path created by combining a line, an arc, a Bézier spline, and a cardinal spline.</span></span>  
  
 <span data-ttu-id="db3f7-115">![Path](./media/aboutgdip02-art14.gif "Aboutgdip02_art14")</span><span class="sxs-lookup"><span data-stu-id="db3f7-115">![Path](./media/aboutgdip02-art14.gif "Aboutgdip02_art14")</span></span>  
  
## <a name="using-a-path"></a><span data-ttu-id="db3f7-116">경로 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="db3f7-116">Using a Path</span></span>  
 <span data-ttu-id="db3f7-117"><xref:System.Drawing.Drawing2D.GraphicsPath> 그릴 항목의 시퀀스를 만들기 위한 다음 메서드를 제공 하는 클래스: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>를 <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (카디널 스플라인 용) 및 <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="db3f7-117">The <xref:System.Drawing.Drawing2D.GraphicsPath> class provides the following methods for creating a sequence of items to be drawn: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (for cardinal splines), and <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>.</span></span> <span data-ttu-id="db3f7-118">이러한 각 메서드는 오버 로드 됩니다. 즉, 각 메서드는 여러 다른 매개 변수 목록을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="db3f7-118">Each of these methods is overloaded; that is, each method supports several different parameter lists.</span></span> <span data-ttu-id="db3f7-119">한 변형 된 예를 들어,를 <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> 메서드 네 개의 정수를 받고 다른 변형이 합니다 <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> 메서드는 두 개의 수신 <xref:System.Drawing.Point> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="db3f7-119">For example, one variation of the <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> method receives four integers, and another variation of the <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> method receives two <xref:System.Drawing.Point> objects.</span></span>  
  
 <span data-ttu-id="db3f7-120">선, 사각형 및 3 차원 곡선 스플라인 경로 추가 하기 위한 메서드는 한 번의 호출 경로에 여러 항목을 추가 하는 동반 메서드를 갖습니다: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>, 및 <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="db3f7-120">The methods for adding lines, rectangles, and Bézier splines to a path have plural companion methods that add several items to the path in a single call: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>, and <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>.</span></span> <span data-ttu-id="db3f7-121">또한 합니다 <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> 하 고 <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> 도우미 메서드를 갖습니다 <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> 및 <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, 닫힌된 곡선 또는 원형 경로에 추가 하는.</span><span class="sxs-lookup"><span data-stu-id="db3f7-121">Also, the <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> methods have companion methods, <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, that add a closed curve or pie to the path.</span></span>  
  
 <span data-ttu-id="db3f7-122">필요한 경로 그릴를 <xref:System.Drawing.Graphics> 개체를 <xref:System.Drawing.Pen> 개체 및 <xref:System.Drawing.Drawing2D.GraphicsPath> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="db3f7-122">To draw a path, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Pen> object, and a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="db3f7-123"><xref:System.Drawing.Graphics> 개체를 제공 합니다 <xref:System.Drawing.Graphics.DrawPath%2A> 메서드를 및 <xref:System.Drawing.Pen> 개체 경로 렌더링 하는 데 선의 색과 두께 같은 특성을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="db3f7-123">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawPath%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the path.</span></span> <span data-ttu-id="db3f7-124"><xref:System.Drawing.Drawing2D.GraphicsPath> 일련의 선과 곡선 경로 구성 하는 개체를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="db3f7-124">The <xref:System.Drawing.Drawing2D.GraphicsPath> object stores the sequence of lines and curves that make up the path.</span></span> <span data-ttu-id="db3f7-125">합니다 <xref:System.Drawing.Pen> 개체와 <xref:System.Drawing.Drawing2D.GraphicsPath> 개체에 대 한 인수로 전달 되는 <xref:System.Drawing.Graphics.DrawPath%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="db3f7-125">The <xref:System.Drawing.Pen> object and the <xref:System.Drawing.Drawing2D.GraphicsPath> object are passed as arguments to the <xref:System.Drawing.Graphics.DrawPath%2A> method.</span></span> <span data-ttu-id="db3f7-126">다음 예제에서는 선, 타원, 및 베 지 어 스플라인을 구성 되는 경로 그립니다.</span><span class="sxs-lookup"><span data-stu-id="db3f7-126">The following example draws a path that consists of a line, an ellipse, and a Bézier spline:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#101](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#101)]
 [!code-vb[LinesCurvesAndShapes#101](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#101)]  
  
 <span data-ttu-id="db3f7-127">다음 그림에서는 경로 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="db3f7-127">The following illustration shows the path.</span></span>  
  
 <span data-ttu-id="db3f7-128">![Path](./media/aboutgdip02-art15.gif "Aboutgdip02_art15")</span><span class="sxs-lookup"><span data-stu-id="db3f7-128">![Path](./media/aboutgdip02-art15.gif "Aboutgdip02_art15")</span></span>  
  
 <span data-ttu-id="db3f7-129">선, 사각형 및 곡선 경로 추가할 뿐만 아니라 경로에 경로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db3f7-129">In addition to adding lines, rectangles, and curves to a path, you can add paths to a path.</span></span> <span data-ttu-id="db3f7-130">이 옵션을 사용 하면 대규모의 복잡 한 경로 구성 하기 위해 기존 경로 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db3f7-130">This allows you to combine existing paths to form large, complex paths.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#102](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#102)]
 [!code-vb[LinesCurvesAndShapes#102](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#102)]  
  
 <span data-ttu-id="db3f7-131">항목이 두 가지 다른 경로 추가할 수 있습니다: 문자열과 원형입니다.</span><span class="sxs-lookup"><span data-stu-id="db3f7-131">There are two other items you can add to a path: strings and pies.</span></span> <span data-ttu-id="db3f7-132">원형은 타원의 내부의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="db3f7-132">A pie is a portion of the interior of an ellipse.</span></span> <span data-ttu-id="db3f7-133">다음 예에서는 원호, 카디널 스플라인을, 문자열 및 원형 경로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="db3f7-133">The following example creates a path from an arc, a cardinal spline, a string, and a pie:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#103](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#103)]
 [!code-vb[LinesCurvesAndShapes#103](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#103)]  
  
 <span data-ttu-id="db3f7-134">다음 그림에서는 경로 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="db3f7-134">The following illustration shows the path.</span></span> <span data-ttu-id="db3f7-135">참고; 연결 되지 않은 경로 호, 카디널 스플라인, 문자열 및 원형 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db3f7-135">Note that a path does not have to be connected; the arc, cardinal spline, string, and pie are separated.</span></span>  
  
 <span data-ttu-id="db3f7-136">![Paths](./media/aboutgdip02-art16.gif "Aboutgdip02_Art16")</span><span class="sxs-lookup"><span data-stu-id="db3f7-136">![Paths](./media/aboutgdip02-art16.gif "Aboutgdip02_Art16")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db3f7-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="db3f7-137">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- [<span data-ttu-id="db3f7-138">선, 곡선 및 도형</span><span class="sxs-lookup"><span data-stu-id="db3f7-138">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="db3f7-139">방법: 그리는 데 필요한 그래픽 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="db3f7-139">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="db3f7-140">경로 구성 및 그리기</span><span class="sxs-lookup"><span data-stu-id="db3f7-140">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
