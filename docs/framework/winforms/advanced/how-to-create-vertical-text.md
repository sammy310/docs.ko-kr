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
ms.openlocfilehash: 86401342625f593945b801f7619ef9ca9681317c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182554"
---
# <a name="how-to-create-vertical-text"></a><span data-ttu-id="8f62a-102">방법: 세로 텍스트 만들기</span><span class="sxs-lookup"><span data-stu-id="8f62a-102">How to: Create Vertical Text</span></span>
<span data-ttu-id="8f62a-103">개체를 <xref:System.Drawing.StringFormat> 사용하여 텍스트를 가로가 아닌 세로로 그릴 수 있도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f62a-103">You can use a <xref:System.Drawing.StringFormat> object to specify that text be drawn vertically rather than horizontally.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f62a-104">예제</span><span class="sxs-lookup"><span data-stu-id="8f62a-104">Example</span></span>  
 <span data-ttu-id="8f62a-105">다음 예제는 개체의 <xref:System.Drawing.StringFormatFlags.DirectionVertical> 속성에 <xref:System.Drawing.StringFormat.FormatFlags%2A> 값을 <xref:System.Drawing.StringFormat> 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="8f62a-105">The following example assigns the value <xref:System.Drawing.StringFormatFlags.DirectionVertical> to the <xref:System.Drawing.StringFormat.FormatFlags%2A> property of a <xref:System.Drawing.StringFormat> object.</span></span> <span data-ttu-id="8f62a-106">해당 <xref:System.Drawing.StringFormat> 개체는 클래스의 <xref:System.Drawing.Graphics.DrawString%2A> 메서드에 <xref:System.Drawing.Graphics> 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f62a-106">That <xref:System.Drawing.StringFormat> object is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="8f62a-107">값은 <xref:System.Drawing.StringFormatFlags.DirectionVertical> 열거형의 <xref:System.Drawing.StringFormatFlags> 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="8f62a-107">The value <xref:System.Drawing.StringFormatFlags.DirectionVertical> is a member of the <xref:System.Drawing.StringFormatFlags> enumeration.</span></span>  
  
 <span data-ttu-id="8f62a-108">다음 그림에서는 세로 텍스트를 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f62a-108">The following illustration shows the vertical text:</span></span>
  
 ![세로 글꼴 텍스트를 표시하는 그래픽입니다.](./media/how-to-create-vertical-text/vertical-font-text-graphic.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8f62a-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="8f62a-110">Compiling the Code</span></span>  
  
- <span data-ttu-id="8f62a-111">앞의 예제는 Windows Forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> `e` 의 매개 변수인 이 <xref:System.Windows.Forms.PaintEventHandler>요구사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8f62a-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e` , which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f62a-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f62a-112">See also</span></span>

- [<span data-ttu-id="8f62a-113">방법: GDI를 사용하여 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="8f62a-113">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
