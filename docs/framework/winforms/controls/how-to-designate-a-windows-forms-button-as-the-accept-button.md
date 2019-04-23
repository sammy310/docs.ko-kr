---
title: '방법: Windows Forms 단추를 적용 단추로 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: 22cc9da6-b913-4e04-9554-dee443ac5c3a
ms.openlocfilehash: 8e608bb2cb4635ef1d29fd7a0aff3ac95fcd9af5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59309825"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a><span data-ttu-id="ced6c-102">방법: Windows Forms 단추를 적용 단추로 지정</span><span class="sxs-lookup"><span data-stu-id="ced6c-102">How to: Designate a Windows Forms Button as the Accept Button</span></span>
<span data-ttu-id="ced6c-103">모든 Windows Form에 지정할 수 있습니다는 <xref:System.Windows.Forms.Button> 컨트롤을 적용 단추가 기본 단추 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="ced6c-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="ced6c-104">ENTER 키를 누를 때마다 폼에서 다른 컨트롤에 포커스가 관계 없이 기본 단추 클릭 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ced6c-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ced6c-105">이 하는 경우 포커스가 있는 컨트롤은 다른 단추에 대 한 예외-포커스가 있는 단추를 클릭 하는 경우-여러 줄 텍스트 상자 또는 ENTER 키를 트래핑 하는 사용자 지정 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="ced6c-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>  
  
### <a name="to-designate-the-accept-button"></a><span data-ttu-id="ced6c-106">적용 단추를 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="ced6c-106">To designate the accept button</span></span>  
  
1. <span data-ttu-id="ced6c-107">폼의 설정 <xref:System.Windows.Forms.Form.AcceptButton%2A> 속성을 적절 한 <xref:System.Windows.Forms.Button> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ced6c-107">Set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub SetDefault(ByVal myDefaultBtn As Button)  
      Me.AcceptButton = myDefaultBtn   
    End Sub  
    ```  
  
    ```csharp  
    private void SetDefault(Button myDefaultBtn)  
    {  
       this.AcceptButton = myDefaultBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetDefault(Button ^ myDefaultBtn)  
       {  
          this->AcceptButton = myDefaultBtn;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ced6c-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="ced6c-108">See also</span></span>

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [<span data-ttu-id="ced6c-109">Button 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="ced6c-109">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="ced6c-110">Windows Forms Button 컨트롤 선택 방법</span><span class="sxs-lookup"><span data-stu-id="ced6c-110">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="ced6c-111">방법: Windows Forms 단추 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="ced6c-111">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="ced6c-112">방법: Windows Forms 단추를 취소 단추로 지정</span><span class="sxs-lookup"><span data-stu-id="ced6c-112">How to: Designate a Windows Forms Button as the Cancel Button</span></span>](how-to-designate-a-windows-forms-button-as-the-cancel-button.md)
- [<span data-ttu-id="ced6c-113">Button 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ced6c-113">Button Control</span></span>](button-control-windows-forms.md)
