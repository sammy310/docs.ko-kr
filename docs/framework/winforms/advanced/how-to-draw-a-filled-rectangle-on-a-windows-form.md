---
title: '방법: Windows Form에서 채워진 사각형 그리기'
description: Windows Form에서 프로그래밍 방식으로 채워진 사각형을 그리는 방법에 대해 알아봅니다. 또한 코드를 컴파일하는 방법에 대해 알아봅니다.
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
ms.openlocfilehash: 0ad8ec97000e29b2194a9eda713aa43d5557b44c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621641"
---
# <a name="how-to-draw-a-filled-rectangle-on-a-windows-form"></a><span data-ttu-id="3bf39-104">방법: Windows Form에서 채워진 사각형 그리기</span><span class="sxs-lookup"><span data-stu-id="3bf39-104">How to: Draw a Filled Rectangle on a Windows Form</span></span>
<span data-ttu-id="3bf39-105">이 예제에서는 폼에 채워진 사각형을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="3bf39-105">This example draws a filled rectangle on a form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3bf39-106">예제</span><span class="sxs-lookup"><span data-stu-id="3bf39-106">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#2](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#2)]
 [!code-csharp[System.Drawing.ConceptualHowTos#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#2)]
 [!code-vb[System.Drawing.ConceptualHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3bf39-107">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="3bf39-107">Compiling the Code</span></span>  
 <span data-ttu-id="3bf39-108">이벤트 처리기에서이 메서드를 호출할 수 없습니다 <xref:System.Windows.Forms.Form.Load> .</span><span class="sxs-lookup"><span data-stu-id="3bf39-108">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="3bf39-109">폼의 크기를 조정 하거나 다른 폼으로 가려져 있는 경우에는 그려지는 콘텐츠가 다시 그려지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3bf39-109">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="3bf39-110">콘텐츠를 자동으로 다시 그리게 하려면 메서드를 재정의 해야 합니다 <xref:System.Windows.Forms.Control.OnPaint%2A> .</span><span class="sxs-lookup"><span data-stu-id="3bf39-110">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="3bf39-111">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="3bf39-111">Robust Programming</span></span>  
 <span data-ttu-id="3bf39-112">항상 <xref:System.IDisposable.Dispose%2A> 및 개체와 같은 시스템 리소스를 사용 하는 개체에 대해를 호출 해야 합니다 <xref:System.Drawing.Brush> <xref:System.Drawing.Graphics> .</span><span class="sxs-lookup"><span data-stu-id="3bf39-112">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Brush> and <xref:System.Drawing.Graphics> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bf39-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3bf39-113">See also</span></span>

- <xref:System.Drawing.Graphics.FillRectangle%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="3bf39-114">그래픽 프로그래밍 시작</span><span class="sxs-lookup"><span data-stu-id="3bf39-114">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="3bf39-115">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="3bf39-115">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="3bf39-116">펜을 사용하여 선 및 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="3bf39-116">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="3bf39-117">GDI+의 브러시 및 채워진 도형</span><span class="sxs-lookup"><span data-stu-id="3bf39-117">Brushes and Filled Shapes in GDI+</span></span>](brushes-and-filled-shapes-in-gdi.md)
