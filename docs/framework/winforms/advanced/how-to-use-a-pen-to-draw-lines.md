---
title: '방법: 펜을 사용하여 선 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
ms.assetid: 0828c331-a438-4bdd-a4d6-3ef1e59e8795
ms.openlocfilehash: 263c0fbda377e64753cd2d607f633117b4b44253
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65593154"
---
# <a name="how-to-use-a-pen-to-draw-lines"></a><span data-ttu-id="49c25-102">방법: 펜을 사용하여 선 그리기</span><span class="sxs-lookup"><span data-stu-id="49c25-102">How to: Use a Pen to Draw Lines</span></span>
<span data-ttu-id="49c25-103">필요한 줄을 그리려면를 <xref:System.Drawing.Graphics> 개체 및 <xref:System.Drawing.Pen> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="49c25-103">To draw lines, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="49c25-104"><xref:System.Drawing.Graphics> 개체를 제공 합니다 <xref:System.Drawing.Graphics.DrawLine%2A> 메서드 및 <xref:System.Drawing.Pen> 개체 저장 되는 선의 색 및 두께 같은 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="49c25-104">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawLine%2A> method, and the <xref:System.Drawing.Pen> object stores features of the line, such as color and width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49c25-105">예제</span><span class="sxs-lookup"><span data-stu-id="49c25-105">Example</span></span>  
 <span data-ttu-id="49c25-106">다음 예제에서 선을 그립니다 (20, 10)에 (300, 100).</span><span class="sxs-lookup"><span data-stu-id="49c25-106">The following example draws a line from (20, 10) to (300, 100).</span></span> <span data-ttu-id="49c25-107">첫 번째 문에서 사용 하는 <xref:System.Drawing.Pen.%23ctor%2A> black 펜을을 만들려면 클래스 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="49c25-107">The first statement uses the <xref:System.Drawing.Pen.%23ctor%2A> class constructor to create a black pen.</span></span> <span data-ttu-id="49c25-108">에 전달 되는 하나의 인수를 <xref:System.Drawing.Pen.%23ctor%2A> 생성자가을 <xref:System.Drawing.Color> 사용 하 여 만든 개체는 <xref:System.Drawing.Color.FromArgb%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="49c25-108">The one argument passed to the <xref:System.Drawing.Pen.%23ctor%2A> constructor is a <xref:System.Drawing.Color> object created with the <xref:System.Drawing.Color.FromArgb%2A> method.</span></span> <span data-ttu-id="49c25-109">만드는 데 사용 하는 값을 <xref:System.Drawing.Color> 개체-(255, 0, 0, 0)-색의 알파, 빨강, 녹색 및 파랑 구성 요소에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="49c25-109">The values used to create the <xref:System.Drawing.Color> object — (255, 0, 0, 0) — correspond to the alpha, red, green, and blue components of the color.</span></span> <span data-ttu-id="49c25-110">이러한 값을 불투명 한 검은색 펜을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="49c25-110">These values define an opaque black pen.</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="49c25-111">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="49c25-111">Compiling the Code</span></span>  
 <span data-ttu-id="49c25-112">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="49c25-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49c25-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="49c25-113">See also</span></span>

- <xref:System.Drawing.Pen>
- [<span data-ttu-id="49c25-114">펜을 사용하여 선과 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="49c25-114">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="49c25-115">GDI+의 펜, 선 및 사각형</span><span class="sxs-lookup"><span data-stu-id="49c25-115">Pens, Lines, and Rectangles in GDI+</span></span>](pens-lines-and-rectangles-in-gdi.md)
