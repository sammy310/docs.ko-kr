---
title: '방법: Windows Forms 단추 클릭에 응답'
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
ms.openlocfilehash: a10eaa3ea62df9301a53f5609b503bfabcb50a46
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110073"
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a><span data-ttu-id="5fc61-102">방법: Windows Forms 단추 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="5fc61-102">How to: Respond to Windows Forms Button Clicks</span></span>
<span data-ttu-id="5fc61-103">Windows Forms의 가장 기본적인 사용 <xref:System.Windows.Forms.Button> 컨트롤 단추를 클릭할 때 일부 코드를 실행 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5fc61-103">The most basic use of a Windows Forms <xref:System.Windows.Forms.Button> control is to run some code when the button is clicked.</span></span>  
  
 <span data-ttu-id="5fc61-104">클릭 하는 <xref:System.Windows.Forms.Button> 컨트롤 생성 다양 한 다른 이벤트와 같은 합니다 <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, 및 <xref:System.Windows.Forms.Control.MouseUp> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="5fc61-104">Clicking a <xref:System.Windows.Forms.Button> control also generates a number of other events, such as the <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, and <xref:System.Windows.Forms.Control.MouseUp> events.</span></span> <span data-ttu-id="5fc61-105">연결 하려는 경우 이러한 이벤트 처리기 관련 이벤트, 해당 작업 충돌 하지 않는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fc61-105">If you intend to attach event handlers for these related events, be sure that their actions do not conflict.</span></span> <span data-ttu-id="5fc61-106">예를 들어, 사용자가 텍스트 상자에 입력 하는 정보를 지웁니다 단추를 클릭 합니다를 단추 위로 마우스 포인터를 일시 중지 하지 표시 되 이제 존재 하지 않는 정보를 사용 하 여 도구 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fc61-106">For example, if clicking the button clears information that the user has typed in a text box, pausing the mouse pointer over the button should not display a tool tip with that now-nonexistent information.</span></span>  
  
 <span data-ttu-id="5fc61-107">사용자가 두 번 클릭 하려고 할 경우는 <xref:System.Windows.Forms.Button> 컨트롤을 클릭할 때마다 개별적으로 처리할; 컨트롤을 두 번 클릭 이벤트를 지원 하지 않습니다, 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fc61-107">If the user attempts to double-click the <xref:System.Windows.Forms.Button> control, each click will be processed separately; that is, the control does not support the double-click event.</span></span>  
  
### <a name="to-respond-to-a-button-click"></a><span data-ttu-id="5fc61-108">단추 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="5fc61-108">To respond to a button click</span></span>  
  
-   <span data-ttu-id="5fc61-109">단추의 `Click` <xref:System.EventHandler> 실행할 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fc61-109">In the button's `Click` <xref:System.EventHandler> write the code to run.</span></span> <span data-ttu-id="5fc61-110">`Button1_Click` 컨트롤에 바인딩해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fc61-110">`Button1_Click` must be bound to the control.</span></span> <span data-ttu-id="5fc61-111">자세한 내용은 [방법: 런타임에 Windows Forms에 대 한 이벤트 처리기를 만들](../how-to-create-event-handlers-at-run-time-for-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5fc61-111">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5fc61-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="5fc61-112">See also</span></span>

- [<span data-ttu-id="5fc61-113">Button 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="5fc61-113">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="5fc61-114">Windows Forms Button 컨트롤 선택 방법</span><span class="sxs-lookup"><span data-stu-id="5fc61-114">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="5fc61-115">Button 컨트롤</span><span class="sxs-lookup"><span data-stu-id="5fc61-115">Button Control</span></span>](button-control-windows-forms.md)
