---
title: '방법: 선 조인'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- miter line join style
- bevel line join style
- line join
- drawing [Windows Forms], joining lines
- GraphicsPath object
- round line join style
- lines [Windows Forms], joining
- graphics [Windows Forms], joining lines
ms.assetid: 9fc480c2-3c75-4fd1-8ab5-296a99e820e2
ms.openlocfilehash: 445d7f12f57137c6b06a074eeaf0574eb027a723
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59174917"
---
# <a name="how-to-join-lines"></a><span data-ttu-id="181b0-102">방법: 선 조인</span><span class="sxs-lookup"><span data-stu-id="181b0-102">How to: Join Lines</span></span>
<span data-ttu-id="181b0-103">선 조인에 끝 부분이 만나거나 겹치는 두 줄으로 구성 되는 일반적인 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="181b0-103">A line join is the common area that is formed by two lines whose ends meet or overlap.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="181b0-104">세 선 조인 스타일을 제공 합니다: 마이터, 빗면 및 반올림 합니다.</span><span class="sxs-lookup"><span data-stu-id="181b0-104">provides three line join styles: miter, bevel, and round.</span></span> <span data-ttu-id="181b0-105">선 조인 스타일의 속성인는 <xref:System.Drawing.Pen> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="181b0-105">Line join style is a property of the <xref:System.Drawing.Pen> class.</span></span> <span data-ttu-id="181b0-106">선 조인 스타일을 지정 하는 경우는 <xref:System.Drawing.Pen> 개체에 연결 된 모든 줄에 조인 스타일을 적용할 <xref:System.Drawing.Drawing2D.GraphicsPath> 개체는 펜을 사용 하 여 그려집니다.</span><span class="sxs-lookup"><span data-stu-id="181b0-106">When you specify a line join style for a <xref:System.Drawing.Pen> object, that join style will be applied to all the connected lines in any <xref:System.Drawing.Drawing2D.GraphicsPath> object drawn using that pen.</span></span>  
  
 <span data-ttu-id="181b0-107">다음 그림에서는 빗면된 선 조인 예제 결과 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="181b0-107">The following illustration shows the results of the beveled line join example.</span></span>  
  
 ![조인된 선을 보여 주는 그림입니다.](./media/how-to-join-lines/joined-beveled-lines.gif)  
  
## <a name="example"></a><span data-ttu-id="181b0-109">예제</span><span class="sxs-lookup"><span data-stu-id="181b0-109">Example</span></span>  
 <span data-ttu-id="181b0-110">사용 하 여 선 조인 스타일을 지정할 수 있습니다는 <xref:System.Drawing.Pen.LineJoin%2A> 의 속성을 <xref:System.Drawing.Pen> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="181b0-110">You can specify the line join style by using the <xref:System.Drawing.Pen.LineJoin%2A> property of the <xref:System.Drawing.Pen> class.</span></span> <span data-ttu-id="181b0-111">이 예제에서는 빗면된 선 조인을 가로 줄 사이의 세로 줄을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="181b0-111">The example demonstrates a beveled line join between a horizontal line and a vertical line.</span></span> <span data-ttu-id="181b0-112">다음 코드에서 값 <xref:System.Drawing.Drawing2D.LineJoin.Bevel> 에 할당 합니다 <xref:System.Drawing.Pen.LineJoin%2A> 속성이 멤버인은 <xref:System.Drawing.Drawing2D.LineJoin> 열거형.</span><span class="sxs-lookup"><span data-stu-id="181b0-112">In the following code, the value <xref:System.Drawing.Drawing2D.LineJoin.Bevel> assigned to the <xref:System.Drawing.Pen.LineJoin%2A> property is a member of the <xref:System.Drawing.Drawing2D.LineJoin> enumeration.</span></span> <span data-ttu-id="181b0-113">다른 멤버를 <xref:System.Drawing.Drawing2D.LineJoin> 열거 <xref:System.Drawing.Drawing2D.LineJoin.Miter> 고 <xref:System.Drawing.Drawing2D.LineJoin.Round>입니다.</span><span class="sxs-lookup"><span data-stu-id="181b0-113">The other members of the <xref:System.Drawing.Drawing2D.LineJoin> enumeration are <xref:System.Drawing.Drawing2D.LineJoin.Miter> and <xref:System.Drawing.Drawing2D.LineJoin.Round>.</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingAPen#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="181b0-114">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="181b0-114">Compiling the Code</span></span>  
 <span data-ttu-id="181b0-115">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="181b0-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="181b0-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="181b0-116">See also</span></span>

- [<span data-ttu-id="181b0-117">펜을 사용하여 선과 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="181b0-117">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
