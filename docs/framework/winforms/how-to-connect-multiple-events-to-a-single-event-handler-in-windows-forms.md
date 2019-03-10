---
title: '방법: Windows Forms에서 단일 이벤트 처리기에 여러 이벤트 연결'
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- events [Windows Forms], connecting multiple to single event handler
- event handlers [Windows Forms], connecting events to
- menus [Windows Forms], event-handling methods for multiple menu items
- Windows Forms controls, events
- menu items [Windows Forms], multicasting event-handling methods
ms.assetid: 5a20749a-41b5-4acc-8eb1-9e5040b0a2c4
ms.openlocfilehash: 71b17e8a4bedca54cb7fff5f14ce28a0c572fe88
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722662"
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a><span data-ttu-id="cf4a9-102">방법: Windows Forms에서 단일 이벤트 처리기에 여러 이벤트 연결</span><span class="sxs-lookup"><span data-stu-id="cf4a9-102">How to: Connect Multiple Events to a Single Event Handler in Windows Forms</span></span>
<span data-ttu-id="cf4a9-103">응용 프로그램 디자인에서 있습니다 경우가 동일한 절차를 수행 하는 여러 이벤트 또는 단일 이벤트 처리기를 사용 하 여 여러 이벤트에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-103">In your application design, you may find it necessary to use a single event handler for multiple events or have multiple events perform the same procedure.</span></span> <span data-ttu-id="cf4a9-104">예를 들어, 동일한 기능을 노출 하는 경우 폼에서 단추와 마찬가지로 동일한 이벤트를 발생 시킬 수 있는 메뉴 명령이에 강력한 시간 보호기가 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-104">For example, it is often a powerful time-saver to have a menu command raise the same event as a button on your form does if they expose the same functionality.</span></span> <span data-ttu-id="cf4a9-105">속성 창의 이벤트 보기를 사용 하 여이 수행할 수 있습니다 C# 를 사용 하 여 또는 합니다 `Handles` 키워드 및 **클래스 이름** 및 **메서드 이름** 드롭다운 목록 상자는 Visual Basic 코드 편집기에서.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-105">You can do this by using the Events view of the Properties window in C# or using the `Handles` keyword and the **Class Name** and **Method Name** drop-down boxes in the Visual Basic Code Editor.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a><span data-ttu-id="cf4a9-106">Visual Basic에서 단일 이벤트 처리기에 여러 이벤트 연결</span><span class="sxs-lookup"><span data-stu-id="cf4a9-106">To connect multiple events to a single event handler in Visual Basic</span></span>  
  
1.  <span data-ttu-id="cf4a9-107">폼을 마우스 오른쪽 단추로 클릭 하 고 선택 **코드 보기**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-107">Right-click the form and choose **View Code**.</span></span>  
  
2.  <span data-ttu-id="cf4a9-108">**클래스 이름** 드롭다운 목록 상자에서 처리할 이벤트 처리기로 원하는 컨트롤 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-108">From the **Class Name** drop-down box, select one of the controls that you want to have the event handler handle.</span></span>  
  
3.  <span data-ttu-id="cf4a9-109">**메서드 이름** 드롭다운 목록 상자에서 이벤트를 처리할 이벤트 처리기를 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-109">From the **Method Name** drop-down box, select one of the events that you want the event handler to handle.</span></span>  
  
4.  <span data-ttu-id="cf4a9-110">코드 편집기는 적절 한 이벤트 처리기를 삽입 하 고 메서드 내에서 커서를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-110">The Code Editor inserts the appropriate event handler and positions the insertion point within the method.</span></span> <span data-ttu-id="cf4a9-111">에서는 아래 예제는 <xref:System.Windows.Forms.Control.Click> 에 대 한 이벤트를 <xref:System.Windows.Forms.Button> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-111">In the example below, it is the <xref:System.Windows.Forms.Control.Click> event for the <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5.  <span data-ttu-id="cf4a9-112">다른 이벤트를 처리를 추가 합니다 `Handles` 절.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-112">Append the other events you would like handled to the `Handles` clause.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6.  <span data-ttu-id="cf4a9-113">이벤트 처리기에 적절 한 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-113">Add the appropriate code to the event handler.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a><span data-ttu-id="cf4a9-114">C에서 단일 이벤트 처리기에 여러 이벤트 연결\#</span><span class="sxs-lookup"><span data-stu-id="cf4a9-114">To connect multiple events to a single event handler in C\#</span></span>
  
1.  <span data-ttu-id="cf4a9-115">이벤트 처리기를 연결 하려는 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-115">Select the control to which you want to connect an event handler.</span></span>  
  
2.  <span data-ttu-id="cf4a9-116">속성 창에서 클릭 합니다 **이벤트** 단추 (![이벤트 단추](./media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).</span><span class="sxs-lookup"><span data-stu-id="cf4a9-116">In the Properties window, click the **Events** button (![Events Button](./media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).</span></span>  
  
3.  <span data-ttu-id="cf4a9-117">처리 하려는 이벤트의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-117">Click the name of the event that you want to handle.</span></span>  
  
4.  <span data-ttu-id="cf4a9-118">이벤트 이름 옆에 있는 값 섹션에서 처리 하려는 이벤트의 메서드 시그니처와 일치 하는 기존 이벤트 처리기의 목록을 표시 하려면 드롭다운 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-118">In the value section next to the event name, click the drop-down button to display a list of existing event handlers that match the method signature of the event you want to handle.</span></span>  
  
5.  <span data-ttu-id="cf4a9-119">목록에서 적절 한 이벤트 처리기를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-119">Select the appropriate event handler from the list.</span></span>  
  
     <span data-ttu-id="cf4a9-120">코드는 이벤트에서 기존 이벤트 처리기를 바인딩할 폼에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf4a9-120">Code will be added to the form to bind the event to the existing event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf4a9-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="cf4a9-121">See also</span></span>
- [<span data-ttu-id="cf4a9-122">Windows Forms에서 이벤트 처리기 만들기</span><span class="sxs-lookup"><span data-stu-id="cf4a9-122">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="cf4a9-123">이벤트 처리기 개요</span><span class="sxs-lookup"><span data-stu-id="cf4a9-123">Event Handlers Overview</span></span>](event-handlers-overview-windows-forms.md)
