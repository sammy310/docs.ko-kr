---
title: '방법: Windows Forms에서 깜빡임을 줄이기 위한 픽셀 복사'
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
ms.openlocfilehash: e3d1c2b681e98dc7c45467683924dd4022eb377e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937750"
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a><span data-ttu-id="0f91e-102">방법: Windows Forms에서 깜빡임을 줄이기 위한 픽셀 복사</span><span class="sxs-lookup"><span data-stu-id="0f91e-102">How to: Copy Pixels for Reducing Flicker in Windows Forms</span></span>
<span data-ttu-id="0f91e-103">간단한 그래픽에 애니메이션을 적용 하면 깜박임을 또는 원치 않는 다른 시각 효과 사용자 경우가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f91e-103">When you animate a simple graphic, users can sometimes encounter flicker or other undesirable visual effects.</span></span> <span data-ttu-id="0f91e-104">이 문제를 제한 하는 한 가지 방법은 그림에서 "bitblt" 프로세스를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0f91e-104">One way to limit this problem is to use a "bitblt" process on the graphic.</span></span> <span data-ttu-id="0f91e-105">Bitblt "비트 블록 전송" 색 데이터의 원본 영역을 픽셀에서 픽셀의 대상 사각형에입니다.</span><span class="sxs-lookup"><span data-stu-id="0f91e-105">Bitblt is the "bit-block transfer" of the color data from an origin rectangle of pixels to a destination rectangle of pixels.</span></span>  
  
 <span data-ttu-id="0f91e-106">Windows Forms를 사용 하 여 bitblt를 사용 하 여 수행 됩니다 합니다 <xref:System.Drawing.Graphics.CopyFromScreen%2A> 메서드는 <xref:System.Drawing.Graphics> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="0f91e-106">With Windows Forms, bitblt is accomplished using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="0f91e-107">메서드의 매개 변수를 원본 및 대상 (점), 복사할 영역의 크기에 새 셰이프를 그리는 데 graphics 개체를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f91e-107">In the parameters of the method, you specify the source and destination (as points), the size of the area to be copied, and the graphics object used to draw the new shape.</span></span>  
  
 <span data-ttu-id="0f91e-108">아래 예제에서는 양식에서 도형이 그려집니다 해당 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="0f91e-108">In the example below, a shape is drawn on the form in its <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="0f91e-109">그런 다음, <xref:System.Drawing.Graphics.CopyFromScreen%2A> 메서드 모양을 복제를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f91e-109">Then, the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method is used to duplicate the shape.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f91e-110">폼의 설정 <xref:System.Windows.Forms.Control.DoubleBuffered%2A> 속성을 `true` 그래픽 기반 코드에 게는 <xref:System.Windows.Forms.Control.Paint> 이중 버퍼링 된 이벤트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="0f91e-110">Setting the form's <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true` will make graphics-based code in the <xref:System.Windows.Forms.Control.Paint> event be double-buffered.</span></span> <span data-ttu-id="0f91e-111">아래 코드를 사용 하는 경우 모든 식별할 수 있는 성능 향상 수 있게 됩니다을 하는 동안 더 복잡 한 그래픽 조작이 코드로 작업할 때 염두 할 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="0f91e-111">While this will not have any discernible performance gains when using the code below, it is something to keep in mind when working with more complex graphics-manipulation code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f91e-112">예제</span><span class="sxs-lookup"><span data-stu-id="0f91e-112">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="0f91e-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="0f91e-113">Compiling the Code</span></span>  
 <span data-ttu-id="0f91e-114">위의 코드는 폼의 실행은 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기 그래픽 양식을 다시 그려질 때 유지 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f91e-114">The code above is run in the form's <xref:System.Windows.Forms.Control.Paint> event handler so that the graphics persist when the form is redrawn.</span></span> <span data-ttu-id="0f91e-115">이와 같이 그래픽 관련 메서드를 호출 하지 마십시오는 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기를 그린된 콘텐츠 비활성 폼 크기를 조정 하거나 다른 폼에 의해 가려지지 경우 때문에 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f91e-115">As such, do not call graphics-related methods in the <xref:System.Windows.Forms.Form.Load> event handler, because the drawn content will not be redrawn if the form is resized or obscured by another form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f91e-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="0f91e-116">See also</span></span>

- <xref:System.Drawing.CopyPixelOperation>
- <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>
- [<span data-ttu-id="0f91e-117">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="0f91e-117">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="0f91e-118">펜을 사용하여 선과 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="0f91e-118">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
