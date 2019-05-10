---
title: '방법: 사각형 안에 줄 바꿈된 텍스트 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drawing text in a rectangle
- text [Windows Forms], drawing in a rectangle
- strings [Windows Forms], drawing in a rectangle
ms.assetid: e1fb432a-dc90-48b5-9b6b-acc14507133d
ms.openlocfilehash: ace79e45737a3ce26d8bdcd603e923c1e6040d4d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626160"
---
# <a name="how-to-draw-wrapped-text-in-a-rectangle"></a><span data-ttu-id="94985-102">방법: 사각형 안에 줄 바꿈된 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="94985-102">How to: Draw Wrapped Text in a Rectangle</span></span>
<span data-ttu-id="94985-103">사용 하 여 사각형 안에 줄 바꿈된 텍스트를 그릴 수 있습니다는 <xref:System.Drawing.Graphics.DrawString%2A> 메서드의 오버 로드는 <xref:System.Drawing.Graphics> 사용 하는 클래스를 <xref:System.Drawing.Rectangle> 또는 <xref:System.Drawing.RectangleF> 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="94985-103">You can draw wrapped text in a rectangle by using the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method of the <xref:System.Drawing.Graphics> class that takes a <xref:System.Drawing.Rectangle> or <xref:System.Drawing.RectangleF> parameter.</span></span> <span data-ttu-id="94985-104">사용할 수도 있습니다는 <xref:System.Drawing.Brush> 및 <xref:System.Drawing.Font>합니다.</span><span class="sxs-lookup"><span data-stu-id="94985-104">You will also use a <xref:System.Drawing.Brush> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="94985-105">사용 하 여 사각형 안에 줄 바꿈된 텍스트를 그릴 수도 있습니다는 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 메서드의 오버 로드는 <xref:System.Windows.Forms.TextRenderer> 를 사용 하는 <xref:System.Drawing.Rectangle> 및 <xref:System.Windows.Forms.TextFormatFlags> 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="94985-105">You can also draw wrapped text in a rectangle by using the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method of the <xref:System.Windows.Forms.TextRenderer> that takes a <xref:System.Drawing.Rectangle> and a <xref:System.Windows.Forms.TextFormatFlags> parameter.</span></span> <span data-ttu-id="94985-106">사용할 수도 있습니다는 <xref:System.Drawing.Color> 및 <xref:System.Drawing.Font>합니다.</span><span class="sxs-lookup"><span data-stu-id="94985-106">You will also use a <xref:System.Drawing.Color> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="94985-107">다음 그림에서는 사용 하 여 그린 사각형에서 텍스트의 출력을 보여 줍니다.는 <xref:System.Drawing.Graphics.DrawString%2A> 메서드:</span><span class="sxs-lookup"><span data-stu-id="94985-107">The following illustration shows the output of text drawn in the rectangle when you use the <xref:System.Drawing.Graphics.DrawString%2A> method:</span></span>
  
 ![DrawString 메서드를 사용 하는 경우 출력을 보여 주는 스크린샷.](./media/how-to-draw-wrapped-text-in-a-rectangle/drawstring-method-font-text.png)  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a><span data-ttu-id="94985-109">GDI +를 사용 하 여 사각형 안에 줄 바꿈된 텍스트를 그리기</span><span class="sxs-lookup"><span data-stu-id="94985-109">To draw wrapped text in a rectangle with GDI+</span></span>  
  
1. <span data-ttu-id="94985-110">사용 된 <xref:System.Drawing.Graphics.DrawString%2A> 오버 로드 된 메서드를 원하는 텍스트를 전달 <xref:System.Drawing.Rectangle> 또는 <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> 및 <xref:System.Drawing.Brush>.</span><span class="sxs-lookup"><span data-stu-id="94985-110">Use the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method, passing the text you want, <xref:System.Drawing.Rectangle> or <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> and <xref:System.Drawing.Brush>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a><span data-ttu-id="94985-111">GDI 사용 하 여 사각형 안에 줄 바꿈된 텍스트를 그리기</span><span class="sxs-lookup"><span data-stu-id="94985-111">To draw wrapped text in a rectangle with GDI</span></span>  
  
1. <span data-ttu-id="94985-112">사용 하 여는 <xref:System.Windows.Forms.TextFormatFlags> 텍스트를 지정 하는 열거형 값을 사용 하 여 래핑되어야 합니다 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 오버 로드 된 메서드를 원하는 텍스트를 전달 <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> 및 <xref:System.Drawing.Color>합니다.</span><span class="sxs-lookup"><span data-stu-id="94985-112">Use the <xref:System.Windows.Forms.TextFormatFlags> enumeration value to specify the text should be wrapped with the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method, passing the text you want, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> and <xref:System.Drawing.Color>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="94985-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="94985-113">Compiling the Code</span></span>  
 <span data-ttu-id="94985-114">앞의 예제에서는 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="94985-114">The previous examples require:</span></span>  
  
- <span data-ttu-id="94985-115"><xref:System.Windows.Forms.PaintEventArgs> `e`에서의 매개 변수인 <xref:System.Windows.Forms.PaintEventHandler>합니다.</span><span class="sxs-lookup"><span data-stu-id="94985-115"><xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94985-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="94985-116">See also</span></span>

- [<span data-ttu-id="94985-117">방법: GDI 사용 하 여 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="94985-117">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
- [<span data-ttu-id="94985-118">글꼴 및 텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="94985-118">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="94985-119">방법: 글꼴 패밀리 및 글꼴 만들기</span><span class="sxs-lookup"><span data-stu-id="94985-119">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)
- [<span data-ttu-id="94985-120">방법: 지정된 된 위치에 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="94985-120">How to: Draw Text at a Specified Location</span></span>](how-to-draw-text-at-a-specified-location.md)
