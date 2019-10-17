---
title: '방법: 빗살 무늬로 도형 채우기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- patterns [Windows Forms], adding to shapes
- shapes [Windows Forms], filling with patterns
- brushes [Windows Forms], using hatch brushes
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
ms.openlocfilehash: b80708f0ce722b1809fe49190639231e7e4c8329
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320067"
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a><span data-ttu-id="18494-102">방법: 빗살 무늬로 도형 채우기</span><span class="sxs-lookup"><span data-stu-id="18494-102">How to: Fill a Shape with a Hatch Pattern</span></span>
<span data-ttu-id="18494-103">빗살 무늬 패턴은 배경에 대해 하나, 배경으로 패턴을 형성 하는 선에 대 한 두 가지 색으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="18494-103">A hatch pattern is made from two colors: one for the background and one for the lines that form the pattern over the background.</span></span> <span data-ttu-id="18494-104">폐쇄형 셰이프를 빗살 무늬 패턴으로 채우려면 <xref:System.Drawing.Drawing2D.HatchBrush> 개체를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="18494-104">To fill a closed shape with a hatch pattern, use a <xref:System.Drawing.Drawing2D.HatchBrush> object.</span></span> <span data-ttu-id="18494-105">다음 예제에서는 빗살 무늬 패턴으로 타원을 채우는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="18494-105">The following example demonstrates how to fill an ellipse with a hatch pattern:</span></span>  
  
## <a name="example"></a><span data-ttu-id="18494-106">예제</span><span class="sxs-lookup"><span data-stu-id="18494-106">Example</span></span>  
 <span data-ttu-id="18494-107">@No__t_0 생성자는 빗살 무늬 스타일, 해치 선 색 및 배경의 색의 세 가지 인수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="18494-107">The <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> constructor takes three arguments: the hatch style, the color of the hatch line, and the color of the background.</span></span> <span data-ttu-id="18494-108">빗살 무늬 스타일 인수는 <xref:System.Drawing.Drawing2D.HatchStyle> 열거형의 모든 값일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18494-108">The hatch style argument can be any value from the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration.</span></span> <span data-ttu-id="18494-109">@No__t_0 열거형에는 요소가 50 개 이상 있습니다. 이러한 요소 중 몇 가지는 다음 목록에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18494-109">There are more than fifty elements in the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration; a few of those elements are shown in the following list:</span></span>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 <span data-ttu-id="18494-110">다음 그림에서는 채워진 타원을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="18494-110">The following illustration shows the filled ellipse.</span></span>  
  
  <span data-ttu-id="18494-111">![해치 패턴으로 채워진 타원이 표시 되는 모양에 대 한 스크린샷](./media/how-to-fill-a-shape-with-a-hatch-pattern/ellipse-filled-hatch.png "hatch1")</span><span class="sxs-lookup"><span data-stu-id="18494-111">![Screenshot of what an ellipse filled with a hatch pattern looks like.](./media/how-to-fill-a-shape-with-a-hatch-pattern/ellipse-filled-hatch.png "hatch1")</span></span>
  
 [!code-csharp[System.Drawing.UsingABrush#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="18494-112">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="18494-112">Compiling the Code</span></span>  
 <span data-ttu-id="18494-113">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> 이벤트 처리기의 매개 변수인 `e`<xref:System.Windows.Forms.Control.Paint>가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="18494-113">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18494-114">참조</span><span class="sxs-lookup"><span data-stu-id="18494-114">See also</span></span>

- [<span data-ttu-id="18494-115">브러시를 사용하여 도형 채우기</span><span class="sxs-lookup"><span data-stu-id="18494-115">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
