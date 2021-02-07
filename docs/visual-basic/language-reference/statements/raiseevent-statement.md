---
description: '자세한 정보: RaiseEvent 문'
title: RaiseEvent 문
ms.date: 07/20/2015
f1_keywords:
- vb.RaiseEventMethod
- vb.RaiseEvent
- RaiseEvent
helpviewer_keywords:
- raising events [Visual Basic], RaiseEvent statement
- RaiseEvent statement [Visual Basic]
- event handlers, connecting events to
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
ms.openlocfilehash: 9549eb64ef32147ed49ae8f805d01db8610b336e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741343"
---
# <a name="raiseevent-statement"></a><span data-ttu-id="71970-103">RaiseEvent 문</span><span class="sxs-lookup"><span data-stu-id="71970-103">RaiseEvent Statement</span></span>

<span data-ttu-id="71970-104">클래스, 폼 또는 문서 내의 모듈 수준에서 선언 된 이벤트를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="71970-104">Triggers an event declared at module level within a class, form, or document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71970-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="71970-105">Syntax</span></span>  
  
```vb  
RaiseEvent eventname[( argumentlist )]  
```  
  
## <a name="parts"></a><span data-ttu-id="71970-106">부분</span><span class="sxs-lookup"><span data-stu-id="71970-106">Parts</span></span>  

 `eventname`  
 <span data-ttu-id="71970-107">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="71970-107">Required.</span></span> <span data-ttu-id="71970-108">트리거할 이벤트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="71970-108">Name of the event to trigger.</span></span>  
  
 `argumentlist`  
 <span data-ttu-id="71970-109">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="71970-109">Optional.</span></span> <span data-ttu-id="71970-110">쉼표로 구분 된 변수, 배열 또는 식 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="71970-110">Comma-delimited list of variables, arrays, or expressions.</span></span> <span data-ttu-id="71970-111">`argumentlist`인수는 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71970-111">The `argumentlist` argument must be enclosed by parentheses.</span></span> <span data-ttu-id="71970-112">인수가 없으면 괄호를 생략 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71970-112">If there are no arguments, the parentheses must be omitted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71970-113">설명</span><span class="sxs-lookup"><span data-stu-id="71970-113">Remarks</span></span>  

 <span data-ttu-id="71970-114">필수는 `eventname` 모듈 내에서 선언 된 이벤트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="71970-114">The required `eventname` is the name of an event declared within the module.</span></span> <span data-ttu-id="71970-115">Visual Basic 변수 명명 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="71970-115">It follows Visual Basic variable naming conventions.</span></span>  
  
 <span data-ttu-id="71970-116">이벤트가 발생 하는 모듈 내에서 선언 되지 않은 경우 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="71970-116">If the event has not been declared within the module in which it is raised, an error occurs.</span></span> <span data-ttu-id="71970-117">다음 코드 조각에서는 이벤트 선언 및 이벤트가 발생 하는 프로시저를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="71970-117">The following code fragment illustrates an event declaration and a procedure in which the event is raised.</span></span>  
  
 [!code-vb[VbVbalrEvents#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#37)]  
  
 <span data-ttu-id="71970-118">`RaiseEvent`를 사용 하 여 모듈에서 명시적으로 선언 되지 않은 이벤트를 발생 시킬 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71970-118">You cannot use `RaiseEvent` to raise events that are not explicitly declared in the module.</span></span> <span data-ttu-id="71970-119">예를 들어 모든 폼이에서 이벤트를 상속 하는 경우 <xref:System.Windows.Forms.Control.Click> <xref:System.Windows.Forms.Form?displayProperty=nameWithType> 파생 된 폼에서를 사용 하 여이 이벤트를 발생 시킬 수 없습니다 `RaiseEvent` .</span><span class="sxs-lookup"><span data-stu-id="71970-119">For example, all forms inherit a <xref:System.Windows.Forms.Control.Click> event from <xref:System.Windows.Forms.Form?displayProperty=nameWithType>, it cannot be raised using `RaiseEvent` in a derived form.</span></span> <span data-ttu-id="71970-120">폼 모듈에서 이벤트를 선언 하는 경우 `Click` 폼의 자체 이벤트를 숨깁니다 <xref:System.Windows.Forms.Control.Click> .</span><span class="sxs-lookup"><span data-stu-id="71970-120">If you declare a `Click` event in the form module, it shadows the form's own <xref:System.Windows.Forms.Control.Click> event.</span></span> <span data-ttu-id="71970-121"><xref:System.Windows.Forms.Control.Click>메서드를 호출 하 여 폼의 이벤트를 여전히 호출할 수 있습니다 <xref:System.Windows.Forms.Control.OnClick%2A> .</span><span class="sxs-lookup"><span data-stu-id="71970-121">You can still invoke the form's <xref:System.Windows.Forms.Control.Click> event by calling the <xref:System.Windows.Forms.Control.OnClick%2A> method.</span></span>  
  
 <span data-ttu-id="71970-122">기본적으로 Visual Basic에 정의 된 이벤트는 연결이 설정 된 순서 대로 이벤트 처리기를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="71970-122">By default, an event defined in Visual Basic raises its event handlers in the order that the connections are established.</span></span> <span data-ttu-id="71970-123">이벤트는 매개 변수를 가질 수 있기 때문에 `ByRef` 런타임에 연결 하는 프로세스는 이전 이벤트 처리기에 의해 변경 된 매개 변수를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71970-123">Because events can have `ByRef` parameters, a process that connects late may receive parameters that have been changed by an earlier event handler.</span></span> <span data-ttu-id="71970-124">이벤트 처리기가 실행 된 후에는 이벤트가 발생 한 서브루틴으로 제어가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71970-124">After the event handlers execute, control is returned to the subroutine that raised the event.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="71970-125">비공유 이벤트는 선언 된 클래스의 생성자 내에서 발생 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71970-125">Non-shared events should not be raised within the constructor of the class in which they are declared.</span></span> <span data-ttu-id="71970-126">이러한 이벤트는 런타임 오류를 발생 시 키 지 않지만 연결 된 이벤트 처리기가 이러한 이벤트를 catch 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71970-126">Although such events do not cause run-time errors, they may fail to be caught by associated event handlers.</span></span> <span data-ttu-id="71970-127">`Shared`생성자에서 이벤트를 발생 시켜야 하는 경우 한정자를 사용 하 여 공유 이벤트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="71970-127">Use the `Shared` modifier to create a shared event if you need to raise an event from a constructor.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="71970-128">사용자 지정 이벤트를 정의 하 여 이벤트의 기본 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71970-128">You can change the default behavior of events by defining a custom event.</span></span> <span data-ttu-id="71970-129">사용자 지정 이벤트의 경우 `RaiseEvent` 문은 이벤트의 접근자를 호출 합니다 `RaiseEvent` .</span><span class="sxs-lookup"><span data-stu-id="71970-129">For custom events, the `RaiseEvent` statement invokes the event's `RaiseEvent` accessor.</span></span> <span data-ttu-id="71970-130">사용자 지정 이벤트에 대 한 자세한 내용은 [이벤트 문](event-statement.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="71970-130">For more information on custom events, see [Event Statement](event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="71970-131">예제</span><span class="sxs-lookup"><span data-stu-id="71970-131">Example</span></span>  

 <span data-ttu-id="71970-132">다음 예제에서는 이벤트를 사용하여 10초부터 0초까지 카운트 다운합니다.</span><span class="sxs-lookup"><span data-stu-id="71970-132">The following example uses events to count down seconds from 10 to 0.</span></span> <span data-ttu-id="71970-133">이 코드는 문을 포함 하 여 몇 가지 이벤트 관련 메서드, 속성 및 문을 보여 줍니다 `RaiseEvent` .</span><span class="sxs-lookup"><span data-stu-id="71970-133">The code illustrates several of the event-related methods, properties, and statements, including the `RaiseEvent` statement.</span></span>  
  
 <span data-ttu-id="71970-134">이벤트를 발생시키는 클래스는 이벤트 소스이고 이벤트를 처리하는 메서드는 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="71970-134">The class that raises an event is the event source, and the methods that process the event are the event handlers.</span></span> <span data-ttu-id="71970-135">이벤트 소스는 생성되는 이벤트에 대해 여러 개의 처리기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71970-135">An event source can have multiple handlers for the events it generates.</span></span> <span data-ttu-id="71970-136">클래스에서 이벤트를 발생시키면 해당 이벤트는 개체의 해당 인스턴스에 대해 이벤트를 처리하도록 선택한 모든 클래스에서 발생됩니다.</span><span class="sxs-lookup"><span data-stu-id="71970-136">When the class raises the event, that event is raised on every class that has elected to handle events for that instance of the object.</span></span>  
  
 <span data-ttu-id="71970-137">또한 이 예제에서는 단추(`Button1`)와 텍스트 상자(`TextBox1`)가 있는 폼(`Form1`)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="71970-137">The example also uses a form (`Form1`) with a button (`Button1`) and a text box (`TextBox1`).</span></span> <span data-ttu-id="71970-138">단추를 클릭하면 첫 번째 텍스트 상자에 10초부터 0초까지의 카운트 다운이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="71970-138">When you click the button, the first text box displays a countdown from 10 to 0 seconds.</span></span> <span data-ttu-id="71970-139">전체 시간(10초)이 경과되면 첫 번째 텍스트 상자에 "Done"이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="71970-139">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
 <span data-ttu-id="71970-140">`Form1`에 대한 코드는 폼의 초기 상태 및 최종 상태를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="71970-140">The code for `Form1` specifies the initial and terminal states of the form.</span></span> <span data-ttu-id="71970-141">또한 이벤트가 발생될 때 실행될 코드도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="71970-141">It also contains the code executed when events are raised.</span></span>  
  
 <span data-ttu-id="71970-142">이 예제를 사용 하려면 새 Windows 응용 프로그램 프로젝트를 열고 이라는 단추와 이라는 `Button1` 텍스트 상자를 `TextBox1` 이라는 기본 폼에 추가 `Form1` 합니다.</span><span class="sxs-lookup"><span data-stu-id="71970-142">To use this example, open a new Windows Application project, add a button named `Button1` and a text box named `TextBox1` to the main form, named `Form1`.</span></span> <span data-ttu-id="71970-143">그런 다음 폼을 마우스 오른쪽 단추로 클릭 하 고 **코드 보기** 를 클릭 하 여 코드 편집기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="71970-143">Then right-click the form and click **View Code** to open the Code Editor.</span></span>  
  
 <span data-ttu-id="71970-144">`WithEvents`클래스의 선언 섹션에 변수를 추가 `Form1` 합니다.</span><span class="sxs-lookup"><span data-stu-id="71970-144">Add a `WithEvents` variable to the declarations section of the `Form1` class.</span></span>  
  
 [!code-vb[VbVbalrEvents#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="71970-145">예제</span><span class="sxs-lookup"><span data-stu-id="71970-145">Example</span></span>  

 <span data-ttu-id="71970-146">`Form1`에 대한 코드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="71970-146">Add the following code to the code for `Form1`.</span></span> <span data-ttu-id="71970-147">또는와 같이 존재할 수 있는 모든 중복 프로시저를 바꿉니다 `Form_Load` `Button_Click` .</span><span class="sxs-lookup"><span data-stu-id="71970-147">Replace any duplicate procedures that may exist, such as `Form_Load`, or `Button_Click`.</span></span>  
  
 [!code-vb[VbVbalrEvents#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#15)]  
  
 <span data-ttu-id="71970-148">F5 키를 눌러 앞의 예제를 실행 하 고 **시작** 이라는 레이블이 지정 된 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="71970-148">Press F5 to run the preceding example, and click the button labeled **Start**.</span></span> <span data-ttu-id="71970-149">첫 번째 텍스트 상자에서 초를 카운트 다운하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="71970-149">The first text box starts to count down the seconds.</span></span> <span data-ttu-id="71970-150">전체 시간(10초)이 경과되면 첫 번째 텍스트 상자에 "Done"이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="71970-150">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="71970-151">`My.Application.DoEvents`메서드는 양식이 수행 하는 것과 정확히 같은 방식으로 이벤트를 처리 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71970-151">The `My.Application.DoEvents` method does not process events in exactly the same way as the form does.</span></span> <span data-ttu-id="71970-152">폼에서 이벤트를 직접 처리할 수 있도록 하려면 다중 스레딩을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71970-152">To allow the form to handle the events directly, you can use multithreading.</span></span> <span data-ttu-id="71970-153">자세한 내용은 [관리 되는 스레딩](../../../standard/threading/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="71970-153">For more information, see [Managed Threading](../../../standard/threading/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71970-154">참조</span><span class="sxs-lookup"><span data-stu-id="71970-154">See also</span></span>

- [<span data-ttu-id="71970-155">이벤트</span><span class="sxs-lookup"><span data-stu-id="71970-155">Events</span></span>](../../programming-guide/language-features/events/index.md)
- [<span data-ttu-id="71970-156">Event 문</span><span class="sxs-lookup"><span data-stu-id="71970-156">Event Statement</span></span>](event-statement.md)
- [<span data-ttu-id="71970-157">AddHandler 문</span><span class="sxs-lookup"><span data-stu-id="71970-157">AddHandler Statement</span></span>](addhandler-statement.md)
- [<span data-ttu-id="71970-158">RemoveHandler 문</span><span class="sxs-lookup"><span data-stu-id="71970-158">RemoveHandler Statement</span></span>](removehandler-statement.md)
- [<span data-ttu-id="71970-159">핸들</span><span class="sxs-lookup"><span data-stu-id="71970-159">Handles</span></span>](handles-clause.md)
