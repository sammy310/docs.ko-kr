---
title: '방법: Windows Form에서 세로 텍스트 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- StringFormat.FormatFlags
- Graphics.DrawString
helpviewer_keywords:
- text [Windows Forms], drawing vertical
- strings [Windows Forms], drawing vertical
- text [Windows Forms], drawing
- text [Windows Forms], vertical text
ms.assetid: 717a6131-00f6-4373-b574-9894e8317799
ms.openlocfilehash: eb00928205a318b068d49ea3f6f71c398f77bbcd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59072495"
---
# <a name="how-to-draw-vertical-text-on-a-windows-form"></a><span data-ttu-id="da3ea-102">방법: Windows Form에서 세로 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="da3ea-102">How to: Draw Vertical Text on a Windows Form</span></span>
<span data-ttu-id="da3ea-103">다음 코드 예제에 사용 하 여 폼의 세로 텍스트를 그리는 방법을 보여 줍니다 합니다 <xref:System.Drawing.Graphics.DrawString%2A> 메서드의 <xref:System.Drawing.Graphics>합니다.</span><span class="sxs-lookup"><span data-stu-id="da3ea-103">The following code example shows how to draw vertical text on a form by using the <xref:System.Drawing.Graphics.DrawString%2A> method of <xref:System.Drawing.Graphics>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da3ea-104">예제</span><span class="sxs-lookup"><span data-stu-id="da3ea-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#8](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#8)]
 [!code-csharp[System.Drawing.ConceptualHowTos#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#8)]
 [!code-vb[System.Drawing.ConceptualHowTos#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#8)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="da3ea-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="da3ea-105">Compiling the Code</span></span>  
 <span data-ttu-id="da3ea-106">이 메서드를 호출할 수 없습니다는 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="da3ea-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="da3ea-107">그려지는 콘텐츠 비활성 폼 크기가 조정 되거나 다른 양식으로 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="da3ea-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="da3ea-108">재정의 해야 하는 자동으로 다시 그리기 콘텐츠를 확인 하는 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="da3ea-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="da3ea-109">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="da3ea-109">Robust Programming</span></span>  
 <span data-ttu-id="da3ea-110">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="da3ea-110">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="da3ea-111">Arial 글꼴이 설치 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="da3ea-111">The Arial font is not installed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da3ea-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="da3ea-112">See also</span></span>

- <xref:System.Drawing.Graphics.DrawString%2A>
- <xref:System.Drawing.StringFormat.FormatFlags%2A>
- <xref:System.Drawing.StringFormatFlags>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="da3ea-113">그래픽 프로그래밍 시작</span><span class="sxs-lookup"><span data-stu-id="da3ea-113">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="da3ea-114">글꼴 및 텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="da3ea-114">Using Fonts and Text</span></span>](using-fonts-and-text.md)
