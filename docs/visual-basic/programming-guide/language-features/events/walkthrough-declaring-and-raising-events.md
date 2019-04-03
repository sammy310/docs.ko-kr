---
title: 선언 및 발생 이벤트 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
ms.openlocfilehash: 0f48c90232c00f53007e7d2f8f08e2107406ecad
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841006"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a><span data-ttu-id="86aef-102">연습: 선언 및 발생 이벤트 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="86aef-102">Walkthrough: Declaring and Raising Events (Visual Basic)</span></span>
<span data-ttu-id="86aef-103">이 연습에는 선언 하 고 라는 클래스에 이벤트를 발생 하는 방법을 보여 줍니다. `Widget`합니다.</span><span class="sxs-lookup"><span data-stu-id="86aef-103">This walkthrough demonstrates how to declare and raise events for a class named `Widget`.</span></span> <span data-ttu-id="86aef-104">항목을 참고할 하려는 단계를 완료 하면 [연습: 이벤트 처리](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)에서 이벤트를 사용 하는 방법을 보여 주는 `Widget` 응용 프로그램에서 상태 정보를 제공 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="86aef-104">After you complete the steps, you might want to read the companion topic, [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), which shows how to use events from `Widget` objects to provide status information in an application.</span></span>  
  
## <a name="the-widget-class"></a><span data-ttu-id="86aef-105">위젯 클래스</span><span class="sxs-lookup"><span data-stu-id="86aef-105">The Widget Class</span></span>  
 <span data-ttu-id="86aef-106">해야 하는 순간에 대 한 가정 된 `Widget` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="86aef-106">Assume for the moment that you have a `Widget` class.</span></span> <span data-ttu-id="86aef-107">프로그램 `Widget` 일종의 완료 표시기 나타내려고 할 수 있는 응용 프로그램 및 클래스에 메서드를 실행 하는 데 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86aef-107">Your `Widget` class has a method that can take a long time to execute, and you want your application to be able to put up some kind of completion indicator.</span></span>  
  
 <span data-ttu-id="86aef-108">물론, 만들 수 있습니다는 `Widget` 개체 완료율 대화 상자를 표시 한 다음 할 수 있지만 수 이후에를 사용 하는 모든 프로젝트에서이 대화 상자는 `Widget` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="86aef-108">Of course, you could make the `Widget` object show a percent-complete dialog box, but then you would be stuck with that dialog box in every project in which you used the `Widget` class.</span></span> <span data-ttu-id="86aef-109">사용자 인터페이스 개체 핸들을 사용 하는 응용 프로그램에 개체를 디자인 하는 좋은 원칙-경우에 개체의 전체 목적은 양식 또는 대화 상자를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="86aef-109">A good principle of object design is to let the application that uses an object handle the user interface—unless the whole purpose of the object is to manage a form or dialog box.</span></span>  
  
 <span data-ttu-id="86aef-110">목적은 `Widget` 추가 하는 것 이므로 다른 작업을 수행 하는 것을 `PercentDone` 이벤트 및 호출 하는 프로시저를 통해 `Widget`의 메서드는 처리할 이벤트 및 표시 상태를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="86aef-110">The purpose of `Widget` is to perform other tasks, so it is better to add a `PercentDone` event and let the procedure that calls `Widget`'s methods handle that event and display status updates.</span></span> <span data-ttu-id="86aef-111">`PercentDone` 이벤트에서 작업을 취소 메커니즘을 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86aef-111">The `PercentDone` event can also provide a mechanism for canceling the task.</span></span>  
  
#### <a name="to-build-the-code-example-for-this-topic"></a><span data-ttu-id="86aef-112">이 항목에 대 한 코드 예제를 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="86aef-112">To build the code example for this topic</span></span>  
  
1.  <span data-ttu-id="86aef-113">새 Visual Basic Windows 응용 프로그램 프로젝트를 열고 이라는 양식을 만듭니다 `Form1`합니다.</span><span class="sxs-lookup"><span data-stu-id="86aef-113">Open a new Visual Basic Windows Application project and create a form named `Form1`.</span></span>  
  
2.  <span data-ttu-id="86aef-114">두 개의 단추 및 레이블을 추가 `Form1`합니다.</span><span class="sxs-lookup"><span data-stu-id="86aef-114">Add two buttons and a label to `Form1`.</span></span>  
  
3.  <span data-ttu-id="86aef-115">다음 표에 나와 있는 것처럼 개체의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="86aef-115">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="86aef-116">개체</span><span class="sxs-lookup"><span data-stu-id="86aef-116">Object</span></span>|<span data-ttu-id="86aef-117">속성</span><span class="sxs-lookup"><span data-stu-id="86aef-117">Property</span></span>|<span data-ttu-id="86aef-118">설정</span><span class="sxs-lookup"><span data-stu-id="86aef-118">Setting</span></span>|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|<span data-ttu-id="86aef-119">시작 태스크</span><span class="sxs-lookup"><span data-stu-id="86aef-119">Start Task</span></span>|  
    |`Button2`|`Text`|<span data-ttu-id="86aef-120">취소</span><span class="sxs-lookup"><span data-stu-id="86aef-120">Cancel</span></span>|  
    |`Label`|<span data-ttu-id="86aef-121">`(Name)`, `Text`</span><span class="sxs-lookup"><span data-stu-id="86aef-121">`(Name)`, `Text`</span></span>|<span data-ttu-id="86aef-122">lblPercentDone, 0</span><span class="sxs-lookup"><span data-stu-id="86aef-122">lblPercentDone, 0</span></span>|  
  
4.  <span data-ttu-id="86aef-123">에 **프로젝트** 메뉴 선택 **클래스 추가** 라는 클래스를 추가 하려면 `Widget.vb` 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="86aef-123">On the **Project** menu, choose **Add Class** to add a class named `Widget.vb` to the project.</span></span>  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a><span data-ttu-id="86aef-124">위젯 클래스에 대 한 이벤트를 선언 하려면</span><span class="sxs-lookup"><span data-stu-id="86aef-124">To declare an event for the Widget class</span></span>  
  
-   <span data-ttu-id="86aef-125">사용 된 `Event` 에서 이벤트를 선언 하는 키워드는 `Widget` 클래스.</span><span class="sxs-lookup"><span data-stu-id="86aef-125">Use the `Event` keyword to declare an event in the `Widget` class.</span></span> <span data-ttu-id="86aef-126">이벤트 않았을 수 있습니다 `ByVal` 하 고 `ByRef` 인수를으로 `Widget`의 `PercentDone` 이벤트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="86aef-126">Note that an event can have `ByVal` and `ByRef` arguments, as `Widget`'s `PercentDone` event demonstrates:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#1)]  
  
 <span data-ttu-id="86aef-127">호출 하는 개체를 받으면를 `PercentDone` 이벤트는 `Percent` 인수 완료 된 작업의 백분율을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="86aef-127">When the calling object receives a `PercentDone` event, the `Percent` argument contains the percentage of the task that is complete.</span></span> <span data-ttu-id="86aef-128">`Cancel` 인수 설정할 수 있습니다 `True` 이벤트를 발생 시킨 메서드를 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="86aef-128">The `Cancel` argument can be set to `True` to cancel the method that raised the event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="86aef-129">다음 예외를 사용 하 여 프로시저의 인수를 수행 하는 것 처럼 이벤트 인수를 선언할 수 있습니다. 이벤트를 사용할 수 없습니다 `Optional` 또는 `ParamArray` 인수와 이벤트 반환 값이 없는 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="86aef-129">You can declare event arguments just as you do arguments of procedures, with the following exceptions: Events cannot have `Optional` or `ParamArray` arguments, and events do not have return values.</span></span>  
  
 <span data-ttu-id="86aef-130">`PercentDone` 이벤트를 발생 합니다 `LongTask` 메서드를 `Widget` 클래스.</span><span class="sxs-lookup"><span data-stu-id="86aef-130">The `PercentDone` event is raised by the `LongTask` method of the `Widget` class.</span></span> <span data-ttu-id="86aef-131">`LongTask` 두 개의 인수: 기간 메서드 프로세스로 작업과 하기 전의 최소 시간 간격을 수행할 수 `LongTask` 일시 중지 시키려면는 `PercentDone` 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="86aef-131">`LongTask` takes two arguments: the length of time the method pretends to be doing work, and the minimum time interval before `LongTask` pauses to raise the `PercentDone` event.</span></span>  
  
#### <a name="to-raise-the-percentdone-event"></a><span data-ttu-id="86aef-132">PercentDone 이벤트 발생</span><span class="sxs-lookup"><span data-stu-id="86aef-132">To raise the PercentDone event</span></span>  
  
1.  <span data-ttu-id="86aef-133">에 대 한 액세스를 간소화 하는 `Timer` 이 클래스에 의해 사용 되는 속성 추가 `Imports` 클래스 모듈의 선언 섹션의 맨 위에 문을 위에 `Class Widget` 문.</span><span class="sxs-lookup"><span data-stu-id="86aef-133">To simplify access to the `Timer` property used by this class, add an `Imports` statement to the top of the declarations section of your class module, above the `Class Widget` statement.</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#2)]  
  
2.  <span data-ttu-id="86aef-134">`Widget` 클래스에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="86aef-134">Add the following code to the `Widget` class:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#3)]  
  
 <span data-ttu-id="86aef-135">응용 프로그램 호출 하는 경우는 `LongTask` 메서드를 `Widget` 클래스에서 발생 시키는 `PercentDone` 이벤트 모든 `MinimumInterval` 시간 (초).</span><span class="sxs-lookup"><span data-stu-id="86aef-135">When your application calls the `LongTask` method, the `Widget` class raises the `PercentDone` event every `MinimumInterval` seconds.</span></span> <span data-ttu-id="86aef-136">이 이벤트는 반환 될 때 `LongTask` 확인 하는 `Cancel` 인수 설정한 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="86aef-136">When the event returns, `LongTask` checks to see if the `Cancel` argument was set to `True`.</span></span>  
  
 <span data-ttu-id="86aef-137">몇 가지 한계는 여기에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="86aef-137">A few disclaimers are necessary here.</span></span> <span data-ttu-id="86aef-138">간단히 하기 위해는 `LongTask` 절차를 이미 아는 작업은 얼마나 걸리나요 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="86aef-138">For simplicity, the `LongTask` procedure assumes you know in advance how long the task will take.</span></span> <span data-ttu-id="86aef-139">이 경우 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="86aef-139">This is almost never the case.</span></span> <span data-ttu-id="86aef-140">작업 짝수 크기의 청크로 분할 것이 어려울 수 있으며 종종 가장 중요 한 사용자에 게는 단순히 표시 하는 상황이 이르기 전에 경과 되는 시간.</span><span class="sxs-lookup"><span data-stu-id="86aef-140">Dividing tasks into chunks of even size can be difficult, and often what matters most to users is simply the amount of time that passes before they get an indication that something is happening.</span></span>  
  
 <span data-ttu-id="86aef-141">이 샘플에서 다른 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86aef-141">You may have spotted another flaw in this sample.</span></span> <span data-ttu-id="86aef-142">`Timer` 자정 직전 시작 된 경우 응용 프로그램 중지 되므로; 속성 자정 이후 경과한 시간 (초) 수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="86aef-142">The `Timer` property returns the number of seconds that have passed since midnight; therefore, the application gets stuck if it is started just before midnight.</span></span> <span data-ttu-id="86aef-143">시간 측정에 보다 신중한 접근을 고려해 야 할 다음과 같은 경계 조건 하거나 피하도록와 같은 속성을 사용 하는 `Now`합니다.</span><span class="sxs-lookup"><span data-stu-id="86aef-143">A more careful approach to measuring time would take boundary conditions such as this into consideration, or avoid them altogether, using properties such as `Now`.</span></span>  
  
 <span data-ttu-id="86aef-144">이제는 `Widget` 클래스 이벤트 발생 수를 이동할 수 있습니다 다음 연습 합니다.</span><span class="sxs-lookup"><span data-stu-id="86aef-144">Now that the `Widget` class can raise events, you can move to the next walkthrough.</span></span> <span data-ttu-id="86aef-145">[연습: 이벤트 처리](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) 사용 하는 방법을 보여 줍니다 `WithEvents` 사용 하 여 이벤트 처리기를 연결 하는 `PercentDone` 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="86aef-145">[Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) demonstrates how to use `WithEvents` to associate an event handler with the `PercentDone` event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86aef-146">참고자료</span><span class="sxs-lookup"><span data-stu-id="86aef-146">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [<span data-ttu-id="86aef-147">연습: 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="86aef-147">Walkthrough: Handling Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)
- [<span data-ttu-id="86aef-148">이벤트</span><span class="sxs-lookup"><span data-stu-id="86aef-148">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
