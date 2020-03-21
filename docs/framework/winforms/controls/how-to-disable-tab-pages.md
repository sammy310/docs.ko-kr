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
# <a name="how-to-disable-tab-pages"></a><span data-ttu-id="8abf5-102">방법: 탭 페이지 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="8abf5-102">How to: Disable Tab Pages</span></span>
<span data-ttu-id="8abf5-103">경우에 따라 Windows Forms 응용 프로그램 내에서 사용할 수 있는 데이터에 대한 액세스를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8abf5-103">On some occasions, you will want to restrict access to data that is available within your Windows Forms application.</span></span> <span data-ttu-id="8abf5-104">한 가지 예는 탭 컨트롤의 탭 페이지에 데이터가 표시되는 경우일 수 있습니다. 관리자는 탭 페이지에 게스트 또는 하위 수준 사용자로부터 제한하려는 정보를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8abf5-104">One example of this might be when you have data displayed in the tab pages of a tab control; administrators could have information on a tab page that you would want to restrict from guest or lower-level users.</span></span>  
  
### <a name="to-disable-tab-pages-programmatically"></a><span data-ttu-id="8abf5-105">프로그래밍 방식으로 탭 페이지를 비활성화하려면</span><span class="sxs-lookup"><span data-stu-id="8abf5-105">To disable tab pages programmatically</span></span>  
  
1. <span data-ttu-id="8abf5-106">탭 컨트롤의 <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> 이벤트를 처리하는 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="8abf5-106">Write code to handle the tab control's <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event.</span></span> <span data-ttu-id="8abf5-107">사용자가 한 탭에서 다음 탭으로 전환할 때 발생하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="8abf5-107">This is the event that is raised when the user switches from one tab to the next.</span></span>  
  
2. <span data-ttu-id="8abf5-108">자격 증명을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8abf5-108">Check credentials.</span></span> <span data-ttu-id="8abf5-109">제공된 정보에 따라 사용자가 탭을 볼 수 있도록 허용하기 전에 사용자가 로그인한 사용자 이름 또는 다른 형태의 자격 증명을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8abf5-109">Depending upon the information presented, you may want to check the user name the user has logged in with or some other form of credentials before allowing the user to view the tab.</span></span>  
  
3. <span data-ttu-id="8abf5-110">사용자에게 적절한 자격 증명이 있는 경우 클릭한 탭을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8abf5-110">If the user has appropriate credentials, display the tab that was clicked.</span></span> <span data-ttu-id="8abf5-111">사용자에게 적절한 자격 증명이 없는 경우 액세스 권한이 없다는 메시지 상자 또는 다른 사용자 인터페이스를 표시하고 초기 탭으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="8abf5-111">If the user does not have appropriate credentials, display a message box or some other user interface indicating that they do not have access, and return to the initial tab.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="8abf5-112">프로덕션 응용 프로그램에서 이 기능을 구현할 때 양식의 <xref:System.Windows.Forms.Form.Load> 이벤트 중에 이 자격 증명 검사를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8abf5-112">When you implement this functionality in your production applications, you can perform this credential check during the form's <xref:System.Windows.Forms.Form.Load> event.</span></span> <span data-ttu-id="8abf5-113">이렇게 하면 사용자 인터페이스가 표시되기 전에 탭을 숨길 수 있으므로 프로그래밍에 훨씬 더 깔끔한 접근 방식이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8abf5-113">This will allow you to hide the tab before any user interface is shown, which is a much cleaner approach to programming.</span></span> <span data-ttu-id="8abf5-114">아래에서 사용되는 <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> 방법론(이벤트 중 자격 증명 확인 및 탭 비활성화)은 예시적인 용도로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8abf5-114">The methodology used below (checking credentials and disabling the tab during the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event) is for illustrative purposes.</span></span>  
  
4. <span data-ttu-id="8abf5-115">선택적으로 두 개 이상의 탭 페이지가 있는 경우 원본과 다른 탭 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8abf5-115">Optionally, if you have more than two tab pages, display a tab page different from the original.</span></span>  
  
     <span data-ttu-id="8abf5-116">아래 예제에서는 탭에 대한 액세스 기준이 응용 프로그램에 따라 다르므로 자격 증명을 확인하는 대신 <xref:System.Windows.Forms.CheckBox> 컨트롤이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8abf5-116">In the example below, a <xref:System.Windows.Forms.CheckBox> control is used in lieu of checking the credentials, as the criteria for access to the tab will vary by application.</span></span> <span data-ttu-id="8abf5-117"><xref:System.Windows.Forms.TabControl.SelectedIndexChanged> 이벤트가 발생하면 자격 증명 확인이 true(즉, 확인란이 선택됨)이고 선택한 `TabPage2` 탭이 (이 예제에서 기밀 정보가 `TabPage2` 있는 탭)이 있으면 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8abf5-117">When the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event is raised, if the credential check is true (that is, the check box is checked) and the selected tab is `TabPage2` (the tab with the confidential information, in this example), then `TabPage2` is displayed.</span></span> <span data-ttu-id="8abf5-118">`TabPage3` 그렇지 않으면 사용자에게 적절한 액세스 권한이 없다는 메시지 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8abf5-118">Otherwise, `TabPage3` is displayed and a message box is shown to the user, indicating they did not have appropriate access privileges.</span></span> <span data-ttu-id="8abf5-119">아래 코드는 <xref:System.Windows.Forms.CheckBox> 컨트롤()`CredentialCheck`및 세 개의 <xref:System.Windows.Forms.TabControl> 탭 페이지가 있는 컨트롤이 있는 폼을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="8abf5-119">The code below assumes a form with a <xref:System.Windows.Forms.CheckBox> control (`CredentialCheck`) and a <xref:System.Windows.Forms.TabControl> control with three tab pages.</span></span>  
  
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
  
     <span data-ttu-id="8abf5-120">(비주얼 C #, 비주얼 C++) 양식의 생성자에서 다음 코드를 배치하여 이벤트 처리기를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="8abf5-120">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8abf5-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8abf5-121">See also</span></span>

- [<span data-ttu-id="8abf5-122">TabControl 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="8abf5-122">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="8abf5-123">방법: 탭 페이지에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="8abf5-123">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="8abf5-124">방법: Windows Forms TabControl을 사용하여 탭 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="8abf5-124">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="8abf5-125">방법: Windows Forms TabControl의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="8abf5-125">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
