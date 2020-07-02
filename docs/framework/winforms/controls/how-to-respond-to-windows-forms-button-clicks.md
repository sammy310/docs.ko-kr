---
title: 단추 클릭에 응답
description: Windows Forms 단추 클릭에 응답 하는 방법에 대해 알아봅니다. Windows Forms Button 컨트롤의 가장 기본적인 사용은 단추를 클릭할 때 코드를 실행 하는 것입니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], responding to Click events
- events [Windows Forms], Click events
- Click event [Windows Forms], Button control
- MouseDown event
- Button control [Windows Forms], click response
- double-clicks
- examples [Windows Forms], controls
- Click event [Windows Forms], responding to
ms.assetid: 7a4951bd-369c-4662-b246-28ad83eda484
ms.openlocfilehash: 5c458d56dbd6f1cab8e88bdbb86ede958367e5c4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619730"
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a>방법: Windows Forms 단추 클릭에 응답
Windows Forms 컨트롤의 가장 기본적인 사용은 <xref:System.Windows.Forms.Button> 단추를 클릭할 때 코드를 실행 하는 것입니다.  
  
 컨트롤을 클릭 하면 <xref:System.Windows.Forms.Button> , 및 이벤트와 같은 여러 이벤트도 생성 <xref:System.Windows.Forms.Control.MouseEnter> <xref:System.Windows.Forms.Control.MouseDown> <xref:System.Windows.Forms.Control.MouseUp> 됩니다. 이러한 관련 이벤트에 대 한 이벤트 처리기를 연결 하려는 경우 해당 작업이 충돌 하지 않도록 해야 합니다. 예를 들어 단추를 클릭 하 여 사용자가 텍스트 상자에 입력 한 정보를 지우면 단추 위에 마우스 포인터를 놓으면 현재 존재 하지 않는 정보가 포함 된 도구 설명이 표시 되지 않습니다.  
  
 사용자가 컨트롤을 두 번 클릭 하면 <xref:System.Windows.Forms.Button> 각 클릭이 개별적으로 처리 됩니다. 즉, 컨트롤이 두 번 클릭 이벤트를 지원 하지 않습니다.  
  
### <a name="to-respond-to-a-button-click"></a>단추 클릭에 응답 하려면  
  
- 단추에서 `Click` <xref:System.EventHandler> 실행할 코드를 작성 합니다. `Button1_Click`컨트롤에 바인딩되어야 합니다. 자세한 내용은 [방법: 런타임에 Windows Forms 이벤트 처리기 만들기](../how-to-create-event-handlers-at-run-time-for-windows-forms.md)를 참조 하세요.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       MessageBox.Show("Button1 was clicked")  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       MessageBox.Show("button1 was clicked");  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          MessageBox::Show("button1 was clicked");  
       }  
    ```  
  
## <a name="see-also"></a>참고 항목

- [Button 컨트롤 개요](button-control-overview-windows-forms.md)
- [Windows Forms Button 컨트롤 선택 방법](ways-to-select-a-windows-forms-button-control.md)
- [Button 컨트롤](button-control-windows-forms.md)
