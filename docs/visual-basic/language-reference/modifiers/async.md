---
description: '자세한 정보: 비동기 (Visual Basic)'
title: Async
ms.date: 07/20/2015
f1_keywords:
- vb.Async
helpviewer_keywords:
- Async [Visual Basic]
- Async keyword [Visual Basic]
ms.assetid: 1be8b4b5-9689-41b5-bd33-b906bfd53bc5
ms.openlocfilehash: a20c80ace06e386e7c106acc2b7e6258abca13b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99701159"
---
# <a name="async-visual-basic"></a><span data-ttu-id="d3e76-103">Async(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d3e76-103">Async (Visual Basic)</span></span>

<span data-ttu-id="d3e76-104">`Async`한정자는 수정 하는 메서드 또는 [람다 식이](../../programming-guide/language-features/procedures/lambda-expressions.md) 비동기 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d3e76-104">The `Async` modifier indicates that the method or [lambda expression](../../programming-guide/language-features/procedures/lambda-expressions.md) that it modifies is asynchronous.</span></span> <span data-ttu-id="d3e76-105">이러한 메서드를 *비동기 메서드* 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3e76-105">Such methods are referred to as *async methods*.</span></span>

<span data-ttu-id="d3e76-106">비동기 메서드는 호출자의 스레드를 차단하지 않고 오래 실행될 수 있는 작업을 수행하는 편리한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d3e76-106">An async method provides a convenient way to do potentially long-running work without blocking the caller's thread.</span></span> <span data-ttu-id="d3e76-107">비동기 메서드의 호출자는 비동기 메서드가 완료 될 때까지 기다리지 않고 작업을 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3e76-107">The caller of an async method can resume its work without waiting for the async method to finish.</span></span>

> [!NOTE]
> <span data-ttu-id="d3e76-108">`Async` 및 `Await` 키워드는 Visual Studio 2012에서 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d3e76-108">The `Async` and `Await` keywords were introduced in Visual Studio 2012.</span></span> <span data-ttu-id="d3e76-109">비동기 프로그래밍에 대 한 소개는 [async 및 wait를 사용한 비동기 프로그래밍](../../programming-guide/concepts/async/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d3e76-109">For an introduction to async programming, see [Asynchronous Programming with Async and Await](../../programming-guide/concepts/async/index.md).</span></span>

<span data-ttu-id="d3e76-110">다음 예제에서는 비동기 메서드의 구조를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d3e76-110">The following example shows the structure of an async method.</span></span> <span data-ttu-id="d3e76-111">규칙에 따라 비동기 메서드는 "Async"로 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="d3e76-111">By convention, async method names end in "Async."</span></span>

```vb
Public Async Function ExampleMethodAsync() As Task(Of Integer)
    ' . . .

    ' At the Await expression, execution in this method is suspended and,
    ' if AwaitedProcessAsync has not already finished, control returns
    ' to the caller of ExampleMethodAsync. When the awaited task is
    ' completed, this method resumes execution.
    Dim exampleInt As Integer = Await AwaitedProcessAsync()

    ' . . .

    ' The return statement completes the task. Any method that is
    ' awaiting ExampleMethodAsync can now get the integer result.
    Return exampleInt
End Function
```

<span data-ttu-id="d3e76-112">일반적으로 키워드에 의해 수정 된 메서드에 `Async` 하나 이상의 [wait](async.md) 식 또는 문이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3e76-112">Typically, a method modified by the `Async` keyword contains at least one [Await](async.md) expression or statement.</span></span> <span data-ttu-id="d3e76-113">대기 중인 작업이 완료될 때까지 일시 중단된 지점인 첫 번째 `Await`에 도달할 때까지 이 메서드는 동기적으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3e76-113">The method runs synchronously until it reaches the first `Await`, at which point it suspends until the awaited task completes.</span></span> <span data-ttu-id="d3e76-114">그리고 메서드의 호출자로 컨트롤이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3e76-114">In the meantime, control is returned to the caller of the method.</span></span> <span data-ttu-id="d3e76-115">메서드에 식 또는 문이 포함 되지 않은 경우 `Await` 메서드는 일시 중단 되지 않고 동기 메서드를 통해 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3e76-115">If the method doesn't contain an `Await` expression or statement, the method isn't suspended and executes as a synchronous method does.</span></span> <span data-ttu-id="d3e76-116">이러한 상황에서 오류가 발생할 수 있으므로가 포함 되지 않은 모든 비동기 메서드에 대 한 컴파일러 경고가 `Await` 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3e76-116">A compiler warning alerts you to any async methods that don't contain `Await` because that situation might indicate an error.</span></span> <span data-ttu-id="d3e76-117">자세한 내용은 [컴파일러 오류](../error-messages/bc42358.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d3e76-117">For more information, see the [compiler error](../error-messages/bc42358.md).</span></span>

<span data-ttu-id="d3e76-118">`Async` 키워드는 예약되지 않은 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="d3e76-118">The `Async` keyword is an unreserved keyword.</span></span> <span data-ttu-id="d3e76-119">이 키워드는 메서드 또는 람다 식을 수정할 때의 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="d3e76-119">It is a keyword when it modifies a method or a lambda expression.</span></span> <span data-ttu-id="d3e76-120">다른 모든 컨텍스트에서는 식별자로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3e76-120">In all other contexts, it is interpreted as an identifier.</span></span>

## <a name="return-types"></a><span data-ttu-id="d3e76-121">반환 형식</span><span class="sxs-lookup"><span data-stu-id="d3e76-121">Return Types</span></span>

<span data-ttu-id="d3e76-122">비동기 메서드는 [Sub](../../programming-guide/language-features/procedures/sub-procedures.md) 프로시저 이거나 반환 형식이 또는 인 [함수](../../programming-guide/language-features/procedures/function-procedures.md) 프로시저입니다 <xref:System.Threading.Tasks.Task> <xref:System.Threading.Tasks.Task%601> .</span><span class="sxs-lookup"><span data-stu-id="d3e76-122">An async method is either a [Sub](../../programming-guide/language-features/procedures/sub-procedures.md) procedure, or a [Function](../../programming-guide/language-features/procedures/function-procedures.md) procedure that has a return type of <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="d3e76-123">메서드는 [ByRef](byref.md) 매개 변수를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d3e76-123">The method cannot declare any [ByRef](byref.md) parameters.</span></span>

<span data-ttu-id="d3e76-124">메서드의 [return](../statements/return-statement.md) 문에 TResult 형식의 피연산자가 있는 경우 비동기 메서드의 반환 형식으로 `Task(Of TResult)`를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3e76-124">You specify `Task(Of TResult)` for the return type of an async method if the [Return](../statements/return-statement.md) statement of the method has an operand of type TResult.</span></span> <span data-ttu-id="d3e76-125">메서드가 완료되었을 때 의미 있는 값이 반환되지 않을 경우 `Task`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3e76-125">You use `Task` if no meaningful value is returned when the method is completed.</span></span> <span data-ttu-id="d3e76-126">즉, 메서드를 호출하면 `Task`가 반환되지만 `Task`가 완료된 경우 `Await`를 대기 중인 모든 `Task` 문이 결과 값을 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3e76-126">That is, a call to the method returns a `Task`, but when the `Task` is completed, any `Await` statement that's awaiting the `Task` doesn’t produce a result value.</span></span>

<span data-ttu-id="d3e76-127">비동기 서브루틴은 `Sub` 프로시저가 필요한 이벤트 처리기를 정의하는 데 주로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3e76-127">Async subroutines are used primarily to define event handlers where a `Sub` procedure is required.</span></span> <span data-ttu-id="d3e76-128">비동기 서브 루틴의 호출자는 이를 기다릴 수 없으며, 메서드가 throw하는 예외를 catch할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d3e76-128">The caller of an async subroutine can't await it and can't catch exceptions that the method throws.</span></span>

<span data-ttu-id="d3e76-129">자세한 내용과 예제는 [비동기 반환 형식](../../programming-guide/concepts/async/async-return-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3e76-129">For more information and examples, see [Async Return Types](../../programming-guide/concepts/async/async-return-types.md).</span></span>

## <a name="example"></a><span data-ttu-id="d3e76-130">예제</span><span class="sxs-lookup"><span data-stu-id="d3e76-130">Example</span></span>

<span data-ttu-id="d3e76-131">다음 예제는 비동기 이벤트 처리기, 비동기 람다 식 및 비동기 메서드를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d3e76-131">The following examples show an async event handler, an async lambda expression, and an async method.</span></span> <span data-ttu-id="d3e76-132">이러한 요소를 사용 하는 전체 예제는 [연습: Async 및 wait를 사용 하 여 웹에 액세스](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d3e76-132">For a full example that uses these elements, see [Walkthrough: Accessing the Web by Using Async and Await](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="d3e76-133">[Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f)(비동기 샘플: 웹 액세스 연습(C# 및 Visual Basic))에서 연습 코드를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3e76-133">You can download the walkthrough code from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span></span>

```vb
' An event handler must be a Sub procedure.
Async Sub button1_Click(sender As Object, e As RoutedEventArgs) Handles button1.Click
    textBox1.Clear()
    ' SumPageSizesAsync is a method that returns a Task.
    Await SumPageSizesAsync()
    textBox1.Text = vbCrLf & "Control returned to button1_Click."
End Sub

' The following async lambda expression creates an equivalent anonymous
' event handler.
AddHandler button1.Click, Async Sub(sender, e)
                              textBox1.Clear()
                              ' SumPageSizesAsync is a method that returns a Task.
                              Await SumPageSizesAsync()
                              textBox1.Text = vbCrLf & "Control returned to button1_Click."
                          End Sub

' The following async method returns a Task(Of T).
' A typical call awaits the Byte array result:
'      Dim result As Byte() = Await GetURLContents("https://msdn.com")
Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())

    ' The downloaded resource ends up in the variable named content.
    Dim content = New MemoryStream()

    ' Initialize an HttpWebRequest for the current URL.
    Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)

    ' Send the request to the Internet resource and wait for
    ' the response.
    Using response As WebResponse = Await webReq.GetResponseAsync()
        ' Get the data stream that is associated with the specified URL.
        Using responseStream As Stream = response.GetResponseStream()
            ' Read the bytes in responseStream and copy them to content.
            ' CopyToAsync returns a Task, not a Task<T>.
            Await responseStream.CopyToAsync(content)
        End Using
    End Using

    ' Return the result as a byte array.
    Return content.ToArray()
End Function
```

## <a name="see-also"></a><span data-ttu-id="d3e76-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3e76-134">See also</span></span>

- <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>
- [<span data-ttu-id="d3e76-135">Await 연산자</span><span class="sxs-lookup"><span data-stu-id="d3e76-135">Await Operator</span></span>](../operators/await-operator.md)
- [<span data-ttu-id="d3e76-136">Async 및 Await를 사용한 비동기 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="d3e76-136">Asynchronous Programming with Async and Await</span></span>](../../programming-guide/concepts/async/index.md)
- [<span data-ttu-id="d3e76-137">연습: Async 및 Await를 사용하여 웹에 액세스</span><span class="sxs-lookup"><span data-stu-id="d3e76-137">Walkthrough: Accessing the Web by Using Async and Await</span></span>](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
