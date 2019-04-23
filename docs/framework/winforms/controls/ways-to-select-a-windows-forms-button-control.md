---
title: Windows Forms Button 컨트롤 선택 방법
ms.date: 03/30/2017
helpviewer_keywords:
- Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
ms.openlocfilehash: f2881646a05d257044c6461f822a4c35a225f8c8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59223292"
---
# <a name="ways-to-select-a-windows-forms-button-control"></a><span data-ttu-id="0385d-102">Windows Forms Button 컨트롤 선택 방법</span><span class="sxs-lookup"><span data-stu-id="0385d-102">Ways to Select a Windows Forms Button Control</span></span>
<span data-ttu-id="0385d-103">다음과 같은 방법으로 Windows Forms 단추를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0385d-103">A Windows Forms button can be selected in the following ways:</span></span>  
  
-   <span data-ttu-id="0385d-104">마우스를 사용 하 여 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0385d-104">Use a mouse to click the button.</span></span>  
  
-   <span data-ttu-id="0385d-105">단추의 호출 <xref:System.Windows.Forms.Control.Click> 코드의 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="0385d-105">Invoke the button's <xref:System.Windows.Forms.Control.Click> event in code.</span></span>  
  
-   <span data-ttu-id="0385d-106">TAB 키를 눌러 단추에 포커스를 이동 하 고 스페이스바 또는 ENTER 키를 누르면 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0385d-106">Move the focus to the button by pressing the TAB key, and then choose the button by pressing the SPACEBAR or ENTER.</span></span>  
  
-   <span data-ttu-id="0385d-107">단추에 대 한 액세스 키 (ALT + 밑줄이 그어진된 문자)를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0385d-107">Press the access key (ALT + the underlined letter) for the button.</span></span> <span data-ttu-id="0385d-108">액세스 키에 대 한 자세한 내용은 참조 하세요. [방법: Windows Forms 컨트롤에 대 한 액세스 키를 만들](how-to-create-access-keys-for-windows-forms-controls.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0385d-108">For more information about access keys, see [How to: Create Access Keys for Windows Forms Controls](how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
-   <span data-ttu-id="0385d-109">다른 컨트롤에 포커스가 있는 경우에 ENTER 키를 눌러 단추가 선택 단추를 폼의 "수락" 단추 이면-다른 단추, 여러 줄 텍스트 상자 또는 enter 키를 트래핑 하는 사용자 지정 컨트롤을 다른 제어 하는 경우를 제외 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0385d-109">If the button is the "accept" button of the form, pressing ENTER chooses the button, even if another control has the focus — except if that other control is another button, a multi-line text box, or a custom control that traps the enter key.</span></span>  
  
-   <span data-ttu-id="0385d-110">단추를 폼의 "취소" 단추를 ESC 키를 눌러 선택 단추를 다른 컨트롤에 포커스가 있는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="0385d-110">If the button is the "cancel" button of the form, pressing ESC chooses the button, even if another control has the focus.</span></span>  
  
-   <span data-ttu-id="0385d-111">호출 된 <xref:System.Windows.Forms.Button.PerformClick%2A> 메서드를 프로그래밍 방식으로 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0385d-111">Call the <xref:System.Windows.Forms.Button.PerformClick%2A> method to select the button programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0385d-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="0385d-112">See also</span></span>

- [<span data-ttu-id="0385d-113">Button 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="0385d-113">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="0385d-114">방법: Windows Forms 단추 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="0385d-114">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="0385d-115">Button 컨트롤</span><span class="sxs-lookup"><span data-stu-id="0385d-115">Button Control</span></span>](button-control-windows-forms.md)
