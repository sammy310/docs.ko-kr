---
title: 비동기 프로그래밍F#
description: 핵심 함수형 F# 프로그래밍 개념에서 파생 된 언어 수준 프로그래밍 모델을 기반으로 비동기에 대 한 완전 한 지원을 제공 하는 방법을 알아봅니다.
ms.date: 12/17/2018
ms.openlocfilehash: 1ede4a5c1e26df271ac94f9b2c216ac84fb38f59
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395785"
---
# <a name="async-programming-in-f"></a><span data-ttu-id="2d0b7-103">F \#의 비동기 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="2d0b7-103">Async programming in F\#</span></span>

<span data-ttu-id="2d0b7-104">비동기 프로그래밍은 다양 한 이유로 최신 응용 프로그램에 필수적인 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-104">Asynchronous programming is a mechanism that is essential to modern applications for diverse reasons.</span></span> <span data-ttu-id="2d0b7-105">대부분의 개발자가 직면 하는 두 가지 주요 사용 사례는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-105">There are two primary use cases that most developers will encounter:</span></span>

- <span data-ttu-id="2d0b7-106">많은 수의 동시 들어오는 요청을 처리할 수 있는 서버 프로세스를 제공 하는 동시에 프로세스의 외부 시스템 또는 서비스에서 기다립니다 입력을 요청 하는 동안 시스템 리소스를 최소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-106">Presenting a server process that can service a significant number of concurrent incoming requests, while minimizing the system resources occupied while request processing awaits inputs from systems or services external to that process</span></span>
- <span data-ttu-id="2d0b7-107">백그라운드 작업을 동시에 진행 하는 동안 응답성이 뛰어난 UI 또는 주 스레드 유지 관리</span><span class="sxs-lookup"><span data-stu-id="2d0b7-107">Maintaining a responsive UI or main thread while concurrently progressing background work</span></span>

<span data-ttu-id="2d0b7-108">백그라운드 작업은 종종 여러 스레드를 사용 하는 경우를 제외 하 고 비동기 및 다중 스레딩의 개념을 별도로 고려 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-108">Although background work often does involve the utilization of multiple threads, it's important to consider the concepts of asynchrony and multi-threading separately.</span></span> <span data-ttu-id="2d0b7-109">사실 이러한 문제는 별개의 문제 이며 다른 항목을 의미 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-109">In fact, they are separate concerns, and one does not imply the other.</span></span> <span data-ttu-id="2d0b7-110">이 문서에서 설명 하는 내용에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-110">What follows in this article will describe this in more detail.</span></span>

## <a name="asynchrony-defined"></a><span data-ttu-id="2d0b7-111">비동기 정의 됨</span><span class="sxs-lookup"><span data-stu-id="2d0b7-111">Asynchrony defined</span></span>

<span data-ttu-id="2d0b7-112">이전 점-비동기은 여러 스레드를 사용 하는 것과 독립적입니다. 조금 더 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-112">The previous point - that asynchrony is independent of the utilization of multiple threads - is worth explaining a bit further.</span></span> <span data-ttu-id="2d0b7-113">경우에 따라 관련 된 세 가지 개념은 서로 독립적입니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-113">There are three concepts that are sometimes related, but strictly independent of one another:</span></span>

- <span data-ttu-id="2d0b7-114">동시성 여러 계산이 겹치는 기간 동안 실행 되는 경우</span><span class="sxs-lookup"><span data-stu-id="2d0b7-114">Concurrency; when multiple computations execute in overlapping time periods.</span></span>
- <span data-ttu-id="2d0b7-115">병렬로 단일 계산의 여러 계산 또는 여러 부분이 정확히 동시에 실행 되는 경우</span><span class="sxs-lookup"><span data-stu-id="2d0b7-115">Parallelism; when multiple computations or several parts of a single computation run at exactly the same time.</span></span>
- <span data-ttu-id="2d0b7-116">비동기 하나 이상의 계산이 주 프로그램 흐름과 별도로 실행 될 수 있는 경우</span><span class="sxs-lookup"><span data-stu-id="2d0b7-116">Asynchrony; when one or more computations can execute separately from the main program flow.</span></span>

<span data-ttu-id="2d0b7-117">세 가지 모두 직교 개념 이지만 특히 함께 사용 하는 경우에는 쉽게 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-117">All three are orthogonal concepts, but can be easily conflated, especially when they are used together.</span></span> <span data-ttu-id="2d0b7-118">예를 들어 여러 비동기 계산을 동시에 실행 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-118">For example, you may need to execute multiple asynchronous computations in parallel.</span></span> <span data-ttu-id="2d0b7-119">이것은 병렬 처리 또는 비동기이 다른 것을 의미 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-119">This does not mean that parallelism or asynchrony imply one another.</span></span>

<span data-ttu-id="2d0b7-120">"Etymology" 라는 단어를 고려 하는 경우에는 두 가지 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-120">If you consider the etymology of the word "asynchronous", there are two pieces involved:</span></span>

- <span data-ttu-id="2d0b7-121">"not"을 의미 하는 "a"입니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-121">"a", meaning "not".</span></span>
- <span data-ttu-id="2d0b7-122">"동기", 즉 "동시" 의미를 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-122">"synchronous", meaning "at the same time".</span></span>

<span data-ttu-id="2d0b7-123">이러한 두 용어를 함께 배치 하는 경우 "비동기"는 "동시에" 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-123">When you put these two terms together, you'll see that "asynchronous" means "not at the same time".</span></span> <span data-ttu-id="2d0b7-124">정말 간단하죠.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-124">That's it!</span></span> <span data-ttu-id="2d0b7-125">이 정의에서는 동시성 또는 병렬 처리의 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-125">There is no implication of concurrency or parallelism in this definition.</span></span> <span data-ttu-id="2d0b7-126">이는 실제로도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-126">This is also true in practice.</span></span>

<span data-ttu-id="2d0b7-127">실제로의 F# 비동기 계산은 주 프로그램 흐름과 독립적으로 실행 되도록 예약 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-127">In practical terms, asynchronous computations in F# are scheduled to execute independently of the main program flow.</span></span> <span data-ttu-id="2d0b7-128">이는 동시성이 나 병렬 처리를 의미 하지 않으며, 백그라운드에서 계산이 항상 발생 한다는 의미는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-128">This doesn't imply concurrency or parallelism, nor does it imply that a computation always happens in the background.</span></span> <span data-ttu-id="2d0b7-129">실제로 비동기 계산은 계산의 특성과 계산을 실행 하는 환경에 따라 동기적으로 실행 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-129">In fact, asynchronous computations can even execute synchronously, depending on the nature of the computation and the environment the computation is executing in.</span></span>

<span data-ttu-id="2d0b7-130">가장 중요 한 요점은는 비동기 계산이 주 프로그램 흐름과 독립적 이라고 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-130">The main takeaway you should have is that asynchronous computations are independent of the main program flow.</span></span> <span data-ttu-id="2d0b7-131">비동기 계산이 실행 되는 시기 또는 방법에 대 한 보장은 거의 없지만 오케스트레이션 하 고 예약 하는 몇 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-131">Although there are few guarantees about when or how an asynchronous computation executes, there are some approaches to orchestrating and scheduling them.</span></span> <span data-ttu-id="2d0b7-132">이 문서의 나머지 부분에서는 비동기의 F# 핵심 개념과에 F#기본 제공 되는 형식, 함수 및 식을 사용 하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-132">The rest of this article explores core concepts for F# asynchrony and how to use the types, functions, and expressions built into F#.</span></span>

## <a name="core-concepts"></a><span data-ttu-id="2d0b7-133">핵심 개념</span><span class="sxs-lookup"><span data-stu-id="2d0b7-133">Core concepts</span></span>

<span data-ttu-id="2d0b7-134">에서 F#비동기 프로그래밍은 세 가지 핵심 개념을 중심으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-134">In F#, asynchronous programming is centered around three core concepts:</span></span>

- <span data-ttu-id="2d0b7-135">구성 가능한 비동기 계산을 나타내는 `Async<'T>` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-135">The `Async<'T>` type, which represents a composable asynchronous computation.</span></span>
- <span data-ttu-id="2d0b7-136">비동기 작업을 예약 하 고, 비동기 계산을 구성 하 고, 비동기 결과를 변환 하는 데 사용할 수 있는 `Async` 모듈 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-136">The `Async` module functions, which let you schedule asynchronous work, compose asynchronous computations, and transform asynchronous results.</span></span>
- <span data-ttu-id="2d0b7-137">비동기 계산을 작성 하 고 제어 하기 위한 편리한 구문을 제공 하는 `async { }` [계산 식](../../language-reference/computation-expressions.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-137">The `async { }` [computation expression](../../language-reference/computation-expressions.md), which provides a convenient syntax for building and controlling asynchronous computations.</span></span>

<span data-ttu-id="2d0b7-138">다음 예제에서는 이러한 세 가지 개념을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-138">You can see these three concepts in the following example:</span></span>

```fsharp
open System
open System.IO

let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    printTotalFileBytes "path-to-file.txt"
    |> Async.RunSynchronously

    Console.Read() |> ignore
    0
```

<span data-ttu-id="2d0b7-139">예제에서 `printTotalFileBytes` 함수는 `string -> Async<unit>` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-139">In the example, the `printTotalFileBytes` function is of type `string -> Async<unit>`.</span></span> <span data-ttu-id="2d0b7-140">함수를 호출 하면 실제로 비동기 계산이 실행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-140">Calling the function does not actually execute the asynchronous computation.</span></span> <span data-ttu-id="2d0b7-141">대신 비동기적으로 실행 되는 작업의 \* 사양 역할을 하는 `Async<unit>`를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-141">Instead, it returns an `Async<unit>` that acts as a \*specification- of the work that is to execute asynchronously.</span></span> <span data-ttu-id="2d0b7-142">본문에서 `Async.AwaitTask`를 호출 하 고, 호출 될 때 <xref:System.IO.File.WriteAllBytesAsync%2A>의 결과를 적절 한 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-142">It will call `Async.AwaitTask` in its body, which will convert the result of <xref:System.IO.File.WriteAllBytesAsync%2A> to an appropriate type when it is called.</span></span>

<span data-ttu-id="2d0b7-143">또 다른 중요 한 줄은 `Async.RunSynchronously`에 대 한 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-143">Another important line is the call to `Async.RunSynchronously`.</span></span> <span data-ttu-id="2d0b7-144">F# 비동기 계산을 실제로 실행 하려는 경우 호출 해야 하는 비동기 모듈 시작 함수 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-144">This is one of the Async module starting functions that you'll need to call if you want to actually execute an F# asynchronous computation.</span></span>

<span data-ttu-id="2d0b7-145">이는 `async` 프로그래밍의 C#/vb 스타일과 근본적으로 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-145">This is a fundamental difference with the C#/VB style of `async` programming.</span></span> <span data-ttu-id="2d0b7-146">에서 F#비동기 계산은 **콜드 작업**으로 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-146">In F#, asynchronous computations can be thought of as **Cold tasks**.</span></span> <span data-ttu-id="2d0b7-147">실제로를 실행 하려면 명시적으로 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-147">They must be explicitly started to actually execute.</span></span> <span data-ttu-id="2d0b7-148">이는 C#/vb. 비동기 작업을 훨씬 더 쉽게 결합 하 고 시퀀스를 수행할 수 있기 때문에 몇 가지 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-148">This has some advantages, as it allows you to combine and sequence asynchronous work much more easily than in C#/VB.</span></span>

## <a name="combining-asynchronous-computations"></a><span data-ttu-id="2d0b7-149">비동기 계산 결합</span><span class="sxs-lookup"><span data-stu-id="2d0b7-149">Combining asynchronous computations</span></span>

<span data-ttu-id="2d0b7-150">다음은 계산을 결합 하 여 이전 예제를 기반으로 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-150">Here is an example that builds upon the previous one by combining computations:</span></span>

```fsharp
open System
open System.IO

let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    argv
    |> Array.map printTotalFileBytes
    |> Async.Parallel
    |> Async.Ignore
    |> Async.RunSynchronously

    0
```

<span data-ttu-id="2d0b7-151">여기서 볼 수 있듯이 `main` 함수에는 몇 가지 추가 호출이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-151">As you can see, the `main` function has quite a few more calls made.</span></span> <span data-ttu-id="2d0b7-152">개념적으로 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-152">Conceptually, it does the following:</span></span>

1. <span data-ttu-id="2d0b7-153">@No__t_1를 사용 하 여 명령줄 인수를 `Async<unit>` 계산으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-153">Transform the command-line arguments into `Async<unit>` computations with `Array.map`.</span></span>
2. <span data-ttu-id="2d0b7-154">@No__t_1 계산이 실행 될 때 병렬 실행을 예약 하 고 실행 하는 `Async<'T[]>`을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-154">Create an `Async<'T[]>` that schedules and runs the `printTotalFileBytes` computations in parallel when it runs.</span></span>
3. <span data-ttu-id="2d0b7-155">병렬 계산을 실행 하 고 결과를 무시 하는 `Async<unit>`을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-155">Create an `Async<unit>` that will run the parallel computation and ignore its result.</span></span>
4. <span data-ttu-id="2d0b7-156">@No__t_0를 사용 하 여 마지막 계산을 명시적으로 실행 하 고 완료 될 때까지 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-156">Explicitly run the last computation with `Async.RunSynchronously` and block until it is completes.</span></span>

<span data-ttu-id="2d0b7-157">이 프로그램을 실행 하면 `printTotalFileBytes` 각 명령줄 인수에 대해 동시에 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-157">When this program runs, `printTotalFileBytes` runs in parallel for each command-line argument.</span></span> <span data-ttu-id="2d0b7-158">비동기 계산은 프로그램 흐름과 별개로 실행 되므로 정보를 인쇄 하 고 실행을 완료 하는 순서는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-158">Because asynchronous computations execute independently of program flow, there is no order in which they print their information and finish executing.</span></span> <span data-ttu-id="2d0b7-159">계산은 병렬로 예약 되지만 실행 순서는 보장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-159">The computations will be scheduled in parallel, but their order of execution is not guaranteed.</span></span>

## <a name="sequencing-asynchronous-computations"></a><span data-ttu-id="2d0b7-160">비동기 계산 시퀀싱</span><span class="sxs-lookup"><span data-stu-id="2d0b7-160">Sequencing asynchronous computations</span></span>

<span data-ttu-id="2d0b7-161">@No__t_0은 이미 실행 중인 태스크가 아니라 작업 사양 이므로 더 복잡 한 변환을 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-161">Because `Async<'T>` is a specification of work rather than an already-running task, you can perform more intricate transformations easily.</span></span> <span data-ttu-id="2d0b7-162">다음은 비동기 계산 집합을 시퀀스 하 여 한 번 실행 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-162">Here is an example that sequences a set of Async computations so they execute one after another.</span></span>

```fsharp
let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    argv
    |> Array.map printTotalFileBytes
    |> Async.Sequential
    |> Async.RunSynchronously
    |> ignore
```

<span data-ttu-id="2d0b7-163">이렇게 하면 동시에 예약 하는 대신 `argv`의 요소 순서에 따라 실행 `printTotalFileBytes` 예약 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-163">This will schedule `printTotalFileBytes` to execute in the order of the elements of `argv` rather than scheduling them in parallel.</span></span> <span data-ttu-id="2d0b7-164">다음 항목은 마지막 계산 실행이 완료 될 때까지 예약 되지 않기 때문에 계산이 계산 되어 실행에 겹치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-164">Because the next item will not be scheduled until after the last computation has finished executing, the computations are sequenced such that there is no overlap in their execution.</span></span>

## <a name="important-async-module-functions"></a><span data-ttu-id="2d0b7-165">중요 한 비동기 모듈 함수</span><span class="sxs-lookup"><span data-stu-id="2d0b7-165">Important Async module functions</span></span>

<span data-ttu-id="2d0b7-166">에서 F# 비동기 코드를 작성 하는 경우 일반적으로 계산 예약을 처리 하는 프레임 워크와 상호 작용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-166">When you write async code in F# you'll usually interact with a framework that handles scheduling of computations for you.</span></span> <span data-ttu-id="2d0b7-167">그러나이는 항상 그렇지는 않기 때문에 비동기 작업을 예약 하는 다양 한 시작 함수를 배우는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-167">However, this is not always the case, so it is good to learn the various starting functions to schedule asynchronous work.</span></span>

<span data-ttu-id="2d0b7-168">비동기 F# 계산은 이미 실행 중인 작업의 표현이 아니라 작업의 _사양_ 이므로 시작 함수를 사용 하 여 명시적으로 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-168">Because F# asynchronous computations are a _specification_ of work rather than a representation of work that is already executing, they must be explicitly started with a starting function.</span></span> <span data-ttu-id="2d0b7-169">여러 컨텍스트에서 유용 하 게 사용할 수 있는 여러 [비동기 시작 함수가](https://msdn.microsoft.com/library/ee370232.aspx) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-169">There are many [Async starting functions](https://msdn.microsoft.com/library/ee370232.aspx) that are helpful in different contexts.</span></span> <span data-ttu-id="2d0b7-170">다음 섹션에서는 몇 가지 일반적인 시작 함수에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-170">The following section describes some of the more common starting functions.</span></span>

### <a name="asyncstartchild"></a><span data-ttu-id="2d0b7-171">Async. StartChild</span><span class="sxs-lookup"><span data-stu-id="2d0b7-171">Async.StartChild</span></span>

<span data-ttu-id="2d0b7-172">비동기 계산 내에서 자식 계산을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-172">Starts a child computation within an asynchronous computation.</span></span> <span data-ttu-id="2d0b7-173">이렇게 하면 여러 비동기 계산을 동시에 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-173">This allows multiple asynchronous computations to be executed concurrently.</span></span> <span data-ttu-id="2d0b7-174">자식 계산은 부모 계산과 함께 취소 토큰을 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-174">The child computation shares a cancellation token with the parent computation.</span></span> <span data-ttu-id="2d0b7-175">부모 계산이 취소 되 면 자식 계산도 취소 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-175">If the parent computation is canceled, the child computation is also canceled.</span></span>

<span data-ttu-id="2d0b7-176">서명과</span><span class="sxs-lookup"><span data-stu-id="2d0b7-176">Signature:</span></span>

```fsharp
computation: Async<'T> - timeout: ?int -> Async<Async<'T>>
```

<span data-ttu-id="2d0b7-177">사용되는 경우:</span><span class="sxs-lookup"><span data-stu-id="2d0b7-177">When to use:</span></span>

- <span data-ttu-id="2d0b7-178">한 번에 여러 비동기 계산을 동시에 실행 하는 것이 아니라 동시에 병렬로 예약 하지 않으려는 경우</span><span class="sxs-lookup"><span data-stu-id="2d0b7-178">When you want to execute multiple asynchronous computations concurrently rather than one at a time, but not have them scheduled in parallel.</span></span>
- <span data-ttu-id="2d0b7-179">자식 계산의 수명을 부모 계산의 수명에 연결 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="2d0b7-179">When you wish to tie the lifetime of a child computation to that of a parent computation.</span></span>

<span data-ttu-id="2d0b7-180">조사할 내용:</span><span class="sxs-lookup"><span data-stu-id="2d0b7-180">What to watch out for:</span></span>

- <span data-ttu-id="2d0b7-181">@No__t_0를 사용 하 여 여러 계산을 시작 하는 것은 병렬로 일정을 예약 하는 것과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-181">Starting multiple computations with `Async.StartChild` isn't the same as scheduling them in parallel.</span></span> <span data-ttu-id="2d0b7-182">계산을 병렬로 예약 하려는 경우 `Async.Parallel`를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-182">If you wish to schedule computations in parallel, use `Async.Parallel`.</span></span>
- <span data-ttu-id="2d0b7-183">부모 계산을 취소 하면 시작 된 모든 자식 계산의 취소가 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-183">Canceling a parent computation will trigger cancellation of all child computations it started.</span></span>

### <a name="asyncstartimmediate"></a><span data-ttu-id="2d0b7-184">StartImmediate</span><span class="sxs-lookup"><span data-stu-id="2d0b7-184">Async.StartImmediate</span></span>

<span data-ttu-id="2d0b7-185">현재 운영 체제 스레드에서 즉시 시작 하는 비동기 계산을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-185">Runs an asynchronous computation, starting immediately on the current operating system thread.</span></span> <span data-ttu-id="2d0b7-186">이는 계산 중에 호출 스레드에서 무언가를 업데이트 해야 하는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-186">This is helpful if you need to update something on the calling thread during the computation.</span></span> <span data-ttu-id="2d0b7-187">예를 들어 비동기 계산에서 UI를 업데이트 해야 하는 경우 (예: 진행률 표시줄 업데이트) `Async.StartImmediate` 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-187">For example, if an asynchronous computation must update a UI (such as updating a progress bar), then `Async.StartImmediate` should be used.</span></span>

<span data-ttu-id="2d0b7-188">서명과</span><span class="sxs-lookup"><span data-stu-id="2d0b7-188">Signature:</span></span>

```fsharp
computation: Async<unit> - cancellationToken: ?CancellationToken -> unit
```

<span data-ttu-id="2d0b7-189">사용되는 경우:</span><span class="sxs-lookup"><span data-stu-id="2d0b7-189">When to use:</span></span>

- <span data-ttu-id="2d0b7-190">비동기 계산의 중간에 있는 호출 스레드에서 무언가를 업데이트 해야 하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-190">When you need to update something on the calling thread in the middle of an asynchronous computation.</span></span>

<span data-ttu-id="2d0b7-191">조사할 내용:</span><span class="sxs-lookup"><span data-stu-id="2d0b7-191">What to watch out for:</span></span>

- <span data-ttu-id="2d0b7-192">비동기 계산의 코드는 예약 되어야 하는 모든 스레드에 대해 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-192">Code in the asynchronous computation will run on whatever thread one happens to be scheduled on.</span></span> <span data-ttu-id="2d0b7-193">이는 해당 스레드가 UI 스레드와 같은 특정 방식으로 중요 한 경우 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-193">This can be problematic if that thread is in some way sensitive, such as a UI thread.</span></span> <span data-ttu-id="2d0b7-194">이 경우 `Async.StartImmediate`를 사용 하기에 적합 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-194">In such cases, `Async.StartImmediate` is likely inappropriate to use.</span></span>

### <a name="asyncstartastask"></a><span data-ttu-id="2d0b7-195">Async.startastask</span><span class="sxs-lookup"><span data-stu-id="2d0b7-195">Async.StartAsTask</span></span>

<span data-ttu-id="2d0b7-196">스레드 풀에서 계산을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-196">Executes a computation in the thread pool.</span></span> <span data-ttu-id="2d0b7-197">계산이 종료 된 후 (결과를 생성 하거나 예외를 throw 하거나 취소 된 경우) 해당 상태에서 완료 되는 <xref:System.Threading.Tasks.Task%601>를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-197">Returns a <xref:System.Threading.Tasks.Task%601> that will be completed on the corresponding state once the computation terminates (produces the result, throws exception, or gets canceled).</span></span> <span data-ttu-id="2d0b7-198">취소 토큰을 제공 하지 않으면 기본 취소 토큰이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-198">If no cancellation token is provided, then the default cancellation token is used.</span></span>

<span data-ttu-id="2d0b7-199">서명과</span><span class="sxs-lookup"><span data-stu-id="2d0b7-199">Signature:</span></span>

```fsharp
computation: Async<'T> - taskCreationOptions: ?TaskCreationOptions - cancellationToken: ?CancellationToken -> Task<'T>
```

<span data-ttu-id="2d0b7-200">사용되는 경우:</span><span class="sxs-lookup"><span data-stu-id="2d0b7-200">When to use:</span></span>

- <span data-ttu-id="2d0b7-201">비동기 계산 결과를 나타내는 <xref:System.Threading.Tasks.Task%601>를 필요로 하는 .NET API를 호출 해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="2d0b7-201">When you need to call into a .NET API that expects a <xref:System.Threading.Tasks.Task%601> to represent the result of an asynchronous computation.</span></span>

<span data-ttu-id="2d0b7-202">조사할 내용:</span><span class="sxs-lookup"><span data-stu-id="2d0b7-202">What to watch out for:</span></span>

- <span data-ttu-id="2d0b7-203">이 호출은 추가 `Task` 개체를 할당 하 여 자주 사용 되는 경우 오버 헤드를 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-203">This call will allocate an additional `Task` object, which can increase overhead if it is used often.</span></span>

### <a name="asyncparallel"></a><span data-ttu-id="2d0b7-204">Async. Parallel</span><span class="sxs-lookup"><span data-stu-id="2d0b7-204">Async.Parallel</span></span>

<span data-ttu-id="2d0b7-205">병렬로 실행 되는 비동기 계산의 시퀀스를 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-205">Schedules a sequence of asynchronous computations to be executed in parallel.</span></span> <span data-ttu-id="2d0b7-206">@No__t_0 매개 변수를 지정 하 여 병렬 처리 수준을 선택적으로 조정/제한 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-206">The degree of parallelism can be optionally tuned/throttled by specifying the `maxDegreesOfParallelism` parameter.</span></span>

<span data-ttu-id="2d0b7-207">서명과</span><span class="sxs-lookup"><span data-stu-id="2d0b7-207">Signature:</span></span>

```fsharp
computations: seq<Async<'T>> - ?maxDegreesOfParallelism: int -> Async<'T[]>
```

<span data-ttu-id="2d0b7-208">사용하는 시기:</span><span class="sxs-lookup"><span data-stu-id="2d0b7-208">When to use it:</span></span>

- <span data-ttu-id="2d0b7-209">계산 집합을 동시에 실행 해야 하며 실행 순서에 의존 하지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="2d0b7-209">If you need to run a set of computations at the same time and have no reliance on their order of execution.</span></span>
- <span data-ttu-id="2d0b7-210">모든 작업이 완료 될 때까지 병렬로 예약 된 계산 결과가 필요 하지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="2d0b7-210">If you don't require results from computations scheduled in parallel until they have all completed.</span></span>

<span data-ttu-id="2d0b7-211">조사할 내용:</span><span class="sxs-lookup"><span data-stu-id="2d0b7-211">What to watch out for:</span></span>

- <span data-ttu-id="2d0b7-212">모든 계산이 완료 되 면 결과 값 배열에만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-212">You can only access the resulting array of values once all computations have finished.</span></span>
- <span data-ttu-id="2d0b7-213">계산을 실행 하지만 예약을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-213">Computations will be run however they end up getting scheduled.</span></span> <span data-ttu-id="2d0b7-214">즉, 실행 순서에 의존할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-214">This means you cannot rely on their order of their execution.</span></span>

### <a name="asyncsequential"></a><span data-ttu-id="2d0b7-215">Async. 순차</span><span class="sxs-lookup"><span data-stu-id="2d0b7-215">Async.Sequential</span></span>

<span data-ttu-id="2d0b7-216">전달 되는 순서 대로 실행 되는 비동기 계산의 시퀀스를 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-216">Schedules a sequence of asynchronous computations to be executed in the order that they are passed.</span></span> <span data-ttu-id="2d0b7-217">첫 번째 계산이 실행 되 고, 그 다음에는 식으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-217">The first computation will be executed, then the next, and so on.</span></span> <span data-ttu-id="2d0b7-218">계산이 병렬로 실행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-218">No computations will be executed in parallel.</span></span>

<span data-ttu-id="2d0b7-219">서명과</span><span class="sxs-lookup"><span data-stu-id="2d0b7-219">Signature:</span></span>

```fsharp
computations: seq<Async<'T>> -> Async<'T[]>
```

<span data-ttu-id="2d0b7-220">사용하는 시기:</span><span class="sxs-lookup"><span data-stu-id="2d0b7-220">When to use it:</span></span>

- <span data-ttu-id="2d0b7-221">여러 계산을 순서 대로 실행 해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="2d0b7-221">If you need to execute multiple computations in order.</span></span>

<span data-ttu-id="2d0b7-222">조사할 내용:</span><span class="sxs-lookup"><span data-stu-id="2d0b7-222">What to watch out for:</span></span>

- <span data-ttu-id="2d0b7-223">모든 계산이 완료 되 면 결과 값 배열에만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-223">You can only access the resulting array of values once all computations have finished.</span></span>
- <span data-ttu-id="2d0b7-224">계산은이 함수로 전달 되는 순서 대로 실행 되므로 결과가 반환 되기 전에 시간이 더 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-224">Computations will be run in the order that they are passed to this function, which can mean that more time will elapse before the results are returned.</span></span>

### <a name="asyncawaittask"></a><span data-ttu-id="2d0b7-225">Async. AwaitTask</span><span class="sxs-lookup"><span data-stu-id="2d0b7-225">Async.AwaitTask</span></span>

<span data-ttu-id="2d0b7-226">지정 된 <xref:System.Threading.Tasks.Task%601> 완료 될 때까지 대기 하 고 그 결과를 `Async<'T>`으로 반환 하는 비동기 계산을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-226">Returns an asynchronous computation that waits for the given <xref:System.Threading.Tasks.Task%601> to complete and returns its result as an `Async<'T>`</span></span>

<span data-ttu-id="2d0b7-227">서명과</span><span class="sxs-lookup"><span data-stu-id="2d0b7-227">Signature:</span></span>

```fsharp
task: Task<'T>  -> Async<'T>
```

<span data-ttu-id="2d0b7-228">사용되는 경우:</span><span class="sxs-lookup"><span data-stu-id="2d0b7-228">When to use:</span></span>

- <span data-ttu-id="2d0b7-229">F# 비동기 계산 내에서 <xref:System.Threading.Tasks.Task%601>을 반환 하는 .net API를 사용 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-229">When you are consuming a .NET API that returns a <xref:System.Threading.Tasks.Task%601> within an F# asynchronous computation.</span></span>

<span data-ttu-id="2d0b7-230">조사할 내용:</span><span class="sxs-lookup"><span data-stu-id="2d0b7-230">What to watch out for:</span></span>

- <span data-ttu-id="2d0b7-231">예외는 작업 병렬 라이브러리의 규칙에 따라 <xref:System.AggregateException>에 래핑됩니다 .이는 비동기 일반적으로 예외를 F# 표시 하는 방법과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-231">Exceptions are wrapped in <xref:System.AggregateException> following the convention of the Task Parallel Library, and this is different from how F# async generally surfaces exceptions.</span></span>

### <a name="asynccatch"></a><span data-ttu-id="2d0b7-232">Async. Catch</span><span class="sxs-lookup"><span data-stu-id="2d0b7-232">Async.Catch</span></span>

<span data-ttu-id="2d0b7-233">지정 된 `Async<'T>`를 실행 하 고 `Async<Choice<'T, exn>>`를 반환 하는 비동기 계산을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-233">Creates an asynchronous computation that executes a given `Async<'T>`, returning an `Async<Choice<'T, exn>>`.</span></span> <span data-ttu-id="2d0b7-234">지정 된 `Async<'T>` 성공적으로 완료 되 면 결과 값과 함께 `Choice1Of2` 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-234">If the given `Async<'T>` completes successfully, then a `Choice1Of2` is returned with the resultant value.</span></span> <span data-ttu-id="2d0b7-235">완료 되기 전에 예외가 throw 되 면 발생 한 예외와 함께 `Choice2of2` 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-235">If an exception is thrown before it completes, then a `Choice2of2` is returned with the raised exception.</span></span> <span data-ttu-id="2d0b7-236">여러 계산으로 구성 된 비동기 계산에서 사용 되는 경우 이러한 계산 중 하나가 예외를 throw 하는 경우 포괄 계산이 완전히 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-236">If it is used on an asynchronous computation that is itself composed of many computations, and one of those computations throws an exception, the encompassing computation will be stopped entirely.</span></span>

<span data-ttu-id="2d0b7-237">서명과</span><span class="sxs-lookup"><span data-stu-id="2d0b7-237">Signature:</span></span>

```fsharp
computation: Async<'T> -> Async<Choice<'T, exn>>
```

<span data-ttu-id="2d0b7-238">사용되는 경우:</span><span class="sxs-lookup"><span data-stu-id="2d0b7-238">When to use:</span></span>

- <span data-ttu-id="2d0b7-239">예외가 발생 하 여 실패할 수 있는 비동기 작업을 수행할 때 호출자에서 해당 예외를 처리 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="2d0b7-239">When you are performing asynchronous work that may fail with an exception and you want to handle that exception in the caller.</span></span>

<span data-ttu-id="2d0b7-240">조사할 내용:</span><span class="sxs-lookup"><span data-stu-id="2d0b7-240">What to watch out for:</span></span>

- <span data-ttu-id="2d0b7-241">결합 또는 시퀀스 된 비동기 계산을 사용 하는 경우 "내부" 계산 중 하나가 예외를 throw 하는 경우 포괄 계산이 완전히 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-241">When using combined or sequenced asynchronous computations, the encompassing computation will fully stop if one of its "internal" computations throws an exception.</span></span>

### <a name="asyncignore"></a><span data-ttu-id="2d0b7-242">Async. 무시</span><span class="sxs-lookup"><span data-stu-id="2d0b7-242">Async.Ignore</span></span>

<span data-ttu-id="2d0b7-243">지정 된 계산을 실행 하 고 해당 결과를 무시 하는 비동기 계산을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-243">Creates an asynchronous computation that runs the given computation and ignores its result.</span></span>

<span data-ttu-id="2d0b7-244">서명과</span><span class="sxs-lookup"><span data-stu-id="2d0b7-244">Signature:</span></span>

```fsharp
computation: Async<'T> -> Async<unit>
```

<span data-ttu-id="2d0b7-245">사용되는 경우:</span><span class="sxs-lookup"><span data-stu-id="2d0b7-245">When to use:</span></span>

- <span data-ttu-id="2d0b7-246">비동기 계산을 수행 하는 경우에는 해당 결과가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-246">When you have an asynchronous computation whose result is not needed.</span></span> <span data-ttu-id="2d0b7-247">이는 비동기 코드가 아닌 코드에 대 한 `ignore` 코드와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-247">This is analogous to the `ignore` code for non-asynchronous code.</span></span>

<span data-ttu-id="2d0b7-248">조사할 내용:</span><span class="sxs-lookup"><span data-stu-id="2d0b7-248">What to watch out for:</span></span>

- <span data-ttu-id="2d0b7-249">@No__t_0 또는 `Async<unit>`를 필요로 하는 다른 함수를 사용 하려고 하므로이를 사용 해야 하는 경우 결과를 삭제 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-249">If you must use this because you wish to use `Async.Start` or another function that requires `Async<unit>`, consider if discarding the result is okay to do.</span></span> <span data-ttu-id="2d0b7-250">형식 시그니처에 맞게 결과를 삭제 하는 것은 일반적으로 수행 되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-250">Discarding results just to fit a type signature should not generally be done.</span></span>

### <a name="asyncrunsynchronously"></a><span data-ttu-id="2d0b7-251">RunSynchronously</span><span class="sxs-lookup"><span data-stu-id="2d0b7-251">Async.RunSynchronously</span></span>

<span data-ttu-id="2d0b7-252">비동기 계산을 실행 하 고 호출 스레드에서 해당 결과를 기다립니다 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-252">Runs an asynchronous computation and awaits its result on the calling thread.</span></span> <span data-ttu-id="2d0b7-253">이 호출이 차단 되 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-253">This call is blocking.</span></span>

<span data-ttu-id="2d0b7-254">서명과</span><span class="sxs-lookup"><span data-stu-id="2d0b7-254">Signature:</span></span>

```fsharp
computation: Async<'T> - timeout: ?int - cancellationToken: ?CancellationToken -> 'T
```

<span data-ttu-id="2d0b7-255">사용하는 시기:</span><span class="sxs-lookup"><span data-stu-id="2d0b7-255">When to use it:</span></span>

- <span data-ttu-id="2d0b7-256">필요할 경우 응용 프로그램에서 실행 파일에 대 한 진입점에서 한 번만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-256">If you need it, use it only once in an application - at the entry point for an executable.</span></span>
- <span data-ttu-id="2d0b7-257">성능이 걱정 되지 않으며 다른 비동기 작업 집합을 한 번에 실행 하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-257">When you don't care about performance and want to execute a set of other asynchronous operations at once.</span></span>

<span data-ttu-id="2d0b7-258">조사할 내용:</span><span class="sxs-lookup"><span data-stu-id="2d0b7-258">What to watch out for:</span></span>

- <span data-ttu-id="2d0b7-259">@No__t_0를 호출 하면 실행이 완료 될 때까지 호출 스레드가 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-259">Calling `Async.RunSynchronously` blocks the calling thread until the execution completes.</span></span>

### <a name="asyncstart"></a><span data-ttu-id="2d0b7-260">Async. 시작</span><span class="sxs-lookup"><span data-stu-id="2d0b7-260">Async.Start</span></span>

<span data-ttu-id="2d0b7-261">@No__t_0를 반환 하는 스레드 풀에서 비동기 계산을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-261">Starts an asynchronous computation in the thread pool that returns `unit`.</span></span> <span data-ttu-id="2d0b7-262">는 결과를 기다리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-262">Doesn't wait for its result.</span></span> <span data-ttu-id="2d0b7-263">@No__t_0에서 시작 된 중첩 계산은 해당 계산을 호출한 부모 계산과 완전히 독립적으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-263">Nested computations started with `Async.Start` are started completely independently of the parent computation that called them.</span></span> <span data-ttu-id="2d0b7-264">수명은 부모 계산과 연결 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-264">Their lifetime is not tied to any parent computation.</span></span> <span data-ttu-id="2d0b7-265">부모 계산이 취소 되 면 자식 계산이 취소 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-265">If the parent computation is canceled, no child computations are cancelled.</span></span>

<span data-ttu-id="2d0b7-266">서명과</span><span class="sxs-lookup"><span data-stu-id="2d0b7-266">Signature:</span></span>

```fsharp
computation: Async<unit> - cancellationToken: ?CancellationToken -> unit
```

<span data-ttu-id="2d0b7-267">다음 경우에만 사용:</span><span class="sxs-lookup"><span data-stu-id="2d0b7-267">Use only when:</span></span>

- <span data-ttu-id="2d0b7-268">결과를 생성 하지 않거나 하나를 처리 해야 하는 비동기 계산이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-268">You have an asynchronous computation that doesn't yield a result and/or require processing of one.</span></span>
- <span data-ttu-id="2d0b7-269">비동기 계산의 완료 시기를 알 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-269">You don't need to know when an asynchronous computation completes.</span></span>
- <span data-ttu-id="2d0b7-270">비동기 계산이 실행 되는 스레드를 걱정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-270">You don't care which thread an asynchronous computation runs on.</span></span>
- <span data-ttu-id="2d0b7-271">작업으로 인해 발생 하는 예외를 인식 하거나 보고할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-271">You don't have any need to be aware of or report exceptions resulting from the task.</span></span>

<span data-ttu-id="2d0b7-272">조사할 내용:</span><span class="sxs-lookup"><span data-stu-id="2d0b7-272">What to watch out for:</span></span>

- <span data-ttu-id="2d0b7-273">@No__t_0에서 시작 된 계산에 의해 발생 한 예외는 호출자에 게 전파 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-273">Exceptions raised by computations started with `Async.Start` aren't propagated to the caller.</span></span> <span data-ttu-id="2d0b7-274">호출 스택이 완전히 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-274">The call stack will be completely unwound.</span></span>
- <span data-ttu-id="2d0b7-275">@No__t_1로 시작 되는 effectful 작업 (예: `printfn`)은 프로그램 실행의 주 스레드에서 효과가 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-275">Any effectful work (such as calling `printfn`) started with `Async.Start` won't cause the effect to happen on the main thread of a program's execution.</span></span>

## <a name="interoperating-with-net"></a><span data-ttu-id="2d0b7-276">.NET과의 상호 운용</span><span class="sxs-lookup"><span data-stu-id="2d0b7-276">Interoperating with .NET</span></span>

<span data-ttu-id="2d0b7-277">[async/await](../../../standard/async.md) 스타일의 비동기 프로그래밍을 사용하는 .net 라이브러리나 C# 코드 베이스를 사용하여 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-277">You may be working with a .NET library or C# codebase that uses [async/await](../../../standard/async.md)-style asynchronous programming.</span></span> <span data-ttu-id="2d0b7-278">및 C# 대부분의 .net 라이브러리는 <xref:System.Threading.Tasks.Task%601> 및 <xref:System.Threading.Tasks.Task> 형식을 `Async<'T>`가 아닌 핵심 추상화로 사용 하기 때문에 이러한 두 가지 방법 간에 경계를 비동기 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-278">Because C# and the majority of .NET libraries use the <xref:System.Threading.Tasks.Task%601> and <xref:System.Threading.Tasks.Task> types as their core abstractions rather than `Async<'T>`, you must cross a boundary between these two approaches to asynchrony.</span></span>

### <a name="how-to-work-with-net-async-and-taskt"></a><span data-ttu-id="2d0b7-279">.NET async 및 `Task<T>`를 사용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="2d0b7-279">How to work with .NET async and `Task<T>`</span></span>

<span data-ttu-id="2d0b7-280">@No__t_0를 사용 하는 .NET 비동기 라이브러리 및 코드 베이스 (즉, 반환 값이 있는 비동기 계산)는 간단 하며를 F#기본적으로 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-280">Working with .NET async libraries and codebases that use <xref:System.Threading.Tasks.Task%601> (that is, async computations that have return values) is straightforward and has built-in support with F#.</span></span>

<span data-ttu-id="2d0b7-281">@No__t_0 함수를 사용 하 여 .NET 비동기 계산을 대기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-281">You can use the `Async.AwaitTask` function to await a .NET asynchronous computation:</span></span>

```fsharp
let getValueFromLibrary param =
    async {
        let! value = DotNetLibrary.GetValueAsync param |> Async.AwaitTask
        return value
    }
```

<span data-ttu-id="2d0b7-282">@No__t_0 함수를 사용 하 여 .NET 호출자에 비동기 계산을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-282">You can use the `Async.StartAsTask` function to pass an asynchronous computation to a .NET caller:</span></span>

```fsharp
let computationForCaller param =
    async {
        let! result = getAsyncResult param
        return result
    } |> Async.StartAsTask
```

### <a name="how-to-work-with-net-async-and-task"></a><span data-ttu-id="2d0b7-283">.NET async 및 `Task`를 사용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="2d0b7-283">How to work with .NET async and `Task`</span></span>

<span data-ttu-id="2d0b7-284">@No__t_0 (즉, 값을 반환 하지 않는 .NET 비동기 계산)를 사용 하는 Api를 사용 하려면 `Async<'T>`를 <xref:System.Threading.Tasks.Task> 변환 하는 추가 함수를 추가 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-284">To work with APIs that use <xref:System.Threading.Tasks.Task> (that is, .NET async computations that do not return a value), you may need to add an additional function that will convert an `Async<'T>` to a <xref:System.Threading.Tasks.Task>:</span></span>

```fsharp
module Async =
    // Async<unit> -> Task
    let startTaskFromAsyncUnit (comp: Async<unit>) =
        Async.StartAsTask comp :> Task
```

<span data-ttu-id="2d0b7-285">@No__t_1를 입력으로 허용 하는 `Async.AwaitTask` 이미 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-285">There is already an `Async.AwaitTask` that accepts a <xref:System.Threading.Tasks.Task> as input.</span></span> <span data-ttu-id="2d0b7-286">이 함수와 이전에 정의 된 `startTaskFromAsyncUnit` 함수를 사용 하 여 F# 비동기 계산에서 <xref:System.Threading.Tasks.Task> 형식을 시작 하 고 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-286">With this and the previously defined `startTaskFromAsyncUnit` function, you can start and await <xref:System.Threading.Tasks.Task> types from an F# async computation.</span></span>

## <a name="relationship-to-multithreading"></a><span data-ttu-id="2d0b7-287">다중 스레딩을 위한 관계</span><span class="sxs-lookup"><span data-stu-id="2d0b7-287">Relationship to multithreading</span></span>

<span data-ttu-id="2d0b7-288">이 문서 전체에서 스레딩을 언급 했지만 다음 두 가지 중요 한 사항을 기억해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-288">Although threading is mentioned throughout this article, there are two important things to remember:</span></span>

1. <span data-ttu-id="2d0b7-289">현재 스레드에서 명시적으로 시작 하지 않는 한 비동기 계산과 스레드 간의 선호도는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-289">There is no affinity between an asynchronous computation and a thread, unless explicitly started on the current thread.</span></span>
1. <span data-ttu-id="2d0b7-290">의 F# 비동기 프로그래밍은 다중 스레딩에 대 한 추상화가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-290">Asynchronous programming in F# is not an abstraction for multi-threading.</span></span>

<span data-ttu-id="2d0b7-291">예를 들어 계산은 작업의 특성에 따라 실제로 호출자의 스레드에서 실행 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-291">For example, a computation may actually run on its caller's thread, depending on the nature of the work.</span></span> <span data-ttu-id="2d0b7-292">계산이 "대기 중" 기간 (예: 네트워크 호출이 전송 중인 경우) 사이에서 유용한 작업을 수행 하기 위해 약간의 시간 동안 borrowing "이동" 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-292">A computation could also "jump" between threads, borrowing them for a small amount of time to do useful work in between periods of "waiting" (such as when a network call is in transit).</span></span>

<span data-ttu-id="2d0b7-293">는 F# 현재 스레드에서 비동기 계산을 시작 하는 기능을 제공 하지만 (또는 현재 스레드에서 명시적으로는 사용 하지 않음) 비동기 일반적으로 특정 스레딩 전략과 연결 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d0b7-293">Although F# provides some abilities to start an asynchronous computation on the current thread (or explicitly not on the current thread), asynchrony generally is not associated with a particular threading strategy.</span></span>

## <a name="see-also"></a><span data-ttu-id="2d0b7-294">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2d0b7-294">See also</span></span>

- [<span data-ttu-id="2d0b7-295">F# 비동기 프로그래밍 모델</span><span class="sxs-lookup"><span data-stu-id="2d0b7-295">The F# Asynchronous Programming Model</span></span>](https://www.microsoft.com/research/publication/the-f-asynchronous-programming-model)
- [<span data-ttu-id="2d0b7-296">Jet의 F# 비동기 가이드</span><span class="sxs-lookup"><span data-stu-id="2d0b7-296">Jet.com's F# Async Guide</span></span>](https://medium.com/jettech/f-async-guide-eb3c8a2d180a)
- [<span data-ttu-id="2d0b7-297">F#재미 있고 이익을 위한 비동기 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="2d0b7-297">F# for fun and profit's Asynchronous Programming guide</span></span>](https://fsharpforfunandprofit.com/posts/concurrency-async-and-parallel/)
- <span data-ttu-id="2d0b7-298">및 F#의 C# [Async: C# @No__t_1 비동기 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="2d0b7-298">[Async in C# and F#: Asynchronous gotchas in C#](http://tomasp.net/blog/csharp-async-gotchas.aspx/)</span></span>
