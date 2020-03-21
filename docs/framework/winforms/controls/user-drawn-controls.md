---
title: 사용자가 그린 컨트롤
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], user-drawn
- OnPaint method [Windows Forms]
- user-drawn controls [Windows Forms]
ms.assetid: 034af4b5-457f-4160-a937-22891817faa8
ms.openlocfilehash: c68c8c88376cfe7295962264c466030115f2f3db
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182018"
---
# <a name="user-drawn-controls"></a>사용자가 그린 컨트롤
.NET 프레임워크는 사용자 고유의 컨트롤을 쉽게 개발할 수 있는 기능을 제공합니다. 코드에 의해 함께 바인딩된 표준 컨트롤 집합인 사용자 컨트롤을 만들거나 처음부터 사용자 고유의 컨트롤을 디자인할 수 있습니다. 상속을 사용하여 기존 컨트롤에서 상속되는 컨트롤을 만들고 고유 기능을 추가할 수도 있습니다. 어떤 방법을 사용하든 .NET Framework는 만드는 모든 컨트롤에 대한 사용자 지정 그래픽 인터페이스를 그리는 기능을 제공합니다.  
  
 컨트롤 페인팅은 컨트롤 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드에서 코드를 실행하여 수행됩니다. <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드의 단일 인수는 <xref:System.Windows.Forms.PaintEventArgs> 컨트롤을 렌더링하는 데 필요한 모든 정보와 기능을 제공하는 개체입니다. 컨트롤 <xref:System.Windows.Forms.PaintEventArgs> 렌더링에 사용할 두 개의 주 개체를 속성으로 제공합니다.  
  
- <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>개체 - 그려질 컨트롤의 일부를 나타내는 사각형입니다. 컨트롤이 그려지는 방식에 따라 전체 컨트롤 또는 컨트롤의 일부일 수 있습니다.  
  
- <xref:System.Drawing.Graphics>object - 컨트롤을 그리는 데 필요한 기능을 제공하는 여러 그래픽 지향 개체 및 메서드를 캡슐화합니다.  
  
 객체 및 객체 사용 방법에 대한 자세한 내용은 [그림에 대한 그래픽 객체 만들기 를](../advanced/how-to-create-graphics-objects-for-drawing.md)참조하세요. <xref:System.Drawing.Graphics>  
  
 이 <xref:System.Windows.Forms.Control.OnPaint%2A> 이벤트는 컨트롤이 화면에 그려지거나 새로 고칠 때마다 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 발생하며 개체는 페인팅이 수행되는 사각형을 나타냅니다. 전체 컨트롤을 새로 고쳐야 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 하는 경우 는 전체 컨트롤의 크기를 나타냅니다. 그러나 컨트롤의 일부만 새로 고쳐야 하는 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 경우 개체는 다시 그려야 하는 영역만 나타냅니다. 이러한 경우의 예로는 사용자 인터페이스의 다른 컨트롤이나 양식에 의해 컨트롤이 부분적으로 가려졌습니다.  
  
 <xref:System.Windows.Forms.Control> 클래스에서 상속할 때 메서드를 <xref:System.Windows.Forms.Control.OnPaint%2A> 재정의하고 그래픽 렌더링 코드를 제공해야 합니다. 사용자 컨트롤 또는 상속된 컨트롤에 사용자 지정 그래픽 인터페이스를 제공 하려는 경우 메서드를 <xref:System.Windows.Forms.Control.OnPaint%2A> 재정의 하 여 수행할 수도 있습니다. 아래에 예가 나와 있습니다.  
  
```vb  
Protected Overrides Sub OnPaint(ByVal e As PaintEventArgs)  
   ' Call the OnPaint method of the base class.  
   MyBase.OnPaint(e)  
  
   ' Declare and instantiate a drawing pen.  
   Using myPen As System.Drawing.Pen = New System.Drawing.Pen(Color.Aqua)  
      ' Draw an aqua rectangle in the rectangle represented by the control.  
      e.Graphics.DrawRectangle(myPen, New Rectangle(Me.Location, Me.Size))  
   End Using
End Sub  
```  
  
```csharp  
protected override void OnPaint(PaintEventArgs e)  
{  
   // Call the OnPaint method of the base class.  
   base.OnPaint(e);  
  
   // Declare and instantiate a new pen.  
   using (System.Drawing.Pen myPen = new System.Drawing.Pen(Color.Aqua))  
   {
      // Draw an aqua rectangle in the rectangle represented by the control.  
      e.Graphics.DrawRectangle(myPen, new Rectangle(this.Location,
         this.Size));  
   }
}  
```  
  
 앞의 예제에서는 매우 간단한 그래픽 표현으로 컨트롤을 렌더링하는 방법을 보여 줍니다. 기본 클래스의 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 호출하고 그릴 <xref:System.Drawing.Pen> 개체를 만들고 컨트롤과 컨트롤에 의해 <xref:System.Windows.Forms.Control.Location%2A> <xref:System.Windows.Forms.Control.Size%2A> 결정된 사각형에 타원을 그립니다. 대부분의 렌더링 코드는 이 보다 훨씬 더 복잡하지만 이 <xref:System.Drawing.Graphics> 예제에서는 <xref:System.Windows.Forms.PaintEventArgs> 개체 내에 포함된 개체의 사용을 보여 줍니다. 또는 와 <xref:System.Windows.Forms.UserControl> <xref:System.Windows.Forms.Button>같은 그래픽 표현이 이미 있는 클래스에서 상속하고 해당 표현을 렌더링에 통합하지 않으려는 경우 기본 클래스의 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 호출해서는 안 됩니다.  
  
 컨트롤 메서드의 <xref:System.Windows.Forms.Control.OnPaint%2A> 코드는 컨트롤이 처음 그려질 때와 새로 고칠 때마다 실행됩니다. 컨트롤의 크기를 조정할 때마다 컨트롤을 다시 그려두려면 컨트롤의 생성자에 다음 줄을 추가합니다.  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
> 속성을 <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> 사용하여 비직사각형 컨트롤을 구현합니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.Control.Region%2A>
- <xref:System.Windows.Forms.ControlStyles>
- <xref:System.Drawing.Graphics>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Windows.Forms.PaintEventArgs>
- [방법: 그리는 데 필요한 그래픽 개체 만들기](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [구성 요소 컨트롤](constituent-controls.md)
- [사용자 지정 컨트롤의 종류](varieties-of-custom-controls.md)
