---
title: CheckBox 클릭에 응답
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
ms.openlocfilehash: ba2afb52939a6274978ce725dac19b5622419b99
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735668"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a><span data-ttu-id="6b95b-102">방법: Windows Forms CheckBox 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="6b95b-102">How to: Respond to Windows Forms CheckBox Clicks</span></span>
<span data-ttu-id="6b95b-103">사용자가 Windows Forms <xref:System.Windows.Forms.CheckBox> 컨트롤을 클릭할 때마다 <xref:System.Windows.Forms.Control.Click> 이벤트가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b95b-103">Whenever a user clicks a Windows Forms <xref:System.Windows.Forms.CheckBox> control, the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span> <span data-ttu-id="6b95b-104">확인란의 상태에 따라 일부 작업을 수행 하도록 응용 프로그램을 프로그래밍할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b95b-104">You can program your application to perform some action depending upon the state of the check box.</span></span>  
  
### <a name="to-respond-to-checkbox-clicks"></a><span data-ttu-id="6b95b-105">CheckBox 클릭에 응답 하려면</span><span class="sxs-lookup"><span data-stu-id="6b95b-105">To respond to CheckBox clicks</span></span>  
  
1. <span data-ttu-id="6b95b-106"><xref:System.Windows.Forms.Control.Click> 이벤트 처리기에서 <xref:System.Windows.Forms.CheckBox.Checked%2A> 속성을 사용 하 여 컨트롤의 상태를 확인 하 고 필요한 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b95b-106">In the <xref:System.Windows.Forms.Control.Click> event handler, use the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine the control's state, and perform any necessary action.</span></span>  
  
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
    > <span data-ttu-id="6b95b-107">사용자가 <xref:System.Windows.Forms.CheckBox> 컨트롤을 두 번 클릭 하면 각 클릭이 개별적으로 처리 됩니다. 즉, <xref:System.Windows.Forms.CheckBox> 컨트롤은 두 번 클릭 이벤트를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6b95b-107">If the user attempts to double-click the <xref:System.Windows.Forms.CheckBox> control, each click will be processed separately; that is, the <xref:System.Windows.Forms.CheckBox> control does not support the double-click event.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="6b95b-108"><xref:System.Windows.Forms.CheckBox.AutoCheck%2A> 속성이 `true` (기본값) 이면 <xref:System.Windows.Forms.CheckBox> 클릭 하면 자동으로 선택 되거나 선택이 취소 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b95b-108">When the <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> property is `true` (the default), the <xref:System.Windows.Forms.CheckBox> is automatically selected or cleared when it is clicked.</span></span> <span data-ttu-id="6b95b-109">그렇지 않으면 <xref:System.Windows.Forms.Control.Click> 이벤트가 발생할 때 <xref:System.Windows.Forms.CheckBox.Checked%2A> 속성을 수동으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b95b-109">Otherwise, you must manually set the <xref:System.Windows.Forms.CheckBox.Checked%2A> property when the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span>  
  
     <span data-ttu-id="6b95b-110"><xref:System.Windows.Forms.CheckBox> 컨트롤을 사용 하 여 작업 과정을 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b95b-110">You can also use the <xref:System.Windows.Forms.CheckBox> control to determine a course of action.</span></span>  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a><span data-ttu-id="6b95b-111">확인란을 클릭할 때 수행 되는 작업을 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="6b95b-111">To determine a course of action when a check box is clicked</span></span>  
  
1. <span data-ttu-id="6b95b-112">Case 문을 사용 하 여 <xref:System.Windows.Forms.CheckBox.CheckState%2A> 속성의 값을 쿼리하여 작업 과정을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b95b-112">Use a case statement to query the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property to determine a course of action.</span></span> <span data-ttu-id="6b95b-113"><xref:System.Windows.Forms.CheckBox.ThreeState%2A> 속성이 `true`로 설정 된 경우 <xref:System.Windows.Forms.CheckBox.CheckState%2A> 속성은 선택할 수 있는 상자, 선택 취소 되는 상자 또는 세 번째 비활성화 상태 (옵션을 사용할 수 없음을 나타내는 단추가 흐리게 표시 됨)를 나타내는 세 가지 가능한 값을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b95b-113">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property may return three possible values, which represent the box being checked, the box being unchecked, or a third indeterminate state in which the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
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
    > <span data-ttu-id="6b95b-114"><xref:System.Windows.Forms.CheckBox.ThreeState%2A> 속성이 `true`로 설정 된 경우 <xref:System.Windows.Forms.CheckBox.Checked%2A> 속성은 <xref:System.Windows.Forms.CheckState.Checked>와 <xref:System.Windows.Forms.CheckState.Indeterminate>에 대 한 `true`를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b95b-114">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns `true` for both <xref:System.Windows.Forms.CheckState.Checked> and <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b95b-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b95b-115">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="6b95b-116">CheckBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="6b95b-116">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="6b95b-117">방법: Windows Forms CheckBox 컨트롤을 사용하여 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="6b95b-117">How to: Set Options with Windows Forms CheckBox Controls</span></span>](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [<span data-ttu-id="6b95b-118">CheckBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="6b95b-118">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
