---
title: '방법: GDI를 사용하여 텍스트 그리기'
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
ms.openlocfilehash: 3ed2b5c94e4a38a5873a34e61287c4038cab5cbb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956538"
---
# <a name="how-to-draw-text-with-gdi"></a><span data-ttu-id="168c6-102">방법: GDI를 사용하여 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="168c6-102">How to: Draw Text with GDI</span></span>
<span data-ttu-id="168c6-103">클래스의 메서드를 사용 하 여 폼 이나 컨트롤에 텍스트를 그리기 위한 GDI 기능에 액세스할 수 있습니다. <xref:System.Windows.Forms.TextRenderer.DrawText%2A> <xref:System.Windows.Forms.TextRenderer></span><span class="sxs-lookup"><span data-stu-id="168c6-103">With the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method in the <xref:System.Windows.Forms.TextRenderer> class, you can access GDI functionality for drawing text on a form or control.</span></span> <span data-ttu-id="168c6-104">GDI 텍스트 렌더링은 일반적으로 GDI + 보다 더 나은 성능 및 보다 정확한 텍스트 측정을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="168c6-104">GDI text rendering typically offers better performance and more accurate text measuring than GDI+.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="168c6-105">합니다 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 의 메서드는 <xref:System.Windows.Forms.TextRenderer> 인쇄에 대 한 클래스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="168c6-105">The <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods of the <xref:System.Windows.Forms.TextRenderer> class are not supported for printing.</span></span> <span data-ttu-id="168c6-106">인쇄 하는 경우 항상 <xref:System.Drawing.Graphics.DrawString%2A> <xref:System.Drawing.Graphics> 클래스의 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="168c6-106">When printing, always use the <xref:System.Drawing.Graphics.DrawString%2A> methods of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="168c6-107">예제</span><span class="sxs-lookup"><span data-stu-id="168c6-107">Example</span></span>  
 <span data-ttu-id="168c6-108">다음 코드 예제에서는 메서드를 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 사용 하 여 사각형 내의 여러 줄에 텍스트를 그리는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="168c6-108">The following code example demonstrates how to draw text on multiple lines within a rectangle using the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method.</span></span>  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 <span data-ttu-id="168c6-109"><xref:System.Windows.Forms.TextRenderer> 클래스를 사용 하 여 텍스트를 렌더링 하려면 <xref:System.Drawing.Graphics> 및 <xref:System.Drawing.Font>와 같은, 텍스트를 그릴 위치 및 그려야 하는 색을 사용 <xref:System.Drawing.IDeviceContext>해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="168c6-109">To render text with the <xref:System.Windows.Forms.TextRenderer> class, you need an <xref:System.Drawing.IDeviceContext>, such as a <xref:System.Drawing.Graphics> and a <xref:System.Drawing.Font>, a location to draw the text, and the color in which it should be drawn.</span></span> <span data-ttu-id="168c6-110">필요에 따라 <xref:System.Windows.Forms.TextFormatFlags> 열거를 사용 하 여 텍스트 서식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="168c6-110">Optionally, you can specify the text formatting by using the <xref:System.Windows.Forms.TextFormatFlags> enumeration.</span></span>  
  
 <span data-ttu-id="168c6-111"><xref:System.Drawing.Graphics> 을[가져오는 방법에 대 한 자세한 내용은 방법: 그리기](how-to-create-graphics-objects-for-drawing.md)를 위한 그래픽 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="168c6-111">For more information about obtaining a <xref:System.Drawing.Graphics>, see [How to: Create Graphics Objects for Drawing](how-to-create-graphics-objects-for-drawing.md).</span></span> <span data-ttu-id="168c6-112"><xref:System.Drawing.Font> 를[구성 하는 방법에 대 한 자세한 내용은 방법: 글꼴 패밀리 및 글꼴](how-to-construct-font-families-and-fonts.md)을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="168c6-112">For more information about constructing a <xref:System.Drawing.Font>, see [How to: Construct Font Families and Fonts](how-to-construct-font-families-and-fonts.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="168c6-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="168c6-113">Compiling the Code</span></span>  
 <span data-ttu-id="168c6-114">위의 코드 예제는 Windows Forms와 함께 사용 하도록 설계 되었으며의 <xref:System.Windows.Forms.PaintEventArgs> <xref:System.Windows.Forms.PaintEventHandler>매개 변수인가 필요 `e`합니다.</span><span class="sxs-lookup"><span data-stu-id="168c6-114">The preceding code example is designed for use with Windows Forms, and it requires the <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="168c6-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="168c6-115">See also</span></span>

- <xref:System.Windows.Forms.TextRenderer>
- <xref:System.Drawing.Font>
- <xref:System.Drawing.Color>
- [<span data-ttu-id="168c6-116">글꼴 및 텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="168c6-116">Using Fonts and Text</span></span>](using-fonts-and-text.md)
