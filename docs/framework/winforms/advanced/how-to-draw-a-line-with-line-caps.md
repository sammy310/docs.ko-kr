---
title: '방법: 선 끝이 있는 선 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
- drawing lines [Windows Forms], line caps
ms.assetid: eb68c3e1-c400-4886-8a04-76978a429cb6
ms.openlocfilehash: c4a78569f6c0b14c32154611412d6b3ccd8a84ce
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59146213"
---
# <a name="how-to-draw-a-line-with-line-caps"></a><span data-ttu-id="7b68c-102">방법: 선 끝이 있는 선 그리기</span><span class="sxs-lookup"><span data-stu-id="7b68c-102">How to: Draw a Line with Line Caps</span></span>
<span data-ttu-id="7b68c-103">선 끝이 호출 하는 여러 도형 중 하나에서 시작 또는 줄의 끝에 그릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b68c-103">You can draw the start or end of a line in one of several shapes called line caps.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="7b68c-104">여러 선 끝 모양을 화살촉 라운드, 사각형, 다이아몬드 등을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7b68c-104">supports several line caps, such as round, square, diamond, and arrowhead.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b68c-105">예제</span><span class="sxs-lookup"><span data-stu-id="7b68c-105">Example</span></span>  
 <span data-ttu-id="7b68c-106">줄 (시작 cap), (end cap) 줄의 끝 또는 파선 (dash cap)의 대시의 시작 부분에 대 한 선 끝 모양을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b68c-106">You can specify line caps for the start of a line (start cap), the end of a line (end cap), or the dashes of a dashed line (dash cap).</span></span>  
  
 <span data-ttu-id="7b68c-107">다음 예제에는 한쪽 end에 있는 화살촉이와 다른 끝에 있는 둥근 단면 선을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="7b68c-107">The following example draws a line with an arrowhead at one end and a round cap at the other end.</span></span> <span data-ttu-id="7b68c-108">그림 결과 줄을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7b68c-108">The illustration shows the resulting line:</span></span>  
  
 ![둥근 끝에 있는 줄을 보여 주는 그림입니다.](./media/how-to-draw-a-line-with-line-caps/line-cap-arrowhead-example.gif)  
  
 [!code-csharp[System.Drawing.UsingAPen#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.UsingAPen#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7b68c-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="7b68c-110">Compiling the Code</span></span>  
  
-   <span data-ttu-id="7b68c-111">Windows Form 만들기 및 폼의 처리 <xref:System.Windows.Forms.Control.Paint> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="7b68c-111">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="7b68c-112">예제 코드를 붙여 합니다 <xref:System.Windows.Forms.Control.Paint> 전달 하는 이벤트 처리기 `e` 으로 <xref:System.Windows.Forms.PaintEventArgs>합니다.</span><span class="sxs-lookup"><span data-stu-id="7b68c-112">Paste the example code into the <xref:System.Windows.Forms.Control.Paint> event handler passing `e` as <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b68c-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="7b68c-113">See also</span></span>

- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.LineCap?displayProperty=nameWithType>
- [<span data-ttu-id="7b68c-114">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="7b68c-114">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="7b68c-115">펜을 사용하여 선과 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="7b68c-115">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
