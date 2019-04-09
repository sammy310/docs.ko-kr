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
ms.openlocfilehash: baf4e6cb3b2a40b1b792ae12e78cb9f878a738ff
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124308"
---
# <a name="overriding-the-onpaint-method"></a><span data-ttu-id="5633a-102">OnPaint 메서드 재정의</span><span class="sxs-lookup"><span data-stu-id="5633a-102">Overriding the OnPaint Method</span></span>
<span data-ttu-id="5633a-103">에 정의 된 이벤트를 재정의 하기 위한 기본 단계는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 동일 하 고 다음 목록에 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5633a-103">The basic steps for overriding any event defined in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] are identical and are summarized in the following list.</span></span>  
  
#### <a name="to-override-an-inherited-event"></a><span data-ttu-id="5633a-104">상속 된 이벤트를 재정의 하려면</span><span class="sxs-lookup"><span data-stu-id="5633a-104">To override an inherited event</span></span>  
  
1.  <span data-ttu-id="5633a-105">보호 된 재정의 `On` *EventName* 메서드.</span><span class="sxs-lookup"><span data-stu-id="5633a-105">Override the protected `On`*EventName* method.</span></span>  
  
2.  <span data-ttu-id="5633a-106">호출을 `On` *EventName* 기본 클래스에서 재정의 된 메서드의 `On` *EventName* 메서드를 등록 된 대리자가 이벤트를 받도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5633a-106">Call the `On`*EventName* method of the base class from the overridden `On`*EventName* method, so that registered delegates receive the event.</span></span>  
  
 <span data-ttu-id="5633a-107">합니다 <xref:System.Windows.Forms.Control.Paint> 이벤트는 모든 Windows Forms 컨트롤 재정의 해야 하기 때문에 여기에서 자세히 설명 되어 합니다 <xref:System.Windows.Forms.Control.Paint> 에서 상속 하는 이벤트 <xref:System.Windows.Forms.Control>합니다.</span><span class="sxs-lookup"><span data-stu-id="5633a-107">The <xref:System.Windows.Forms.Control.Paint> event is discussed in detail here because every Windows Forms control must override the <xref:System.Windows.Forms.Control.Paint> event that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="5633a-108">기본 <xref:System.Windows.Forms.Control> 클래스에서 파생된 된 컨트롤을 그릴 수 있도록 요구 하는 방법을 알 수 없습니다 및의 모든 그리기 논리를 제공 하지 않습니다는 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="5633a-108">The base <xref:System.Windows.Forms.Control> class does not know how a derived control needs to be drawn and does not provide any painting logic in the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="5633a-109">합니다 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드의 <xref:System.Windows.Forms.Control> 디스패치 하기만 합니다 <xref:System.Windows.Forms.Control.Paint> 이벤트 등록 된 이벤트 수신기를 합니다.</span><span class="sxs-lookup"><span data-stu-id="5633a-109">The <xref:System.Windows.Forms.Control.OnPaint%2A> method of <xref:System.Windows.Forms.Control> simply dispatches the <xref:System.Windows.Forms.Control.Paint> event to registered event receivers.</span></span>  
  
 <span data-ttu-id="5633a-110">샘플을 수행한 경우 [방법: 간단한 Windows Forms 컨트롤 개발](how-to-develop-a-simple-windows-forms-control.md)를 재정의 하는 예를 살펴보았습니다는 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="5633a-110">If you worked through the sample in [How to: Develop a Simple Windows Forms Control](how-to-develop-a-simple-windows-forms-control.md), you have seen an example of overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="5633a-111">다음 코드 조각은 샘플에서 가져온 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5633a-111">The following code fragment is taken from that sample.</span></span>  
  
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
  
 <span data-ttu-id="5633a-112"><xref:System.Windows.Forms.PaintEventArgs> 클래스에 대 한 데이터가 포함 된 <xref:System.Windows.Forms.Control.Paint> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="5633a-112">The <xref:System.Windows.Forms.PaintEventArgs> class contains data for the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="5633a-113">다음 코드와 같이 두 개의 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5633a-113">It has two properties, as shown in the following code.</span></span>  
  
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
  
 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> <span data-ttu-id="5633a-114">를 그릴 사각형 및 <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> 속성은 참조를 <xref:System.Drawing.Graphics> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5633a-114">is the rectangle to be painted, and the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property refers to a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="5633a-115">클래스는 <xref:System.Drawing?displayProperty=nameWithType> 네임 스페이스는 관리 되는 기능에 대 한 액세스를 제공 하는 클래스 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], 새로운 Windows 그래픽 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="5633a-115">The classes in the <xref:System.Drawing?displayProperty=nameWithType> namespace are managed classes that provide access to the functionality of [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], the new Windows graphics library.</span></span> <span data-ttu-id="5633a-116"><xref:System.Drawing.Graphics> 지점, 문자열, 선, 원호, 타원, 및 기타 많은 도형을 그릴 메서드가 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5633a-116">The <xref:System.Drawing.Graphics> object has methods to draw points, strings, lines, arcs, ellipses, and many other shapes.</span></span>  
  
 <span data-ttu-id="5633a-117">호출 하는 컨트롤을 해당 <xref:System.Windows.Forms.Control.OnPaint%2A> 해당 시각적 표시를 변경 해야 할 때마다 메서드.</span><span class="sxs-lookup"><span data-stu-id="5633a-117">A control invokes its <xref:System.Windows.Forms.Control.OnPaint%2A> method whenever it needs to change its visual display.</span></span> <span data-ttu-id="5633a-118">이 메서드가 발생을 <xref:System.Windows.Forms.Control.Paint> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="5633a-118">This method in turn raises the <xref:System.Windows.Forms.Control.Paint> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5633a-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="5633a-119">See also</span></span>

- [<span data-ttu-id="5633a-120">이벤트</span><span class="sxs-lookup"><span data-stu-id="5633a-120">Events</span></span>](../../../standard/events/index.md)
- [<span data-ttu-id="5633a-121">Windows Forms 컨트롤 렌더링</span><span class="sxs-lookup"><span data-stu-id="5633a-121">Rendering a Windows Forms Control</span></span>](rendering-a-windows-forms-control.md)
- [<span data-ttu-id="5633a-122">이벤트 정의</span><span class="sxs-lookup"><span data-stu-id="5633a-122">Defining an Event</span></span>](defining-an-event-in-windows-forms-controls.md)
