---
title: '방법: 깜박임을 줄이기 위한 픽셀 복사'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitblt
- graphics [Windows Forms], copying
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing flicker
- pixels [Windows Forms], copying
- flicker
- bit-block transfer
ms.assetid: 33b76910-13a3-4521-be98-5c097341ae3b
ms.openlocfilehash: 299041e7038d5bd5b9824d668b3f47d842030ac7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746477"
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a><span data-ttu-id="7ac41-102">방법: Windows Forms에서 깜빡임을 줄이기 위한 픽셀 복사</span><span class="sxs-lookup"><span data-stu-id="7ac41-102">How to: Copy Pixels for Reducing Flicker in Windows Forms</span></span>
<span data-ttu-id="7ac41-103">간단한 그래픽에 애니메이션 효과를 주는 경우 사용자는 때때로 깜박임 또는 기타 원치 않는 시각적 효과를 발생 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ac41-103">When you animate a simple graphic, users can sometimes encounter flicker or other undesirable visual effects.</span></span> <span data-ttu-id="7ac41-104">이 문제를 제한 하는 한 가지 방법은 그래픽에서 "bitblt" 프로세스를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7ac41-104">One way to limit this problem is to use a "bitblt" process on the graphic.</span></span> <span data-ttu-id="7ac41-105">Bitblt는 픽셀의 원본 사각형에서 대상 사각형 까지의 색 데이터의 "비트 블록 전송"입니다.</span><span class="sxs-lookup"><span data-stu-id="7ac41-105">Bitblt is the "bit-block transfer" of the color data from an origin rectangle of pixels to a destination rectangle of pixels.</span></span>  
  
 <span data-ttu-id="7ac41-106">Windows Forms에서 bitblt는 <xref:System.Drawing.Graphics> 클래스의 <xref:System.Drawing.Graphics.CopyFromScreen%2A> 메서드를 사용 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ac41-106">With Windows Forms, bitblt is accomplished using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="7ac41-107">메서드의 매개 변수에서 원본 및 대상 (포인트로), 복사할 영역의 크기 및 새 셰이프를 그리는 데 사용 되는 그래픽 개체를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac41-107">In the parameters of the method, you specify the source and destination (as points), the size of the area to be copied, and the graphics object used to draw the new shape.</span></span>  
  
 <span data-ttu-id="7ac41-108">아래 예제에서는 셰이프를 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 폼에 그립니다.</span><span class="sxs-lookup"><span data-stu-id="7ac41-108">In the example below, a shape is drawn on the form in its <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="7ac41-109">그런 다음 <xref:System.Drawing.Graphics.CopyFromScreen%2A> 메서드를 사용 하 여 셰이프를 복제 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac41-109">Then, the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method is used to duplicate the shape.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7ac41-110">폼의 <xref:System.Windows.Forms.Control.DoubleBuffered%2A> 속성을 `true`로 설정 하면 <xref:System.Windows.Forms.Control.Paint> 이벤트의 그래픽 기반 코드를 이중 버퍼링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ac41-110">Setting the form's <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true` will make graphics-based code in the <xref:System.Windows.Forms.Control.Paint> event be double-buffered.</span></span> <span data-ttu-id="7ac41-111">이는 아래 코드를 사용할 때 뚜렷한 성능이 향상 되지 않지만 보다 복잡 한 그래픽 조작 코드를 사용할 때 고려해 야 할 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7ac41-111">While this will not have any discernible performance gains when using the code below, it is something to keep in mind when working with more complex graphics-manipulation code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ac41-112">예제</span><span class="sxs-lookup"><span data-stu-id="7ac41-112">Example</span></span>  
  
```vb  
Private Sub Form1_Paint(ByVal sender As Object, ByVal e As _  
    System.Windows.Forms.PaintEventArgs) Handles MyBase.Paint  
    ' Draw a circle with a bar on top.  
        e.Graphics.FillEllipse(Brushes.DarkBlue, New Rectangle _  
             (10, 10, 60, 60))  
        e.Graphics.FillRectangle(Brushes.Khaki, New Rectangle _  
             (20, 30, 60, 10))  
    ' Copy the graphic to a new location.  
        e.Graphics.CopyFromScreen(New Point(10, 10), New Point _  
             (100, 100), New Size(70, 70))  
End Sub  
```  
  
```csharp  
private void Form1_Paint(System.Object sender,  
    System.Windows.Forms.PaintEventArgs e)  
        {  
        e.Graphics.FillEllipse(Brushes.DarkBlue, new  
            Rectangle(10,10,60,60));  
        e.Graphics.FillRectangle(Brushes.Khaki, new  
            Rectangle(20,30,60,10));  
        e.Graphics.CopyFromScreen(new Point(10, 10), new Point(100, 100),   
            new Size(70, 70));  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7ac41-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="7ac41-113">Compiling the Code</span></span>  
 <span data-ttu-id="7ac41-114">위의 코드는 폼의 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기에서 실행 되므로 폼을 다시 그릴 때 그래픽이 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ac41-114">The code above is run in the form's <xref:System.Windows.Forms.Control.Paint> event handler so that the graphics persist when the form is redrawn.</span></span> <span data-ttu-id="7ac41-115">따라서 폼의 크기를 조정 하거나 다른 폼으로 숨기는 경우에는 그려지는 콘텐츠가 다시 그려지지 않으므로 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기에서 그래픽 관련 메서드를 호출 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="7ac41-115">As such, do not call graphics-related methods in the <xref:System.Windows.Forms.Form.Load> event handler, because the drawn content will not be redrawn if the form is resized or obscured by another form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ac41-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7ac41-116">See also</span></span>

- <xref:System.Drawing.CopyPixelOperation>
- <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>
- [<span data-ttu-id="7ac41-117">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="7ac41-117">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="7ac41-118">펜을 사용하여 선과 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="7ac41-118">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
