---
title: '방법: 윤곽선이 있는 도형 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.DrawEllipse
helpviewer_keywords:
- ellipses [Windows Forms], drawing
- circles [Windows Forms], drawing
- drawing [Windows Forms], shapes
- circular shapes
- forms [Windows Forms], drawing circular shapes
- circles
- outlined shapes [Windows Forms], examples
- outlined shapes [Windows Forms], drawing
- drawing [Windows Forms], circular shapes
- shapes [Windows Forms], drawing
ms.assetid: f4f9214c-607e-407d-8cdd-6549f0278451
ms.openlocfilehash: 019bbc19cc4b26c42f8539eccd93ec4ff87fab12
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59192208"
---
# <a name="how-to-draw-an-outlined-shape"></a><span data-ttu-id="c8e29-102">방법: 윤곽선이 있는 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="c8e29-102">How to: Draw an Outlined Shape</span></span>
<span data-ttu-id="c8e29-103">이 예제에서는 폼에 윤곽선이 있는 타원 및 사각형을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="c8e29-103">This example draws outlined ellipses and rectangles on a form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8e29-104">예제</span><span class="sxs-lookup"><span data-stu-id="c8e29-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#6](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#6)]
 [!code-csharp[System.Drawing.ConceptualHowTos#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#6)]
 [!code-vb[System.Drawing.ConceptualHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#6)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c8e29-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="c8e29-105">Compiling the Code</span></span>  
 <span data-ttu-id="c8e29-106">이 메서드를 호출할 수 없습니다는 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="c8e29-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="c8e29-107">그려지는 콘텐츠 비활성 폼 크기가 조정 되거나 다른 양식으로 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="c8e29-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="c8e29-108">재정의 해야 하는 자동으로 다시 그리기 콘텐츠를 확인 하는 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="c8e29-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="c8e29-109">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="c8e29-109">Robust Programming</span></span>  
 <span data-ttu-id="c8e29-110">항상 호출 해야 <xref:System.IDisposable.Dispose%2A> 와 같은 시스템 리소스를 사용 하는 모든 개체에 <xref:System.Drawing.Pen> 고 <xref:System.Drawing.Graphics> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c8e29-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Pen> and <xref:System.Drawing.Graphics> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8e29-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="c8e29-111">See also</span></span>

- <xref:System.Drawing.Graphics.DrawEllipse%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Drawing.Graphics.DrawRectangle%2A>
- [<span data-ttu-id="c8e29-112">그래픽 프로그래밍 시작</span><span class="sxs-lookup"><span data-stu-id="c8e29-112">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="c8e29-113">펜을 사용하여 선과 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="c8e29-113">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="c8e29-114">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="c8e29-114">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
