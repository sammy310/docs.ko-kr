---
description: async - C# 참조
title: async - C# 참조
ms.date: 05/22/2017
f1_keywords:
- async_CSharpKeyword
helpviewer_keywords:
- async keyword [C#]
- async method [C#]
- async [C#]
ms.assetid: 16f14f09-b2ce-42c7-a875-e4eca5d50674
ms.openlocfilehash: 78079d9940ea5363215411acea6b9ca269ff3ae1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91160543"
---
# <a name="async-c-reference"></a><span data-ttu-id="beaf0-103">async(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="beaf0-103">async (C# Reference)</span></span>

<span data-ttu-id="beaf0-104">`async` 한정자를 사용하여 메서드, [람다 식](../operators/lambda-expressions.md) 또는 [무명 메서드](../operators/delegate-operator.md)를 비동기로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="beaf0-104">Use the `async` modifier to specify that a method, [lambda expression](../operators/lambda-expressions.md), or [anonymous method](../operators/delegate-operator.md) is asynchronous.</span></span> <span data-ttu-id="beaf0-105">메서드 또는 식에 이 한정자를 사용하면 *비동기 메서드*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="beaf0-105">If you use this modifier on a method or expression, it's referred to as an *async method*.</span></span> <span data-ttu-id="beaf0-106">다음 예제에서는 `ExampleMethodAsync`라는 비동기 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="beaf0-106">The following example defines an async method named `ExampleMethodAsync`:</span></span>

```csharp
public async Task<int> ExampleMethodAsync()
{
    //...
}
```

<span data-ttu-id="beaf0-107">비동기 프로그래밍이 처음이거나 비동기 메서드가 [`await` 연산자](../operators/await.md)를 사용하여 호출자의 스레드를 차단하지 않고 장기 실행 작업을 수행할 수 있는 방법을 잘 모르겠으면 [async 및 await를 사용한 비동기 프로그래밍](../../programming-guide/concepts/async/index.md)의 소개 내용을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="beaf0-107">If you're new to asynchronous programming or do not understand how an async method uses the [`await` operator](../operators/await.md) to do potentially long-running work without blocking the caller's thread, read the introduction in [Asynchronous programming with async and await](../../programming-guide/concepts/async/index.md).</span></span> <span data-ttu-id="beaf0-108">다음 코드는 비동기 메서드 안에 있으며 <xref:System.Net.Http.HttpClient.GetStringAsync%2a?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="beaf0-108">The following code is found inside an async method and calls the <xref:System.Net.Http.HttpClient.GetStringAsync%2a?displayProperty=nameWithType> method:</span></span>

```csharp
string contents = await httpClient.GetStringAsync(requestUrl);
```

<span data-ttu-id="beaf0-109">비동기 메서드는 대기 중인 작업이 완료될 때까지 메서드가 일시 중단되는 지점인 첫 번째 `await` 식에 도달하기 전에는 동기적으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="beaf0-109">An async method runs synchronously until it reaches its first `await` expression, at which point the method is suspended until the awaited task is complete.</span></span> <span data-ttu-id="beaf0-110">다음 단원의 예제에서처럼 그 동안에는 제어가 메서드 호출자에게 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="beaf0-110">In the meantime, control returns to the caller of the method, as the example in the next section shows.</span></span>

<span data-ttu-id="beaf0-111">`async` 키워드에서 수정하는 메서드에 `await` 식 또는 문이 없는 경우 해당 메서드가 동기적으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="beaf0-111">If the method that the `async` keyword modifies doesn't contain an `await` expression or statement, the method executes synchronously.</span></span> <span data-ttu-id="beaf0-112">`await` 문이 포함되지 않은 모든 비동기 메서드에서는 오류가 발생할 수 있으므로 컴파일러 경고가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="beaf0-112">A compiler warning alerts you to any async methods that don't contain `await` statements, because that situation might indicate an error.</span></span> <span data-ttu-id="beaf0-113">[컴파일러 경고(수준 1) CS4014](../compiler-messages/cs4014.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="beaf0-113">See [Compiler Warning (level 1) CS4014](../compiler-messages/cs4014.md).</span></span>

 <span data-ttu-id="beaf0-114">`async` 키워드는 메서드, 람다 식 또는 무명 메서드를 수정할 때만 키워드로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="beaf0-114">The `async` keyword is contextual in that it's a keyword only when it modifies a method, a lambda expression, or an anonymous method.</span></span> <span data-ttu-id="beaf0-115">다른 모든 컨텍스트에서는 식별자로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="beaf0-115">In all other contexts, it's interpreted as an identifier.</span></span>

## <a name="example"></a><span data-ttu-id="beaf0-116">예제</span><span class="sxs-lookup"><span data-stu-id="beaf0-116">Example</span></span>

<span data-ttu-id="beaf0-117">다음 예제에서는 비동기 이벤트 처리기, `StartButton_Click`, 비동기 메서드 및 `ExampleMethodAsync` 간의 제어 흐름과 구조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="beaf0-117">The following example shows the structure and flow of control between an async event handler, `StartButton_Click`, and an async method, `ExampleMethodAsync`.</span></span> <span data-ttu-id="beaf0-118">비동기 메서드의 결과는 웹 페이지의 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="beaf0-118">The result from the async method is the number of characters of a web page.</span></span> <span data-ttu-id="beaf0-119">이 코드는 Visual Studio에서 만든 WPF(Windows Presentation Foundation) 앱 또는 Windows 스토어 앱에 적합합니다. 앱을 설정하는 방법은 코드 주석을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="beaf0-119">The code is suitable for a Windows Presentation Foundation (WPF) app or Windows Store app that you create in Visual Studio; see the code comments for setting up the app.</span></span>

<span data-ttu-id="beaf0-120">Visual Studio에서 이 코드를 WPF(Windows Presentation Foundation) 앱 또는 Windows 스토어 앱으로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="beaf0-120">You can run this code in Visual Studio as a Windows Presentation Foundation (WPF) app or a Windows Store app.</span></span> <span data-ttu-id="beaf0-121">`StartButton`이라는 Button 컨트롤과 `ResultsTextBox`라는 Textbox 컨트롤이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="beaf0-121">You need a Button control named `StartButton` and a Textbox control named `ResultsTextBox`.</span></span> <span data-ttu-id="beaf0-122">다음과 같이 작성되도록 이름과 처리기를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="beaf0-122">Remember to set the names and handler so that you have something like this:</span></span>

```xaml
<Button Content="Button" HorizontalAlignment="Left" Margin="88,77,0,0" VerticalAlignment="Top" Width="75"
        Click="StartButton_Click" Name="StartButton"/>
<TextBox HorizontalAlignment="Left" Height="137" Margin="88,140,0,0" TextWrapping="Wrap"
         Text="&lt;Enter a URL&gt;" VerticalAlignment="Top" Width="310" Name="ResultsTextBox"/>
```

<span data-ttu-id="beaf0-123">코드를 WPF 앱으로 실행하려면</span><span class="sxs-lookup"><span data-stu-id="beaf0-123">To run the code as a WPF app:</span></span>

- <span data-ttu-id="beaf0-124">이 코드를 MainWindow.xaml.cs의 `MainWindow` 클래스에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="beaf0-124">Paste this code into the `MainWindow` class in MainWindow.xaml.cs.</span></span>
- <span data-ttu-id="beaf0-125">System.Net.Http에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="beaf0-125">Add a reference to System.Net.Http.</span></span>
- <span data-ttu-id="beaf0-126">System.Net.Http에 대한 `using` 지시문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="beaf0-126">Add a `using` directive for System.Net.Http.</span></span>

<span data-ttu-id="beaf0-127">코드를 Windows 스토어 앱으로 실행하려면</span><span class="sxs-lookup"><span data-stu-id="beaf0-127">To run the code as a Windows Store app:</span></span>

- <span data-ttu-id="beaf0-128">이 코드를 MainPage.xaml.cs의 `MainPage` 클래스에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="beaf0-128">Paste this code into the `MainPage` class in MainPage.xaml.cs.</span></span>
- <span data-ttu-id="beaf0-129">System.Net.Http 및 System.Threading.Tasks에 대한 using 지시문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="beaf0-129">Add using directives for System.Net.Http and System.Threading.Tasks.</span></span>

[!code-csharp[wpf-async](../../../../samples/snippets/csharp/language-reference/keywords/async/wpf/mainwindow.xaml.cs#1)]

> [!IMPORTANT]
> <span data-ttu-id="beaf0-130">작업 및 작업 완료를 기다리는 동안 실행되는 코드에 관한 자세한 내용은 [async 및 await를 사용한 비동기 프로그래밍](../../programming-guide/concepts/async/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="beaf0-130">For more information about tasks and the code that executes while waiting for a task, see [Asynchronous programming with async and await](../../programming-guide/concepts/async/index.md).</span></span> <span data-ttu-id="beaf0-131">비슷한 요소를 사용하는 전체 콘솔 예제는 [완료되면 비동기 작업 처리(C#)](../../programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="beaf0-131">For a full console example that uses similar elements, see [Process asynchronous tasks as they complete (C#)](../../programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).</span></span>

## <a name="return-types"></a><span data-ttu-id="beaf0-132">반환 형식</span><span class="sxs-lookup"><span data-stu-id="beaf0-132">Return Types</span></span>

<span data-ttu-id="beaf0-133">비동기 메서드의 반환 형식은 다음과 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="beaf0-133">An async method can have the following return types:</span></span>

- <xref:System.Threading.Tasks.Task>
- <xref:System.Threading.Tasks.Task%601>
- <span data-ttu-id="beaf0-134">[void](../builtin-types/void.md).</span><span class="sxs-lookup"><span data-stu-id="beaf0-134">[void](../builtin-types/void.md).</span></span> <span data-ttu-id="beaf0-135">`async void` 메서드는 호출자가 `await` 해당 메서드를 사용할 수 없으며 성공적으로 완료 또는 오류 조건을 보고하는 다른 메커니즘을 구현해야 하기 때문에 이벤트 처리기 이외의 코드에 대해 일반적으로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="beaf0-135">`async void` methods are generally discouraged for code other than event handlers because callers cannot `await` those methods and must implement a different mechanism to report successful completion or error conditions.</span></span>
- <span data-ttu-id="beaf0-136">C# 7.0부터 액세스 가능한 `GetAwaiter` 메서드가 있는 모든 형식.</span><span class="sxs-lookup"><span data-stu-id="beaf0-136">Starting with C# 7.0, any type that has an accessible `GetAwaiter` method.</span></span> <span data-ttu-id="beaf0-137">`System.Threading.Tasks.ValueTask<TResult>` 형식은 이러한 구현 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="beaf0-137">The `System.Threading.Tasks.ValueTask<TResult>` type is one such implementation.</span></span> <span data-ttu-id="beaf0-138">NuGet 패키지 `System.Threading.Tasks.Extensions`를 추가하면 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="beaf0-138">It is available by adding the NuGet package `System.Threading.Tasks.Extensions`.</span></span>

<span data-ttu-id="beaf0-139">비동기 메서드는 모든 [in](./in-parameter-modifier.md), [ref](./ref.md) 또는 [out](./out-parameter-modifier.md) 매개 변수를 선언할 수 없고 [참조 반환 값](../../programming-guide/classes-and-structs/ref-returns.md)을 가질 수도 없지만, 이러한 매개 변수가 있는 메서드를 호출할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="beaf0-139">The async method can't declare any [in](./in-parameter-modifier.md), [ref](./ref.md) or [out](./out-parameter-modifier.md) parameters, nor can it have a [reference return value](../../programming-guide/classes-and-structs/ref-returns.md), but it can call methods that have such parameters.</span></span>

<span data-ttu-id="beaf0-140">메서드의 [return](./return.md) 문에서 `TResult` 형식의 피연산자를 지정할 경우 비동기 메서드의 반환 형식으로 `Task<TResult>`를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="beaf0-140">You specify `Task<TResult>` as the return type of an async method if the [return](./return.md) statement of the method specifies an operand of type `TResult`.</span></span> <span data-ttu-id="beaf0-141">메서드가 완료되었을 때 의미 있는 값이 반환되지 않을 경우 `Task`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="beaf0-141">You use `Task` if no meaningful value is returned when the method is completed.</span></span> <span data-ttu-id="beaf0-142">즉, 이 메서드를 호출하면 `Task`가 반환되지만 `Task`가 완료되면 `await`를 기다리는 모든 `Task` 식이 `void`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="beaf0-142">That is, a call to the method returns a `Task`, but when the `Task` is completed, any `await` expression that's awaiting the `Task` evaluates to `void`.</span></span>

<span data-ttu-id="beaf0-143">`void` 반환 형식은 주로 해당 반환 형식이 필요한 이벤트 처리기를 정의할 때 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="beaf0-143">You use the `void` return type primarily to define event handlers, which require that return type.</span></span> <span data-ttu-id="beaf0-144">`void` 반환 비동기 메서드의 호출자는 기다릴 수 없으므로 메서드가 throw하는 예외를 catch할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="beaf0-144">The caller of a `void`-returning async method can't await it and can't catch exceptions that the method throws.</span></span>

<span data-ttu-id="beaf0-145">C# 7.0부터 `GetAwaiter` 메서드가 있는 다른 형식(일반적으로 값 형식)을 반환하여 성능이 중요한 코드 섹션에서 메모리 할당을 최소화합니다.</span><span class="sxs-lookup"><span data-stu-id="beaf0-145">Starting with C# 7.0, you return another type, typically a value type, that has a `GetAwaiter` method to minimize memory allocations in performance-critical sections of code.</span></span>

<span data-ttu-id="beaf0-146">자세한 내용과 예제는 [비동기 반환 형식](../../programming-guide/concepts/async/async-return-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="beaf0-146">For more information and examples, see [Async Return Types](../../programming-guide/concepts/async/async-return-types.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="beaf0-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="beaf0-147">See also</span></span>

- <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>
- [<span data-ttu-id="beaf0-148">await</span><span class="sxs-lookup"><span data-stu-id="beaf0-148">await</span></span>](../operators/await.md)
- [<span data-ttu-id="beaf0-149">async 및 await를 사용한 비동기 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="beaf0-149">Asynchronous programming with async and await</span></span>](../../programming-guide/concepts/async/index.md)
- [<span data-ttu-id="beaf0-150">완료되면 비동기 작업 처리</span><span class="sxs-lookup"><span data-stu-id="beaf0-150">Process asynchronous tasks as they complete</span></span>](../../programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)
