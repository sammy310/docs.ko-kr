---
title: '방법: 사용자 지정 파선 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], custom
- lines [Windows Forms], drawing
- lines [Windows Forms], dashed
ms.assetid: cd0ed96a-cce4-47b9-b58a-3bae2e3d1bee
ms.openlocfilehash: 830fa45fc88c35b8aa5f047e065ae1efc161f581
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718946"
---
# <a name="how-to-draw-a-custom-dashed-line"></a><span data-ttu-id="37cfc-102">방법: 사용자 지정 파선 그리기</span><span class="sxs-lookup"><span data-stu-id="37cfc-102">How to: Draw a Custom Dashed Line</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="37cfc-103">에 나열 된 몇 가지 대시 스타일을 제공 합니다 <xref:System.Drawing.Drawing2D.DashStyle> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="37cfc-103">provides several dash styles that are listed in the <xref:System.Drawing.Drawing2D.DashStyle> enumeration.</span></span> <span data-ttu-id="37cfc-104">이러한 표준 대시 스타일 사용자 요구에 적합 하지 않는 경우 사용자 지정 대시 패턴을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfc-104">If those standard dash styles do not suit your needs, you can create a custom dash pattern.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37cfc-105">예제</span><span class="sxs-lookup"><span data-stu-id="37cfc-105">Example</span></span>  
 <span data-ttu-id="37cfc-106">사용자 지정 파선을 그리려면 대시와 공백의 길이 배열에 배치 하 고 값으로 배열을 할당 합니다 <xref:System.Drawing.Pen.DashPattern%2A> 의 속성을 <xref:System.Drawing.Pen> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="37cfc-106">To draw a custom dashed line, put the lengths of the dashes and spaces in an array and assign the array as the value of the <xref:System.Drawing.Pen.DashPattern%2A> property of a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="37cfc-107">다음 예제에서는 배열을 기반으로 사용자 지정 파선 그립니다 `{5, 2, 15, 4}`합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfc-107">The following example draws a custom dashed line based on the array `{5, 2, 15, 4}`.</span></span> <span data-ttu-id="37cfc-108">배열 요소의 5의 펜 너비를 곱하면 경우 `{25, 10, 75, 20}`합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfc-108">If you multiply the elements of the array by the pen width of 5, you get `{25, 10, 75, 20}`.</span></span> <span data-ttu-id="37cfc-109">25 사이의 75는 길이가 표시 된 대시 대체 하 고 길이가 10과 20 사이의 공간을 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfc-109">The displayed dashes alternate in length between 25 and 75, and the spaces alternate in length between 10 and 20.</span></span>  
  
 <span data-ttu-id="37cfc-110">다음 그림에서는 결과 파선을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="37cfc-110">The following illustration shows the resulting dashed line.</span></span> <span data-ttu-id="37cfc-111">최종 대시 줄 끝날 수 있도록 25 단위 보다 짧을 수에 (405, 5).</span><span class="sxs-lookup"><span data-stu-id="37cfc-111">Note that the final dash has to be shorter than 25 units so that the line can end at (405, 5).</span></span>  
  
 <span data-ttu-id="37cfc-112">![펜](./media/pens6.gif "pens6")</span><span class="sxs-lookup"><span data-stu-id="37cfc-112">![Pens](./media/pens6.gif "pens6")</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.UsingAPen#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="37cfc-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="37cfc-113">Compiling the Code</span></span>  
 <span data-ttu-id="37cfc-114">Windows Form 만들기 및 폼의 처리 <xref:System.Windows.Forms.Control.Paint> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="37cfc-114">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="37cfc-115">앞의 코드를 붙여를 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="37cfc-115">Paste the preceding code into the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37cfc-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="37cfc-116">See also</span></span>
- [<span data-ttu-id="37cfc-117">펜을 사용하여 선과 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="37cfc-117">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
