---
title: '방법: 단일 이벤트 처리기에 여러 이벤트 연결'
description: 'C #에서 속성 창의 이벤트 뷰를 사용 하 여 Windows Forms에서 단일 이벤트 처리기에 여러 이벤트를 연결 하는 방법에 대해 알아봅니다.'
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
ms.openlocfilehash: cca85c223b46d9a82dbc3e34e3377fb83c075959
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621888"
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a><span data-ttu-id="a138f-103">방법: Windows Forms에서 단일 이벤트 처리기에 여러 이벤트 연결</span><span class="sxs-lookup"><span data-stu-id="a138f-103">How to: Connect Multiple Events to a Single Event Handler in Windows Forms</span></span>
<span data-ttu-id="a138f-104">응용 프로그램 디자인에서 여러 이벤트에 대해 단일 이벤트 처리기를 사용 해야 하거나 여러 이벤트에서 동일한 절차를 수행 해야 하는 경우가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a138f-104">In your application design, you may find it necessary to use a single event handler for multiple events or have multiple events perform the same procedure.</span></span> <span data-ttu-id="a138f-105">예를 들어, 동일한 기능을 노출 하는 경우 메뉴 명령에서 폼의 단추와 동일한 이벤트를 발생 시 키도 록 하는 것이 효과적입니다.</span><span class="sxs-lookup"><span data-stu-id="a138f-105">For example, it is often a powerful time-saver to have a menu command raise the same event as a button on your form does if they expose the same functionality.</span></span> <span data-ttu-id="a138f-106">이렇게 하려면 c #에서 속성 창의 이벤트 뷰를 사용 하거나 `Handles` Visual Basic 코드 편집기에서 키워드 및 **클래스 이름** 및 **메서드 이름** 드롭다운 상자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a138f-106">You can do this by using the Events view of the Properties window in C# or using the `Handles` keyword and the **Class Name** and **Method Name** drop-down boxes in the Visual Basic Code Editor.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a><span data-ttu-id="a138f-107">Visual Basic에서 단일 이벤트 처리기에 여러 이벤트를 연결 하려면</span><span class="sxs-lookup"><span data-stu-id="a138f-107">To connect multiple events to a single event handler in Visual Basic</span></span>  
  
1. <span data-ttu-id="a138f-108">폼을 마우스 오른쪽 단추로 클릭 하 고 **코드 보기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a138f-108">Right-click the form and choose **View Code**.</span></span>  
  
2. <span data-ttu-id="a138f-109">**클래스 이름** 드롭다운 상자에서 이벤트 처리기를 처리 하려는 컨트롤 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a138f-109">From the **Class Name** drop-down box, select one of the controls that you want to have the event handler handle.</span></span>  
  
3. <span data-ttu-id="a138f-110">**메서드 이름** 드롭다운 상자에서 이벤트 처리기가 처리할 이벤트 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a138f-110">From the **Method Name** drop-down box, select one of the events that you want the event handler to handle.</span></span>  
  
4. <span data-ttu-id="a138f-111">코드 편집기는 적절 한 이벤트 처리기를 삽입 하 고 메서드 내에 삽입 지점을 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a138f-111">The Code Editor inserts the appropriate event handler and positions the insertion point within the method.</span></span> <span data-ttu-id="a138f-112">아래 예제에서는 <xref:System.Windows.Forms.Control.Click> 컨트롤에 대 한 이벤트입니다 <xref:System.Windows.Forms.Button> .</span><span class="sxs-lookup"><span data-stu-id="a138f-112">In the example below, it is the <xref:System.Windows.Forms.Control.Click> event for the <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5. <span data-ttu-id="a138f-113">처리 하려는 다른 이벤트를 절에 추가 합니다 `Handles` .</span><span class="sxs-lookup"><span data-stu-id="a138f-113">Append the other events you would like handled to the `Handles` clause.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6. <span data-ttu-id="a138f-114">이벤트 처리기에 적절 한 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a138f-114">Add the appropriate code to the event handler.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a><span data-ttu-id="a138f-115">C에서 단일 이벤트 처리기에 여러 이벤트를 연결 하려면\#</span><span class="sxs-lookup"><span data-stu-id="a138f-115">To connect multiple events to a single event handler in C\#</span></span>
  
1. <span data-ttu-id="a138f-116">이벤트 처리기를 연결 하려는 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a138f-116">Select the control to which you want to connect an event handler.</span></span>  
  
2. <span data-ttu-id="a138f-117">속성 창에서 **이벤트** 단추 (![이벤트 단추](./media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow"))를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a138f-117">In the Properties window, click the **Events** button (![Events Button](./media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).</span></span>  
  
3. <span data-ttu-id="a138f-118">처리 하려는 이벤트의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a138f-118">Click the name of the event that you want to handle.</span></span>  
  
4. <span data-ttu-id="a138f-119">이벤트 이름 옆의 값 섹션에서 드롭다운 단추를 클릭 하 여 처리 하려는 이벤트의 메서드 시그니처와 일치 하는 기존 이벤트 처리기의 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a138f-119">In the value section next to the event name, click the drop-down button to display a list of existing event handlers that match the method signature of the event you want to handle.</span></span>  
  
5. <span data-ttu-id="a138f-120">목록에서 적절 한 이벤트 처리기를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a138f-120">Select the appropriate event handler from the list.</span></span>  
  
     <span data-ttu-id="a138f-121">기존 이벤트 처리기에 이벤트를 바인딩하기 위해 코드를 폼에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a138f-121">Code will be added to the form to bind the event to the existing event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a138f-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a138f-122">See also</span></span>

- [<span data-ttu-id="a138f-123">Windows Forms에서 이벤트 처리기 만들기</span><span class="sxs-lookup"><span data-stu-id="a138f-123">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="a138f-124">이벤트 처리기 개요</span><span class="sxs-lookup"><span data-stu-id="a138f-124">Event Handlers Overview</span></span>](event-handlers-overview-windows-forms.md)
