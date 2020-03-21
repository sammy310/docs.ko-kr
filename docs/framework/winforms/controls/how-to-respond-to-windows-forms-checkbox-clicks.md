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
ms.openlocfilehash: 6ff20c443519446d3804b325924cb3c5cbedea97
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141928"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a><span data-ttu-id="83a11-102">방법: Windows Forms CheckBox 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="83a11-102">How to: Respond to Windows Forms CheckBox Clicks</span></span>
<span data-ttu-id="83a11-103">사용자가 Windows Forms <xref:System.Windows.Forms.CheckBox> 컨트롤을 클릭할 <xref:System.Windows.Forms.Control.Click> 때마다 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="83a11-103">Whenever a user clicks a Windows Forms <xref:System.Windows.Forms.CheckBox> control, the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span> <span data-ttu-id="83a11-104">확인란의 상태에 따라 응용 프로그램을 프로그래밍하여 일부 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83a11-104">You can program your application to perform some action depending upon the state of the check box.</span></span>  
  
### <a name="to-respond-to-checkbox-clicks"></a><span data-ttu-id="83a11-105">확인란 클릭에 응답하려면</span><span class="sxs-lookup"><span data-stu-id="83a11-105">To respond to CheckBox clicks</span></span>  
  
1. <span data-ttu-id="83a11-106"><xref:System.Windows.Forms.Control.Click> 이벤트 처리기에서 <xref:System.Windows.Forms.CheckBox.Checked%2A> 속성을 사용하여 컨트롤의 상태를 확인하고 필요한 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="83a11-106">In the <xref:System.Windows.Forms.Control.Click> event handler, use the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine the control's state, and perform any necessary action.</span></span>  
  
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
    > <span data-ttu-id="83a11-107">사용자가 <xref:System.Windows.Forms.CheckBox> 컨트롤을 두 번 클릭하려고 하면 각 클릭이 별도로 처리됩니다. 즉, 컨트롤은 <xref:System.Windows.Forms.CheckBox> 더블 클릭 이벤트를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83a11-107">If the user attempts to double-click the <xref:System.Windows.Forms.CheckBox> control, each click will be processed separately; that is, the <xref:System.Windows.Forms.CheckBox> control does not support the double-click event.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="83a11-108">속성이 <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> `true` (기본값) 경우, <xref:System.Windows.Forms.CheckBox> 속성이 클릭될 때 자동으로 선택되거나 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="83a11-108">When the <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> property is `true` (the default), the <xref:System.Windows.Forms.CheckBox> is automatically selected or cleared when it is clicked.</span></span> <span data-ttu-id="83a11-109">그렇지 않으면 <xref:System.Windows.Forms.CheckBox.Checked%2A> <xref:System.Windows.Forms.Control.Click> 이벤트가 발생할 때 속성을 수동으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83a11-109">Otherwise, you must manually set the <xref:System.Windows.Forms.CheckBox.Checked%2A> property when the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span>  
  
     <span data-ttu-id="83a11-110">컨트롤을 <xref:System.Windows.Forms.CheckBox> 사용하여 작업 과정을 결정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83a11-110">You can also use the <xref:System.Windows.Forms.CheckBox> control to determine a course of action.</span></span>  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a><span data-ttu-id="83a11-111">확인란을 클릭할 때 작업 과정을 결정하려면</span><span class="sxs-lookup"><span data-stu-id="83a11-111">To determine a course of action when a check box is clicked</span></span>  
  
1. <span data-ttu-id="83a11-112">사례 문을 사용하여 <xref:System.Windows.Forms.CheckBox.CheckState%2A> 속성 값을 쿼리하여 작업 과정을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="83a11-112">Use a case statement to query the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property to determine a course of action.</span></span> <span data-ttu-id="83a11-113"><xref:System.Windows.Forms.CheckBox.ThreeState%2A> 속성이 `true`설정되면 <xref:System.Windows.Forms.CheckBox.CheckState%2A> 속성은 선택 중인 확인란, 선택취소중인 상자 또는 옵션을 사용할 수 없음을 나타내기 위해 확인란이 흐리게 표시된 세 번째 확정되지 않은 상태를 나타내는 세 가지 가능한 값을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83a11-113">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property may return three possible values, which represent the box being checked, the box being unchecked, or a third indeterminate state in which the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
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
    > <span data-ttu-id="83a11-114">속성이 <xref:System.Windows.Forms.CheckBox.ThreeState%2A> `true`로 설정되면 <xref:System.Windows.Forms.CheckBox.Checked%2A> 속성이 `true` 둘 <xref:System.Windows.Forms.CheckState.Checked> <xref:System.Windows.Forms.CheckState.Indeterminate>다 및 에 대해 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="83a11-114">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns `true` for both <xref:System.Windows.Forms.CheckState.Checked> and <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83a11-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83a11-115">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="83a11-116">CheckBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="83a11-116">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="83a11-117">방법: Windows Forms CheckBox 컨트롤을 사용하여 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="83a11-117">How to: Set Options with Windows Forms CheckBox Controls</span></span>](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [<span data-ttu-id="83a11-118">확인란 컨트롤</span><span class="sxs-lookup"><span data-stu-id="83a11-118">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
