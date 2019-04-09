---
title: '방법: 탭 페이지를 사용하지 않도록 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tab pages [Windows Forms], hiding in forms
- TabControl control [Windows Forms], disabling pages
ms.assetid: adcc6618-8a34-4ee1-bbe3-47e732de6a59
ms.openlocfilehash: ace713a635b5d9c4b73f85cd3d378c0f1ff3dba1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107577"
---
# <a name="how-to-disable-tab-pages"></a>방법: 탭 페이지를 사용하지 않도록 설정
일부 경우에 Windows Forms 응용 프로그램 내에서 사용할 수 있는 데이터에 대 한 액세스를 제한 해야 합니다. 데이터는 탭 컨트롤의 탭 페이지에 표시 된 경우의 예로 들 수 있습니다. 관리자는 게스트 또는 하위 수준의 사용자를 제한 하려고 하는 탭 페이지에 대 한 정보를 있을 수 있습니다.  
  
### <a name="to-disable-tab-pages-programmatically"></a>탭 페이지를 프로그래밍 방식으로 사용 하지 않도록 설정  
  
1.  탭 컨트롤을 처리 하는 코드를 작성 <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> 이벤트입니다. 다음 탭에서 사용자가 전환할 때 발생 하는 이벤트입니다.  
  
2.  자격 증명을 확인 합니다. 제공 된 정보에 따라 탭을 볼 수 있도록 허용 하기 전에 사용 하 여 사용자가 로그인 사용자 이름 또는 다른 형태의 자격 증명을 확인 하려는 수도 있습니다.  
  
3.  사용자가 적절 한 자격 증명을 클릭 한 탭을 표시 합니다. 사용자에 적절 한 자격 증명이 없는 경우 메시지 상자를 표시 하거나 나타내는 다른 사용자 인터페이스는 액세스 없고 초기 탭으로 돌아갑니다.  
  
    > [!NOTE]
    >  프로덕션 응용 프로그램에서이 기능을 구현 하는 경우 양식의 하는 동안이 자격 증명 확인을 수행할 수 있습니다 <xref:System.Windows.Forms.Form.Load> 이벤트입니다. 이렇게 하면 모든 사용자 인터페이스는은 훨씬 깔끔한 방법 프로그래밍 표시 되기 전에 탭을 숨길 수 있습니다. 아래 사용 되는 (자격 증명을 확인 하 고 중의 탭을 사용 하지 않도록 설정 합니다 <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> 이벤트)은 설명 목적으로 합니다.  
  
4.  필요에 따라 두 개 이상의 탭 페이지에 있는 경우에 원래 탭 페이지를 표시 합니다.  
  
     아래 예제에서는 <xref:System.Windows.Forms.CheckBox> 컨트롤 탭에 대 한 액세스는 응용 프로그램에 따라 달라 집니다 조건으로 자격 증명을 확인 하는 대신 사용 됩니다. 경우는 <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> 이벤트가 자격 증명 확인이 true (확인란 선택 이므로) 선택한 탭 및 `TabPage2` (이 예제의 기밀 정보를 사용 하 여 탭), 다음 `TabPage2` 표시 됩니다. 이 고, 그렇지 `TabPage3` 표시 되 고 적절 한 액세스 권한이 없음을 나타내는 사용자에 게는 메시지 상자가 표시 됩니다. 아래 코드에서는 사용 하 여 폼을 <xref:System.Windows.Forms.CheckBox> 컨트롤 (`CredentialCheck`) 및 <xref:System.Windows.Forms.TabControl> 세 탭 페이지를 사용 하 여 컨트롤입니다.  
  
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
  
     (Visual C#, Visual c + +) 이벤트 처리기를 등록 하려면 폼의 생성자에 다음 코드를 추가 합니다.  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=   
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a>참고자료

- [TabControl 컨트롤 개요](tabcontrol-control-overview-windows-forms.md)
- [방법: 탭 페이지에 컨트롤 추가](how-to-add-a-control-to-a-tab-page.md)
- [방법: Windows Forms TabControl을 사용하여 탭 추가 및 제거](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [방법: Windows Forms TabControl의 모양 변경](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
