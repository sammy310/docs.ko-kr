---
title: '방법: 카디널 스플라인 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cardinal splines [Windows Forms], drawing
- drawing [Windows Forms], cardinal splines
- graphics [Windows Forms], cardinal splines
ms.assetid: a4a41e80-4461-4b47-b6bd-2c5e68881994
ms.openlocfilehash: 2f03177bf97936a2ca9558972d4d82fa3e07463c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204954"
---
# <a name="how-to-draw-cardinal-splines"></a><span data-ttu-id="658ae-102">방법: 카디널 스플라인 그리기</span><span class="sxs-lookup"><span data-stu-id="658ae-102">How to: Draw Cardinal Splines</span></span>
<span data-ttu-id="658ae-103">카디널 스플라인 곡선이 요소의 지정 된 집합을 통해 원활 하 게 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="658ae-103">A cardinal spline is a curve that passes smoothly through a given set of points.</span></span> <span data-ttu-id="658ae-104">카디널 스플라인 그리기를 만들려면를 <xref:System.Drawing.Graphics> 개체 및 배열 요소의 주소를 전달 합니다 <xref:System.Drawing.Graphics.DrawCurve%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="658ae-104">To draw a cardinal spline, create a <xref:System.Drawing.Graphics> object and pass the address of an array of points to the <xref:System.Drawing.Graphics.DrawCurve%2A> method.</span></span>  
  
### <a name="drawing-a-bell-shaped-cardinal-spline"></a><span data-ttu-id="658ae-105">종 모양의 카디널 스플라인 그리기</span><span class="sxs-lookup"><span data-stu-id="658ae-105">Drawing a Bell-Shaped Cardinal Spline</span></span>  
  
-   <span data-ttu-id="658ae-106">다음 예제에서는 5 개의 지정 된 지점을 통과 하는 종 모양의 카디널 스플라인을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="658ae-106">The following example draws a bell-shaped cardinal spline that passes through five designated points.</span></span> <span data-ttu-id="658ae-107">다음 그림에서는 5 점과 곡선을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="658ae-107">The following illustration shows the curve and five points.</span></span>  
  
     ![종 모양의 카디널 스플라인 보여 주는 다이어그램입니다.](./media/how-to-draw-cardinal-splines/bell-shaped-cardinal-spline.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#21)]  
  
### <a name="drawing-a-closed-cardinal-spline"></a><span data-ttu-id="658ae-109">폐쇄형된 카디널 스플라인 그리기</span><span class="sxs-lookup"><span data-stu-id="658ae-109">Drawing a Closed Cardinal Spline</span></span>  
  
-   <span data-ttu-id="658ae-110">사용 합니다 <xref:System.Drawing.Graphics.DrawClosedCurve%2A> 메서드는 <xref:System.Drawing.Graphics> 클래스는 폐쇄형된 카디널 스플라인을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="658ae-110">Use the <xref:System.Drawing.Graphics.DrawClosedCurve%2A> method of the <xref:System.Drawing.Graphics> class to draw a closed cardinal spline.</span></span> <span data-ttu-id="658ae-111">폐쇄형된 카디널 스플라인 곡선 배열의 마지막 요소를 계속 하 고 배열의 첫 번째 지점과 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="658ae-111">In a closed cardinal spline, the curve continues through the last point in the array and connects with the first point in the array.</span></span> <span data-ttu-id="658ae-112">다음 예제에서는 6 개의 지정 된 지점을 통과 하는 폐쇄형된 카디널 스플라인을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="658ae-112">The following example draws a closed cardinal spline that passes through six designated points.</span></span> <span data-ttu-id="658ae-113">다음 그림에서는 6 포인트에 따라 닫힌된 스플라인 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="658ae-113">The following illustration shows the closed spline along with the six points:</span></span>  
  
 ![폐쇄형된 카디널 스플라인을 보여 주는 다이어그램입니다.](./media/how-to-draw-cardinal-splines/closed-cardinal-spine.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#22)]  
  
### <a name="changing-the-bend-of-a-cardinal-spline"></a><span data-ttu-id="658ae-115">카디널 스플라인의 굴곡 변경</span><span class="sxs-lookup"><span data-stu-id="658ae-115">Changing the Bend of a Cardinal Spline</span></span>  
  
-   <span data-ttu-id="658ae-116">카디널 스플라인의 장력 인수를 전달 하 여 굴곡 방법을 변경 하 여 <xref:System.Drawing.Graphics.DrawCurve%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="658ae-116">Change the way a cardinal spline bends by passing a tension argument to the <xref:System.Drawing.Graphics.DrawCurve%2A> method.</span></span> <span data-ttu-id="658ae-117">다음 예제에서는 동일한 점 집합을 통과 하는 세 개의 카디널 스플라인을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="658ae-117">The following example draws three cardinal splines that pass through the same set of points.</span></span> <span data-ttu-id="658ae-118">다음 그림에서는 세 가지 스플라인 해당 장력 값과 함께 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="658ae-118">The following illustration shows the three splines along with their tension values.</span></span> <span data-ttu-id="658ae-119">참고 장력 0 인 점 직선으로 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="658ae-119">Note that when the tension is 0, the points are connected by straight lines.</span></span>  
  
 ![카디널 스플라인 세 가지를 보여 주는 다이어그램입니다.](./media/how-to-draw-cardinal-splines/three-cardinal-splines.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#23)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="658ae-121">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="658ae-121">Compiling the Code</span></span>  
 <span data-ttu-id="658ae-122">앞의 예제에서는 Windows Forms에서 사용 하도록 설계 되었으며 필요할 <xref:System.Windows.Forms.PaintEventArgs> `e`의 매개 변수는 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="658ae-122">The preceding examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="658ae-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="658ae-123">See also</span></span>

- [<span data-ttu-id="658ae-124">선, 곡선 및 도형</span><span class="sxs-lookup"><span data-stu-id="658ae-124">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="658ae-125">곡선 구성 및 그리기</span><span class="sxs-lookup"><span data-stu-id="658ae-125">Constructing and Drawing Curves</span></span>](constructing-and-drawing-curves.md)
