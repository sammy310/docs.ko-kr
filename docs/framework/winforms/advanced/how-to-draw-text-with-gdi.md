---
title: '방법: GDI 사용 하 여 텍스트 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing with TextRenderer
- drawing [Windows Forms], text
- Windows Forms, drawing text with GDI
ms.assetid: 2a19fe5d-2ace-451c-94db-01cb1118ef7b
ms.openlocfilehash: 644e180e2f15592db2112a5cd6f5b0130c6abea8
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722332"
---
# <a name="how-to-draw-text-with-gdi"></a><span data-ttu-id="0e30d-102">방법: GDI 사용 하 여 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="0e30d-102">How to: Draw Text with GDI</span></span>
<span data-ttu-id="0e30d-103">사용 하 여 합니다 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 의 메서드를 <xref:System.Windows.Forms.TextRenderer> 클래스에 액세스할 수 있습니다 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 폼 이나 컨트롤에서 텍스트를 그리기 위한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="0e30d-103">With the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method in the <xref:System.Windows.Forms.TextRenderer> class, you can access [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] functionality for drawing text on a form or control.</span></span> [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] <span data-ttu-id="0e30d-104">텍스트 렌더링은 일반적으로 더 나은 성능과 더 정확 하 게 텍스트 보다 측정 제공 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="0e30d-104">text rendering typically offers better performance and more accurate text measuring than [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0e30d-105">합니다 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 의 메서드는 <xref:System.Windows.Forms.TextRenderer> 인쇄에 대 한 클래스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0e30d-105">The <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods of the <xref:System.Windows.Forms.TextRenderer> class are not supported for printing.</span></span> <span data-ttu-id="0e30d-106">인쇄 하는 경우 항상 사용 합니다 <xref:System.Drawing.Graphics.DrawString%2A> 의 메서드는 <xref:System.Drawing.Graphics> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="0e30d-106">When printing, always use the <xref:System.Drawing.Graphics.DrawString%2A> methods of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e30d-107">예제</span><span class="sxs-lookup"><span data-stu-id="0e30d-107">Example</span></span>  
 <span data-ttu-id="0e30d-108">다음 코드 예제에 사용 하 여 사각형 내에서 여러 줄에 텍스트를 그리는 방법을 보여 줍니다는 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="0e30d-108">The following code example demonstrates how to draw text on multiple lines within a rectangle using the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method.</span></span>  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 <span data-ttu-id="0e30d-109">사용 하 여 텍스트를 렌더링 하는 <xref:System.Windows.Forms.TextRenderer> 해야 클래스는 <xref:System.Drawing.IDeviceContext>와 같은 <xref:System.Drawing.Graphics> 및 <xref:System.Drawing.Font>, 텍스트 및 색 나타나는 것을 그려야 그릴 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="0e30d-109">To render text with the <xref:System.Windows.Forms.TextRenderer> class, you need an <xref:System.Drawing.IDeviceContext>, such as a <xref:System.Drawing.Graphics> and a <xref:System.Drawing.Font>, a location to draw the text, and the color in which it should be drawn.</span></span> <span data-ttu-id="0e30d-110">필요에 따라 사용 하 여 텍스트 서식을 지정할 수 있습니다는 <xref:System.Windows.Forms.TextFormatFlags> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="0e30d-110">Optionally, you can specify the text formatting by using the <xref:System.Windows.Forms.TextFormatFlags> enumeration.</span></span>  
  
 <span data-ttu-id="0e30d-111">가져오기에 대 한 자세한를 <xref:System.Drawing.Graphics>를 참조 하세요 [방법: 그리는 데 필요한 그래픽 개체 만들기](how-to-create-graphics-objects-for-drawing.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0e30d-111">For more information about obtaining a <xref:System.Drawing.Graphics>, see [How to: Create Graphics Objects for Drawing](how-to-create-graphics-objects-for-drawing.md).</span></span> <span data-ttu-id="0e30d-112">생성 하는 방법에 대 한 자세한 내용은 <xref:System.Drawing.Font>를 참조 하세요 [방법: 글꼴 패밀리 및 글꼴](how-to-construct-font-families-and-fonts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0e30d-112">For more information about constructing a <xref:System.Drawing.Font>, see [How to: Construct Font Families and Fonts](how-to-construct-font-families-and-fonts.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0e30d-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="0e30d-113">Compiling the Code</span></span>  
 <span data-ttu-id="0e30d-114">앞의 코드 예제는 Windows Forms에서 사용 하도록 설계 되었으며 필요 합니다 <xref:System.Windows.Forms.PaintEventArgs> `e`의 매개 변수인 <xref:System.Windows.Forms.PaintEventHandler>합니다.</span><span class="sxs-lookup"><span data-stu-id="0e30d-114">The preceding code example is designed for use with Windows Forms, and it requires the <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e30d-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="0e30d-115">See also</span></span>
- <xref:System.Windows.Forms.TextRenderer>
- <xref:System.Drawing.Font>
- <xref:System.Drawing.Color>
- <xref:System.Drawing.Color>
- [<span data-ttu-id="0e30d-116">글꼴 및 텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="0e30d-116">Using Fonts and Text</span></span>](using-fonts-and-text.md)
