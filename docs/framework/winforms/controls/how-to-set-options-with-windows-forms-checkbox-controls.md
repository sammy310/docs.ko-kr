---
title: CheckBox 컨트롤을 사용하여 옵션 설정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- checked
helpviewer_keywords:
- CheckBox control [Windows Forms], checked state
- check boxes [Windows Forms], using to set options
- CheckBox control [Windows Forms], using to set options
ms.assetid: 2ac70498-7e3e-4e07-8901-ccabaeb5fd3e
ms.openlocfilehash: 84198eab42aa02b1bb37fa16a3c4247a37f58a10
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746769"
---
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a>방법: Windows Forms CheckBox 컨트롤을 사용하여 옵션 설정
Windows Forms <xref:System.Windows.Forms.CheckBox> 컨트롤은 사용자에 게 True/False 또는 예/아니요 옵션을 제공 하는 데 사용 됩니다. 컨트롤이 선택 되 면 컨트롤이 확인 표시를 표시 합니다.  
  
### <a name="to-set-options-with-checkbox-controls"></a>CheckBox 컨트롤을 사용 하 여 옵션을 설정 하려면  
  
1. <xref:System.Windows.Forms.CheckBox.Checked%2A> 속성의 값을 검사 하 여 해당 상태를 확인 하 고 해당 값을 사용 하 여 옵션을 설정 합니다.  
  
     아래 코드 샘플에서는 <xref:System.Windows.Forms.CheckBox> 컨트롤의 <xref:System.Windows.Forms.CheckBox.CheckedChanged> 이벤트가 발생할 때 확인란을 선택 하면 폼의 <xref:System.Windows.Forms.Control.AllowDrop%2A> 속성이 `false`로 설정 됩니다. 사용자 상호 작용을 제한 하려는 경우에 유용 합니다.  
  
    ```vb  
    Private Sub CheckBox1_CheckedChanged(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles CheckBox1.CheckedChanged  
       ' Determine the CheckState of the check box.  
       If CheckBox1.CheckState = CheckState.Checked Then  
          ' If checked, do not allow items to be dragged onto the form.  
          Me.AllowDrop = False  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_CheckedChanged(object sender, System.EventArgs e)  
    {  
       // Determine the CheckState of the check box.  
       if (checkBox1.CheckState == CheckState.Checked)   
       {  
          // If checked, do not allow items to be dragged onto the form.  
          this.AllowDrop = false;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // Determine the CheckState of the check box.  
          if (checkBox1->CheckState == CheckState::Checked)   
          {  
             // If checked, do not allow items to be dragged onto the form.  
             this->AllowDrop = false;  
          }  
       }  
    ```  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.CheckBox>
- [CheckBox 컨트롤 개요](checkbox-control-overview-windows-forms.md)
- [방법: Windows Forms CheckBox 클릭에 응답](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [CheckBox 컨트롤](checkbox-control-windows-forms.md)
