---
title: '방법: Windows Form에서 채워진 타원 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.FillEllipse
helpviewer_keywords:
- ellipses [Windows Forms], drawing
- circles [Windows Forms], drawing
- circular shapes
- drawing [Windows Forms], ellipses
- shapes [Windows Forms], drawing
- forms [Windows Forms], drawing ellipses
ms.assetid: 781db806-950d-4c5b-b022-493f7fd0c4a8
ms.openlocfilehash: 2e7be3f2c4c710bb24568dd2e70f6f5cc4706c63
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59171010"
---
# <a name="how-to-draw-a-filled-ellipse-on-a-windows-form"></a><span data-ttu-id="4f15d-102">방법: Windows Form에서 채워진 타원 그리기</span><span class="sxs-lookup"><span data-stu-id="4f15d-102">How to: Draw a Filled Ellipse on a Windows Form</span></span>
<span data-ttu-id="4f15d-103">이 예제에서는 폼에 채워진된 타원을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="4f15d-103">This example draws a filled ellipse on a form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f15d-104">예제</span><span class="sxs-lookup"><span data-stu-id="4f15d-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4f15d-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="4f15d-105">Compiling the Code</span></span>  
 <span data-ttu-id="4f15d-106">이 메서드를 호출할 수 없습니다는 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="4f15d-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="4f15d-107">그려지는 콘텐츠 비활성 폼 크기가 조정 되거나 다른 양식으로 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="4f15d-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="4f15d-108">재정의 해야 하는 자동으로 다시 그리기 콘텐츠를 확인 하는 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="4f15d-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4f15d-109">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="4f15d-109">Robust Programming</span></span>  
 <span data-ttu-id="4f15d-110">항상 호출 해야 <xref:System.IDisposable.Dispose%2A> 와 같은 시스템 리소스를 사용 하는 모든 개체에 <xref:System.Drawing.Brush> 고 <xref:System.Drawing.Graphics> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4f15d-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Brush> and <xref:System.Drawing.Graphics> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f15d-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="4f15d-111">See also</span></span>

- [<span data-ttu-id="4f15d-112">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="4f15d-112">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="4f15d-113">그래픽 프로그래밍 시작</span><span class="sxs-lookup"><span data-stu-id="4f15d-113">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="4f15d-114">선 및 채우기 알파 혼합</span><span class="sxs-lookup"><span data-stu-id="4f15d-114">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)
- [<span data-ttu-id="4f15d-115">브러시를 사용하여 도형 채우기</span><span class="sxs-lookup"><span data-stu-id="4f15d-115">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
