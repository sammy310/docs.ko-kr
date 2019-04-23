---
title: 비동기 프로그래밍
description: 에 대해 알아봅니다 하는 방법 F# 는 사용 하기 쉬운 및 언어에 자연 스러운 언어 수준 프로그래밍 모델을 통해 비동기 프로그래밍이 수행 됩니다.
ms.date: 06/20/2016
ms.openlocfilehash: 6925a0132f9beed6be5f9dded3630b551072bea2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59343456"
---
# <a name="async-programming-in-f"></a><span data-ttu-id="91e05-103">F #의 비동기 프로그래밍\#</span><span class="sxs-lookup"><span data-stu-id="91e05-103">Async Programming in F\#</span></span>

> [!NOTE]
> <span data-ttu-id="91e05-104">이 문서에 일부 잘못 된 검색 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-104">Some inaccuracies have been discovered in this article.</span></span>  <span data-ttu-id="91e05-105">다시 작성 되 고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-105">It is being rewritten.</span></span>  <span data-ttu-id="91e05-106">참조 [문제 #666](https://github.com/dotnet/docs/issues/666) 변경 내용에 대해 자세히 알아보려면 합니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-106">See [Issue #666](https://github.com/dotnet/docs/issues/666) to learn about the changes.</span></span>

<span data-ttu-id="91e05-107">비동기 프로그래밍에서 F# 사용은 쉽고 자연 언어 설계 언어 수준 프로그래밍 모델을 통해 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-107">Async programming in F# can be accomplished through a language-level programming model designed to be easy to use and natural to the language.</span></span>

<span data-ttu-id="91e05-108">비동기 프로그래밍의 핵심 F# 은 `Async<'T>`, 백그라운드에서 실행을 트리거할 수 있는 작업의 표현을 위치 `'T` 특수 통해 형식 반환 됩니다 `return` 키워드 또는 `unit` 하는 경우 비동기 워크플로 반환할 결과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-108">The core of async programming in F# is `Async<'T>`, a representation of work that can be triggered to run in the background, where `'T` is either the type returned via the special `return` keyword or `unit` if the async workflow has no result to return.</span></span>

<span data-ttu-id="91e05-109">주요 개념은 비동기 식의 형식이 `Async<'T>`는 단순히 _사양_ 비동기 컨텍스트를 수행 해야 하는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-109">The key concept to understand is that an async expression’s type is `Async<'T>`, which is merely a _specification_ of work to be done in an asynchronous context.</span></span> <span data-ttu-id="91e05-110">시작 함수 중 하나를 사용 하 여 명시적으로 시작할 때까지 실행 되지 않습니다 (같은 `Async.RunSynchronously`).</span><span class="sxs-lookup"><span data-stu-id="91e05-110">It is not executed until you explicitly start it with one of the starting functions (such as `Async.RunSynchronously`).</span></span> <span data-ttu-id="91e05-111">다른 방식으로 작업을 수행 하는 방법에 대 한 생각의 경우에이 결국 실제로 매우 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-111">Although this is a different way of thinking about doing work, it ends up being quite simple in practice.</span></span>

<span data-ttu-id="91e05-112">예를 들어 주 스레드를 차단 하지 않고 dotnetfoundation.org에서 HTML을 다운로드 하 려 한다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-112">For example, say you wanted to download the HTML from dotnetfoundation.org without blocking the main thread.</span></span> <span data-ttu-id="91e05-113">다음과 같이를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-113">You can accomplish it like this:</span></span>

```fsharp
open System
open System.Net

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()

        // Execution of fetchHtmlAsync won't continue until the result
        // of AsyncDownloadString is bound.
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

let html = "https://dotnetfoundation.org" |> fetchHtmlAsync |> Async.RunSynchronously
printfn "%s" html
```

<span data-ttu-id="91e05-114">이제 끝났습니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-114">And that’s it!</span></span> <span data-ttu-id="91e05-115">사용 하는 것 외 `async`, `let!`, 및 `return`,이 방금 정상 F# 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-115">Aside from the use of `async`, `let!`, and `return`, this is just normal F# code.</span></span>

<span data-ttu-id="91e05-116">주목할 만한는 구문을 몇 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-116">There are a few syntactical constructs which are worth noting:</span></span>

*   <span data-ttu-id="91e05-117">`let!` (다른 컨텍스트에서 실행)이 표시 되는 비동기 식의 결과 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-117">`let!` binds the result of an async expression (which runs on another context).</span></span>
*   <span data-ttu-id="91e05-118">`use!` 같은 방식으로 작동 `let!`, 하지만 범위를 벗어나면 해당 바인딩된 리소스를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-118">`use!` works just like `let!`, but disposes its bound resources when it goes out of scope.</span></span>
*   <span data-ttu-id="91e05-119">`do!` 아무 것도 반환 하지 않는 비동기 워크플로 await 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-119">`do!` will await an async workflow which doesn’t return anything.</span></span>
*   <span data-ttu-id="91e05-120">`return` 비동기 식에서 결과 반환 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-120">`return` simply returns a result from an async expression.</span></span>
*   <span data-ttu-id="91e05-121">`return!` 다른 비동기 워크플로 실행 하 고 해당 반환 값을 결과로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-121">`return!` executes another async workflow and returns its return value as a result.</span></span>

<span data-ttu-id="91e05-122">또한 정상적인 `let`, `use`, 및 `do` 키워드는 일반 함수 에서처럼 비동기 버전과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-122">Additionally, normal `let`, `use`, and `do` keywords can be used alongside the async versions just as they would in a normal function.</span></span>

## <a name="how-to-start-async-code-in-f"></a><span data-ttu-id="91e05-123">F #의 비동기 코드를 시작 하는 방법\#</span><span class="sxs-lookup"><span data-stu-id="91e05-123">How to start Async Code in F\#</span></span>

<span data-ttu-id="91e05-124">앞에서 설명한 대로 비동기 코드는 명시적으로 시작 해야 하는 다른 컨텍스트에서 수행할 작업에 대 한 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-124">As mentioned earlier, async code is a specification of work to be done in another context which needs to be explicitly started.</span></span> <span data-ttu-id="91e05-125">이렇게 하려면 두 가지는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-125">Here are two primary ways to accomplish this:</span></span>

1. <span data-ttu-id="91e05-126">`Async.RunSynchronously` 다른 스레드에서 비동기 워크플로 시작 하 고 그 결과 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-126">`Async.RunSynchronously` will start an async workflow on another thread and await its result.</span></span>

```fsharp
open System
open System.Net

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

 // Execution will pause until fetchHtmlAsync finishes
 let html = "https://dotnetfoundation.org" |> fetchHtmlAsync |> Async.RunSynchronously

 // you actually have the result from fetchHtmlAsync now!
 printfn "%s" html
 ```

2. <span data-ttu-id="91e05-127">`Async.Start` 비동기 워크플로 다른 스레드에서 시작 되며 됩니다 **되지** 그 결과 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-127">`Async.Start` will start an async workflow on another thread, and will **not** await its result.</span></span>

```fsharp
open System
open System.Net
  
let uploadDataAsync url data = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        webClient.UploadStringAsync(uri, data)
    }

let workflow = uploadDataAsync "https://url-to-upload-to.com" "hello, world!"

// Execution will continue after calling this!
Async.Start(workflow)

printfn "%s" "uploadDataAsync is running in the background..."
 ```

<span data-ttu-id="91e05-128">보다 구체적인 시나리오에 사용할 수 있는 비동기 워크플로 시작 하는 다른 방법 이며</span><span class="sxs-lookup"><span data-stu-id="91e05-128">There are other ways to start an async workflow available for more specific scenarios.</span></span> <span data-ttu-id="91e05-129">자세히 설명 [비동기 참조에서](https://msdn.microsoft.com/library/ee370232.aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-129">They are detailed [in the Async reference](https://msdn.microsoft.com/library/ee370232.aspx).</span></span>

### <a name="a-note-on-threads"></a><span data-ttu-id="91e05-130">스레드에 대 한 참고 사항</span><span class="sxs-lookup"><span data-stu-id="91e05-130">A Note on Threads</span></span>

<span data-ttu-id="91e05-131">"다른 스레드에서" 라는 문구는 위에서 언급 한 이지만 사실이 중요 **하기 위한 외관 비동기 워크플로 그렇다고 다중 스레딩**합니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-131">The phrase "on another thread" is mentioned above, but it is important to know that **this does not mean that async workflows are a facade for multithreading**.</span></span> <span data-ttu-id="91e05-132">워크플로 실제로 "이동" 하는 적은 양의 유용한 작업을 수행 하는 시간에 대 한 이론을 가져와 스레드 간에 합니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-132">The workflow actually "jumps" between threads, borrowing them for a small amount of time to do useful work.</span></span> <span data-ttu-id="91e05-133">비동기 워크플로 효과적으로 "대기" (예: 결과를 반환 하는 네트워크 호출에 대 한 대기 중), 다른 유용한 작업 이동 수행까지 시간에 차용 되었습니다 스레드에 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-133">When an async workflow is effectively "waiting" (for example, waiting for a network call to return something), any thread it was borrowing at the time is freed up to go do useful work on something else.</span></span> <span data-ttu-id="91e05-134">가능한 한 효과적으로 실행 하는 시스템을 이용 하는 비동기 워크플로 있으며 특히 고용량 I/O 시나리오에 대 한 강력한 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-134">This allows async workflows to utilize the system they run on as effectively as possible, and makes them especially strong for high-volume I/O scenarios.</span></span>

## <a name="how-to-add-parallelism-to-async-code"></a><span data-ttu-id="91e05-135">비동기 코드에 병렬 처리를 추가 하는 방법</span><span class="sxs-lookup"><span data-stu-id="91e05-135">How to Add Parallelism to Async Code</span></span>

<span data-ttu-id="91e05-136">경우에 따라 필요한 동시에 여러 비동기 작업을 수행 하 해당 결과 수집 하 고 수 있습니다 어떤 방식으로든에서 해석 합니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-136">Sometimes you may need to perform multiple asynchronous jobs in parallel, collect their results, and interpret them in some way.</span></span> <span data-ttu-id="91e05-137">`Async.Parallel` 강제 변환할 필요 없이 포함 하는 작업 병렬 라이브러리를 사용 하지 않고도이 작업을 수행할 수 있습니다 `Task<'T>` 고 `Async<'T>` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-137">`Async.Parallel` allows you to do this without needing to use the Task Parallel Library, which would involve needing to coerce `Task<'T>` and `Async<'T>` types.</span></span>

<span data-ttu-id="91e05-138">다음 예제에서는 사용할지 `Async.Parallel` 를 동시에 4 개의 인기 있는 사이트에서 HTML을 다운로드 하려면 해당 태스크를 완료 하려면 기다린 다음 다운로드 하는 HTML을 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-138">The following example will use `Async.Parallel` to download the HTML from four popular sites in parallel, wait for those tasks to complete, and then print the HTML which was downloaded.</span></span>

```fsharp
open System
open System.Net

let urlList = 
    [ "https://www.microsoft.com"
      "https://www.google.com"
      "https://www.amazon.com"
      "https://www.facebook.com" ]

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

let getHtmlList urls =
    urls
    |> Seq.map fetchHtmlAsync   // Build an Async<'T> for each site
    |> Async.Parallel           // Returns an Async<'T []>
    |> Async.RunSynchronously   // Wait for the result of the parallel work

let htmlList = getHtmlList urlList

// We now have the downloaded HTML for each site!
for html in htmlList do
    printfn "%s" html
```

## <a name="important-info-and-advice"></a><span data-ttu-id="91e05-139">중요한 정보 및 조언</span><span class="sxs-lookup"><span data-stu-id="91e05-139">Important Info and Advice</span></span>

*   <span data-ttu-id="91e05-140">사용할 수 있는 함수의 끝에 "Async"를 추가</span><span class="sxs-lookup"><span data-stu-id="91e05-140">Append "Async" to the end of any functions you’ll consume</span></span>

 <span data-ttu-id="91e05-141">명명 규칙 일 뿐 이기는 하지만 API 검색 기능 등 쉽게에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-141">Although this is just a naming convention, it does make things like API discoverability easier.</span></span> <span data-ttu-id="91e05-142">동일한 루틴의 동기 버전과 비동기 인 경우에 특히 명시적으로 지정 되는 이름을 통해 비동기는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-142">Particularly if there are synchronous and asynchronous versions of the same routine, it’s a good idea to explicitly state which is asynchronous via the name.</span></span>

*   <span data-ttu-id="91e05-143">컴파일러에 수신!</span><span class="sxs-lookup"><span data-stu-id="91e05-143">Listen to the compiler!</span></span>

 <span data-ttu-id="91e05-144">F#컴파일러는 매우 엄격한, "async" 코드를 동기적으로 실행 하므로 같은 까다로운 작업을 수행 하는 거의 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-144">F#’s compiler is very strict, making it nearly impossible to do something troubling like run "async" code synchronously.</span></span> <span data-ttu-id="91e05-145">경고에서 제공 하는 경우 것을 알게 하는 방법을 생각 하는 코드를 실행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-145">If you come across a warning, that’s a sign that the code won’t execute how you think it will.</span></span> <span data-ttu-id="91e05-146">즐거운 컴파일러를 만들 수 있는, 경우 예상 대로 코드를 실행할 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-146">If you can make the compiler happy, your code will most likely execute as expected.</span></span>

## <a name="for-the-cvb-programmer-looking-into-f"></a><span data-ttu-id="91e05-147">에 대 한는 C#F 살펴볼 /VB 프로그래머가\#</span><span class="sxs-lookup"><span data-stu-id="91e05-147">For the C#/VB Programmer Looking Into F\#</span></span>

<span data-ttu-id="91e05-148">이 섹션에서는 비동기 모델에 익숙한 가정 C#/VB.</span><span class="sxs-lookup"><span data-stu-id="91e05-148">This section assumes you’re familiar with the async model in C#/VB.</span></span> <span data-ttu-id="91e05-149">그렇지 않은 경우 [의 비동기 프로그래밍 C# ](../../../csharp/async.md) 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-149">If you are not, [Async Programming in C#](../../../csharp/async.md) is a starting point.</span></span>

<span data-ttu-id="91e05-150">간의 기본적인 차이는 C#/VB 비동기 모델 및 F# 비동기 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-150">There is a fundamental difference between the C#/VB async model and the F# async model.</span></span>

<span data-ttu-id="91e05-151">반환 하는 함수를 호출 하는 경우는 `Task` 또는 `Task<'T>`, 해당 작업이 이미 실행을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-151">When you call a function which returns a `Task` or `Task<'T>`, that job has already begun execution.</span></span> <span data-ttu-id="91e05-152">반환 된 핸들이 이미 실행 중인 비동기 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-152">The handle returned represents an already-running asynchronous job.</span></span> <span data-ttu-id="91e05-153">반면, 호출 하는 경우 비동기 함수 F#의 `Async<'a>` 반환 될 작업을 나타냅니다 **생성** 어느 시점입니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-153">In contrast, when you call an async function in F#, the `Async<'a>` returned represents a job which will be **generated** at some point.</span></span> <span data-ttu-id="91e05-154">비동기 작업의 수 있다는 점에서 강력 하 고는이 모델을 이해 F# 모두 연결 하 여 수월해 조건부로 수행 하 고 세부적인 제어를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-154">Understanding this model is powerful, because it allows for asynchronous jobs in F# to be chained together easier, performed conditionally, and be started with a finer grain of control.</span></span>

<span data-ttu-id="91e05-155">다른 몇 가지 유사점 및 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-155">There are a few other similarities and differences worth noting.</span></span>

### <a name="similarities"></a><span data-ttu-id="91e05-156">유사성</span><span class="sxs-lookup"><span data-stu-id="91e05-156">Similarities</span></span>

*   <span data-ttu-id="91e05-157">`let!`를 `use!`, 및 `do!` 비슷합니다 `await` 내에서 비동기 작업을 호출 하는 경우는 `async{ }` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-157">`let!`, `use!`, and `do!` are analogous to `await` when calling an async job from within an `async{ }` block.</span></span>

 <span data-ttu-id="91e05-158">세 개의 키워드 내 에서만 사용할 수는 `async { }` 블록 방법과 유사 `await` 내 에서만 호출할 수는 `async` 메서드.</span><span class="sxs-lookup"><span data-stu-id="91e05-158">The three keywords can only be used within an `async { }` block, similar to how `await` can only be invoked inside an `async` method.</span></span> <span data-ttu-id="91e05-159">간단히 말해 `let!` 캡처하고 결과 사용 하려는 경우입니다 `use!` 는 동일 하지만 해당 리소스를 사용 하는 후 정리 해야 무엇 인가 및 `do!` 완료 반환 값이 없는 비동기 워크플로에 대기 하려는 경우에 앞으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-159">In short, `let!` is for when you want to capture and use a result, `use!` is the same but for something whose resources should get cleaned after it’s used, and `do!` is for when you want to wait for an async workflow with no return value to finish before moving on.</span></span>

*   <span data-ttu-id="91e05-160">F#비슷한 방식으로 데이터 병렬 처리를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-160">F# supports data-parallelism in a similar way.</span></span>

 <span data-ttu-id="91e05-161">매우 다른 방식으로 작동 하지만 `Async.Parallel` 에 해당 `Task.WhenAll` 모두 완료 하는 경우 비동기 작업 집합의 결과 하고자 하는 시나리오에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-161">Although it operates very differently, `Async.Parallel` corresponds to `Task.WhenAll` for the scenario of wanting the results of a set of async jobs when they all complete.</span></span>

### <a name="differences"></a><span data-ttu-id="91e05-162">차이점</span><span class="sxs-lookup"><span data-stu-id="91e05-162">Differences</span></span>

*   <span data-ttu-id="91e05-163">중첩 된 `let!` 허용 되지를 달리 중첩 `await`</span><span class="sxs-lookup"><span data-stu-id="91e05-163">Nested `let!` is not allowed, unlike nested `await`</span></span>

 <span data-ttu-id="91e05-164">와 달리 `await`는 무기한으로 중첩 될 수 있습니다 `let!` 없으며 다른 내부에서 사용 하기 전에 해당 결과 있어야 합니다. `let!`, `do!`, 또는 `use!`합니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-164">Unlike `await`, which can be nested indefinitely, `let!` cannot and must have its result bound before using it inside of another `let!`, `do!`, or `use!`.</span></span>

*   <span data-ttu-id="91e05-165">취소 지원에는 F# 보다 C#/VB.</span><span class="sxs-lookup"><span data-stu-id="91e05-165">Cancellation support is simpler in F# than in C#/VB.</span></span>

 <span data-ttu-id="91e05-166">작업 중간에 실행 취소를 지 원하는 C#/VB 검사 해야 합니다 `IsCancellationRequested` 속성 또는 호출 `ThrowIfCancellationRequested()` 에 `CancellationToken` 비동기 메서드로 전달 되는 개체.</span><span class="sxs-lookup"><span data-stu-id="91e05-166">Supporting cancellation of a task midway through its execution in C#/VB requires checking the `IsCancellationRequested` property or calling `ThrowIfCancellationRequested()` on a `CancellationToken` object that’s passed into the async method.</span></span>

<span data-ttu-id="91e05-167">반면, F# 비동기 워크플로 더 자연스럽 게 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-167">In contrast, F# async workflows are more naturally cancellable.</span></span> <span data-ttu-id="91e05-168">취소는 간단한 3 단계로 이루어진 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-168">Cancellation is a simple three-step process.</span></span>

1. <span data-ttu-id="91e05-169">새 `CancellationTokenSource`를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-169">Create a new `CancellationTokenSource`.</span></span>
2. <span data-ttu-id="91e05-170">시작 함수에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-170">Pass it into a starting function.</span></span>
3. <span data-ttu-id="91e05-171">호출 `Cancel` 토큰에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-171">Call `Cancel` on the token.</span></span>

<span data-ttu-id="91e05-172">예제:</span><span class="sxs-lookup"><span data-stu-id="91e05-172">Example:</span></span>

```fsharp
open System.Threading

// Create a workflow which will loop forever.
let workflow =
    async {
        while true do
            printfn "Working..."
            do! Async.Sleep 1000
    }
    
let tokenSource = new CancellationTokenSource()

// Start the workflow in the background
Async.Start (workflow, tokenSource.Token)

// Executing the next line will stop the workflow
tokenSource.Cancel()
```

<span data-ttu-id="91e05-173">이제 끝났습니다.</span><span class="sxs-lookup"><span data-stu-id="91e05-173">And that’s it!</span></span>

## <a name="further-resources"></a><span data-ttu-id="91e05-174">추가 리소스:</span><span class="sxs-lookup"><span data-stu-id="91e05-174">Further resources:</span></span>

*   [<span data-ttu-id="91e05-175">MSDN에 대 한 비동기 워크플로</span><span class="sxs-lookup"><span data-stu-id="91e05-175">Async Workflows on MSDN</span></span>](https://msdn.microsoft.com/library/dd233250.aspx)
*   [<span data-ttu-id="91e05-176">에 대 한 비동기 시퀀스F#</span><span class="sxs-lookup"><span data-stu-id="91e05-176">Asynchronous Sequences for F#</span></span>](https://fsprojects.github.io/FSharp.Control.AsyncSeq/library/AsyncSeq.html)
*   [<span data-ttu-id="91e05-177">F#HTTP 데이터 유틸리티</span><span class="sxs-lookup"><span data-stu-id="91e05-177">F# Data HTTP Utilities</span></span>](https://fsharp.github.io/FSharp.Data/library/Http.html)