---
title: '방법: B의 시퀀스를 그리는&#233;zier 스플라인'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- splines [Windows Forms], drawing Bezier
- Bezier splines [Windows Forms], drawing sequence of
ms.assetid: 37a0bedb-20c2-4cf0-91fa-a5509e826b30
ms.openlocfilehash: 976787f5830282a581d05a9c24d1f83dceca4b25
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004263"
---
# <a name="how-to-draw-a-sequence-of-b233zier-splines"></a><span data-ttu-id="9ee99-102">방법: B의 시퀀스를 그리는&#233;zier 스플라인</span><span class="sxs-lookup"><span data-stu-id="9ee99-102">How to: Draw a Sequence of B&#233;zier Splines</span></span>
<span data-ttu-id="9ee99-103">사용할 수는 <xref:System.Drawing.Graphics.DrawBeziers%2A> 메서드는 <xref:System.Drawing.Graphics> 일련의 그리기 클래스에는 3 차원 곡선 스플라인 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee99-103">You can use the <xref:System.Drawing.Graphics.DrawBeziers%2A> method of the <xref:System.Drawing.Graphics> class to draw a sequence of connected Bézier splines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ee99-104">예제</span><span class="sxs-lookup"><span data-stu-id="9ee99-104">Example</span></span>  
 <span data-ttu-id="9ee99-105">다음 예제에서는 두 개의 연결 된 3 차원 곡선 스플라인 구성 된 곡선을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="9ee99-105">The following example draws a curve that consists of two connected Bézier splines.</span></span> <span data-ttu-id="9ee99-106">첫 번째 베 지 어 스플라인의 끝점에는 두 번째 베 지 어 스플라인의 시작 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="9ee99-106">The endpoint of the first Bézier spline is the start point of the second Bézier spline.</span></span>  
  
 <span data-ttu-id="9ee99-107">다음 그림에는 7 개의 점이 함께 연결 된 스플라인 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9ee99-107">The following illustration shows the connected splines along with the seven points:</span></span>  
  
 ![7 개의 점이 함께 연결 된 스플라인 보여 주는 그래픽.](./media/how-to-draw-a-sequence-of-bezier-splines/bezier-spline-seven-points.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9ee99-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="9ee99-109">Compiling the Code</span></span>  
 <span data-ttu-id="9ee99-110">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee99-110">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ee99-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="9ee99-111">See also</span></span>

- [<span data-ttu-id="9ee99-112">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="9ee99-112">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="9ee99-113">GDI+의 3차원 곡선 스플라인</span><span class="sxs-lookup"><span data-stu-id="9ee99-113">Bézier Splines in GDI+</span></span>](bezier-splines-in-gdi.md)
- [<span data-ttu-id="9ee99-114">곡선 구성 및 그리기</span><span class="sxs-lookup"><span data-stu-id="9ee99-114">Constructing and Drawing Curves</span></span>](constructing-and-drawing-curves.md)
