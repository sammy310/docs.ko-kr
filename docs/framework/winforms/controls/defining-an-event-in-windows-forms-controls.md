---
title: 컨트롤에서 이벤트 정의
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- events [Windows Forms], defining within Windows Forms custom controls
- custom controls [Windows Forms], events using code
ms.assetid: d89f1096-8061-42e2-a855-a1f053f1940a
ms.openlocfilehash: d45c369e1fc82ee009a85b5b35fe6aa754873436
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746083"
---
# <a name="defining-an-event-in-windows-forms-controls"></a><span data-ttu-id="b3d89-102">Windows Forms 컨트롤에서 이벤트 정의</span><span class="sxs-lookup"><span data-stu-id="b3d89-102">Defining an Event in Windows Forms Controls</span></span>
<span data-ttu-id="b3d89-103">사용자 지정 이벤트를 정의 하는 방법에 대 한 자세한 내용은 [이벤트](../../../standard/events/index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b3d89-103">For details about defining custom events, see [Events](../../../standard/events/index.md).</span></span> <span data-ttu-id="b3d89-104">연결된 데이터가 없는 이벤트를 정의하는 경우에는 이벤트 데이터의 기본 형식인 <xref:System.EventArgs>를 사용하고 이벤트 대리자로 <xref:System.EventHandler>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d89-104">If you define an event that does not have any associated data, use the base type for event data, <xref:System.EventArgs>, and use <xref:System.EventHandler> as the event delegate.</span></span> <span data-ttu-id="b3d89-105">이벤트 멤버와 이벤트를 발생 시키는 보호 된 `On`*EventName* 메서드를 정의 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d89-105">All that remains to do is to define an event member and a protected `On`*EventName* method that raises the event.</span></span>  
  
 <span data-ttu-id="b3d89-106">다음 코드 조각은 `FlashTrackBar` 사용자 지정 컨트롤이 사용자 지정 이벤트 `ValueChanged`를 정의하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b3d89-106">The following code fragment shows how the `FlashTrackBar` custom control defines a custom event, `ValueChanged`.</span></span> <span data-ttu-id="b3d89-107">`FlashTrackBar` 샘플에 대 한 전체 코드는 [방법: 진행률을 보여 주는 Windows Forms 컨트롤 만들기](how-to-create-a-windows-forms-control-that-shows-progress.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b3d89-107">For the complete code for the `FlashTrackBar` sample, see the [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.Windows.Forms  
Imports System.Drawing  
  
Public Class FlashTrackBar  
   Inherits Control  
  
   ' The event does not have any data, so EventHandler is adequate   
   ' as the event delegate.          
   ' Define the event member using the event keyword.  
   ' In this case, for efficiency, the event is defined   
   ' using the event property construct.  
   Public Event ValueChanged As EventHandler  
   ' The protected method that raises the ValueChanged   
   ' event when the value has actually   
   ' changed. Derived controls can override this method.    
   Protected Overridable Sub OnValueChanged(e As EventArgs)  
      RaiseEvent ValueChanged(Me, e)  
   End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Windows.Forms;  
using System.Drawing;  
  
public class FlashTrackBar : Control {  
   // The event does not have any data, so EventHandler is adequate   
   // as the event delegate.  
   private EventHandler onValueChanged;  
   // Define the event member using the event keyword.  
   // In this case, for efficiency, the event is defined   
   // using the event property construct.  
   public event EventHandler ValueChanged {  
            add {  
                onValueChanged += value;  
            }  
            remove {  
                onValueChanged -= value;  
            }  
        }  
   // The protected method that raises the ValueChanged  
   // event when the value has actually   
   // changed. Derived controls can override this method.    
   protected virtual void OnValueChanged(EventArgs e) 
   {  
       ValueChanged?.Invoke(this, e);  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="b3d89-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b3d89-108">See also</span></span>

- [<span data-ttu-id="b3d89-109">Windows Forms 컨트롤의 이벤트</span><span class="sxs-lookup"><span data-stu-id="b3d89-109">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)
- [<span data-ttu-id="b3d89-110">이벤트</span><span class="sxs-lookup"><span data-stu-id="b3d89-110">Events</span></span>](../../../standard/events/index.md)
