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
ms.openlocfilehash: d03a9b79dc2c0ec61bbafe2ff09b5aba7fffc57b
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57719249"
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a>방법: Windows Forms에서 깜빡임을 줄이기 위한 픽셀 복사
간단한 그래픽에 애니메이션을 적용 하면 깜박임을 또는 원치 않는 다른 시각 효과 사용자 경우가 발생할 수 있습니다. 이 문제를 제한 하는 한 가지 방법은 그림에서 "bitblt" 프로세스를 사용 하는 것입니다. Bitblt "비트 블록 전송" 색 데이터의 원본 영역을 픽셀에서 픽셀의 대상 사각형에입니다.  
  
 Windows Forms를 사용 하 여 bitblt를 사용 하 여 수행 됩니다 합니다 <xref:System.Drawing.Graphics.CopyFromScreen%2A> 메서드는 <xref:System.Drawing.Graphics> 클래스입니다. 메서드의 매개 변수를 원본 및 대상 (점), 복사할 영역의 크기에 새 셰이프를 그리는 데 graphics 개체를 지정 합니다.  
  
 아래 예제에서는 양식에서 도형이 그려집니다 해당 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기입니다. 그런 다음, <xref:System.Drawing.Graphics.CopyFromScreen%2A> 메서드 모양을 복제를 사용 합니다.  
  
> [!NOTE]
>  폼의 설정 <xref:System.Windows.Forms.Control.DoubleBuffered%2A> 속성을 `true` 그래픽 기반 코드에 게는 <xref:System.Windows.Forms.Control.Paint> 이중 버퍼링 된 이벤트 수입니다. 아래 코드를 사용 하는 경우 모든 식별할 수 있는 성능 향상 수 있게 됩니다을 하는 동안 더 복잡 한 그래픽 조작이 코드로 작업할 때 염두 할 사항입니다.  
  
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
 위의 코드는 폼의 실행은 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기 그래픽 양식을 다시 그려질 때 유지 되도록 합니다. 이와 같이 그래픽 관련 메서드를 호출 하지 마십시오는 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기를 그린된 콘텐츠 비활성 폼 크기를 조정 하거나 다른 폼에 의해 가려지지 경우 때문에 합니다.  
  
## <a name="see-also"></a>참고자료
- <xref:System.Drawing.CopyPixelOperation>
- <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>
- [Windows Forms의 그래픽 및 그리기](graphics-and-drawing-in-windows-forms.md)
- [펜을 사용하여 선과 도형 그리기](using-a-pen-to-draw-lines-and-shapes.md)
