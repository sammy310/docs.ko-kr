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
# <a name="overriding-the-onpaint-method"></a><span data-ttu-id="b4995-102">OnPaint 메서드 재정의</span><span class="sxs-lookup"><span data-stu-id="b4995-102">Overriding the OnPaint Method</span></span>
<span data-ttu-id="b4995-103">.NET Framework에 정의된 모든 이벤트를 재정의하기 위한 기본 단계는 동일하며 다음 목록에 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4995-103">The basic steps for overriding any event defined in the .NET Framework are identical and are summarized in the following list.</span></span>  
  
#### <a name="to-override-an-inherited-event"></a><span data-ttu-id="b4995-104">상속된 이벤트를 재정의하려면</span><span class="sxs-lookup"><span data-stu-id="b4995-104">To override an inherited event</span></span>  
  
1. <span data-ttu-id="b4995-105">보호된 `On` *EventName* 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b4995-105">Override the protected `On`*EventName* method.</span></span>  
  
2. <span data-ttu-id="b4995-106">등록된 대리자가 이벤트를 수신할 수 있도록 `On`재정의된 *EventName* 메서드에서 기본 클래스의 EventName 메서드를 호출합니다. *EventName* `On`</span><span class="sxs-lookup"><span data-stu-id="b4995-106">Call the `On`*EventName* method of the base class from the overridden `On`*EventName* method, so that registered delegates receive the event.</span></span>  
  
 <span data-ttu-id="b4995-107">모든 <xref:System.Windows.Forms.Control.Paint> Windows Forms 컨트롤에서 상속하는 <xref:System.Windows.Forms.Control.Paint> 이벤트를 재정의해야 하기 때문에 이 <xref:System.Windows.Forms.Control>이벤트는 여기에서 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b4995-107">The <xref:System.Windows.Forms.Control.Paint> event is discussed in detail here because every Windows Forms control must override the <xref:System.Windows.Forms.Control.Paint> event that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="b4995-108">기본 <xref:System.Windows.Forms.Control> 클래스는 파생 된 컨트롤을 그려야 하는 방법을 알 수 없으며 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드에서 페인팅 논리를 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4995-108">The base <xref:System.Windows.Forms.Control> class does not know how a derived control needs to be drawn and does not provide any painting logic in the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="b4995-109">단순히 등록된 이벤트 수신기에 <xref:System.Windows.Forms.Control.Paint> 이벤트를 디스패치하는 방법입니다. <xref:System.Windows.Forms.Control.OnPaint%2A> <xref:System.Windows.Forms.Control></span><span class="sxs-lookup"><span data-stu-id="b4995-109">The <xref:System.Windows.Forms.Control.OnPaint%2A> method of <xref:System.Windows.Forms.Control> simply dispatches the <xref:System.Windows.Forms.Control.Paint> event to registered event receivers.</span></span>  
  
 <span data-ttu-id="b4995-110">[방법: 간단한 Windows 양식 컨트롤 개발의](how-to-develop-a-simple-windows-forms-control.md)샘플을 통해 작업하는 경우 메서드를 <xref:System.Windows.Forms.Control.OnPaint%2A> 재정의하는 예제를 보았습니다.</span><span class="sxs-lookup"><span data-stu-id="b4995-110">If you worked through the sample in [How to: Develop a Simple Windows Forms Control](how-to-develop-a-simple-windows-forms-control.md), you have seen an example of overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="b4995-111">다음 코드 조각은 해당 샘플에서 가져온 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b4995-111">The following code fragment is taken from that sample.</span></span>  
  
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
  
 <span data-ttu-id="b4995-112">클래스에는 <xref:System.Windows.Forms.PaintEventArgs> 이벤트에 대한 <xref:System.Windows.Forms.Control.Paint> 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4995-112">The <xref:System.Windows.Forms.PaintEventArgs> class contains data for the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="b4995-113">다음 코드와 같이 두 개의 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4995-113">It has two properties, as shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="b4995-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>는 페인팅할 사각형이며 속성은 <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> 개체를 <xref:System.Drawing.Graphics> 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="b4995-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> is the rectangle to be painted, and the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property refers to a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="b4995-115">네임스페이스의 <xref:System.Drawing?displayProperty=nameWithType> 클래스는 새 Windows 그래픽 라이브러리인 GDI+의 기능에 대한 액세스를 제공하는 관리되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b4995-115">The classes in the <xref:System.Drawing?displayProperty=nameWithType> namespace are managed classes that provide access to the functionality of GDI+, the new Windows graphics library.</span></span> <span data-ttu-id="b4995-116"><xref:System.Drawing.Graphics> 개체에는 점, 문자열, 선, 호, 타원 및 기타 여러 모양을 그리는 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4995-116">The <xref:System.Drawing.Graphics> object has methods to draw points, strings, lines, arcs, ellipses, and many other shapes.</span></span>  
  
 <span data-ttu-id="b4995-117">컨트롤은 시각적 표시를 <xref:System.Windows.Forms.Control.OnPaint%2A> 변경해야 할 때마다 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="b4995-117">A control invokes its <xref:System.Windows.Forms.Control.OnPaint%2A> method whenever it needs to change its visual display.</span></span> <span data-ttu-id="b4995-118">이 메서드는 차례로 <xref:System.Windows.Forms.Control.Paint> 이벤트를 발생 시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4995-118">This method in turn raises the <xref:System.Windows.Forms.Control.Paint> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4995-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b4995-119">See also</span></span>

- [<span data-ttu-id="b4995-120">Events</span><span class="sxs-lookup"><span data-stu-id="b4995-120">Events</span></span>](../../../standard/events/index.md)
- [<span data-ttu-id="b4995-121">Windows Forms 컨트롤 렌더링</span><span class="sxs-lookup"><span data-stu-id="b4995-121">Rendering a Windows Forms Control</span></span>](rendering-a-windows-forms-control.md)
- [<span data-ttu-id="b4995-122">이벤트 정의</span><span class="sxs-lookup"><span data-stu-id="b4995-122">Defining an Event</span></span>](defining-an-event-in-windows-forms-controls.md)
