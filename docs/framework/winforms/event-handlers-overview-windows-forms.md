---
title: 이벤트 처리기 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handling [Windows Forms], Windows Forms
- event handlers [Windows Forms], about event handlers
ms.assetid: 228112e1-1711-42ee-8ffa-ff3555bffe66
ms.openlocfilehash: 10ba458197973ede35849a86fec35003f139b8d2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743463"
---
# <a name="event-handlers-overview-windows-forms"></a>이벤트 처리기 개요(Windows Forms)
이벤트 처리기는 이벤트에 바인딩된 메서드입니다. 이벤트가 발생 하면 이벤트 처리기 내의 코드가 실행 됩니다. 각 이벤트 처리기는 이벤트를 올바르게 처리할 수 있는 두 개의 매개 변수를 제공 합니다. 다음 예제에서는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트에 대 한 이벤트 처리기를 보여 줍니다.  
  
```vb  
Private Sub button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles button1.Click  
  
End Sub  
```  
  
```csharp  
private void button1_Click(object sender, System.EventArgs e)   
{  
  
}  
```  
  
```cpp  
private:  
  void button1_Click(System::Object ^ sender,  
    System::EventArgs ^ e)  
  {  
  
  }  
```  
  
 첫 번째 매개 변수인`sender`는 이벤트를 발생 시킨 개체에 대 한 참조를 제공 합니다. 위의 예제에서 `e`두 번째 매개 변수는 처리 중인 이벤트와 관련 된 개체를 전달 합니다. 개체의 속성 (및 경우에 따라 메서드)을 참조 하 여 마우스 이벤트에 대 한 마우스 위치 또는 끌어서 놓기 이벤트에서 전송 되는 데이터와 같은 정보를 얻을 수 있습니다.  
  
 일반적으로 각 이벤트는 두 번째 매개 변수에 대해 다른 이벤트 개체 형식을 사용 하 여 이벤트 처리기를 생성 합니다. <xref:System.Windows.Forms.Control.MouseDown> 및 <xref:System.Windows.Forms.Control.MouseUp> 이벤트에 대 한 이벤트 처리기와 같은 일부 이벤트 처리기는 두 번째 매개 변수에 대해 동일한 개체 형식을 갖습니다. 이러한 이벤트 형식의 경우 동일한 이벤트 처리기를 사용 하 여 두 이벤트를 모두 처리할 수 있습니다.  
  
 동일한 이벤트 처리기를 사용 하 여 다른 컨트롤에 대해 동일한 이벤트를 처리할 수도 있습니다. 예를 들어 폼에 <xref:System.Windows.Forms.RadioButton> 컨트롤 그룹이 있는 경우 <xref:System.Windows.Forms.Control.Click> 이벤트에 대 한 단일 이벤트 처리기를 만들고 각 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트를 단일 이벤트 처리기에 바인딩할 수 있습니다. 자세한 내용은 [방법: 여러 이벤트를 Windows Forms의 단일 이벤트 처리기에 연결](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)을 참조 하세요.  
  
## <a name="see-also"></a>참조

- [Windows Forms에서 이벤트 처리기 만들기](creating-event-handlers-in-windows-forms.md)
- [이벤트 개요](events-overview-windows-forms.md)
