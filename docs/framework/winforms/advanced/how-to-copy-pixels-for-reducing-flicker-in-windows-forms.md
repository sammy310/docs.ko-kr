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
ms.openlocfilehash: a25295532d7123d92bcacc6828d3e8cfcc839d6e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182582"
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a>방법: Windows Forms에서 깜빡임을 줄이기 위한 픽셀 복사
간단한 그래픽에 애니메이션을 만들 면 깜박이거나 다른 바람직하지 않은 시각 효과가 발생할 수 있습니다. 이 문제를 제한하는 한 가지 방법은 그래픽에서 "bitblt" 프로세스를 사용하는 것입니다. Bitblt는 픽셀의 원점에서 픽셀의 대상 사각형으로 색상 데이터의 "비트 블록 전송"입니다.  
  
 Windows Forms를 사용하면 bitblt는 <xref:System.Drawing.Graphics.CopyFromScreen%2A> 클래스의 <xref:System.Drawing.Graphics> 메서드를 사용하여 수행됩니다. 메서드의 매개 변수에서 소스 및 대상(점으로), 복사할 영역의 크기 및 새 셰이프를 그리는 데 사용되는 그래픽 개체를 지정합니다.  
  
 아래 예제에서는 이벤트 처리기의 양식에 <xref:System.Windows.Forms.Control.Paint> 셰이프가 그려집니다. 그런 다음 <xref:System.Drawing.Graphics.CopyFromScreen%2A> 메서드를 사용하여 셰이프를 복제합니다.  
  
> [!NOTE]
> 폼의 <xref:System.Windows.Forms.Control.DoubleBuffered%2A> 속성을 설정하면 `true` <xref:System.Windows.Forms.Control.Paint> 이벤트의 그래픽 기반 코드가 이중 버퍼링됩니다. 아래 코드를 사용할 때 눈에 띄는 성능 향상은 없지만 보다 복잡한 그래픽 조작 코드로 작업할 때 염두에 두어야 할 사항입니다.  
  
## <a name="example"></a>예제  
  
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
  
## <a name="compiling-the-code"></a>코드 컴파일  
 위의 코드는 양식의 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기에서 실행되므로 양식을 다시 그릴 때 그래픽이 유지됩니다. 따라서 양식의 크기가 조정되거나 <xref:System.Windows.Forms.Form.Load> 다른 양식에 의해 가려진 경우 그려진 콘텐츠가 다시 그려지지 않으므로 이벤트 처리기에서 그래픽 관련 메서드를 호출하지 마십시오.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Drawing.CopyPixelOperation>
- <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>
- [Windows Forms의 그래픽 및 그리기](graphics-and-drawing-in-windows-forms.md)
- [펜을 사용하여 선과 도형 그리기](using-a-pen-to-draw-lines-and-shapes.md)
