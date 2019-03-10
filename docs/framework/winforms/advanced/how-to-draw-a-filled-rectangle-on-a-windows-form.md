---
title: '방법: Windows Form에 채워진된 사각형 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.FillRectangle
helpviewer_keywords:
- drawing [Windows Forms], rectangles
- rectangles [Windows Forms], drawing
- drawing rectangles
ms.assetid: d656a93c-987d-4809-aafd-493fe17450f0
ms.openlocfilehash: 53fab93f47c16257b5ab2e336b43c6133a31d509
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716896"
---
# <a name="how-to-draw-a-filled-rectangle-on-a-windows-form"></a><span data-ttu-id="abb29-102">방법: Windows Form에 채워진된 사각형 그리기</span><span class="sxs-lookup"><span data-stu-id="abb29-102">How to: Draw a Filled Rectangle on a Windows Form</span></span>
<span data-ttu-id="abb29-103">이 예제에서는 폼에 채워진된 사각형을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="abb29-103">This example draws a filled rectangle on a form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="abb29-104">예제</span><span class="sxs-lookup"><span data-stu-id="abb29-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#2](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#2)]
 [!code-csharp[System.Drawing.ConceptualHowTos#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#2)]
 [!code-vb[System.Drawing.ConceptualHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="abb29-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="abb29-105">Compiling the Code</span></span>  
 <span data-ttu-id="abb29-106">이 메서드를 호출할 수 없습니다는 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="abb29-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="abb29-107">그려지는 콘텐츠 비활성 폼 크기가 조정 되거나 다른 양식으로 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="abb29-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="abb29-108">재정의 해야 하는 자동으로 다시 그리기 콘텐츠를 확인 하는 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="abb29-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="abb29-109">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="abb29-109">Robust Programming</span></span>  
 <span data-ttu-id="abb29-110">항상 호출 해야 <xref:System.IDisposable.Dispose%2A> 와 같은 시스템 리소스를 사용 하는 모든 개체에 <xref:System.Drawing.Brush> 고 <xref:System.Drawing.Graphics> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="abb29-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Brush> and <xref:System.Drawing.Graphics> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abb29-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="abb29-111">See also</span></span>
- <xref:System.Drawing.Graphics.FillRectangle%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="abb29-112">그래픽 프로그래밍 시작</span><span class="sxs-lookup"><span data-stu-id="abb29-112">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="abb29-113">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="abb29-113">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="abb29-114">펜을 사용하여 선과 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="abb29-114">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="abb29-115">GDI+의 브러시 및 채워진 도형</span><span class="sxs-lookup"><span data-stu-id="abb29-115">Brushes and Filled Shapes in GDI+</span></span>](brushes-and-filled-shapes-in-gdi.md)
