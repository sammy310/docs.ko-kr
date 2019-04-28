---
title: B&#233;zier GDI +의 스플라인
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines
- splines [Windows Forms], Bezier
- GDI+, Bezier splines
ms.assetid: 5774ce1e-87d4-4bc7-88c4-4862052781b8
ms.openlocfilehash: ff4e9eb18610b70c88e057d3d44020321bbb9f4f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61779276"
---
# <a name="b233zier-splines-in-gdi"></a><span data-ttu-id="a1314-102">B&#233;zier GDI +의 스플라인</span><span class="sxs-lookup"><span data-stu-id="a1314-102">B&#233;zier Splines in GDI+</span></span>
<span data-ttu-id="a1314-103">베 지 어 스플라인을 네 지점에서 지정 된 곡선이: 두 끝점 (예: p1 및 p2) 및 두 개의 제어점 (c1 및 c2).</span><span class="sxs-lookup"><span data-stu-id="a1314-103">A Bézier spline is a curve specified by four points: two end points (p1 and p2) and two control points (c1 and c2).</span></span> <span data-ttu-id="a1314-104">곡선 시작 된 p1 및 p2에서 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="a1314-104">The curve begins at p1 and ends at p2.</span></span> <span data-ttu-id="a1314-105">곡선의 제어점 통과 하지 않습니다 않지만 제어점 자석, 특정 방향으로 곡선을 가져와서 곡률 방식에 영향을 주는 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1314-105">The curve does not pass through the control points, but the control points act as magnets, pulling the curve in certain directions and influencing the way the curve bends.</span></span> <span data-ttu-id="a1314-106">다음 그림은 끝점 및 제어점와 함께 베 지 어 곡선을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a1314-106">The following illustration shows a Bézier curve along with its endpoints and control points.</span></span>  
  
 <span data-ttu-id="a1314-107">![3 차원 곡선 스플라인](./media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")</span><span class="sxs-lookup"><span data-stu-id="a1314-107">![Bezier Splines](./media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")</span></span>  
  
 <span data-ttu-id="a1314-108">곡선 p1에서 시작 하 고 제어 지점 c1 쪽으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1314-108">The curve starts at p1 and moves toward the control point c1.</span></span> <span data-ttu-id="a1314-109">접선를 p1에서 곡선은 c1 p1에서 그린 선입니다.</span><span class="sxs-lookup"><span data-stu-id="a1314-109">The tangent line to the curve at p1 is the line drawn from p1 to c1.</span></span> <span data-ttu-id="a1314-110">끝점 p2의 탄젠트 줄은 c2에서 p2로 그린 선입니다.</span><span class="sxs-lookup"><span data-stu-id="a1314-110">The tangent line at the endpoint p2 is the line drawn from c2 to p2.</span></span>  
  
## <a name="drawing-bzier-splines"></a><span data-ttu-id="a1314-111">3 차원 곡선 스플라인 그리기</span><span class="sxs-lookup"><span data-stu-id="a1314-111">Drawing Bézier Splines</span></span>  
 <span data-ttu-id="a1314-112">베 지 어 스플라인의 그리려면 인스턴스의 해야 합니다 <xref:System.Drawing.Graphics> 클래스 및 <xref:System.Drawing.Pen>합니다.</span><span class="sxs-lookup"><span data-stu-id="a1314-112">To draw a Bézier spline, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Pen>.</span></span> <span data-ttu-id="a1314-113">인스턴스를 <xref:System.Drawing.Graphics> 클래스를 제공 합니다 <xref:System.Drawing.Graphics.DrawBezier%2A> 메서드를 및 <xref:System.Drawing.Pen> 곡선을 렌더링 하는 데 사용 하는 선의 색과 두께 같은 특성을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1314-113">The instance of the <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.DrawBezier%2A> method, and the <xref:System.Drawing.Pen> stores attributes, such as width and color, of the line used to render the curve.</span></span> <span data-ttu-id="a1314-114">합니다 <xref:System.Drawing.Pen> 에 대 한 인수 중 하나로 전달 되는 <xref:System.Drawing.Graphics.DrawBezier%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="a1314-114">The <xref:System.Drawing.Pen> is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawBezier%2A> method.</span></span> <span data-ttu-id="a1314-115">나머지 인수에 전달 된 <xref:System.Drawing.Graphics.DrawBezier%2A> 메서드는 끝점 및 제어점입니다.</span><span class="sxs-lookup"><span data-stu-id="a1314-115">The remaining arguments passed to the <xref:System.Drawing.Graphics.DrawBezier%2A> method are the endpoints and the control points.</span></span> <span data-ttu-id="a1314-116">다음 예제에서는 시작 지점 (0, 0)를 사용 하 여 베 지 어 스플라인을 그립니다 지점 (40, 20) 및 (80, 150)을 제어 하 고 끝 지점 (100, 10):</span><span class="sxs-lookup"><span data-stu-id="a1314-116">The following example draws a Bézier spline with starting point (0, 0), control points (40, 20) and (80, 150), and ending point (100, 10):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#71](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#71)]
 [!code-vb[LinesCurvesAndShapes#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#71)]  
  
 <span data-ttu-id="a1314-117">다음 그림에서는 곡선는 제어점과 두 개의 접선을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a1314-117">The following illustration shows the curve, the control points, and two tangent lines.</span></span>  
  
 <span data-ttu-id="a1314-118">![3 차원 곡선 스플라인](./media/aboutgdip02-art12.gif "Aboutgdip02_art12")</span><span class="sxs-lookup"><span data-stu-id="a1314-118">![Bezier Splines](./media/aboutgdip02-art12.gif "Aboutgdip02_art12")</span></span>  
  
 <span data-ttu-id="a1314-119">3 차원 곡선 스플라인 처음 개발한 피에르 베 지 어 디자인 자동차 업계에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1314-119">Bézier splines were originally developed by Pierre Bézier for design in the automotive industry.</span></span> <span data-ttu-id="a1314-120">다양 한 유형의 컴퓨터 지원 디자인에 유용한 것으로 입증 하므로 않으며는 또한 윤곽선 글꼴을 정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1314-120">They have since proven to be useful in many types of computer-aided design and are also used to define the outlines of fonts.</span></span> <span data-ttu-id="a1314-121">3 차원 곡선 스플라인 다양 한 셰이프를 다음 그림에 나와 있는 일부를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1314-121">Bézier splines can yield a wide variety of shapes, some of which are shown in the following illustration.</span></span>  
  
 <span data-ttu-id="a1314-122">![Paths](./media/aboutgdip02-art13.gif "Aboutgdip02_art13")</span><span class="sxs-lookup"><span data-stu-id="a1314-122">![Paths](./media/aboutgdip02-art13.gif "Aboutgdip02_art13")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1314-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="a1314-123">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [<span data-ttu-id="a1314-124">선, 곡선 및 도형</span><span class="sxs-lookup"><span data-stu-id="a1314-124">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="a1314-125">곡선 구성 및 그리기</span><span class="sxs-lookup"><span data-stu-id="a1314-125">Constructing and Drawing Curves</span></span>](constructing-and-drawing-curves.md)
- [<span data-ttu-id="a1314-126">방법: 그리는 데 필요한 그래픽 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="a1314-126">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="a1314-127">방법: 펜 만들기</span><span class="sxs-lookup"><span data-stu-id="a1314-127">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
