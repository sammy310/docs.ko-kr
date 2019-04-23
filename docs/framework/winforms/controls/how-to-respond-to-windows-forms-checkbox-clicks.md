---
title: '방법: Windows Forms 확인란 클릭에 응답'
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
ms.openlocfilehash: ce616f45ceaa3db117c6981d2987ac09bba7b3fb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59319900"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a><span data-ttu-id="ebb30-102">방법: Windows Forms 확인란 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="ebb30-102">How to: Respond to Windows Forms CheckBox Clicks</span></span>
<span data-ttu-id="ebb30-103">Windows Forms를 클릭할 때마다 <xref:System.Windows.Forms.CheckBox> 컨트롤을 <xref:System.Windows.Forms.Control.Click> 이벤트가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb30-103">Whenever a user clicks a Windows Forms <xref:System.Windows.Forms.CheckBox> control, the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span> <span data-ttu-id="ebb30-104">확인란의 상태에 따라 몇 가지 작업을 수행 하려면 응용 프로그램을 프로그래밍할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebb30-104">You can program your application to perform some action depending upon the state of the check box.</span></span>  
  
### <a name="to-respond-to-checkbox-clicks"></a><span data-ttu-id="ebb30-105">CheckBox 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="ebb30-105">To respond to CheckBox clicks</span></span>  
  
1. <span data-ttu-id="ebb30-106">에 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 사용 하 여는 <xref:System.Windows.Forms.CheckBox.Checked%2A> 속성을 컨트롤의 상태를 확인 하 고 필요한 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb30-106">In the <xref:System.Windows.Forms.Control.Click> event handler, use the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine the control's state, and perform any necessary action.</span></span>  
  
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
    >  <span data-ttu-id="ebb30-107">사용자가 두 번 클릭 합니다 <xref:System.Windows.Forms.CheckBox> 컨트롤을 클릭할 때마다 별도로 처리 됩니다. 즉, <xref:System.Windows.Forms.CheckBox> 컨트롤을 두 번 클릭 이벤트를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ebb30-107">If the user attempts to double-click the <xref:System.Windows.Forms.CheckBox> control, each click will be processed separately; that is, the <xref:System.Windows.Forms.CheckBox> control does not support the double-click event.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ebb30-108">경우는 <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> 속성은 `true` (기본값)는 <xref:System.Windows.Forms.CheckBox> 를 자동으로 선택 하거나 클릭 하면 선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb30-108">When the <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> property is `true` (the default), the <xref:System.Windows.Forms.CheckBox> is automatically selected or cleared when it is clicked.</span></span> <span data-ttu-id="ebb30-109">수동으로 설정 해야이 고, 그렇지 합니다 <xref:System.Windows.Forms.CheckBox.Checked%2A> 속성 때는 <xref:System.Windows.Forms.Control.Click> 이벤트가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb30-109">Otherwise, you must manually set the <xref:System.Windows.Forms.CheckBox.Checked%2A> property when the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span>  
  
     <span data-ttu-id="ebb30-110">사용할 수도 있습니다는 <xref:System.Windows.Forms.CheckBox> 일련의 동작을 확인 하기 위해 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="ebb30-110">You can also use the <xref:System.Windows.Forms.CheckBox> control to determine a course of action.</span></span>  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a><span data-ttu-id="ebb30-111">클릭할 때 확인란을 작업의 과정을 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="ebb30-111">To determine a course of action when a check box is clicked</span></span>  
  
1. <span data-ttu-id="ebb30-112">Case 문을 사용 하 여 값을 쿼리 합니다 <xref:System.Windows.Forms.CheckBox.CheckState%2A> 일련의 동작을 결정 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ebb30-112">Use a case statement to query the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property to determine a course of action.</span></span> <span data-ttu-id="ebb30-113">경우는 <xref:System.Windows.Forms.CheckBox.ThreeState%2A> 속성이로 설정 되어 `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A> 속성 상자를 나타내는 세 가지 가능한 값을 반환할 수 있습니다 상자 옵션을 선택 취소 되 고 또는 미 확정 상태로 상자를 표시 하는 흐리게 표시를 사용 하 여 옵션을 나타내는 모양은 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ebb30-113">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property may return three possible values, which represent the box being checked, the box being unchecked, or a third indeterminate state in which the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
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
    >  <span data-ttu-id="ebb30-114">경우는 <xref:System.Windows.Forms.CheckBox.ThreeState%2A> 속성이로 설정 된 `true`, <xref:System.Windows.Forms.CheckBox.Checked%2A> 속성에서 반환 `true` 둘 다에 대해 <xref:System.Windows.Forms.CheckState.Checked> 및 <xref:System.Windows.Forms.CheckState.Indeterminate>합니다.</span><span class="sxs-lookup"><span data-stu-id="ebb30-114">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns `true` for both <xref:System.Windows.Forms.CheckState.Checked> and <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebb30-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="ebb30-115">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="ebb30-116">CheckBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="ebb30-116">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="ebb30-117">방법: Windows Forms CheckBox 컨트롤을 사용 하 여 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="ebb30-117">How to: Set Options with Windows Forms CheckBox Controls</span></span>](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [<span data-ttu-id="ebb30-118">CheckBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ebb30-118">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
