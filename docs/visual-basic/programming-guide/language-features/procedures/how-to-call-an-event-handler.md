---
title: '방법: Visual Basic에서 이벤트 처리기를 호출 합니다.'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
ms.openlocfilehash: a9e090e83b180686ccb832aa6efb314c7e0fcc9a
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216622"
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a><span data-ttu-id="057a9-102">방법: Visual Basic에서 이벤트 처리기를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="057a9-102">How to: Call an Event Handler in Visual Basic</span></span>

<span data-ttu-id="057a9-103">*이벤트* 는 일부 프로그램 구성 요소에서 인식 하 고 응답 하는 코드를 작성할 수 있는 마우스 클릭 또는 신용 한도 초과와 같은 작업 또는 발생입니다.</span><span class="sxs-lookup"><span data-stu-id="057a9-103">An *event* is an action or occurrence — such as a mouse click or a credit limit exceeded — that is recognized by some program component, and for which you can write code to respond.</span></span> <span data-ttu-id="057a9-104">이벤트 *처리기* 는 이벤트에 응답 하기 위해 작성 하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="057a9-104">An *event handler* is the code you write to respond to an event.</span></span>

 <span data-ttu-id="057a9-105">Visual Basic 이벤트 처리기는 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="057a9-105">An event handler in Visual Basic is a `Sub` procedure.</span></span> <span data-ttu-id="057a9-106">그러나 일반적으로 다른 `Sub` 프로시저와 동일한 방식으로 호출 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="057a9-106">However, you do not normally call it the same way as other `Sub` procedures.</span></span> <span data-ttu-id="057a9-107">대신 프로시저를 이벤트 처리기로 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="057a9-107">Instead, you identify the procedure as a handler for the event.</span></span> <span data-ttu-id="057a9-108">[Handles](../../../language-reference/statements/handles-clause.md) 절과 [WithEvents](../../../language-reference/modifiers/withevents.md) 변수를 사용 하거나 [AddHandler 문을](../../../language-reference/statements/addhandler-statement.md)사용 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="057a9-108">You can do this either with a [Handles](../../../language-reference/statements/handles-clause.md) clause and a [WithEvents](../../../language-reference/modifiers/withevents.md) variable, or with an [AddHandler Statement](../../../language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="057a9-109">Visual Basic에서 `Handles` 이벤트 처리기를 선언 하는 기본 방법은 절을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="057a9-109">Using a `Handles` clause is the default way to declare an event handler in Visual Basic.</span></span> <span data-ttu-id="057a9-110">IDE (통합 개발 환경)에서 프로그래밍할 때 디자이너에서 이벤트 처리기를 작성 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="057a9-110">This is the way the event handlers are written by the designers when you program in the integrated development environment (IDE).</span></span> <span data-ttu-id="057a9-111">`AddHandler` 문은 런타임에 이벤트를 동적으로 발생 시키는 데 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="057a9-111">The `AddHandler` statement is suitable for raising events dynamically at run time.</span></span>

 <span data-ttu-id="057a9-112">이벤트가 발생할 때 Visual Basic는 이벤트 처리기 프로시저를 자동으로 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="057a9-112">When the event occurs, Visual Basic automatically calls the event handler procedure.</span></span> <span data-ttu-id="057a9-113">이벤트에 액세스할 수 있는 모든 코드는 [RaiseEvent 문을](../../../language-reference/statements/raiseevent-statement.md)실행 하 여 발생 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="057a9-113">Any code that has access to the event can cause it to occur by executing a [RaiseEvent Statement](../../../language-reference/statements/raiseevent-statement.md).</span></span>

 <span data-ttu-id="057a9-114">둘 이상의 이벤트 처리기를 동일한 이벤트와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="057a9-114">You can associate more than one event handler with the same event.</span></span> <span data-ttu-id="057a9-115">경우에 따라 이벤트에서 처리기를 분리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="057a9-115">In some cases you can dissociate a handler from an event.</span></span> <span data-ttu-id="057a9-116">자세한 내용은 [이벤트](../events/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="057a9-116">For more information, see [Events](../events/index.md).</span></span>

### <a name="to-call-an-event-handler-using-handles-and-withevents"></a><span data-ttu-id="057a9-117">핸들 및 WithEvents를 사용 하 여 이벤트 처리기를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="057a9-117">To call an event handler using Handles and WithEvents</span></span>

1. <span data-ttu-id="057a9-118">이벤트가 [이벤트 문으로](../../../language-reference/statements/event-statement.md)선언 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="057a9-118">Make sure the event is declared with an [Event Statement](../../../language-reference/statements/event-statement.md).</span></span>

2. <span data-ttu-id="057a9-119">[WithEvents](../../../language-reference/modifiers/withevents.md) 키워드를 사용 하 여 모듈 또는 클래스 수준에서 개체 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="057a9-119">Declare an object variable at module or class level, using the [WithEvents](../../../language-reference/modifiers/withevents.md) keyword.</span></span> <span data-ttu-id="057a9-120">이 `As` 변수에 대 한 절은 이벤트를 발생 시키는 클래스를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="057a9-120">The `As` clause for this variable must specify the class that raises the event.</span></span>

3. <span data-ttu-id="057a9-121">이벤트 처리 `Sub` 프로시저 선언에서 `WithEvents` 변수와 이벤트 이름을 지정 하는 [Handles](../../../language-reference/statements/handles-clause.md) 절을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="057a9-121">In the declaration of the event-handling `Sub` procedure, add a [Handles](../../../language-reference/statements/handles-clause.md) clause that specifies the `WithEvents` variable and the event name.</span></span>

4. <span data-ttu-id="057a9-122">이벤트가 발생할 때 Visual Basic는 프로시저를 `Sub` 자동으로 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="057a9-122">When the event occurs, Visual Basic automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="057a9-123">코드에서 `RaiseEvent` 문을 사용 하 여 이벤트를 발생 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="057a9-123">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>

     <span data-ttu-id="057a9-124">다음 예제에서는 이벤트를 정의 하 고 `WithEvents` 이벤트를 발생 시키는 클래스를 참조 하는 변수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="057a9-124">The following example defines an event and a `WithEvents` variable that refers to the class that raises the event.</span></span> <span data-ttu-id="057a9-125">이벤트 처리 `Sub` 프로시저는 절을 `Handles` 사용 하 여 처리 하는 클래스 및 이벤트를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="057a9-125">The event-handling `Sub` procedure uses a `Handles` clause to specify the class and event it handles.</span></span>

     [!code-vb[VbVbcnProcedures#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#4)]

### <a name="to-call-an-event-handler-using-addhandler"></a><span data-ttu-id="057a9-126">AddHandler를 사용 하 여 이벤트 처리기를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="057a9-126">To call an event handler using AddHandler</span></span>

1. <span data-ttu-id="057a9-127">이벤트가 `Event` 문으로 선언 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="057a9-127">Make sure the event is declared with an `Event` statement.</span></span>

2. <span data-ttu-id="057a9-128">이벤트 처리 `Sub` 프로시저를 이벤트와 동적으로 연결 하려면 [AddHandler 문을](../../../language-reference/statements/addhandler-statement.md) 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="057a9-128">Execute an [AddHandler Statement](../../../language-reference/statements/addhandler-statement.md) to dynamically connect the event-handling `Sub` procedure with the event.</span></span>

3. <span data-ttu-id="057a9-129">이벤트가 발생할 때 Visual Basic는 프로시저를 `Sub` 자동으로 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="057a9-129">When the event occurs, Visual Basic automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="057a9-130">코드에서 `RaiseEvent` 문을 사용 하 여 이벤트를 발생 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="057a9-130">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>

     <span data-ttu-id="057a9-131">다음 예에서는 폼의 `Sub` <xref:System.Windows.Forms.Form.Closing> 이벤트를 처리 하는 프로시저를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="057a9-131">The following example defines a `Sub` procedure to handle the <xref:System.Windows.Forms.Form.Closing> event of a form.</span></span> <span data-ttu-id="057a9-132">그런 다음 [AddHandler 문을](../../../language-reference/statements/addhandler-statement.md) 사용 하 여 프로시저를 `catchClose` 에 대 한 <xref:System.Windows.Forms.Form.Closing>이벤트 처리기와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="057a9-132">It then uses the [AddHandler Statement](../../../language-reference/statements/addhandler-statement.md) to associate the `catchClose` procedure as an event handler for <xref:System.Windows.Forms.Form.Closing>.</span></span>

     [!code-vb[VbVbcnProcedures#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#5)]

     <span data-ttu-id="057a9-133">[RemoveHandler 문을](../../../language-reference/statements/removehandler-statement.md)실행 하 여 이벤트에서 이벤트 처리기를 분리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="057a9-133">You can dissociate an event handler from an event by executing the [RemoveHandler Statement](../../../language-reference/statements/removehandler-statement.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="057a9-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="057a9-134">See also</span></span>

- [<span data-ttu-id="057a9-135">절차</span><span class="sxs-lookup"><span data-stu-id="057a9-135">Procedures</span></span>](index.md)
- [<span data-ttu-id="057a9-136">Sub 프로시저</span><span class="sxs-lookup"><span data-stu-id="057a9-136">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="057a9-137">Sub 문</span><span class="sxs-lookup"><span data-stu-id="057a9-137">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="057a9-138">AddressOf 연산자</span><span class="sxs-lookup"><span data-stu-id="057a9-138">AddressOf Operator</span></span>](../../../language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="057a9-139">방법: 프로시저 만들기</span><span class="sxs-lookup"><span data-stu-id="057a9-139">How to: Create a Procedure</span></span>](how-to-create-a-procedure.md)
- [<span data-ttu-id="057a9-140">방법: 값을 반환 하지 않는 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="057a9-140">How to: Call a Procedure that Does Not Return a Value</span></span>](how-to-call-a-procedure-that-does-not-return-a-value.md)
