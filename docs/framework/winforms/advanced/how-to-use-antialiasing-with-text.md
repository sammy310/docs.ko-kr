---
title: '방법: 텍스트에 앤티 앨리어싱 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [Windows Forms], smoothing drawn
- antialiasing [Windows Forms], using with text
- text [Windows Forms], smoothing
- text [Windows Forms], antialiasing
- strings [Windows Forms], antialiasing when drawing
ms.assetid: 48fc34f3-f236-4b01-a0cb-f0752e6d22ae
ms.openlocfilehash: 632ed329173d134495a424b34ca7c71e402607bf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182481"
---
# <a name="how-to-use-antialiasing-with-text"></a><span data-ttu-id="c7ade-102">방법: 텍스트에 앤티 앨리어싱 사용</span><span class="sxs-lookup"><span data-stu-id="c7ade-102">How to: Use Antialiasing with Text</span></span>
<span data-ttu-id="c7ade-103">*안티앨리어싱은* 그려진 그래픽과 텍스트의 들쭉날쭉한 가장자리를 스무딩하여 모양이나 가독성을 향상시키는 것을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ade-103">*Antialiasing* refers to the smoothing of jagged edges of drawn graphics and text to improve their appearance or readability.</span></span> <span data-ttu-id="c7ade-104">관리되는 GDI+ 클래스를 사용하면 고품질의 안티 앨리어시드 텍스트와 낮은 품질의 텍스트를 렌더링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7ade-104">With the managed GDI+ classes, you can render high quality antialiased text, as well as lower quality text.</span></span> <span data-ttu-id="c7ade-105">일반적으로 고품질 렌더링은 낮은 품질의 렌더링보다 처리 시간이 더 오래 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="c7ade-105">Typically, higher quality rendering takes more processing time than lower quality rendering.</span></span> <span data-ttu-id="c7ade-106">텍스트 품질 수준을 설정하려면 <xref:System.Drawing.Graphics.TextRenderingHint%2A> <xref:System.Drawing.Text.TextRenderingHint> 열거형 <xref:System.Drawing.Graphics> 요소 중 하나에 의한 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ade-106">To set the text quality level, set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property of a <xref:System.Drawing.Graphics> to one of the elements of the <xref:System.Drawing.Text.TextRenderingHint> enumeration</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7ade-107">예제</span><span class="sxs-lookup"><span data-stu-id="c7ade-107">Example</span></span>  
 <span data-ttu-id="c7ade-108">다음 코드 예제는 두 가지 품질 설정으로 텍스트를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="c7ade-108">The following code example draws text with two different quality settings.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  

 <span data-ttu-id="c7ade-109">다음 그림에서는 예제 코드의 출력을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7ade-109">The following illustration shows the output of the example code:</span></span>  
  
 ![두 가지 품질 설정이 다른 텍스트를 표시하는 스크린샷입니다.](./media/how-to-use-antialiasing-with-text/antialiasing-text-quality-settings.png)  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c7ade-111">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="c7ade-111">Compiling the Code</span></span>  
 <span data-ttu-id="c7ade-112">앞의 코드 예제는 Windows Forms에서 사용하도록 설계되었으며 의 매개 <xref:System.Windows.Forms.PaintEventHandler>변수인 이 요구사항입니다. <xref:System.Windows.Forms.PaintEventArgs> `e`</span><span class="sxs-lookup"><span data-stu-id="c7ade-112">The preceding code example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7ade-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7ade-113">See also</span></span>

- [<span data-ttu-id="c7ade-114">글꼴 및 텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="c7ade-114">Using Fonts and Text</span></span>](using-fonts-and-text.md)
