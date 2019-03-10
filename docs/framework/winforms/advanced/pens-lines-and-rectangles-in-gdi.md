---
title: GDI+의 펜, 선 및 사각형
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines
- GDI+, lines
- drawing [Windows Forms], rectangles
- rectangles
- drawing [Windows Forms], lines
- GDI+, pens
- examples [Windows Forms], drawing lines and shapes
- examples [Windows Forms], pens
- GDI+, rectangles
- examples [Windows Forms], GDI+
- lines [Windows Forms], dashed
ms.assetid: 30b25aae-e3eb-4479-bdb8-187cf651fc84
ms.openlocfilehash: 91f41fb4acf5ec174bd76498a70aed3dcda076f9
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705742"
---
# <a name="pens-lines-and-rectangles-in-gdi"></a><span data-ttu-id="ed657-102">GDI+의 펜, 선 및 사각형</span><span class="sxs-lookup"><span data-stu-id="ed657-102">Pens, Lines, and Rectangles in GDI+</span></span>
<span data-ttu-id="ed657-103">있는 선을 그리려면 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 만들어야를 <xref:System.Drawing.Graphics> 개체 및 <xref:System.Drawing.Pen> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ed657-103">To draw lines with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] you need to create a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="ed657-104">합니다 <xref:System.Drawing.Graphics> 실제로 그리기를 수행 하는 메서드를 제공 하는 개체 및 <xref:System.Drawing.Pen> 개체 선 색, 너비 및 스타일 같은 특성을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed657-104">The <xref:System.Drawing.Graphics> object provides the methods that actually do the drawing, and the <xref:System.Drawing.Pen> object stores attributes, such as line color, width, and style.</span></span>  
  
## <a name="drawing-a-line"></a><span data-ttu-id="ed657-105">선 그리기</span><span class="sxs-lookup"><span data-stu-id="ed657-105">Drawing a Line</span></span>  
 <span data-ttu-id="ed657-106">선 그리기를 호출 합니다 <xref:System.Drawing.Graphics.DrawLine%2A> 메서드는 <xref:System.Drawing.Graphics> 개체.</span><span class="sxs-lookup"><span data-stu-id="ed657-106">To draw a line, call the <xref:System.Drawing.Graphics.DrawLine%2A> method of the <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="ed657-107">합니다 <xref:System.Drawing.Pen> 개체에 대 한 인수 중 하나로 전달 되는 <xref:System.Drawing.Graphics.DrawLine%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="ed657-107">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawLine%2A> method.</span></span> <span data-ttu-id="ed657-108">다음 예제에서는 점 (12, 6) 줄 (4, 2) 지점에서 그립니다.</span><span class="sxs-lookup"><span data-stu-id="ed657-108">The following example draws a line from the point (4, 2) to the point (12, 6):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#41](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#41)]
 [!code-vb[LinesCurvesAndShapes#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#41)]  
  
 <span data-ttu-id="ed657-109"><xref:System.Drawing.Graphics.DrawLine%2A> 오버 로드 메서드도 <xref:System.Drawing.Graphics> 클래스를 여러 가지 인수를 사용 하 여 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed657-109"><xref:System.Drawing.Graphics.DrawLine%2A> is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="ed657-110">예를 들어 두 생성할 수 있습니다 <xref:System.Drawing.Point> 개체를 전달 합니다 <xref:System.Drawing.Point> 개체에 대 한 인수로 <xref:System.Drawing.Graphics.DrawLine%2A> 메서드:</span><span class="sxs-lookup"><span data-stu-id="ed657-110">For example, you can construct two <xref:System.Drawing.Point> objects and pass the <xref:System.Drawing.Point> objects as arguments to the <xref:System.Drawing.Graphics.DrawLine%2A> method:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#42](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#42)]
 [!code-vb[LinesCurvesAndShapes#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#42)]  
  
## <a name="constructing-a-pen"></a><span data-ttu-id="ed657-111">펜 생성</span><span class="sxs-lookup"><span data-stu-id="ed657-111">Constructing a Pen</span></span>  
 <span data-ttu-id="ed657-112">생성 하는 경우에 특정 특성을 지정할 수 있습니다는 <xref:System.Drawing.Pen> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ed657-112">You can specify certain attributes when you construct a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="ed657-113">예를 들어 하나 `Pen` 생성자를 사용 하면 색 및 두께 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed657-113">For example, one `Pen` constructor allows you to specify color and width.</span></span> <span data-ttu-id="ed657-114">다음 예제에서는 2에서 너비의 파란색 선을 그립니다 (0, 0)를 (60, 30):</span><span class="sxs-lookup"><span data-stu-id="ed657-114">The following example draws a blue line of width 2 from (0, 0) to (60, 30):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#43](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#43)]
 [!code-vb[LinesCurvesAndShapes#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#43)]  
  
## <a name="dashed-lines-and-line-caps"></a><span data-ttu-id="ed657-115">파선 및 선 끝</span><span class="sxs-lookup"><span data-stu-id="ed657-115">Dashed Lines and Line Caps</span></span>  
 <span data-ttu-id="ed657-116"><xref:System.Drawing.Pen> 개체도 노출 속성을 같은 <xref:System.Drawing.Pen.DashStyle%2A>, 줄의 기능을 지정 하려면 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed657-116">The <xref:System.Drawing.Pen> object also exposes properties, such as <xref:System.Drawing.Pen.DashStyle%2A>, that you can use to specify features of the line.</span></span> <span data-ttu-id="ed657-117">다음 예제에서는 그리는 파선에서 (100, 50)에 (300, 80):</span><span class="sxs-lookup"><span data-stu-id="ed657-117">The following example draws a dashed line from (100, 50) to (300, 80):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#44](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#44)]
 [!code-vb[LinesCurvesAndShapes#44](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#44)]  
  
 <span data-ttu-id="ed657-118">속성을 사용할 수는 <xref:System.Drawing.Pen> 줄의 다양 한 특성을 설정할 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ed657-118">You can use the properties of the <xref:System.Drawing.Pen> object to set many more attributes of the line.</span></span> <span data-ttu-id="ed657-119">합니다 <xref:System.Drawing.Pen.StartCap%2A> 및 <xref:System.Drawing.Pen.EndCap%2A> 속성 선 끝 모양을 지정; 플랫, 사각형, 둥근, 삼각형, 끝 수 또는 사용자 지정 셰이프.</span><span class="sxs-lookup"><span data-stu-id="ed657-119">The <xref:System.Drawing.Pen.StartCap%2A> and <xref:System.Drawing.Pen.EndCap%2A> properties specify the appearance of the ends of the line; the ends can be flat, square, rounded, triangular, or a custom shape.</span></span> <span data-ttu-id="ed657-120"><xref:System.Drawing.Pen.LineJoin%2A> 속성 또는 지정할 수 있습니다 있는지 여부를 연결 된 선 됩니다 (날카로운 모퉁이 사용 하 여 조인) 음, 경사진, 반올림 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="ed657-120">The <xref:System.Drawing.Pen.LineJoin%2A> property lets you specify whether connected lines are mitered (joined with sharp corners), beveled, rounded, or clipped.</span></span> <span data-ttu-id="ed657-121">다음 그림에서는 한도 및 조인에 대 한 다양 한 스타일을 사용 하 여 줄을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ed657-121">The following illustration shows lines with various cap and join styles.</span></span>  
  
 <span data-ttu-id="ed657-122">![Lines](./media/aboutgdip02-art04.gif "Aboutgdip02_art04")</span><span class="sxs-lookup"><span data-stu-id="ed657-122">![Lines](./media/aboutgdip02-art04.gif "Aboutgdip02_art04")</span></span>  
  
## <a name="drawing-a-rectangle"></a><span data-ttu-id="ed657-123">사각형 그리기</span><span class="sxs-lookup"><span data-stu-id="ed657-123">Drawing a Rectangle</span></span>  
 <span data-ttu-id="ed657-124">사용 하 여 사각형 그리기 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 선을 그릴 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="ed657-124">Drawing rectangles with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] is similar to drawing lines.</span></span> <span data-ttu-id="ed657-125">사각형을 그리려면 하려면를 <xref:System.Drawing.Graphics> 개체 및 <xref:System.Drawing.Pen> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ed657-125">To draw a rectangle, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="ed657-126"><xref:System.Drawing.Graphics> 개체를 제공을 <xref:System.Drawing.Graphics.DrawRectangle%2A> 메서드 및 <xref:System.Drawing.Pen> 개체 선 두께 색 같은 특성을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed657-126">The <xref:System.Drawing.Graphics> object provides a <xref:System.Drawing.Graphics.DrawRectangle%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as line width and color.</span></span> <span data-ttu-id="ed657-127">합니다 <xref:System.Drawing.Pen> 개체에 대 한 인수 중 하나로 전달 되는 <xref:System.Drawing.Graphics.DrawRectangle%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="ed657-127">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method.</span></span> <span data-ttu-id="ed657-128">다음 예제에서는 왼쪽 위 모퉁이가 사용 하 여 사각형을 그립니다 (100, 50), 80, 너비 및 높이가 40:</span><span class="sxs-lookup"><span data-stu-id="ed657-128">The following example draws a rectangle with its upper-left corner at (100, 50), a width of 80, and a height of 40:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#45](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#45)]
 [!code-vb[LinesCurvesAndShapes#45](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#45)]  
  
 <span data-ttu-id="ed657-129"><xref:System.Drawing.Graphics.DrawRectangle%2A> 오버 로드 메서드도 <xref:System.Drawing.Graphics> 클래스를 여러 가지 인수를 사용 하 여 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed657-129"><xref:System.Drawing.Graphics.DrawRectangle%2A> is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="ed657-130">예를 들어, 생성할 수 있습니다는 <xref:System.Drawing.Rectangle> 개체를 전달 합니다 <xref:System.Drawing.Rectangle> 개체는 <xref:System.Drawing.Graphics.DrawRectangle%2A> 메서드에 인수로:</span><span class="sxs-lookup"><span data-stu-id="ed657-130">For example, you can construct a <xref:System.Drawing.Rectangle> object and pass the <xref:System.Drawing.Rectangle> object to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method as an argument:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#46](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#46)]
 [!code-vb[LinesCurvesAndShapes#46](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#46)]  
  
 <span data-ttu-id="ed657-131"><xref:System.Drawing.Rectangle> 개체에 메서드와 속성을 조작 하 고 사각형에 대 한 정보를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed657-131">A <xref:System.Drawing.Rectangle> object has methods and properties for manipulating and gathering information about the rectangle.</span></span> <span data-ttu-id="ed657-132">예를 들어 합니다 <xref:System.Drawing.Rectangle.Inflate%2A> 및 <xref:System.Drawing.Rectangle.Offset%2A> 메서드 사각형의 위치와 크기를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed657-132">For example, the <xref:System.Drawing.Rectangle.Inflate%2A> and <xref:System.Drawing.Rectangle.Offset%2A> methods change the size and position of the rectangle.</span></span> <span data-ttu-id="ed657-133">합니다 <xref:System.Drawing.Rectangle.IntersectsWith%2A> 메서드를 알려 사각형 다른 인스턴스와 교차 하는지 여부 사각형을 지정 및 <xref:System.Drawing.Rectangle.Contains%2A> 메서드 알려 사각형 내에서 지정된 된 지점 인지 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed657-133">The <xref:System.Drawing.Rectangle.IntersectsWith%2A> method tells you whether the rectangle intersects another given rectangle, and the <xref:System.Drawing.Rectangle.Contains%2A> method tells you whether a given point is inside the rectangle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed657-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="ed657-134">See also</span></span>
- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Rectangle?displayProperty=nameWithType>
- [<span data-ttu-id="ed657-135">방법: 펜 만들기</span><span class="sxs-lookup"><span data-stu-id="ed657-135">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
- [<span data-ttu-id="ed657-136">방법: Windows Form에 선 그리기</span><span class="sxs-lookup"><span data-stu-id="ed657-136">How to: Draw a Line on a Windows Form</span></span>](how-to-draw-a-line-on-a-windows-form.md)
- [<span data-ttu-id="ed657-137">방법: 윤곽선이 있는 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="ed657-137">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)
