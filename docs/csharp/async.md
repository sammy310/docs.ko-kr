---
title: 비동기 프로그래밍 - C#
description: .NET Core에서 제공하는 C# 언어 수준 비동기 프로그래밍 모델에 대해 알아봅니다.
author: cartermp
ms.date: 05/20/2020
ms.technology: csharp-async
ms.assetid: b878c34c-a78f-419e-a594-a2b44fa521a4
ms.openlocfilehash: ee5edc80d9c020dbbeced3fc36d3ff273036d7b1
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761891"
---
# <a name="asynchronous-programming"></a><span data-ttu-id="30dd6-103">비동기 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="30dd6-103">Asynchronous programming</span></span>

<span data-ttu-id="30dd6-104">I/O 바인딩된 요구 사항이 있는 경우(예: 네트워크에 데이터 요청, 데이터베이스 액세스 또는 파일 시스템 읽기 및 쓰기) 비동기 프로그래밍을 활용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-104">If you have any I/O-bound needs (such as requesting data from a network, accessing a database, or reading and writing to a file system), you'll want to utilize asynchronous programming.</span></span> <span data-ttu-id="30dd6-105">부담이 큰 계산을 수행하는 것과 같이 CPU 바인딩된 코드가 있을 수도 있으며 이는 비동기 코드 작성의 좋은 시나리오이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-105">You could also have CPU-bound code, such as performing an expensive calculation, which is also a good scenario for writing async code.</span></span>

<span data-ttu-id="30dd6-106">C#에는 콜백을 조작하거나 비동기를 지원하는 라이브러리를 따를 필요 없이 비동기 코드를 쉽게 작성할 수 있는 언어 수준 비동기 프로그래밍 모델이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-106">C# has a language-level asynchronous programming model, which allows for easily writing asynchronous code, without having to juggle callbacks or conform to a library that supports asynchrony.</span></span> <span data-ttu-id="30dd6-107">이 모델은 [TAP(작업 기반 비동기 패턴)](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-107">It follows what is known as the [Task-based Asynchronous Pattern (TAP)](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).</span></span>

## <a name="overview-of-the-asynchronous-model"></a><span data-ttu-id="30dd6-108">비동기 모델 개요</span><span class="sxs-lookup"><span data-stu-id="30dd6-108">Overview of the asynchronous model</span></span>

<span data-ttu-id="30dd6-109">비동기 프로그래밍의 핵심은 비동기 작업을 모델링하는 `Task` 및 `Task<T>` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-109">The core of async programming is the `Task` and `Task<T>` objects, which model asynchronous operations.</span></span> <span data-ttu-id="30dd6-110">이러한 개체는 `async` 및 `await` 키워드를 통해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-110">They are supported by the `async` and `await` keywords.</span></span> <span data-ttu-id="30dd6-111">대부분의 경우 모델은 매우 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-111">The model is fairly simple in most cases:</span></span>

- <span data-ttu-id="30dd6-112">I/O 바인딩된 코드에서는 `async` 메서드의 내부에서 `Task` 또는 `Task<T>`를 반환하는 작업을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-112">For I/O-bound code, you await an operation that returns a `Task` or `Task<T>` inside of an `async` method.</span></span>
- <span data-ttu-id="30dd6-113">CPU 바인딩된 코드에서는 <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> 메서드로 백그라운드 스레드에서 시작되는 작업을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-113">For CPU-bound code, you await an operation that is started on a background thread with the <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="30dd6-114">`await` 키워드가 마법이 일어나는 곳입니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-114">The `await` keyword is where the magic happens.</span></span> <span data-ttu-id="30dd6-115">`await`를 수행한 메서드의 호출자에게 제어를 넘기고, 궁극적으로 UI가 응답하거나 서비스가 탄력적일 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-115">It yields control to the caller of the method that performed `await`, and it ultimately allows a UI to be responsive or a service to be elastic.</span></span> <span data-ttu-id="30dd6-116">`async` 및 `await` 외에 비동기 코드를 사용하는 [여러 방법](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)이 있지만, 이 문서에서는 언어 수준 구문을 집중적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-116">While [there are ways](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) to approach async code other than `async` and `await`, this article focuses on the language-level constructs.</span></span>

### <a name="io-bound-example-download-data-from-a-web-service"></a><span data-ttu-id="30dd6-117">I/O 바인딩 예제: 웹 서비스에서 데이터 다운로드</span><span class="sxs-lookup"><span data-stu-id="30dd6-117">I/O-bound example: Download data from a web service</span></span>

<span data-ttu-id="30dd6-118">단추가 눌릴 때 웹 서비스에서 일부 데이터를 다운로드해야 할 수 있지만 UI 스레드를 차단하지 않으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-118">You may need to download some data from a web service when a button is pressed, but don't want to block the UI thread.</span></span> <span data-ttu-id="30dd6-119">이 작업은 다음과 같이 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-119">It can be accomplished like this:</span></span>

```csharp
private readonly HttpClient _httpClient = new HttpClient();

downloadButton.Clicked += async (o, e) =>
{
    // This line will yield control to the UI as the request
    // from the web service is happening.
    //
    // The UI thread is now free to perform other work.
    var stringData = await _httpClient.GetStringAsync(URL);
    DoSomethingWithData(stringData);
};
```

<span data-ttu-id="30dd6-120">이 코드는 `Task` 개체 조작 시 위험에 빠지지 않고 의도(데이터를 비동기식으로 다운로드)를 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-120">The code expresses the intent (downloading data asynchronously) without getting bogged down in interacting with `Task` objects.</span></span>

### <a name="cpu-bound-example-perform-a-calculation-for-a-game"></a><span data-ttu-id="30dd6-121">CPU 바인딩 예제: 게임에 대한 계산 수행</span><span class="sxs-lookup"><span data-stu-id="30dd6-121">CPU-bound example: Perform a calculation for a game</span></span>

<span data-ttu-id="30dd6-122">단추를 누르면 화면의 많은 적에게 손상을 입힐 수 있는 모바일 게임을 작성한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-122">Say you're writing a mobile game where pressing a button can inflict damage on many enemies on the screen.</span></span> <span data-ttu-id="30dd6-123">손상 계산을 수행하는 것은 부담이 클 수 있고 UI 스레드에서 이 작업을 수행하면 계산이 수행될 때 게임이 일시 중지되는 것처럼 보입니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-123">Performing the damage calculation can be expensive, and doing it on the UI thread would make the game appear to pause as the calculation is performed!</span></span>

<span data-ttu-id="30dd6-124">이 작업을 처리하는 가장 좋은 방법은 `Task.Run`을 사용하여 작업을 수행하는 백그라운드 스레드를 시작하고 `await`를 사용하여 결과를 기다리는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-124">The best way to handle this is to start a background thread, which does the work using `Task.Run`, and await its result using `await`.</span></span> <span data-ttu-id="30dd6-125">이렇게 하면 작업이 수행되는 동안 UI가 매끄럽게 느껴질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-125">This allows the UI to feel smooth as the work is being done.</span></span>

```csharp
private DamageResult CalculateDamageDone()
{
    // Code omitted:
    //
    // Does an expensive calculation and returns
    // the result of that calculation.
}

calculateButton.Clicked += async (o, e) =>
{
    // This line will yield control to the UI while CalculateDamageDone()
    // performs its work. The UI thread is free to perform other work.
    var damageResult = await Task.Run(() => CalculateDamageDone());
    DisplayDamage(damageResult);
};
```

<span data-ttu-id="30dd6-126">이 코드는 단추 클릭 이벤트의 의도를 표현하고, 백그라운드 스레드를 수동으로 관리할 필요가 없고, 비차단 방식으로 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-126">This code cleanly expresses the intent of the button's click event, it doesn't require managing a background thread manually, and it does so in a non-blocking way.</span></span>

### <a name="what-happens-under-the-covers"></a><span data-ttu-id="30dd6-127">백그라운드에서 수행되는 작업</span><span class="sxs-lookup"><span data-stu-id="30dd6-127">What happens under the covers</span></span>

<span data-ttu-id="30dd6-128">비동기 작업과 관련하여 많은 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-128">There are many moving pieces where asynchronous operations are concerned.</span></span> <span data-ttu-id="30dd6-129">`Task` 및 `Task<T>`의 백그라운드에서 수행되는 작업이 궁금하면 [세부 비동기](../standard/async-in-depth.md) 문서에서 자세한 내용을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="30dd6-129">If you're curious about what's happening underneath the covers of `Task` and `Task<T>`, see the [Async in-depth](../standard/async-in-depth.md) article for more information.</span></span>

<span data-ttu-id="30dd6-130">C#에서는 컴파일러가 해당 코드를, `await`에 도달할 때 실행을 양도하고 백그라운드 작업이 완료될 때 실행을 다시 시작하는 것과 같은 작업을 추적하는 상태 시스템으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-130">On the C# side of things, the compiler transforms your code into a state machine that keeps track of things like yielding execution when an `await` is reached and resuming execution when a background job has finished.</span></span>

<span data-ttu-id="30dd6-131">이론적으로 보면 이 변환은 [비동기 약속 모델](https://en.wikipedia.org/wiki/Futures_and_promises)입니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-131">For the theoretically-inclined, this is an implementation of the [Promise Model of asynchrony](https://en.wikipedia.org/wiki/Futures_and_promises).</span></span>

## <a name="key-pieces-to-understand"></a><span data-ttu-id="30dd6-132">이해해야 할 주요 부분</span><span class="sxs-lookup"><span data-stu-id="30dd6-132">Key pieces to understand</span></span>

* <span data-ttu-id="30dd6-133">비동기 코드는 I/O 바인딩된 코드와 CPU 바인딩된 코드에 둘 다 사용할 수 있지만 시나리오마다 다르게 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-133">Async code can be used for both I/O-bound and CPU-bound code, but differently for each scenario.</span></span>
* <span data-ttu-id="30dd6-134">비동기 코드는 백그라운드에서 수행되는 작업을 모델링하는 데 사용되는 구문인 `Task<T>` 및 `Task`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-134">Async code uses `Task<T>` and `Task`, which are constructs used to model work being done in the background.</span></span>
* <span data-ttu-id="30dd6-135">`async` 키워드는 본문에서 `await` 키워드를 사용할 수 있는 비동기 메서드로 메서드를 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-135">The `async` keyword turns a method into an async method, which allows you to use the `await` keyword in its body.</span></span>
* <span data-ttu-id="30dd6-136">`await` 키워드가 적용되면 이 키워드는 호출 메서드를 일시 중단하고 대기 작업이 완료할 때까지 제어 권한을 다시 호출자에게 양도합니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-136">When the `await` keyword is applied, it suspends the calling method and yields control back to its caller until the awaited task is complete.</span></span>
* <span data-ttu-id="30dd6-137">`await`는 비동기 메서드 내부에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-137">`await` can only be used inside an async method.</span></span>

## <a name="recognize-cpu-bound-and-io-bound-work"></a><span data-ttu-id="30dd6-138">CPU 바인딩된 작업 및 I/O 바인딩된 작업 인식</span><span class="sxs-lookup"><span data-stu-id="30dd6-138">Recognize CPU-bound and I/O-bound work</span></span>

<span data-ttu-id="30dd6-139">이 가이드의 처음 두 예제에서는 I/O 바인딩된 작업과 CPU 바인딩된 작업에 `async` 및 `await`를 사용하는 방법을 설명했습니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-139">The first two examples of this guide showed how you can use `async` and `await` for I/O-bound and CPU-bound work.</span></span> <span data-ttu-id="30dd6-140">이 방법은 수행해야 하는 작업이 I/O 바인딩된 작업 또는 CPU 바인딩된 작업일 경우 이를 식별할 수 있는 키입니다. 이 방법이 코드 성능에 큰 영향을 미칠 수 있고 잠재적으로 특정 구문을 잘못 사용하게 될 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-140">It's key that you can identify when a job you need to do is I/O-bound or CPU-bound, because it can greatly affect the performance of your code and could potentially lead to misusing certain constructs.</span></span>

<span data-ttu-id="30dd6-141">다음은 코드를 작성하기 전에 질문해야 하는 두 가지 질문입니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-141">Here are two questions you should ask before you write any code:</span></span>

1. <span data-ttu-id="30dd6-142">코드가 데이터베이스의 데이터와 같은 무엇인가를 “기다리게” 되나요?</span><span class="sxs-lookup"><span data-stu-id="30dd6-142">Will your code be "waiting" for something, such as data from a database?</span></span>

   <span data-ttu-id="30dd6-143">대답이 "예"이면 **I/O 바인딩된** 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-143">If your answer is "yes", then your work is **I/O-bound**.</span></span>

1. <span data-ttu-id="30dd6-144">코드가 비용이 높은 계산을 수행하게 되나요?</span><span class="sxs-lookup"><span data-stu-id="30dd6-144">Will your code be performing an expensive computation?</span></span>

   <span data-ttu-id="30dd6-145">대답이 "예"이면 **CPU 바인딩된** 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-145">If you answered "yes", then your work is **CPU-bound**.</span></span>

<span data-ttu-id="30dd6-146">**I/O 바인딩된** 작업이 있을 경우 `Task.Run` *없이* `async` 및 `await`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-146">If the work you have is **I/O-bound**, use `async` and `await` *without* `Task.Run`.</span></span> <span data-ttu-id="30dd6-147">작업 병렬 라이브러리를 사용*하면 안 됩니다*.</span><span class="sxs-lookup"><span data-stu-id="30dd6-147">You *should not* use the Task Parallel Library.</span></span> <span data-ttu-id="30dd6-148">그 이유는 [세부 비동기](../standard/async-in-depth.md)에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-148">The reason for this is outlined in [Async in Depth](../standard/async-in-depth.md).</span></span>

<span data-ttu-id="30dd6-149">**CPU 바인딩된** 작업이 있고 빠른 응답이 필요할 경우 `async` 및 `await`를 사용하지만 `Task.Run`을 사용하여 또 다른 스레드에서 작업을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-149">If the work you have is **CPU-bound** and you care about responsiveness, use `async` and `await`, but spawn off the work on another thread *with* `Task.Run`.</span></span> <span data-ttu-id="30dd6-150">작업이 동시성 및 병렬 처리에 해당할 경우 [작업 병렬 라이브러리](../standard/parallel-programming/task-parallel-library-tpl.md)를 사용할 것을 고려할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-150">If the work is appropriate for concurrency and parallelism, also consider using the [Task Parallel Library](../standard/parallel-programming/task-parallel-library-tpl.md).</span></span>

<span data-ttu-id="30dd6-151">또한 항상 코드 실행을 측정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-151">Additionally, you should always measure the execution of your code.</span></span> <span data-ttu-id="30dd6-152">예를 들어 CPU 바인딩된 작업이 다중 스레딩 시 컨텍스트 전환의 오버헤드에 비해 부담이 크지 않은 상황이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-152">For example, you may find yourself in a situation where your CPU-bound work is not costly enough compared with the overhead of context switches when multithreading.</span></span> <span data-ttu-id="30dd6-153">모든 선택에는 절충점이 있습니다. 상황에 맞는 올바른 절충점을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-153">Every choice has its tradeoff, and you should pick the correct tradeoff for your situation.</span></span>

## <a name="more-examples"></a><span data-ttu-id="30dd6-154">추가 예제</span><span class="sxs-lookup"><span data-stu-id="30dd6-154">More examples</span></span>

<span data-ttu-id="30dd6-155">다음 예제에서는 C#에서 비동기 코드를 작성할 수 있는 다양한 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-155">The following examples demonstrate various ways you can write async code in C#.</span></span> <span data-ttu-id="30dd6-156">예제에서는 발생할 수 있는 몇 가지 시나리오를 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-156">They cover a few different scenarios you may come across.</span></span>

### <a name="extract-data-from-a-network"></a><span data-ttu-id="30dd6-157">네트워크에서 데이터 추출</span><span class="sxs-lookup"><span data-stu-id="30dd6-157">Extract data from a network</span></span>

<span data-ttu-id="30dd6-158">이 코드 조각은 홈페이지 <https://dotnetfoundation.org>에서 HTML을 다운로드하고 문자열 ".NET"이 HTML에서 발생하는 횟수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-158">This snippet downloads the HTML from the homepage at <https://dotnetfoundation.org> and counts the number of times the string ".NET" occurs in the HTML.</span></span> <span data-ttu-id="30dd6-159">이 작업을 수행하고 횟수를 반환하는 Web API 컨트롤러 메서드를 정의하기 위해 ASP.NET을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-159">It uses ASP.NET to define a Web API controller method, which performs this task and returns the number.</span></span>

> [!NOTE]
> <span data-ttu-id="30dd6-160">프로덕션 코드에서 HTML 구문 분석을 수행하려는 경우 정규식을 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="30dd6-160">If you plan on doing HTML parsing in production code, don't use regular expressions.</span></span> <span data-ttu-id="30dd6-161">대신 구문 분석 라이브러리를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="30dd6-161">Use a parsing library instead.</span></span>

```csharp
private readonly HttpClient _httpClient = new HttpClient();

[HttpGet, Route("DotNetCount")]
public async Task<int> GetDotNetCount()
{
    // Suspends GetDotNetCount() to allow the caller (the web server)
    // to accept another request, rather than blocking on this one.
    var html = await _httpClient.GetStringAsync("https://dotnetfoundation.org");

    return Regex.Matches(html, @"\.NET").Count;
}
```

<span data-ttu-id="30dd6-162">다음은 단추가 눌릴 때 같은 작업을 수행하는 유니버설 Windows 앱용으로 작성된 동일한 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-162">Here's the same scenario written for a Universal Windows App, which performs the same task when a Button is pressed:</span></span>

```csharp
private readonly HttpClient _httpClient = new HttpClient();

private async void OnSeeTheDotNetsButtonClick(object sender, RoutedEventArgs e)
{
    // Capture the task handle here so we can await the background task later.
    var getDotNetFoundationHtmlTask = _httpClient.GetStringAsync("https://dotnetfoundation.org");

    // Any other work on the UI thread can be done here, such as enabling a Progress Bar.
    // This is important to do here, before the "await" call, so that the user
    // sees the progress bar before execution of this method is yielded.
    NetworkProgressBar.IsEnabled = true;
    NetworkProgressBar.Visibility = Visibility.Visible;

    // The await operator suspends SeeTheDotNets_Click, returning control to its caller.
    // This is what allows the app to be responsive and not block the UI thread.
    var html = await getDotNetFoundationHtmlTask;
    int count = Regex.Matches(html, @"\.NET").Count;

    DotNetCountLabel.Text = $"Number of .NETs on dotnetfoundation.org: {count}";

    NetworkProgressBar.IsEnabled = false;
    NetworkProgressBar.Visibility = Visibility.Collapsed;
}
```

### <a name="wait-for-multiple-tasks-to-complete"></a><span data-ttu-id="30dd6-163">여러 작업이 완료될 때까지 대기</span><span class="sxs-lookup"><span data-stu-id="30dd6-163">Wait for multiple tasks to complete</span></span>

<span data-ttu-id="30dd6-164">동시에 데이터의 여러 부분을 검색해야 하는 상황이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-164">You may find yourself in a situation where you need to retrieve multiple pieces of data concurrently.</span></span> <span data-ttu-id="30dd6-165">`Task` API에는 여러 백그라운드 작업에서 비차단 대기를 수행하는 비동기 코드를 작성할 수 있는 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> 및 <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> 메서드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-165">The `Task` API contains two methods, <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>, that allow you to write asynchronous code that performs a non-blocking wait on multiple background jobs.</span></span>

<span data-ttu-id="30dd6-166">이 예제에서는 `userId` 집합에 대한 `User` 데이터를 확인하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-166">This example shows how you might grab `User` data for a set of `userId`s.</span></span>

```csharp
public async Task<User> GetUserAsync(int userId)
{
    // Code omitted:
    //
    // Given a user Id {userId}, retrieves a User object corresponding
    // to the entry in the database with {userId} as its Id.
}

public static async Task<IEnumerable<User>> GetUsersAsync(IEnumerable<int> userIds)
{
    var getUserTasks = new List<Task<User>>();
    foreach (int userId in userIds)
    {
        getUserTasks.Add(GetUserAsync(userId));
    }

    return await Task.WhenAll(getUserTasks);
}
```

<span data-ttu-id="30dd6-167">다음은 LINQ를 사용하여 이 코드를 보다 간결하게 작성하는 또 다른 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-167">Here's another way to write this more succinctly, using LINQ:</span></span>

```csharp
public async Task<User> GetUserAsync(int userId)
{
    // Code omitted:
    //
    // Given a user Id {userId}, retrieves a User object corresponding
    // to the entry in the database with {userId} as its Id.
}

public static async Task<User[]> GetUsersAsync(IEnumerable<int> userIds)
{
    var getUserTasks = userIds.Select(id => GetUserAsync(id));
    return await Task.WhenAll(getUserTasks);
}
```

<span data-ttu-id="30dd6-168">코드 양은 더 적지만 LINQ를 비동기 코드와 혼합할 경우 주의하세요.</span><span class="sxs-lookup"><span data-stu-id="30dd6-168">Although it's less code, take care when mixing LINQ with asynchronous code.</span></span> <span data-ttu-id="30dd6-169">LINQ는 연기된(지연) 실행을 사용하므로, `.ToList()` 또는 `.ToArray()` 호출을 반복하도록 생성된 시퀀스를 적용해야 비동기 호출이 `foreach` 루프에서 수행되면 즉시 비동기 호출이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-169">Because LINQ uses deferred (lazy) execution, async calls won't happen immediately as they do in a `foreach` loop unless you force the generated sequence to iterate with a call to `.ToList()` or `.ToArray()`.</span></span>

## <a name="important-info-and-advice"></a><span data-ttu-id="30dd6-170">중요한 정보 및 조언</span><span class="sxs-lookup"><span data-stu-id="30dd6-170">Important info and advice</span></span>

<span data-ttu-id="30dd6-171">비동기 프로그래밍을 사용하는 경우 예기치 않은 동작을 방지할 수 있는 몇 가지 세부 사항을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-171">With async programming there are some details to keep in mind which can prevent unexpected behavior.</span></span>

* <span data-ttu-id="30dd6-172">`async` **메서드에는 본문에**  `await`  **키워드가 있어야 합니다. 키워드가 없으면 일시 중단되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="30dd6-172">`async` **methods need to have an** `await` **keyword in their body or they will never yield!**</span></span>

  <span data-ttu-id="30dd6-173">기억해야 할 중요한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-173">This is important to keep in mind.</span></span> <span data-ttu-id="30dd6-174">`await`가 `async` 메서드의 본문에서 사용되지 않으면 C# 컴파일러가 경고를 생성하지만 코드는 일반 메서드인 것처럼 컴파일 및 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-174">If `await` is not used in the body of an `async` method, the C# compiler generates a warning, but the code compiles and runs as if it were a normal method.</span></span> <span data-ttu-id="30dd6-175">이는 C# 컴파일러가 비동기 메서드에 대해 생성한 상태 시스템이 아무것도 수행하지 않기 때문에 매우 비효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-175">This is incredibly inefficient, as the state machine generated by the C# compiler for the async method is not accomplishing anything.</span></span>

* <span data-ttu-id="30dd6-176">**작성하는 모든 비동기 메서드 이름의 접미사로 "Async"를 추가해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="30dd6-176">**You should add "Async" as the suffix of every async method name you write.**</span></span>

<span data-ttu-id="30dd6-177">이 규칙을 .NET에서 사용하여 동기 및 비동기 메서드를 더 쉽게 구별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-177">This is the convention used in .NET to more easily differentiate synchronous and asynchronous methods.</span></span> <span data-ttu-id="30dd6-178">코드에서 명시적으로 호출되지 않은 특정 메서드(예: 이벤트 처리기 또는 웹 컨트롤러 메서드)가 반드시 적용되는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-178">Certain methods that aren't explicitly called by your code (such as event handlers or web controller methods) don't necessarily apply.</span></span> <span data-ttu-id="30dd6-179">이러한 메서드는 코드에서 명시적으로 호출되지 않으므로 명시적으로 명명하는 것은 별로 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-179">Because they are not explicitly called by your code, being explicit about their naming isn't as important.</span></span>

* <span data-ttu-id="30dd6-180">`async void`는 **이벤트 처리기에만 사용해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="30dd6-180">`async void` **should only to be used for event handlers.**</span></span>

<span data-ttu-id="30dd6-181">이벤트에는 반환 형식이 없어서 `Task` 및 `Task<T>`를 사용할 수 없으므로 비동기 이벤트 처리기가 작동하도록 허용하는 유일한 방법은 `async void`입니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-181">`async void` is the only way to allow asynchronous event handlers to work because events do not have return types (thus cannot make use of `Task` and `Task<T>`).</span></span> <span data-ttu-id="30dd6-182">`async void`의 다른 사용은 TAP 모델을 따르지 않고 다음과 같이 사용이 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-182">Any other use of `async void` does not follow the TAP model and can be challenging to use, such as:</span></span>

* <span data-ttu-id="30dd6-183">`async void` 메서드에서 throw된 예외는 해당 메서드 외부에서 catch될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-183">Exceptions thrown in an `async void` method can't be caught outside of that method.</span></span>
* <span data-ttu-id="30dd6-184">`async void` 메서드는 테스트하기가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-184">`async void` methods are difficult to test.</span></span>
* <span data-ttu-id="30dd6-185">호출자가 `async void` 메서드를 비동기로 예상하지 않을 경우 이러한 메서드는 의도하지 않은 잘못된 결과를 일으킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-185">`async void` methods can cause bad side effects if the caller isn't expecting them to be async.</span></span>

* <span data-ttu-id="30dd6-186">**LINQ 식에서 비동기 람다를 사용할 경우 신중하게 스레드**</span><span class="sxs-lookup"><span data-stu-id="30dd6-186">**Tread carefully when using async lambdas in LINQ expressions**</span></span>

<span data-ttu-id="30dd6-187">LINQ의 람다 식은 연기된 실행을 사용합니다. 즉, 예상치 않은 시점에 코드 실행이 끝날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-187">Lambda expressions in LINQ use deferred execution, meaning code could end up executing at a time when you're not expecting it to.</span></span> <span data-ttu-id="30dd6-188">이 코드에 차단 작업을 도입하면 코드가 제대로 작성되지 않은 경우 교착 상태가 쉽게 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-188">The introduction of blocking tasks into this can easily result in a deadlock if not written correctly.</span></span> <span data-ttu-id="30dd6-189">또한 이 코드처럼 비동기 코드를 중첩하면 코드 실행에 대해 추론하기가 훨씬 더 어려울 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-189">Additionally, the nesting of asynchronous code like this can also make it more difficult to reason about the execution of the code.</span></span> <span data-ttu-id="30dd6-190">비동기 및 LINQ는 강력하지만 가능한 한 신중하고 분명하게 함께 사용되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-190">Async and LINQ are powerful, but should be used together as carefully and clearly as possible.</span></span>

* <span data-ttu-id="30dd6-191">**비차단 방식으로 작업을 기다리는 코드 작성**</span><span class="sxs-lookup"><span data-stu-id="30dd6-191">**Write code that awaits Tasks in a non-blocking manner**</span></span>

<span data-ttu-id="30dd6-192">`Task`가 완료될 때까지 대기하는 수단으로 현재 스레드를 차단하면 교착 상태가 발생하고 컨텍스트 스레드가 차단될 수 있고 더 복잡한 오류 처리가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-192">Blocking the current thread as a means to wait for a `Task` to complete can result in deadlocks and blocked context threads, and can require more complex error-handling.</span></span> <span data-ttu-id="30dd6-193">다음 표에서는 비차단 방식으로 작업 대기를 처리하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-193">The following table provides guidance on how to deal with waiting for tasks in a non-blocking way:</span></span>

| <span data-ttu-id="30dd6-194">사용 방법</span><span class="sxs-lookup"><span data-stu-id="30dd6-194">Use this...</span></span>          | <span data-ttu-id="30dd6-195">대체 방법</span><span class="sxs-lookup"><span data-stu-id="30dd6-195">Instead of this...</span></span>           | <span data-ttu-id="30dd6-196">수행할 작업</span><span class="sxs-lookup"><span data-stu-id="30dd6-196">When wishing to do this...</span></span>                 |
|----------------------|------------------------------|--------------------------------------------|
| `await`              | <span data-ttu-id="30dd6-197">`Task.Wait` 또는 `Task.Result`</span><span class="sxs-lookup"><span data-stu-id="30dd6-197">`Task.Wait` or `Task.Result`</span></span> | <span data-ttu-id="30dd6-198">백그라운드 작업의 결과 검색</span><span class="sxs-lookup"><span data-stu-id="30dd6-198">Retrieving the result of a background task</span></span> |
| `await Task.WhenAny` | `Task.WaitAny`               | <span data-ttu-id="30dd6-199">작업이 완료될 때까지 대기</span><span class="sxs-lookup"><span data-stu-id="30dd6-199">Waiting for any task to complete</span></span>           |
| `await Task.WhenAll` | `Task.WaitAll`               | <span data-ttu-id="30dd6-200">모든 작업이 완료될 때까지 대기</span><span class="sxs-lookup"><span data-stu-id="30dd6-200">Waiting for all tasks to complete</span></span>          |
| `await Task.Delay`   | `Thread.Sleep`               | <span data-ttu-id="30dd6-201">일정 기간 대기</span><span class="sxs-lookup"><span data-stu-id="30dd6-201">Waiting for a period of time</span></span>               |

* <span data-ttu-id="30dd6-202">**가능하면** `ValueTask`를 **사용**</span><span class="sxs-lookup"><span data-stu-id="30dd6-202">**Consider using** `ValueTask` **where possible**</span></span>

<span data-ttu-id="30dd6-203">비동기 메서드에서 `Task` 개체를 반환하면 특정 경로에 성능 병목 현상이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-203">Returning a `Task` object from async methods can introduce performance bottlenecks in certain paths.</span></span> <span data-ttu-id="30dd6-204">`Task`는 참조 형식이므로 이를 사용하는 것은 개체 할당을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-204">`Task` is a reference type, so using it means allocating an object.</span></span> <span data-ttu-id="30dd6-205">`async` 한정자로 선언된 메서드가 캐시된 결과를 반환하거나 동기적으로 완료된 경우 코드의 성능이 중요한 섹션에서 추가 할당에 상당한 시간이 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-205">In cases where a method declared with the `async` modifier returns a cached result or completes synchronously, the extra allocations can become a significant time cost in performance critical sections of code.</span></span> <span data-ttu-id="30dd6-206">연속 루프에서 이러한 할당이 발생하면 부담이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-206">It can become costly if those allocations occur in tight loops.</span></span> <span data-ttu-id="30dd6-207">자세한 내용은 [일반화된 비동기 반환 형식](whats-new/csharp-7.md#generalized-async-return-types)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30dd6-207">For more information, see [generalized async return types](whats-new/csharp-7.md#generalized-async-return-types).</span></span>

* <span data-ttu-id="30dd6-208">`ConfigureAwait(false)`를 **사용**</span><span class="sxs-lookup"><span data-stu-id="30dd6-208">**Consider using** `ConfigureAwait(false)`</span></span>

<span data-ttu-id="30dd6-209">일반적인 질문은 "언제 <xref:System.Threading.Tasks.Task.ConfigureAwait(System.Boolean)?displayProperty=nameWithType> 메서드를 사용해야 하는가"입니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-209">A common question is, "when should I use the <xref:System.Threading.Tasks.Task.ConfigureAwait(System.Boolean)?displayProperty=nameWithType> method?".</span></span> <span data-ttu-id="30dd6-210">이 메서드를 사용하면 `Task` 인스턴스가 awaiter를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-210">The method allows for a `Task` instance to configure its awaiter.</span></span> <span data-ttu-id="30dd6-211">이는 중요한 고려 사항이며 잘못 설정할 경우 성능에 영향을 미칠 수 있고 심지어 교착 상태가 발생할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-211">This is an important consideration and setting it incorrectly could potentially have performance implications and even deadlocks.</span></span> <span data-ttu-id="30dd6-212">`ConfigureAwait`에 대한 자세한 내용은 [ConfigureAwait FAQ](https://devblogs.microsoft.com/dotnet/configureawait-faq)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30dd6-212">For more information on `ConfigureAwait`, see the [ConfigureAwait FAQ](https://devblogs.microsoft.com/dotnet/configureawait-faq).</span></span>

* <span data-ttu-id="30dd6-213">**상태 저장 코드 작성 분량 감소**</span><span class="sxs-lookup"><span data-stu-id="30dd6-213">**Write less stateful code**</span></span>

<span data-ttu-id="30dd6-214">전역 개체의 상태나 특정 메서드의 실행에 의존하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="30dd6-214">Don't depend on the state of global objects or the execution of certain methods.</span></span> <span data-ttu-id="30dd6-215">대신, 메서드의 반환 값에만 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-215">Instead, depend only on the return values of methods.</span></span> <span data-ttu-id="30dd6-216">이유</span><span class="sxs-lookup"><span data-stu-id="30dd6-216">Why?</span></span>

* <span data-ttu-id="30dd6-217">코드를 더 쉽게 추론할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-217">Code will be easier to reason about.</span></span>
* <span data-ttu-id="30dd6-218">코드를 더 쉽게 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-218">Code will be easier to test.</span></span>
* <span data-ttu-id="30dd6-219">비동기 및 동기 코드를 훨씬 더 쉽게 혼합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-219">Mixing async and synchronous code is far simpler.</span></span>
* <span data-ttu-id="30dd6-220">일반적으로 함께 경합 상태를 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-220">Race conditions can typically be avoided altogether.</span></span>
* <span data-ttu-id="30dd6-221">반환 값에 의존하면 비동기 코드를 간단히 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-221">Depending on return values makes coordinating async code simple.</span></span>
* <span data-ttu-id="30dd6-222">(이점) 이 방법은 실제로 종속성 주입에도 잘 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-222">(Bonus) it works really well with dependency injection.</span></span>

<span data-ttu-id="30dd6-223">권장되는 목적은 코드에서 완전하거나 거의 완전한 [참조 투명성](https://en.wikipedia.org/wiki/Referential_transparency_%28computer_science%29)을 달성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-223">A recommended goal is to achieve complete or near-complete [Referential Transparency](https://en.wikipedia.org/wiki/Referential_transparency_%28computer_science%29) in your code.</span></span> <span data-ttu-id="30dd6-224">이렇게 하면 확실히 예측 가능하고, 테스트 가능하고, 유지 관리 가능한 코드베이스가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-224">Doing so will result in an extremely predictable, testable, and maintainable codebase.</span></span>

## <a name="other-resources"></a><span data-ttu-id="30dd6-225">기타 리소스</span><span class="sxs-lookup"><span data-stu-id="30dd6-225">Other resources</span></span>

* <span data-ttu-id="30dd6-226">[세부 비동기](../standard/async-in-depth.md)에서는 작업이 어떻게 작동하는지 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-226">[Async in-depth](../standard/async-in-depth.md) provides more information about how Tasks work.</span></span>
* [<span data-ttu-id="30dd6-227">async 및 await를 사용한 비동기 프로그래밍(C#)</span><span class="sxs-lookup"><span data-stu-id="30dd6-227">Asynchronous programming with async and await (C#)</span></span>](./programming-guide/concepts/async/index.md)
* <span data-ttu-id="30dd6-228">Lucian Wischik의 [Six Essential Tips for Async](https://channel9.msdn.com/Series/Three-Essential-Tips-for-Async)(비동기에 대한 6가지 필수 팁)는 비동기 프로그래밍에 대한 훌륭한 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="30dd6-228">Lucian Wischik's [Six Essential Tips for Async](https://channel9.msdn.com/Series/Three-Essential-Tips-for-Async) are a wonderful resource for async programming</span></span>
