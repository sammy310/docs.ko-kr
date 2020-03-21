---
title: OnPaint 메서드 재정의
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Paint event [Windows Forms], handling in Windows Forms custom control
- OnPaint method [Windows Forms], overriding in Windows Forms custom controls
ms.assetid: e9ca2723-0107-4540-bb21-4f5ffb4a9906
ms.openlocfilehash: 863726a6264f01de9f00296b4a64b9fd1bb96765
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182038"
---
# <a name="overriding-the-onpaint-method"></a>OnPaint 메서드 재정의
.NET Framework에 정의된 모든 이벤트를 재정의하기 위한 기본 단계는 동일하며 다음 목록에 요약되어 있습니다.  
  
#### <a name="to-override-an-inherited-event"></a>상속된 이벤트를 재정의하려면  
  
1. 보호된 `On` *EventName* 메서드를 재정의합니다.  
  
2. 등록된 대리자가 이벤트를 수신할 수 있도록 `On`재정의된 *EventName* 메서드에서 기본 클래스의 EventName 메서드를 호출합니다. *EventName* `On`  
  
 모든 <xref:System.Windows.Forms.Control.Paint> Windows Forms 컨트롤에서 상속하는 <xref:System.Windows.Forms.Control.Paint> 이벤트를 재정의해야 하기 때문에 이 <xref:System.Windows.Forms.Control>이벤트는 여기에서 자세히 설명합니다. 기본 <xref:System.Windows.Forms.Control> 클래스는 파생 된 컨트롤을 그려야 하는 방법을 알 수 없으며 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드에서 페인팅 논리를 제공하지 않습니다. 단순히 등록된 이벤트 수신기에 <xref:System.Windows.Forms.Control.Paint> 이벤트를 디스패치하는 방법입니다. <xref:System.Windows.Forms.Control.OnPaint%2A> <xref:System.Windows.Forms.Control>  
  
 [방법: 간단한 Windows 양식 컨트롤 개발의](how-to-develop-a-simple-windows-forms-control.md)샘플을 통해 작업하는 경우 메서드를 <xref:System.Windows.Forms.Control.OnPaint%2A> 재정의하는 예제를 보았습니다. 다음 코드 조각은 해당 샘플에서 가져온 것입니다.  
  
```vb  
Public Class FirstControl  
   Inherits Control  
  
   Public Sub New()  
   End Sub  
  
   Protected Overrides Sub OnPaint(e As PaintEventArgs)  
      ' Call the OnPaint method of the base class.  
      MyBase.OnPaint(e)  
      ' Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, New SolidBrush(ForeColor), RectangleF.op_Implicit(ClientRectangle))  
   End Sub  
End Class
```  
  
```csharp  
public class FirstControl : Control {  
   public FirstControl() {}  
   protected override void OnPaint(PaintEventArgs e) {  
      // Call the OnPaint method of the base class.  
      base.OnPaint(e);  
      // Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, new SolidBrush(ForeColor), ClientRectangle);  
   }
}
```  
  
 클래스에는 <xref:System.Windows.Forms.PaintEventArgs> 이벤트에 대한 <xref:System.Windows.Forms.Control.Paint> 데이터가 포함되어 있습니다. 다음 코드와 같이 두 개의 속성이 있습니다.  
  
```vb  
Public Class PaintEventArgs  
   Inherits EventArgs  
   ...  
   Public ReadOnly Property ClipRectangle() As System.Drawing.Rectangle  
      ...  
   End Property  
  
   Public ReadOnly Property Graphics() As System.Drawing.Graphics  
      ...  
   End Property
   ...  
End Class  
```  
  
```csharp  
public class PaintEventArgs : EventArgs {  
...  
    public System.Drawing.Rectangle ClipRectangle {}  
    public System.Drawing.Graphics Graphics {}  
...  
}  
```  
  
 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>는 페인팅할 사각형이며 속성은 <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> 개체를 <xref:System.Drawing.Graphics> 참조합니다. 네임스페이스의 <xref:System.Drawing?displayProperty=nameWithType> 클래스는 새 Windows 그래픽 라이브러리인 GDI+의 기능에 대한 액세스를 제공하는 관리되는 클래스입니다. <xref:System.Drawing.Graphics> 개체에는 점, 문자열, 선, 호, 타원 및 기타 여러 모양을 그리는 메서드가 있습니다.  
  
 컨트롤은 시각적 표시를 <xref:System.Windows.Forms.Control.OnPaint%2A> 변경해야 할 때마다 메서드를 호출합니다. 이 메서드는 차례로 <xref:System.Windows.Forms.Control.Paint> 이벤트를 발생 시됩니다.  
  
## <a name="see-also"></a>참고 항목

- [Events](../../../standard/events/index.md)
- [Windows Forms 컨트롤 렌더링](rendering-a-windows-forms-control.md)
- [이벤트 정의](defining-an-event-in-windows-forms-controls.md)
