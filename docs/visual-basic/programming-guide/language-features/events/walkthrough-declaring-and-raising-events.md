---
title: 이벤트 선언 및 발생
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
ms.openlocfilehash: 6f4c303604f9cf55b4ecd500636e0d2772b6234c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345094"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a><span data-ttu-id="fe15f-102">연습: 이벤트 선언 및 발생(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe15f-102">Walkthrough: Declaring and Raising Events (Visual Basic)</span></span>
<span data-ttu-id="fe15f-103">이 연습에서는 `Widget`라는 클래스에 대 한 이벤트를 선언 하 고 발생 시키는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-103">This walkthrough demonstrates how to declare and raise events for a class named `Widget`.</span></span> <span data-ttu-id="fe15f-104">단계를 완료 한 후에는 `Widget` 개체의 이벤트를 사용 하 여 응용 프로그램에서 상태 정보를 제공 하는 방법을 보여 주는 [연습: 이벤트 처리](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)항목을 읽어 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-104">After you complete the steps, you might want to read the companion topic, [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), which shows how to use events from `Widget` objects to provide status information in an application.</span></span>  
  
## <a name="the-widget-class"></a><span data-ttu-id="fe15f-105">Widget 클래스</span><span class="sxs-lookup"><span data-stu-id="fe15f-105">The Widget Class</span></span>  
 <span data-ttu-id="fe15f-106">`Widget` 클래스가 있는 순간을 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-106">Assume for the moment that you have a `Widget` class.</span></span> <span data-ttu-id="fe15f-107">`Widget` 클래스에는 실행 하는 데 시간이 오래 걸릴 수 있는 메서드가 있으며 응용 프로그램에서 일종의 완성 표시기를 배치할 수 있도록 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-107">Your `Widget` class has a method that can take a long time to execute, and you want your application to be able to put up some kind of completion indicator.</span></span>  
  
 <span data-ttu-id="fe15f-108">물론 `Widget` 개체에 완료율 대화 상자를 표시할 수 있지만 `Widget` 클래스를 사용 하는 모든 프로젝트에서 해당 대화 상자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-108">Of course, you could make the `Widget` object show a percent-complete dialog box, but then you would be stuck with that dialog box in every project in which you used the `Widget` class.</span></span> <span data-ttu-id="fe15f-109">개체를 사용 하는 응용 프로그램은 폼 이나 대화 상자를 관리 하는 것이 아니라 개체를 사용 하는 응용 프로그램에서 사용자 인터페이스를 처리 하도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-109">A good principle of object design is to let the application that uses an object handle the user interface—unless the whole purpose of the object is to manage a form or dialog box.</span></span>  
  
 <span data-ttu-id="fe15f-110">`Widget`의 목적은 다른 작업을 수행 하는 것 이므로 `PercentDone` 이벤트를 추가 하 고 `Widget`의 메서드를 호출 하는 프로시저가 해당 이벤트를 처리 하 고 상태 업데이트를 표시 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-110">The purpose of `Widget` is to perform other tasks, so it is better to add a `PercentDone` event and let the procedure that calls `Widget`'s methods handle that event and display status updates.</span></span> <span data-ttu-id="fe15f-111">또한 `PercentDone` 이벤트는 작업을 취소 하는 메커니즘을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-111">The `PercentDone` event can also provide a mechanism for canceling the task.</span></span>  
  
#### <a name="to-build-the-code-example-for-this-topic"></a><span data-ttu-id="fe15f-112">이 항목에 대 한 코드 예제를 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="fe15f-112">To build the code example for this topic</span></span>  
  
1. <span data-ttu-id="fe15f-113">새 Visual Basic Windows 응용 프로그램 프로젝트를 열고 `Form1`라는 양식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-113">Open a new Visual Basic Windows Application project and create a form named `Form1`.</span></span>  
  
2. <span data-ttu-id="fe15f-114">`Form1`에 두 개의 단추와 레이블을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-114">Add two buttons and a label to `Form1`.</span></span>  
  
3. <span data-ttu-id="fe15f-115">다음 표에 나와 있는 것처럼 개체의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-115">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="fe15f-116">개체</span><span class="sxs-lookup"><span data-stu-id="fe15f-116">Object</span></span>|<span data-ttu-id="fe15f-117">속성</span><span class="sxs-lookup"><span data-stu-id="fe15f-117">Property</span></span>|<span data-ttu-id="fe15f-118">설정</span><span class="sxs-lookup"><span data-stu-id="fe15f-118">Setting</span></span>|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|<span data-ttu-id="fe15f-119">시작 태스크</span><span class="sxs-lookup"><span data-stu-id="fe15f-119">Start Task</span></span>|  
    |`Button2`|`Text`|<span data-ttu-id="fe15f-120">취소</span><span class="sxs-lookup"><span data-stu-id="fe15f-120">Cancel</span></span>|  
    |`Label`|<span data-ttu-id="fe15f-121">`(Name)`, `Text`</span><span class="sxs-lookup"><span data-stu-id="fe15f-121">`(Name)`, `Text`</span></span>|<span data-ttu-id="fe15f-122">lblPercentDone, 0</span><span class="sxs-lookup"><span data-stu-id="fe15f-122">lblPercentDone, 0</span></span>|  
  
4. <span data-ttu-id="fe15f-123">**프로젝트** 메뉴에서 **클래스 추가** 를 선택 하 여 `Widget.vb` 라는 클래스를 프로젝트에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-123">On the **Project** menu, choose **Add Class** to add a class named `Widget.vb` to the project.</span></span>  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a><span data-ttu-id="fe15f-124">Widget 클래스의 이벤트를 선언 하려면</span><span class="sxs-lookup"><span data-stu-id="fe15f-124">To declare an event for the Widget class</span></span>  
  
- <span data-ttu-id="fe15f-125">`Event` 키워드를 사용 하 여 `Widget` 클래스에서 이벤트를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-125">Use the `Event` keyword to declare an event in the `Widget` class.</span></span> <span data-ttu-id="fe15f-126">이벤트는 `Widget`의 `PercentDone` 이벤트에서 보여 주는 것 처럼 `ByVal` 및 `ByRef` 인수를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-126">Note that an event can have `ByVal` and `ByRef` arguments, as `Widget`'s `PercentDone` event demonstrates:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#1)]  
  
 <span data-ttu-id="fe15f-127">호출 하는 개체가 `PercentDone` 이벤트를 수신 하는 경우 `Percent` 인수에는 완료 된 작업의 백분율이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-127">When the calling object receives a `PercentDone` event, the `Percent` argument contains the percentage of the task that is complete.</span></span> <span data-ttu-id="fe15f-128">이벤트를 발생 시킨 메서드를 취소 하려면 `True`로 `Cancel` 인수를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-128">The `Cancel` argument can be set to `True` to cancel the method that raised the event.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fe15f-129">프로시저의 인수를 사용 하는 것과 같은 방법으로 이벤트 인수를 선언할 수 있습니다. 단, 이벤트는 `Optional` 또는 `ParamArray` 인수를 가질 수 없고 이벤트에 반환 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-129">You can declare event arguments just as you do arguments of procedures, with the following exceptions: Events cannot have `Optional` or `ParamArray` arguments, and events do not have return values.</span></span>  
  
 <span data-ttu-id="fe15f-130">`PercentDone` 이벤트는 `Widget` 클래스의 `LongTask` 메서드에 의해 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-130">The `PercentDone` event is raised by the `LongTask` method of the `Widget` class.</span></span> <span data-ttu-id="fe15f-131">`LongTask`는 두 개의 인수를 사용 합니다. 메서드가 작업을 수행 하는 시간을 lie 하 고 `LongTask` 하기 전의 최소 시간 간격을 사용 하 여 `PercentDone` 이벤트를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-131">`LongTask` takes two arguments: the length of time the method pretends to be doing work, and the minimum time interval before `LongTask` pauses to raise the `PercentDone` event.</span></span>  
  
#### <a name="to-raise-the-percentdone-event"></a><span data-ttu-id="fe15f-132">PercentDone 이벤트를 발생 시키려면</span><span class="sxs-lookup"><span data-stu-id="fe15f-132">To raise the PercentDone event</span></span>  
  
1. <span data-ttu-id="fe15f-133">이 클래스에서 사용 하는 `Timer` 속성에 대 한 액세스를 간소화 하려면 `Class Widget` 문 위의 클래스 모듈의 선언 섹션 맨 위에 `Imports` 문을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-133">To simplify access to the `Timer` property used by this class, add an `Imports` statement to the top of the declarations section of your class module, above the `Class Widget` statement.</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#2)]  
  
2. <span data-ttu-id="fe15f-134">`Widget` 클래스에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-134">Add the following code to the `Widget` class:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#3)]  
  
 <span data-ttu-id="fe15f-135">응용 프로그램이 `LongTask` 메서드를 호출 하면 `Widget` 클래스는 `MinimumInterval` 초 마다 `PercentDone` 이벤트를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-135">When your application calls the `LongTask` method, the `Widget` class raises the `PercentDone` event every `MinimumInterval` seconds.</span></span> <span data-ttu-id="fe15f-136">이벤트가 반환 될 때 `LongTask`는 `Cancel` 인수가 `True`로 설정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-136">When the event returns, `LongTask` checks to see if the `Cancel` argument was set to `True`.</span></span>  
  
 <span data-ttu-id="fe15f-137">여기에 몇 가지 법적 사항이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-137">A few disclaimers are necessary here.</span></span> <span data-ttu-id="fe15f-138">간단 하 게 하기 위해 `LongTask` 절차에서는 작업에 걸리는 시간을 미리 알고 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-138">For simplicity, the `LongTask` procedure assumes you know in advance how long the task will take.</span></span> <span data-ttu-id="fe15f-139">거의 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-139">This is almost never the case.</span></span> <span data-ttu-id="fe15f-140">작업을 짝수의 청크로 분할 하는 것은 어려울 수 있으며, 대부분의 경우 사용자에 게 가장 중요 한 것은 문제가 발생 했음을 표시 하기 전에 경과 하는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-140">Dividing tasks into chunks of even size can be difficult, and often what matters most to users is simply the amount of time that passes before they get an indication that something is happening.</span></span>  
  
 <span data-ttu-id="fe15f-141">이 샘플에서 다른 결함을 발견 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-141">You may have spotted another flaw in this sample.</span></span> <span data-ttu-id="fe15f-142">`Timer` 속성은 자정 이후 경과 된 시간 (초)을 반환 합니다. 따라서 응용 프로그램은 자정 직전에 시작 되는 경우 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-142">The `Timer` property returns the number of seconds that have passed since midnight; therefore, the application gets stuck if it is started just before midnight.</span></span> <span data-ttu-id="fe15f-143">보다 신중 하 게 시간을 측정 하는 방법은이를 고려 하거나 `Now`같은 속성을 사용 하 여 모두 사용 하지 않도록 하는 것과 같은 경계 조건을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-143">A more careful approach to measuring time would take boundary conditions such as this into consideration, or avoid them altogether, using properties such as `Now`.</span></span>  
  
 <span data-ttu-id="fe15f-144">이제 `Widget` 클래스가 이벤트를 발생 시킬 수 있으므로 다음 연습으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-144">Now that the `Widget` class can raise events, you can move to the next walkthrough.</span></span> <span data-ttu-id="fe15f-145">[연습: 이벤트 처리](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) 에서는 `WithEvents` 사용 하 여 이벤트 처리기를 `PercentDone` 이벤트와 연결 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fe15f-145">[Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) demonstrates how to use `WithEvents` to associate an event handler with the `PercentDone` event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe15f-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe15f-146">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [<span data-ttu-id="fe15f-147">연습: 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="fe15f-147">Walkthrough: Handling Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)
- [<span data-ttu-id="fe15f-148">이벤트</span><span class="sxs-lookup"><span data-stu-id="fe15f-148">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
