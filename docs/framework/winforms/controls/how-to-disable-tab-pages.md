---
title: '방법: 탭 페이지 사용 안 함'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tab pages [Windows Forms], hiding in forms
- TabControl control [Windows Forms], disabling pages
ms.assetid: adcc6618-8a34-4ee1-bbe3-47e732de6a59
ms.openlocfilehash: 9074aedb81a485267dc4faff92e0fe8d0d3b467f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182166"
---
# <a name="how-to-disable-tab-pages"></a>방법: 탭 페이지 사용 안 함
경우에 따라 Windows Forms 응용 프로그램 내에서 사용할 수 있는 데이터에 대한 액세스를 제한할 수 있습니다. 한 가지 예는 탭 컨트롤의 탭 페이지에 데이터가 표시되는 경우일 수 있습니다. 관리자는 탭 페이지에 게스트 또는 하위 수준 사용자로부터 제한하려는 정보를 가질 수 있습니다.  
  
### <a name="to-disable-tab-pages-programmatically"></a>프로그래밍 방식으로 탭 페이지를 비활성화하려면  
  
1. 탭 컨트롤의 <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> 이벤트를 처리하는 코드를 작성합니다. 사용자가 한 탭에서 다음 탭으로 전환할 때 발생하는 이벤트입니다.  
  
2. 자격 증명을 확인합니다. 제공된 정보에 따라 사용자가 탭을 볼 수 있도록 허용하기 전에 사용자가 로그인한 사용자 이름 또는 다른 형태의 자격 증명을 확인할 수 있습니다.  
  
3. 사용자에게 적절한 자격 증명이 있는 경우 클릭한 탭을 표시합니다. 사용자에게 적절한 자격 증명이 없는 경우 액세스 권한이 없다는 메시지 상자 또는 다른 사용자 인터페이스를 표시하고 초기 탭으로 돌아갑니다.  
  
    > [!NOTE]
    > 프로덕션 응용 프로그램에서 이 기능을 구현할 때 양식의 <xref:System.Windows.Forms.Form.Load> 이벤트 중에 이 자격 증명 검사를 수행할 수 있습니다. 이렇게 하면 사용자 인터페이스가 표시되기 전에 탭을 숨길 수 있으므로 프로그래밍에 훨씬 더 깔끔한 접근 방식이 됩니다. 아래에서 사용되는 <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> 방법론(이벤트 중 자격 증명 확인 및 탭 비활성화)은 예시적인 용도로 사용됩니다.  
  
4. 선택적으로 두 개 이상의 탭 페이지가 있는 경우 원본과 다른 탭 페이지를 표시합니다.  
  
     아래 예제에서는 탭에 대한 액세스 기준이 응용 프로그램에 따라 다르므로 자격 증명을 확인하는 대신 <xref:System.Windows.Forms.CheckBox> 컨트롤이 사용됩니다. <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> 이벤트가 발생하면 자격 증명 확인이 true(즉, 확인란이 선택됨)이고 선택한 `TabPage2` 탭이 (이 예제에서 기밀 정보가 `TabPage2` 있는 탭)이 있으면 표시됩니다. `TabPage3` 그렇지 않으면 사용자에게 적절한 액세스 권한이 없다는 메시지 상자가 표시됩니다. 아래 코드는 <xref:System.Windows.Forms.CheckBox> 컨트롤()`CredentialCheck`및 세 개의 <xref:System.Windows.Forms.TabControl> 탭 페이지가 있는 컨트롤이 있는 폼을 가정합니다.  
  
    ```vb  
    Private Sub TabControl1_SelectedIndexChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles TabControl1.SelectedIndexChanged  
       ' Check Credentials Here  
  
       If CredentialCheck.Checked = True And _
       TabControl1.SelectedTab Is TabPage2 Then  
          TabControl1.SelectedTab = TabPage2  
       ElseIf CredentialCheck.Checked = False _
       And TabControl1.SelectedTab Is TabPage2 Then  
          MessageBox.Show _
         ("Unable to load tab. You have insufficient access privileges.")  
          TabControl1.SelectedTab = TabPage3  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void tabControl1_SelectedIndexChanged(object sender, System.EventArgs e)  
    {  
        // Check Credentials Here  
  
        if ((CredentialCheck.Checked == true) && (tabControl1.SelectedTab == tabPage2))
        {  
            tabControl1.SelectedTab = tabPage2;  
        }  
        else if ((CredentialCheck.Checked == false) && (tabControl1.SelectedTab == tabPage2))  
        {  
            MessageBox.Show("Unable to load tab. You have insufficient access privileges.");  
            tabControl1.SelectedTab = tabPage3;  
        }  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void tabControl1_SelectedIndexChanged(  
          System::Object ^ sender,  
          System::EventArgs ^  e)  
       {  
          // Check Credentials Here  
          if ((CredentialCheck->Checked == true) &&  
              (tabControl1->SelectedTab == tabPage2))  
          {  
             tabControl1->SelectedTab = tabPage2;  
          }  
          else if ((CredentialCheck->Checked == false) &&  
                   (tabControl1->SelectedTab == tabPage2))  
          {  
             MessageBox::Show(String::Concat("Unable to load tab. ",  
                "You have insufficient access privileges."));  
             tabControl1->SelectedTab = tabPage3;  
          }  
       }  
    ```  
  
     (비주얼 C #, 비주얼 C++) 양식의 생성자에서 다음 코드를 배치하여 이벤트 처리기를 등록합니다.  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a>참고 항목

- [TabControl 컨트롤 개요](tabcontrol-control-overview-windows-forms.md)
- [방법: 탭 페이지에 컨트롤 추가](how-to-add-a-control-to-a-tab-page.md)
- [방법: Windows Forms TabControl을 사용하여 탭 추가 및 제거](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [방법: Windows Forms TabControl의 모양 변경](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
