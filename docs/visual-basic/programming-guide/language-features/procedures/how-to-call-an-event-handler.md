---
title: '방법: Visual Basic의 이벤트 처리기를 호출 합니다.'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
ms.openlocfilehash: 3690d1c2eb8ece9059b8b25b5a14bef2021bc8f6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59320173"
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a><span data-ttu-id="20bc5-102">방법: Visual Basic의 이벤트 처리기를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="20bc5-102">How to: Call an Event Handler in Visual Basic</span></span>
<span data-ttu-id="20bc5-103">*이벤트* 작업 또는 항목은-같은 마우스 클릭 이나 신용 한도 초과-응답 코드를 작성할 수 있는 한 일부 프로그램 구성 요소에 의해 인식 합니다.</span><span class="sxs-lookup"><span data-stu-id="20bc5-103">An *event* is an action or occurrence — such as a mouse click or a credit limit exceeded — that is recognized by some program component, and for which you can write code to respond.</span></span> <span data-ttu-id="20bc5-104">*이벤트 처리기* 이벤트에 응답을 작성 하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="20bc5-104">An *event handler* is the code you write to respond to an event.</span></span>  
  
 <span data-ttu-id="20bc5-105">Visual Basic의 이벤트 처리기는는 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="20bc5-105">An event handler in Visual Basic is a `Sub` procedure.</span></span> <span data-ttu-id="20bc5-106">그러나 호출 하지 않으면 일반적으로 동일한 방식으로 다른 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="20bc5-106">However, you do not normally call it the same way as other `Sub` procedures.</span></span> <span data-ttu-id="20bc5-107">대신, 이벤트 처리기로 프로시저를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="20bc5-107">Instead, you identify the procedure as a handler for the event.</span></span> <span data-ttu-id="20bc5-108">이렇게 하려면 사용 하 여는 [처리](../../../../visual-basic/language-reference/statements/handles-clause.md) 절 및 [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) 변수를 또는 [AddHandler 문](../../../../visual-basic/language-reference/statements/addhandler-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="20bc5-108">You can do this either with a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause and a [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) variable, or with an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="20bc5-109">사용 하는 `Handles` 절은 Visual Basic의 이벤트 처리기를 선언 하는 기본 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="20bc5-109">Using a `Handles` clause is the default way to declare an event handler in Visual Basic.</span></span> <span data-ttu-id="20bc5-110">이 방법은 이벤트 처리기는 통합된 개발 환경 (IDE)에서 프로그래밍할 때 디자이너에서 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20bc5-110">This is the way the event handlers are written by the designers when you program in the integrated development environment (IDE).</span></span> <span data-ttu-id="20bc5-111">`AddHandler` 문을 런타임에 동적으로 이벤트를 발생 시키기에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="20bc5-111">The `AddHandler` statement is suitable for raising events dynamically at run time.</span></span>  
  
 <span data-ttu-id="20bc5-112">이벤트가 발생할 때 Visual Basic에서는 이벤트 처리기 프로시저를 자동으로 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="20bc5-112">When the event occurs, Visual Basic automatically calls the event handler procedure.</span></span> <span data-ttu-id="20bc5-113">이벤트에 대 한 액세스 권한이 있는 모든 코드를 사용 하면 실행 하 여 발생 하는 [RaiseEvent 문](../../../../visual-basic/language-reference/statements/raiseevent-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="20bc5-113">Any code that has access to the event can cause it to occur by executing a [RaiseEvent Statement](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span></span>  
  
 <span data-ttu-id="20bc5-114">동일한 이벤트를 사용 하 여 둘 이상의 이벤트 처리기를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20bc5-114">You can associate more than one event handler with the same event.</span></span> <span data-ttu-id="20bc5-115">경우에 따라 이벤트에서 처리기를 분리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20bc5-115">In some cases you can dissociate a handler from an event.</span></span> <span data-ttu-id="20bc5-116">자세한 내용은 [이벤트](../../../../visual-basic/programming-guide/language-features/events/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="20bc5-116">For more information, see [Events](../../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>  
  
### <a name="to-call-an-event-handler-using-handles-and-withevents"></a><span data-ttu-id="20bc5-117">WithEvents 및 처리를 사용 하 여 이벤트 처리기를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="20bc5-117">To call an event handler using Handles and WithEvents</span></span>  
  
1. <span data-ttu-id="20bc5-118">이벤트가 사용 하 여 선언 해야는 [이벤트 연결 문으로](../../../../visual-basic/language-reference/statements/event-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="20bc5-118">Make sure the event is declared with an [Event Statement](../../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
2. <span data-ttu-id="20bc5-119">수준에서 사용 하 여 모듈 또는 클래스에서 개체 변수를 선언 합니다 [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="20bc5-119">Declare an object variable at module or class level, using the [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) keyword.</span></span> <span data-ttu-id="20bc5-120">`As` 절이이 변수에 대 한 이벤트를 발생 시키는 클래스를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20bc5-120">The `As` clause for this variable must specify the class that raises the event.</span></span>  
  
3. <span data-ttu-id="20bc5-121">이벤트 처리의 선언에 `Sub` 프로시저를 추가 [처리](../../../../visual-basic/language-reference/statements/handles-clause.md) 지정 하는 절을 `WithEvents` 이벤트 이름과 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="20bc5-121">In the declaration of the event-handling `Sub` procedure, add a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause that specifies the `WithEvents` variable and the event name.</span></span>  
  
4. <span data-ttu-id="20bc5-122">Visual Basic 자동으로 호출 이벤트가 발생할 때를 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="20bc5-122">When the event occurs, Visual Basic automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="20bc5-123">코드에서 사용할 수는 `RaiseEvent` 문을 이벤트를 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="20bc5-123">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>  
  
     <span data-ttu-id="20bc5-124">다음 예제에서는 이벤트를 정의 및 `WithEvents` 이벤트를 발생 시키는 클래스를 참조 하는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="20bc5-124">The following example defines an event and a `WithEvents` variable that refers to the class that raises the event.</span></span> <span data-ttu-id="20bc5-125">이벤트 처리 `Sub` 프로시저는 `Handles` 절 클래스와 처리 하는 이벤트를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="20bc5-125">The event-handling `Sub` procedure uses a `Handles` clause to specify the class and event it handles.</span></span>  
  
     [!code-vb[VbVbcnProcedures#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#4)]  
  
### <a name="to-call-an-event-handler-using-addhandler"></a><span data-ttu-id="20bc5-126">AddHandler를 사용 하 여 이벤트 처리기를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="20bc5-126">To call an event handler using AddHandler</span></span>  
  
1. <span data-ttu-id="20bc5-127">이벤트가 사용 하 여 선언 해야는 `Event` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="20bc5-127">Make sure the event is declared with an `Event` statement.</span></span>  
  
2. <span data-ttu-id="20bc5-128">실행 프로그램 [AddHandler 문](../../../../visual-basic/language-reference/statements/addhandler-statement.md) 이벤트 처리를 동적으로 연결할 `Sub` 이벤트를 사용 하 여 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="20bc5-128">Execute an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) to dynamically connect the event-handling `Sub` procedure with the event.</span></span>  
  
3. <span data-ttu-id="20bc5-129">Visual Basic 자동으로 호출 이벤트가 발생할 때를 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="20bc5-129">When the event occurs, Visual Basic automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="20bc5-130">코드에서 사용할 수는 `RaiseEvent` 문을 이벤트를 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="20bc5-130">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>  
  
     <span data-ttu-id="20bc5-131">다음 예제에서는 정의 `Sub` 처리 하는 절차는 <xref:System.Windows.Forms.Form.Closing> 폼의 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="20bc5-131">The following example defines a `Sub` procedure to handle the <xref:System.Windows.Forms.Form.Closing> event of a form.</span></span> <span data-ttu-id="20bc5-132">사용 하 여는 [AddHandler 문](../../../../visual-basic/language-reference/statements/addhandler-statement.md) 연결 하는 `catchClose` 에 대 한 이벤트 처리기로 프로시저 <xref:System.Windows.Forms.Form.Closing>합니다.</span><span class="sxs-lookup"><span data-stu-id="20bc5-132">It then uses the [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) to associate the `catchClose` procedure as an event handler for <xref:System.Windows.Forms.Form.Closing>.</span></span>  
  
     [!code-vb[VbVbcnProcedures#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#5)]  
  
     <span data-ttu-id="20bc5-133">실행 하 여 이벤트에서 이벤트 처리기를 분리할 수 있습니다 합니다 [RemoveHandler 문](../../../../visual-basic/language-reference/statements/removehandler-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="20bc5-133">You can dissociate an event handler from an event by executing the [RemoveHandler Statement](../../../../visual-basic/language-reference/statements/removehandler-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20bc5-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="20bc5-134">See also</span></span>

- [<span data-ttu-id="20bc5-135">절차</span><span class="sxs-lookup"><span data-stu-id="20bc5-135">Procedures</span></span>](./index.md)
- [<span data-ttu-id="20bc5-136">하위 프로시저</span><span class="sxs-lookup"><span data-stu-id="20bc5-136">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="20bc5-137">Sub 문</span><span class="sxs-lookup"><span data-stu-id="20bc5-137">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="20bc5-138">AddressOf 연산자</span><span class="sxs-lookup"><span data-stu-id="20bc5-138">AddressOf Operator</span></span>](../../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="20bc5-139">방법: 프로시저 만들기</span><span class="sxs-lookup"><span data-stu-id="20bc5-139">How to: Create a Procedure</span></span>](./how-to-create-a-procedure.md)
- [<span data-ttu-id="20bc5-140">방법: 값을 반환하지 않는 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="20bc5-140">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
