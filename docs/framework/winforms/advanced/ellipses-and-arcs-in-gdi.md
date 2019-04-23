---
title: GDI+의 타원 및 원호
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- arcs
- GDI+, arcs
- drawing [Windows Forms], ellipses
- GDI+, ellipses
- ellipses
- drawing [Windows Forms], arcs
ms.assetid: 34f35133-a835-4ca4-81f6-0dfedee8b683
ms.openlocfilehash: 8bbc2eda6450128eac55576259880e83f07099ab
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59117458"
---
# <a name="ellipses-and-arcs-in-gdi"></a><span data-ttu-id="5ec08-102">GDI+의 타원 및 원호</span><span class="sxs-lookup"><span data-stu-id="5ec08-102">Ellipses and Arcs in GDI+</span></span>
<span data-ttu-id="5ec08-103">타원 및 원호를 사용 하 여 쉽게 그릴 수 있습니다는 <xref:System.Drawing.Graphics.DrawEllipse%2A> 하 고 <xref:System.Drawing.Graphics.DrawArc%2A> 의 메서드는 <xref:System.Drawing.Graphics> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="5ec08-103">You can easily draw ellipses and arcs using the <xref:System.Drawing.Graphics.DrawEllipse%2A> and <xref:System.Drawing.Graphics.DrawArc%2A> methods of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="drawing-an-ellipse"></a><span data-ttu-id="5ec08-104">타원 그리기</span><span class="sxs-lookup"><span data-stu-id="5ec08-104">Drawing an Ellipse</span></span>  
 <span data-ttu-id="5ec08-105">타원을 그릴 필요는 <xref:System.Drawing.Graphics> 개체 및 <xref:System.Drawing.Pen> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5ec08-105">To draw an ellipse, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="5ec08-106"><xref:System.Drawing.Graphics> 개체를 제공 합니다 <xref:System.Drawing.Graphics.DrawEllipse%2A> 메서드를 및 <xref:System.Drawing.Pen> 개체 타원을 렌더링 하는 데 사용 하는 선의 색과 두께 같은 특성을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec08-106">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawEllipse%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the ellipse.</span></span> <span data-ttu-id="5ec08-107">합니다 <xref:System.Drawing.Pen> 개체에 대 한 인수 중 하나로 전달 되는 <xref:System.Drawing.Graphics.DrawEllipse%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="5ec08-107">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method.</span></span> <span data-ttu-id="5ec08-108">나머지 인수에 전달 된 <xref:System.Drawing.Graphics.DrawEllipse%2A> 메서드 타원의 경계 사각형을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec08-108">The remaining arguments passed to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method specify the bounding rectangle for the ellipse.</span></span> <span data-ttu-id="5ec08-109">다음 그림에서는 경계 사각형과 함께 타원을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5ec08-109">The following illustration shows an ellipse along with its bounding rectangle.</span></span>  
  
 <span data-ttu-id="5ec08-110">![타원 및 원호](./media/aboutgdip02-art05.gif "Aboutgdip02_art05")</span><span class="sxs-lookup"><span data-stu-id="5ec08-110">![Ellipses and arcs](./media/aboutgdip02-art05.gif "Aboutgdip02_art05")</span></span>  
  
 <span data-ttu-id="5ec08-111">다음 예제에서는; 타원을 그립니다. 경계 사각형에 80, 40, 높이 및를 왼쪽 위 모퉁이의 너비 (100, 50):</span><span class="sxs-lookup"><span data-stu-id="5ec08-111">The following example draws an ellipse; the bounding rectangle has a width of 80, a height of 40, and an upper-left corner of (100, 50):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#51](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#51)]
 [!code-vb[LinesCurvesAndShapes#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#51)]  
  
 <span data-ttu-id="5ec08-112"><xref:System.Drawing.Graphics.DrawEllipse%2A> 오버 로드 메서드도 <xref:System.Drawing.Graphics> 클래스를 여러 가지 인수를 사용 하 여 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ec08-112"><xref:System.Drawing.Graphics.DrawEllipse%2A> is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="5ec08-113">예를 들어, 생성할 수 있습니다는 <xref:System.Drawing.Rectangle> 전달 합니다 <xref:System.Drawing.Rectangle> 에 <xref:System.Drawing.Graphics.DrawEllipse%2A> 메서드에 인수로:</span><span class="sxs-lookup"><span data-stu-id="5ec08-113">For example, you can construct a <xref:System.Drawing.Rectangle> and pass the <xref:System.Drawing.Rectangle> to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method as an argument:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#52](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#52)]
 [!code-vb[LinesCurvesAndShapes#52](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#52)]  
  
## <a name="drawing-an-arc"></a><span data-ttu-id="5ec08-114">호를 그리기</span><span class="sxs-lookup"><span data-stu-id="5ec08-114">Drawing an Arc</span></span>  
 <span data-ttu-id="5ec08-115">호에는 타원의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="5ec08-115">An arc is a portion of an ellipse.</span></span> <span data-ttu-id="5ec08-116">호출 호를 그릴 합니다 <xref:System.Drawing.Graphics.DrawArc%2A> 메서드는 <xref:System.Drawing.Graphics> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="5ec08-116">To draw an arc, you call the <xref:System.Drawing.Graphics.DrawArc%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="5ec08-117">매개 변수를 <xref:System.Drawing.Graphics.DrawArc%2A> 의 매개 변수와 동일 합니다 <xref:System.Drawing.Graphics.DrawEllipse%2A> 메서드 <xref:System.Drawing.Graphics.DrawArc%2A> 시작 각도 및 스윕 각도 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec08-117">The parameters of the <xref:System.Drawing.Graphics.DrawArc%2A> method are the same as the parameters of the <xref:System.Drawing.Graphics.DrawEllipse%2A> method, except that <xref:System.Drawing.Graphics.DrawArc%2A> requires a starting angle and sweep angle.</span></span> <span data-ttu-id="5ec08-118">다음 예제에서는 30도의 시작 각도 및 스윕 각도 180도 호를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="5ec08-118">The following example draws an arc with a starting angle of 30 degrees and a sweep angle of 180 degrees:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#53](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#53)]
 [!code-vb[LinesCurvesAndShapes#53](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#53)]  
  
 <span data-ttu-id="5ec08-119">다음 그림은 호의 타원 및 경계 사각형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5ec08-119">The following illustration shows the arc, the ellipse, and the bounding rectangle.</span></span>  
  
 <span data-ttu-id="5ec08-120">![타원 및 원호](./media/aboutgdip02-art06.gif "Aboutgdip02_art06")</span><span class="sxs-lookup"><span data-stu-id="5ec08-120">![Ellipses and arcs](./media/aboutgdip02-art06.gif "Aboutgdip02_art06")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ec08-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="5ec08-121">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [<span data-ttu-id="5ec08-122">선, 곡선 및 도형</span><span class="sxs-lookup"><span data-stu-id="5ec08-122">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="5ec08-123">방법: 그리는 데 필요한 그래픽 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="5ec08-123">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="5ec08-124">방법: 펜 만들기</span><span class="sxs-lookup"><span data-stu-id="5ec08-124">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
- [<span data-ttu-id="5ec08-125">방법: 윤곽선이 있는 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="5ec08-125">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)
