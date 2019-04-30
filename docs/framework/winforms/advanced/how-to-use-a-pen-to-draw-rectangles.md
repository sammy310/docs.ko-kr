---
title: '방법: 펜을 사용하여 사각형 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- rectangles [Windows Forms], drawing
- pens [Windows Forms], drawing rectangles
ms.assetid: 54a7fa14-3ad8-4d64-b424-2a12005b250c
ms.openlocfilehash: 0e51a1e3a2d14754147dbd36f170127a7e978acd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61954492"
---
# <a name="how-to-use-a-pen-to-draw-rectangles"></a><span data-ttu-id="29d41-102">방법: 펜을 사용하여 사각형 그리기</span><span class="sxs-lookup"><span data-stu-id="29d41-102">How to: Use a Pen to Draw Rectangles</span></span>
<span data-ttu-id="29d41-103">사각형을 그리려면 필요는 <xref:System.Drawing.Graphics> 개체 및 <xref:System.Drawing.Pen> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="29d41-103">To draw rectangles, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="29d41-104"><xref:System.Drawing.Graphics> 개체를 제공 합니다 <xref:System.Drawing.Graphics.DrawRectangle%2A> 메서드 및 <xref:System.Drawing.Pen> 개체 저장 되는 선의 색 및 두께 같은 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="29d41-104">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawRectangle%2A> method, and the <xref:System.Drawing.Pen> object stores features of the line, such as color and width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29d41-105">예제</span><span class="sxs-lookup"><span data-stu-id="29d41-105">Example</span></span>  
 <span data-ttu-id="29d41-106">다음 예제에서는 왼쪽 위 모퉁이가 사용 하 여 사각형을 그립니다 (10, 10).</span><span class="sxs-lookup"><span data-stu-id="29d41-106">The following example draws a rectangle with its upper-left corner at (10, 10).</span></span> <span data-ttu-id="29d41-107">사각형의 너비를 100 고 50 높이.</span><span class="sxs-lookup"><span data-stu-id="29d41-107">The rectangle has a width of 100 and a height of 50.</span></span> <span data-ttu-id="29d41-108">전달 된 두 번째 인수는 <xref:System.Drawing.Pen.%23ctor%2A> 생성자 펜 굵기 5 픽셀 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="29d41-108">The second argument passed to the <xref:System.Drawing.Pen.%23ctor%2A> constructor indicates that the pen width is 5 pixels.</span></span>  
  
 <span data-ttu-id="29d41-109">사각형을 그릴 때 펜 사각형의 경계에서 가운데 맞춤 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29d41-109">When the rectangle is drawn, the pen is centered on the rectangle's boundary.</span></span> <span data-ttu-id="29d41-110">사각형의 면은 그려지는 5 픽셀 펜 너비는 5 이므로 해당 1 픽셀이 그려집니다 와이드 등 자체 경계에서 2 픽셀로 내부적으로 그려지며 2 픽셀로 바깥쪽에 그려집니다.</span><span class="sxs-lookup"><span data-stu-id="29d41-110">Because the pen width is 5, the sides of the rectangle are drawn 5 pixels wide, such that 1 pixel is drawn on the boundary itself, 2 pixels are drawn on the inside, and 2 pixels are drawn on the outside.</span></span> <span data-ttu-id="29d41-111">펜 맞춤에 대 한 자세한 내용은 참조 하세요. [방법: 펜 굵기 및 맞춤 설정](how-to-set-pen-width-and-alignment.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="29d41-111">For more details on pen alignment, see [How to: Set Pen Width and Alignment](how-to-set-pen-width-and-alignment.md).</span></span>  
  
 <span data-ttu-id="29d41-112">다음 그림에서는 결과 사각형을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="29d41-112">The following illustration shows the resulting rectangle.</span></span> <span data-ttu-id="29d41-113">여기서 사각형 그려지는 펜 너비는 픽 했다면 점선 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="29d41-113">The dotted lines show where the rectangle would have been drawn if the pen width had been one pixel.</span></span> <span data-ttu-id="29d41-114">사각형의 왼쪽 위 모퉁이의 확대 된 뷰는 두꺼운 검정 선은 가운데에 이러한 점선 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="29d41-114">The enlarged view of the upper-left corner of the rectangle shows that the thick black lines are centered on those dotted lines.</span></span>  
  
 ![검정 및 점선을 사용 하 여 그린된 사각형을 보여주는 스크린샷.](./media/how-to-use-a-pen-to-draw-rectangles/drawn-rectangle-black-lines-dotted-lines.gif)  
  
 [!code-csharp[System.Drawing.UsingAPen#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingAPen#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="29d41-116">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="29d41-116">Compiling the Code</span></span>  
 <span data-ttu-id="29d41-117">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> 이벤트 처리기의 매개 변수인 `e`<xref:System.Windows.Forms.Control.Paint>가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="29d41-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29d41-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="29d41-118">See also</span></span>

- [<span data-ttu-id="29d41-119">펜을 사용하여 선과 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="29d41-119">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
