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
ms.openlocfilehash: 6799b229de8e8eb49dd3b8bbaffe0d08a32b7208
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142292"
---
# <a name="defining-an-event-in-windows-forms-controls"></a>Windows Forms 컨트롤에서 이벤트 정의
사용자 지정 이벤트 정의에 대한 자세한 내용은 [이벤트를](../../../standard/events/index.md)참조하십시오. 연결된 데이터가 없는 이벤트를 정의하는 경우에는 이벤트 데이터의 기본 형식인 <xref:System.EventArgs>를 사용하고 이벤트 대리자로 <xref:System.EventHandler>를 사용합니다. 이벤트 멤버와 이벤트를 발생 시키는 보호된 `On` *EventName* 메서드를 정의 하기 만 하면 남아 있습니다.  
  
 다음 코드 조각은 `FlashTrackBar` 사용자 지정 컨트롤이 사용자 지정 이벤트 `ValueChanged`를 정의하는 방법을 보여줍니다. 샘플의 전체 코드는 [진행률을 표시하는 Windows 양식 컨트롤 만들기](how-to-create-a-windows-forms-control-that-shows-progress.md)방법을 참조하십시오. `FlashTrackBar`  
  
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
  
## <a name="see-also"></a>참고 항목

- [Windows Forms 컨트롤의 이벤트](events-in-windows-forms-controls.md)
- [Events](../../../standard/events/index.md)
