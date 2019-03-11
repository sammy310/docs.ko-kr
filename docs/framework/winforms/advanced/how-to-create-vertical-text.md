---
title: '방법: 세로 텍스트 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing vertical
- Windows Forms, drawing vertical text
- strings [Windows Forms], drawing vertical
- vertical text [Windows Forms], drawing
ms.assetid: 50c69046-4188-47d9-b949-cc2610ffd337
ms.openlocfilehash: b2c26ab220fc9b796c8f8ababdef144847d52698
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710409"
---
# <a name="how-to-create-vertical-text"></a><span data-ttu-id="893d9-102">방법: 세로 텍스트 만들기</span><span class="sxs-lookup"><span data-stu-id="893d9-102">How to: Create Vertical Text</span></span>
<span data-ttu-id="893d9-103">사용할 수는 <xref:System.Drawing.StringFormat> 가로로 아닌 세로 텍스트를 그릴지를 지정 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="893d9-103">You can use a <xref:System.Drawing.StringFormat> object to specify that text be drawn vertically rather than horizontally.</span></span>  
  
## <a name="example"></a><span data-ttu-id="893d9-104">예제</span><span class="sxs-lookup"><span data-stu-id="893d9-104">Example</span></span>  
 <span data-ttu-id="893d9-105">다음 예제에서는 값을 할당 <xref:System.Drawing.StringFormatFlags.DirectionVertical> 에 <xref:System.Drawing.StringFormat.FormatFlags%2A> 의 속성을 <xref:System.Drawing.StringFormat> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="893d9-105">The following example assigns the value <xref:System.Drawing.StringFormatFlags.DirectionVertical> to the <xref:System.Drawing.StringFormat.FormatFlags%2A> property of a <xref:System.Drawing.StringFormat> object.</span></span> <span data-ttu-id="893d9-106">있는지 <xref:System.Drawing.StringFormat> 개체를 전달 하는 <xref:System.Drawing.Graphics.DrawString%2A> 메서드의 <xref:System.Drawing.Graphics> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="893d9-106">That <xref:System.Drawing.StringFormat> object is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="893d9-107">값 <xref:System.Drawing.StringFormatFlags.DirectionVertical> 멤버인는 <xref:System.Drawing.StringFormatFlags> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="893d9-107">The value <xref:System.Drawing.StringFormatFlags.DirectionVertical> is a member of the <xref:System.Drawing.StringFormatFlags> enumeration.</span></span>  
  
 <span data-ttu-id="893d9-108">다음 그림에서는 세로 텍스트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="893d9-108">The following illustration shows the vertical text.</span></span>  
  
 <span data-ttu-id="893d9-109">![글꼴 텍스트](./media/csfontstext5.png "csfontstext5")</span><span class="sxs-lookup"><span data-stu-id="893d9-109">![Fonts Text](./media/csfontstext5.png "csfontstext5")</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="893d9-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="893d9-110">Compiling the Code</span></span>  
  
-   <span data-ttu-id="893d9-111">앞의 예제는 Windows Forms에서 사용 하도록 설계 되었으며 필요 <xref:System.Windows.Forms.PaintEventArgs> `e` 의 매개 변수인 <xref:System.Windows.Forms.PaintEventHandler>합니다.</span><span class="sxs-lookup"><span data-stu-id="893d9-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e` , which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="893d9-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="893d9-112">See also</span></span>
- [<span data-ttu-id="893d9-113">방법: GDI 사용 하 여 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="893d9-113">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
