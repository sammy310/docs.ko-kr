---
title: '방법: Windows Form에 텍스트 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- forms [Windows Forms], drawing text
- text [Windows Forms], drawing
ms.assetid: 5d2447a9-21a1-4adc-b954-5516f2bb9b2c
ms.openlocfilehash: ed7aa89c3bd3751ed93f5bda33a26a8309d39143
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703506"
---
# <a name="how-to-draw-text-on-a-windows-form"></a><span data-ttu-id="0ef40-102">방법: Windows Form에 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="0ef40-102">How to: Draw Text on a Windows Form</span></span>
<span data-ttu-id="0ef40-103">다음 코드 예제를 사용 하는 방법을 보여 줍니다 합니다 <xref:System.Drawing.Graphics.DrawString%2A> 메서드는 <xref:System.Drawing.Graphics> 폼에 텍스트를 그리는 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef40-103">The following code example shows how to use the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> to draw text on a form.</span></span> <span data-ttu-id="0ef40-104">사용할 수 있습니다 <xref:System.Windows.Forms.TextRenderer> 폼에 텍스트를 그리기 위한 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef40-104">Alternatively, you can use <xref:System.Windows.Forms.TextRenderer> for drawing text on a form.</span></span> <span data-ttu-id="0ef40-105">자세한 내용은 [방법: GDI 사용 하 여 텍스트 그리기](how-to-draw-text-with-gdi.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef40-105">For more information, see [How to: Draw Text with GDI](how-to-draw-text-with-gdi.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ef40-106">예제</span><span class="sxs-lookup"><span data-stu-id="0ef40-106">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#7](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#7)]
 [!code-csharp[System.Drawing.ConceptualHowTos#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#7)]
 [!code-vb[System.Drawing.ConceptualHowTos#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#7)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0ef40-107">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="0ef40-107">Compiling the Code</span></span>  
 <span data-ttu-id="0ef40-108">호출할 수 없습니다는 <xref:System.Drawing.Graphics.DrawString%2A> 의 메서드는 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="0ef40-108">You cannot call the <xref:System.Drawing.Graphics.DrawString%2A> method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="0ef40-109">그려지는 콘텐츠 비활성 폼 크기가 조정 되거나 다른 양식으로 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="0ef40-109">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="0ef40-110">재정의 해야 하는 자동으로 다시 그리기 콘텐츠를 확인 하는 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="0ef40-110">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="0ef40-111">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="0ef40-111">Robust Programming</span></span>  
 <span data-ttu-id="0ef40-112">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef40-112">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="0ef40-113">Arial 글꼴이 설치 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="0ef40-113">The Arial font is not installed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ef40-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="0ef40-114">See also</span></span>
- <xref:System.Drawing.Graphics.DrawString%2A>
- <xref:System.Windows.Forms.TextRenderer.DrawText%2A>
- <xref:System.Drawing.StringFormat.FormatFlags%2A>
- <xref:System.Drawing.StringFormatFlags>
- <xref:System.Windows.Forms.TextFormatFlags>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="0ef40-115">그래픽 프로그래밍 시작</span><span class="sxs-lookup"><span data-stu-id="0ef40-115">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="0ef40-116">방법: GDI 사용 하 여 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="0ef40-116">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
