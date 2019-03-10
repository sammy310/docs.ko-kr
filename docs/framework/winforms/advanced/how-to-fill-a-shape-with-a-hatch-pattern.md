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
ms.openlocfilehash: 885f0d22e83767bda3ef76c54f0857dd2a148344
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57719717"
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a><span data-ttu-id="141ed-102">방법: 빗살 무늬로 도형 채우기</span><span class="sxs-lookup"><span data-stu-id="141ed-102">How to: Fill a Shape with a Hatch Pattern</span></span>
<span data-ttu-id="141ed-103">빗살 무늬 두 색으로에서 이루어집니다: 배경색 및 배경 위에 패턴을 형성 하는 줄에 대 한 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="141ed-103">A hatch pattern is made from two colors: one for the background and one for the lines that form the pattern over the background.</span></span> <span data-ttu-id="141ed-104">빗살 무늬를 사용 하 여 닫힌된 도형 채우기를 사용 하 여를 <xref:System.Drawing.Drawing2D.HatchBrush> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="141ed-104">To fill a closed shape with a hatch pattern, use a <xref:System.Drawing.Drawing2D.HatchBrush> object.</span></span> <span data-ttu-id="141ed-105">다음 예제에서는 빗살 무늬를 사용 하 여 타원을 채우는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="141ed-105">The following example demonstrates how to fill an ellipse with a hatch pattern:</span></span>  
  
## <a name="example"></a><span data-ttu-id="141ed-106">예제</span><span class="sxs-lookup"><span data-stu-id="141ed-106">Example</span></span>  
 <span data-ttu-id="141ed-107"><xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> 생성자에는 세 가지 인수: 해치 스타일, 빗살 무늬 선의 색 및 배경색입니다.</span><span class="sxs-lookup"><span data-stu-id="141ed-107">The <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> constructor takes three arguments: the hatch style, the color of the hatch line, and the color of the background.</span></span> <span data-ttu-id="141ed-108">빗살 무늬 스타일 인수로 사용할 수 있는 모든 값은 <xref:System.Drawing.Drawing2D.HatchStyle> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="141ed-108">The hatch style argument can be any value from the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration.</span></span> <span data-ttu-id="141ed-109">에 50 개 이상의 요소가 <xref:System.Drawing.Drawing2D.HatchStyle> 열거형; 몇 가지 요소는 다음 목록에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="141ed-109">There are more than fifty elements in the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration; a few of those elements are shown in the following list:</span></span>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 <span data-ttu-id="141ed-110">다음 그림은 채워진된 타원을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="141ed-110">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="141ed-111">![패턴을 해치](./media/hatch1.png "hatch1")</span><span class="sxs-lookup"><span data-stu-id="141ed-111">![Hatch Pattern](./media/hatch1.png "hatch1")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="141ed-112">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="141ed-112">Compiling the Code</span></span>  
 <span data-ttu-id="141ed-113">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> 이벤트 처리기의 매개 변수인 `e`<xref:System.Windows.Forms.Control.Paint>가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="141ed-113">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="141ed-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="141ed-114">See also</span></span>
- [<span data-ttu-id="141ed-115">브러시를 사용하여 도형 채우기</span><span class="sxs-lookup"><span data-stu-id="141ed-115">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
