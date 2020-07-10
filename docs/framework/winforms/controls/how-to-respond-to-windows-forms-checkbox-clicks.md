---
title: CheckBox 클릭에 응답
description: Windows Forms 응용 프로그램을 프로그래밍 하 여 확인란의 상태에 따라 몇 가지 작업을 수행 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Click event [Windows Forms], CheckBox control
- CheckBox control [Windows Forms], Click events
- events [Windows Forms], Click events
- double-clicks
- check boxes [Windows Forms], responding to events
ms.assetid: c39f901e-8899-43b6-aa31-939cbf7089fb
ms.openlocfilehash: 58944bc421f990343b6c58484aaab3d79c8bda5e
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174499"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a>방법: Windows Forms CheckBox 클릭에 응답
사용자가 Windows Forms 컨트롤을 클릭할 때마다 <xref:System.Windows.Forms.CheckBox> <xref:System.Windows.Forms.Control.Click> 이벤트가 발생 합니다. 확인란의 상태에 따라 일부 작업을 수행 하도록 응용 프로그램을 프로그래밍할 수 있습니다.  
  
### <a name="to-respond-to-checkbox-clicks"></a>CheckBox 클릭에 응답 하려면  
  
1. <xref:System.Windows.Forms.Control.Click>이벤트 처리기에서 속성을 사용 <xref:System.Windows.Forms.CheckBox.Checked%2A> 하 여 컨트롤의 상태를 확인 하 고 필요한 작업을 수행 합니다.  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       ' The CheckBox control's Text property is changed each time the
       ' control is clicked, indicating a checked or unchecked state.  
       If CheckBox1.Checked = True Then  
          CheckBox1.Text = "Checked"  
       Else  
          CheckBox1.Text = "Unchecked"  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       // The CheckBox control's Text property is changed each time the
       // control is clicked, indicating a checked or unchecked state.  
       if (checkBox1.Checked)  
       {  
          checkBox1.Text = "Checked";  
       }  
       else  
       {  
          checkBox1.Text = "Unchecked";  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if (checkBox1->Checked)  
          {  
             checkBox1->Text = "Checked";  
          }  
          else  
          {  
             checkBox1->Text = "Unchecked";  
          }  
       }  
    ```  
  
    > [!NOTE]
    > 사용자가 컨트롤을 두 번 클릭 하면 <xref:System.Windows.Forms.CheckBox> 각 클릭이 개별적으로 처리 됩니다. 즉, <xref:System.Windows.Forms.CheckBox> 컨트롤이 두 번 클릭 이벤트를 지원 하지 않습니다.  
  
    > [!NOTE]
    > <xref:System.Windows.Forms.CheckBox.AutoCheck%2A>속성이 `true` (기본값) 이면가 <xref:System.Windows.Forms.CheckBox> 클릭 될 때가 자동으로 선택 되거나 선택 취소 됩니다. 그렇지 않으면 <xref:System.Windows.Forms.CheckBox.Checked%2A> 이벤트가 발생할 때 속성을 수동으로 설정 해야 합니다 <xref:System.Windows.Forms.Control.Click> .  
  
     컨트롤을 사용 하 여 <xref:System.Windows.Forms.CheckBox> 작업 과정을 확인할 수도 있습니다.  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a>확인란을 클릭할 때 수행 되는 작업을 확인 하려면  
  
1. Case 문을 사용 하 여 속성 값을 쿼리하여 <xref:System.Windows.Forms.CheckBox.CheckState%2A> 작업 과정을 확인할 수 있습니다. <xref:System.Windows.Forms.CheckBox.ThreeState%2A>속성이로 설정 된 경우이 `true` 속성은 <xref:System.Windows.Forms.CheckBox.CheckState%2A> 선택 되는 상자, 선택 취소 되는 상자 또는 세 번째 비활성화 상태 (옵션을 사용할 수 없음을 나타내기 위해 흐리게 표시 되는 확인란)를 나타내는 세 가지 가능한 값을 반환할 수 있습니다.  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       Select Case CheckBox1.CheckState  
          Case CheckState.Checked  
             ' Code for checked state.  
          Case CheckState.Unchecked  
             ' Code for unchecked state.  
          Case CheckState.Indeterminate  
             ' Code for indeterminate state.  
       End Select
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       switch(checkBox1.CheckState)  
       {  
          case CheckState.Checked:  
             // Code for checked state.  
             break;  
          case CheckState.Unchecked:  
             // Code for unchecked state.  
             break;  
          case CheckState.Indeterminate:  
             // Code for indeterminate state.  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          switch(checkBox1->CheckState) {  
             case CheckState::Checked:  
                // Code for checked state.  
                break;  
             case CheckState::Unchecked:  
                // Code for unchecked state.  
                break;  
             case CheckState::Indeterminate:  
                // Code for indeterminate state.  
                break;  
          }  
       }  
    ```  
  
    > [!NOTE]
    > <xref:System.Windows.Forms.CheckBox.ThreeState%2A>속성이로 설정 되 면 `true` <xref:System.Windows.Forms.CheckBox.Checked%2A> 속성은 `true` 및 둘 다에 대해를 반환 합니다 <xref:System.Windows.Forms.CheckState.Checked> <xref:System.Windows.Forms.CheckState.Indeterminate> .  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.CheckBox>
- [CheckBox 컨트롤 개요](checkbox-control-overview-windows-forms.md)
- [방법: Windows Forms CheckBox 컨트롤을 사용하여 옵션 설정](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [CheckBox 컨트롤](checkbox-control-windows-forms.md)
