---
title: 비동기 프로그래밍
description: F#이 핵심 기능적 프로그래밍 개념에서 파생된 언어 수준 프로그래밍 모델을 기반으로 비동기에 대한 깨끗한 지원을 제공하는 방법을 알아봅니다.
ms.date: 12/17/2018
ms.openlocfilehash: 9b2e3057c126d84474c21fde653da5bbee32938a
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/17/2020
ms.locfileid: "81608038"
---
# <a name="async-programming-in-f"></a><span data-ttu-id="fd6ed-103">F의 비동기 프로그래밍\#</span><span class="sxs-lookup"><span data-stu-id="fd6ed-103">Async programming in F\#</span></span>

<span data-ttu-id="fd6ed-104">비동기 프로그래밍은 다양한 이유로 최신 응용 프로그램에 필수적인 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-104">Asynchronous programming is a mechanism that is essential to modern applications for diverse reasons.</span></span> <span data-ttu-id="fd6ed-105">대부분의 개발자가 발생할 수 있는 두 가지 기본 사용 사례가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-105">There are two primary use cases that most developers will encounter:</span></span>

- <span data-ttu-id="fd6ed-106">요청 처리가 해당 프로세스 외부의 시스템 또는 서비스의 입력을 기다리는 동안 점유된 시스템 리소스를 최소화하면서 상당수의 동시 수신 요청을 처리할 수 있는 서버 프로세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-106">Presenting a server process that can service a significant number of concurrent incoming requests, while minimizing the system resources occupied while request processing awaits inputs from systems or services external to that process</span></span>
- <span data-ttu-id="fd6ed-107">백그라운드 작업을 동시에 진행하는 동안 반응형 UI 또는 기본 스레드 유지 관리</span><span class="sxs-lookup"><span data-stu-id="fd6ed-107">Maintaining a responsive UI or main thread while concurrently progressing background work</span></span>

<span data-ttu-id="fd6ed-108">백그라운드 작업에는 여러 스레드의 사용이 포함되는 경우가 많지만 비동기 및 다중 스레딩의 개념을 별도로 고려하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-108">Although background work often does involve the utilization of multiple threads, it's important to consider the concepts of asynchrony and multi-threading separately.</span></span> <span data-ttu-id="fd6ed-109">사실, 그들은 별개의 관심사이며, 하나는 다른 것을 의미하지 는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-109">In fact, they are separate concerns, and one does not imply the other.</span></span> <span data-ttu-id="fd6ed-110">이 문서의 다음 내용은 이에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-110">What follows in this article describes this in more detail.</span></span>

## <a name="asynchrony-defined"></a><span data-ttu-id="fd6ed-111">정의된 비동기</span><span class="sxs-lookup"><span data-stu-id="fd6ed-111">Asynchrony defined</span></span>

<span data-ttu-id="fd6ed-112">이전 점 - 비동기는 여러 스레드의 사용률과 독립적입니다 - 조금 더 설명 할 가치가있다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-112">The previous point - that asynchrony is independent of the utilization of multiple threads - is worth explaining a bit further.</span></span> <span data-ttu-id="fd6ed-113">때로는 서로 관련이 있지만 엄격하게 서로 독립적 인 세 가지 개념이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-113">There are three concepts that are sometimes related, but strictly independent of one another:</span></span>

- <span data-ttu-id="fd6ed-114">동시성; 겹치는 기간에서 여러 계산이 실행되는 경우</span><span class="sxs-lookup"><span data-stu-id="fd6ed-114">Concurrency; when multiple computations execute in overlapping time periods.</span></span>
- <span data-ttu-id="fd6ed-115">병렬 처리; 여러 계산 또는 단일 계산의 여러 부분이 정확히 동시에 실행되는 경우</span><span class="sxs-lookup"><span data-stu-id="fd6ed-115">Parallelism; when multiple computations or several parts of a single computation run at exactly the same time.</span></span>
- <span data-ttu-id="fd6ed-116">비동기; 하나 이상의 계산이 주 프로그램 흐름과 별도로 실행될 수 있는 경우</span><span class="sxs-lookup"><span data-stu-id="fd6ed-116">Asynchrony; when one or more computations can execute separately from the main program flow.</span></span>

<span data-ttu-id="fd6ed-117">세 가지 모두 직교 개념이지만, 특히 함께 사용할 때 쉽게 수축 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-117">All three are orthogonal concepts, but can be easily conflated, especially when they are used together.</span></span> <span data-ttu-id="fd6ed-118">예를 들어 여러 비동기 계산을 병렬로 실행해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-118">For example, you may need to execute multiple asynchronous computations in parallel.</span></span> <span data-ttu-id="fd6ed-119">그렇다고 해서 병렬 처리나 비동기가 서로를 암시하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-119">This does not mean that parallelism or asynchrony imply one another.</span></span>

<span data-ttu-id="fd6ed-120">"비동기"라는 단어의 어장을 고려하면 다음과 같은 두 가지 조각이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-120">If you consider the etymology of the word "asynchronous", there are two pieces involved:</span></span>

- <span data-ttu-id="fd6ed-121">"a", "하지"를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-121">"a", meaning "not".</span></span>
- <span data-ttu-id="fd6ed-122">"동기", "동시에"를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-122">"synchronous", meaning "at the same time".</span></span>

<span data-ttu-id="fd6ed-123">이 두 용어를 함께 사용하면 "비동기"가 "동시에 아님"을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-123">When you put these two terms together, you'll see that "asynchronous" means "not at the same time".</span></span> <span data-ttu-id="fd6ed-124">정말 간단하죠.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-124">That's it!</span></span> <span data-ttu-id="fd6ed-125">이 정의에는 동시성 또는 병렬 처리의 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-125">There is no implication of concurrency or parallelism in this definition.</span></span> <span data-ttu-id="fd6ed-126">이것은 실제로도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-126">This is also true in practice.</span></span>

<span data-ttu-id="fd6ed-127">실질적으로 F#의 비동기 계산은 주 프로그램 흐름과 독립적으로 실행되도록 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-127">In practical terms, asynchronous computations in F# are scheduled to execute independently of the main program flow.</span></span> <span data-ttu-id="fd6ed-128">이는 동시성 또는 병렬성을 의미하지 않으며 백그라운드에서 항상 계산이 발생한다는 의미도 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-128">This doesn't imply concurrency or parallelism, nor does it imply that a computation always happens in the background.</span></span> <span data-ttu-id="fd6ed-129">실제로 비동기 계산은 계산의 특성과 계산이 실행되는 환경에 따라 동기적으로 실행될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-129">In fact, asynchronous computations can even execute synchronously, depending on the nature of the computation and the environment the computation is executing in.</span></span>

<span data-ttu-id="fd6ed-130">비동기 계산은 주 프로그램 흐름과 독립적이라는 것이 주요 테이크 아웃입니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-130">The main takeaway you should have is that asynchronous computations are independent of the main program flow.</span></span> <span data-ttu-id="fd6ed-131">비동기 계산이 실행되는 시기 또는 방법에 대한 보장은 거의 없지만 이를 오케스트레이션하고 예약하는 몇 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-131">Although there are few guarantees about when or how an asynchronous computation executes, there are some approaches to orchestrating and scheduling them.</span></span> <span data-ttu-id="fd6ed-132">이 문서의 나머지 부분에서는 F# 비동기에 대한 핵심 개념과 F#에 기본 제공된 형식, 함수 및 식을 사용하는 방법을 살펴봅습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-132">The rest of this article explores core concepts for F# asynchrony and how to use the types, functions, and expressions built into F#.</span></span>

## <a name="core-concepts"></a><span data-ttu-id="fd6ed-133">핵심 개념</span><span class="sxs-lookup"><span data-stu-id="fd6ed-133">Core concepts</span></span>

<span data-ttu-id="fd6ed-134">F#에서 비동기 프로그래밍은 다음 세 가지 핵심 개념을 중심으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-134">In F#, asynchronous programming is centered around three core concepts:</span></span>

- <span data-ttu-id="fd6ed-135">컴포셔블 비동기 계산을 나타내는 `Async<'T>` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-135">The `Async<'T>` type, which represents a composable asynchronous computation.</span></span>
- <span data-ttu-id="fd6ed-136">비동기 작업을 예약하고 비동기 계산을 작성하고 비동기 결과를 변환할 수 있는 `Async` 모듈 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-136">The `Async` module functions, which let you schedule asynchronous work, compose asynchronous computations, and transform asynchronous results.</span></span>
- <span data-ttu-id="fd6ed-137">`async { }` [비동기](../../language-reference/computation-expressions.md)계산을 빌드하고 제어하기 위한 편리한 구문을 제공하는 계산 식입니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-137">The `async { }` [computation expression](../../language-reference/computation-expressions.md), which provides a convenient syntax for building and controlling asynchronous computations.</span></span>

<span data-ttu-id="fd6ed-138">다음 예제에서는 다음 세 가지 개념을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-138">You can see these three concepts in the following example:</span></span>

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

<span data-ttu-id="fd6ed-139">이 예제에서 `printTotalFileBytes` 함수는 형식입니다. `string -> Async<unit>`</span><span class="sxs-lookup"><span data-stu-id="fd6ed-139">In the example, the `printTotalFileBytes` function is of type `string -> Async<unit>`.</span></span> <span data-ttu-id="fd6ed-140">함수를 호출해도 실제로 비동기 계산이 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-140">Calling the function does not actually execute the asynchronous computation.</span></span> <span data-ttu-id="fd6ed-141">대신 비동기적으로 `Async<unit>` 실행하는 작업의 *사양역할을* 하는 을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-141">Instead, it returns an `Async<unit>` that acts as a *specification* of the work that is to execute asynchronously.</span></span> <span data-ttu-id="fd6ed-142">본문을 `Async.AwaitTask` 호출하여 결과를 적절한 <xref:System.IO.File.ReadAllBytesAsync%2A> 유형으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-142">It calls `Async.AwaitTask` in its body, which converts the result of <xref:System.IO.File.ReadAllBytesAsync%2A> to an appropriate type.</span></span>

<span data-ttu-id="fd6ed-143">또 다른 중요한 줄은 `Async.RunSynchronously`에 대한 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-143">Another important line is the call to `Async.RunSynchronously`.</span></span> <span data-ttu-id="fd6ed-144">실제로 F# 비동기 계산을 실행하려는 경우 호출해야 하는 비동기 모듈 시작 함수 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-144">This is one of the Async module starting functions that you'll need to call if you want to actually execute an F# asynchronous computation.</span></span>

<span data-ttu-id="fd6ed-145">이는 C#/Visual Basic 프로그래밍 스타일과의 `async` 근본적인 차이점입니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-145">This is a fundamental difference with the C#/Visual Basic style of `async` programming.</span></span> <span data-ttu-id="fd6ed-146">F#에서 비동기 계산은 **콜드 작업으로**생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-146">In F#, asynchronous computations can be thought of as **Cold tasks**.</span></span> <span data-ttu-id="fd6ed-147">실제로 실행하기 위해 명시적으로 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-147">They must be explicitly started to actually execute.</span></span> <span data-ttu-id="fd6ed-148">C# 또는 Visual Basic보다 비동기 작업을 훨씬 쉽게 결합하고 시퀀스할 수 있으므로 몇 가지 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-148">This has some advantages, as it allows you to combine and sequence asynchronous work much more easily than in C# or Visual Basic.</span></span>

## <a name="combine-asynchronous-computations"></a><span data-ttu-id="fd6ed-149">비동기 계산 결합</span><span class="sxs-lookup"><span data-stu-id="fd6ed-149">Combine asynchronous computations</span></span>

<span data-ttu-id="fd6ed-150">다음은 계산을 결합하여 이전 예제를 기반으로 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-150">Here is an example that builds upon the previous one by combining computations:</span></span>

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

<span data-ttu-id="fd6ed-151">보시다시피 이 `main` 함수에는 호출이 꽤 많이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-151">As you can see, the `main` function has quite a few more calls made.</span></span> <span data-ttu-id="fd6ed-152">개념적으로 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-152">Conceptually, it does the following:</span></span>

1. <span data-ttu-id="fd6ed-153">명령줄 인수를 을 통해 `Async<unit>` `Array.map`계산으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-153">Transform the command-line arguments into `Async<unit>` computations with `Array.map`.</span></span>
2. <span data-ttu-id="fd6ed-154">계산이 `Async<'T[]>` 실행될 때 `printTotalFileBytes` 병렬로 계산을 예약하고 실행하는 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-154">Create an `Async<'T[]>` that schedules and runs the `printTotalFileBytes` computations in parallel when it runs.</span></span>
3. <span data-ttu-id="fd6ed-155">병렬 `Async<unit>` 계산을 실행하고 결과를 무시하는 을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-155">Create an `Async<unit>` that will run the parallel computation and ignore its result.</span></span>
4. <span data-ttu-id="fd6ed-156">마지막 계산을 `Async.RunSynchronously` 명시적으로 실행하고 완료될 때까지 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-156">Explicitly run the last computation with `Async.RunSynchronously` and block until it is completes.</span></span>

<span data-ttu-id="fd6ed-157">이 프로그램이 실행되면 각 명령줄 인수에 대해 병렬로 `printTotalFileBytes` 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-157">When this program runs, `printTotalFileBytes` runs in parallel for each command-line argument.</span></span> <span data-ttu-id="fd6ed-158">비동기 계산은 프로그램 흐름과 독립적으로 실행되므로 정보를 인쇄하고 실행을 완료하는 순서는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-158">Because asynchronous computations execute independently of program flow, there is no order in which they print their information and finish executing.</span></span> <span data-ttu-id="fd6ed-159">계산은 병렬로 예약되지만 실행 순서는 보장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-159">The computations will be scheduled in parallel, but their order of execution is not guaranteed.</span></span>

## <a name="sequence-asynchronous-computations"></a><span data-ttu-id="fd6ed-160">시퀀스 비동기 계산</span><span class="sxs-lookup"><span data-stu-id="fd6ed-160">Sequence asynchronous computations</span></span>

<span data-ttu-id="fd6ed-161">이미 `Async<'T>` 실행 중인 작업이 아니라 작업 사양이므로 보다 복잡한 변환을 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-161">Because `Async<'T>` is a specification of work rather than an already-running task, you can perform more intricate transformations easily.</span></span> <span data-ttu-id="fd6ed-162">다음은 비동기 계산 집합을 시퀀싱하여 차례로 실행하도록 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-162">Here is an example that sequences a set of Async computations so they execute one after another.</span></span>

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
    |> Async.Ignore
    |> Async.RunSynchronously
    |> ignore
```

<span data-ttu-id="fd6ed-163">이렇게 하면 `printTotalFileBytes` 병렬로 예약하는 대신 `argv` 요소의 순서대로 실행하도록 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-163">This will schedule `printTotalFileBytes` to execute in the order of the elements of `argv` rather than scheduling them in parallel.</span></span> <span data-ttu-id="fd6ed-164">마지막 계산이 실행을 완료할 때까지 다음 항목이 예약되지 않으므로 계산이 순서대로 정렬되어 실행에 겹치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-164">Because the next item will not be scheduled until after the last computation has finished executing, the computations are sequenced such that there is no overlap in their execution.</span></span>

## <a name="important-async-module-functions"></a><span data-ttu-id="fd6ed-165">중요한 비동기 모듈 기능</span><span class="sxs-lookup"><span data-stu-id="fd6ed-165">Important Async module functions</span></span>

<span data-ttu-id="fd6ed-166">F#에서 비동기 코드를 작성할 때 일반적으로 계산 일정을 처리하는 프레임워크와 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-166">When you write async code in F# you'll usually interact with a framework that handles scheduling of computations for you.</span></span> <span data-ttu-id="fd6ed-167">그러나 항상 그런 것은 아니므로 비동기 작업을 예약하기 위해 다양한 시작 함수를 배우는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-167">However, this is not always the case, so it is good to learn the various starting functions to schedule asynchronous work.</span></span>

<span data-ttu-id="fd6ed-168">F# 비동기 계산은 이미 실행 중인 작업의 표현이 아니라 작업 _사양이므로_ 시작 함수로 명시적으로 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-168">Because F# asynchronous computations are a _specification_ of work rather than a representation of work that is already executing, they must be explicitly started with a starting function.</span></span> <span data-ttu-id="fd6ed-169">다른 컨텍스트에서 유용한 많은 [비동기 시작 함수가](https://msdn.microsoft.com/library/ee370232.aspx) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-169">There are many [Async starting functions](https://msdn.microsoft.com/library/ee370232.aspx) that are helpful in different contexts.</span></span> <span data-ttu-id="fd6ed-170">다음 섹션에서는 보다 일반적인 시작 함수 중 일부에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-170">The following section describes some of the more common starting functions.</span></span>

### <a name="asyncstartchild"></a><span data-ttu-id="fd6ed-171">비동기.시작자</span><span class="sxs-lookup"><span data-stu-id="fd6ed-171">Async.StartChild</span></span>

<span data-ttu-id="fd6ed-172">비동기 계산 내에서 자식 계산을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-172">Starts a child computation within an asynchronous computation.</span></span> <span data-ttu-id="fd6ed-173">이렇게 하면 여러 비동기 계산을 동시에 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-173">This allows multiple asynchronous computations to be executed concurrently.</span></span> <span data-ttu-id="fd6ed-174">자식 계산은 부모 계산과 취소 토큰을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-174">The child computation shares a cancellation token with the parent computation.</span></span> <span data-ttu-id="fd6ed-175">상위 계산이 취소되면 자식 계산도 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-175">If the parent computation is canceled, the child computation is also canceled.</span></span>

<span data-ttu-id="fd6ed-176">서명:</span><span class="sxs-lookup"><span data-stu-id="fd6ed-176">Signature:</span></span>

```fsharp
computation: Async<'T> * timeout: ?int -> Async<Async<'T>>
```

<span data-ttu-id="fd6ed-177">사용 시기:</span><span class="sxs-lookup"><span data-stu-id="fd6ed-177">When to use:</span></span>

- <span data-ttu-id="fd6ed-178">한 번에 하나씩이 아니라 동시에 여러 비동기 계산을 실행하려는 경우 병렬로 예약되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-178">When you want to execute multiple asynchronous computations concurrently rather than one at a time, but not have them scheduled in parallel.</span></span>
- <span data-ttu-id="fd6ed-179">하위 계산의 수명을 상위 계산의 수명과 연결하려는 경우</span><span class="sxs-lookup"><span data-stu-id="fd6ed-179">When you wish to tie the lifetime of a child computation to that of a parent computation.</span></span>

<span data-ttu-id="fd6ed-180">주의해야 할 사항:</span><span class="sxs-lookup"><span data-stu-id="fd6ed-180">What to watch out for:</span></span>

- <span data-ttu-id="fd6ed-181">여러 계산을 `Async.StartChild` 병렬로 예약하는 것과 는 다중 계산을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-181">Starting multiple computations with `Async.StartChild` isn't the same as scheduling them in parallel.</span></span> <span data-ttu-id="fd6ed-182">계산을 병렬로 예약하려면 을 `Async.Parallel`사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-182">If you wish to schedule computations in parallel, use `Async.Parallel`.</span></span>
- <span data-ttu-id="fd6ed-183">상위 계산을 취소하면 시작된 모든 자식 계산이 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-183">Canceling a parent computation will trigger cancellation of all child computations it started.</span></span>

### <a name="asyncstartimmediate"></a><span data-ttu-id="fd6ed-184">비동기.즉시 시작</span><span class="sxs-lookup"><span data-stu-id="fd6ed-184">Async.StartImmediate</span></span>

<span data-ttu-id="fd6ed-185">현재 운영 체제 스레드에서 즉시 시작하여 비동기 계산을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-185">Runs an asynchronous computation, starting immediately on the current operating system thread.</span></span> <span data-ttu-id="fd6ed-186">이 기능은 계산 중에 호출 스레드에서 무언가를 업데이트해야 하는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-186">This is helpful if you need to update something on the calling thread during the computation.</span></span> <span data-ttu-id="fd6ed-187">예를 들어 비동기 계산에서 UI(예: 진행률 표시줄 업데이트)를 `Async.StartImmediate` 업데이트해야 하는 경우 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-187">For example, if an asynchronous computation must update a UI (such as updating a progress bar), then `Async.StartImmediate` should be used.</span></span>

<span data-ttu-id="fd6ed-188">서명:</span><span class="sxs-lookup"><span data-stu-id="fd6ed-188">Signature:</span></span>

```fsharp
computation: Async<unit> - cancellationToken: ?CancellationToken -> unit
```

<span data-ttu-id="fd6ed-189">사용 시기:</span><span class="sxs-lookup"><span data-stu-id="fd6ed-189">When to use:</span></span>

- <span data-ttu-id="fd6ed-190">비동기 계산 중간에 호출 스레드에서 무언가를 업데이트해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="fd6ed-190">When you need to update something on the calling thread in the middle of an asynchronous computation.</span></span>

<span data-ttu-id="fd6ed-191">주의해야 할 사항:</span><span class="sxs-lookup"><span data-stu-id="fd6ed-191">What to watch out for:</span></span>

- <span data-ttu-id="fd6ed-192">비동기 계산의 코드는 예약될 스레드가 무엇이든에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-192">Code in the asynchronous computation will run on whatever thread one happens to be scheduled on.</span></span> <span data-ttu-id="fd6ed-193">이 스레드는 UI 스레드와 같은 어떤 식으로든 중요 한 경우 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-193">This can be problematic if that thread is in some way sensitive, such as a UI thread.</span></span> <span data-ttu-id="fd6ed-194">이러한 경우 `Async.StartImmediate` 사용하기에 부적절할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-194">In such cases, `Async.StartImmediate` is likely inappropriate to use.</span></span>

### <a name="asyncstartastask"></a><span data-ttu-id="fd6ed-195">비동기.시작 작업</span><span class="sxs-lookup"><span data-stu-id="fd6ed-195">Async.StartAsTask</span></span>

<span data-ttu-id="fd6ed-196">스레드 풀에서 계산을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-196">Executes a computation in the thread pool.</span></span> <span data-ttu-id="fd6ed-197">계산이 <xref:System.Threading.Tasks.Task%601> 종료되면 해당 상태에서 완료될 a를 반환합니다(결과가 생성되거나 예외가 발생하거나 취소됨).</span><span class="sxs-lookup"><span data-stu-id="fd6ed-197">Returns a <xref:System.Threading.Tasks.Task%601> that will be completed on the corresponding state once the computation terminates (produces the result, throws exception, or gets canceled).</span></span> <span data-ttu-id="fd6ed-198">취소 토큰이 제공되지 않으면 기본 취소 토큰이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-198">If no cancellation token is provided, then the default cancellation token is used.</span></span>

<span data-ttu-id="fd6ed-199">서명:</span><span class="sxs-lookup"><span data-stu-id="fd6ed-199">Signature:</span></span>

```fsharp
computation: Async<'T> - taskCreationOptions: ?TaskCreationOptions - cancellationToken: ?CancellationToken -> Task<'T>
```

<span data-ttu-id="fd6ed-200">사용 시기:</span><span class="sxs-lookup"><span data-stu-id="fd6ed-200">When to use:</span></span>

- <span data-ttu-id="fd6ed-201">a가 비동기 계산의 결과를 나타낼 것으로 <xref:System.Threading.Tasks.Task%601> 예상되는 .NET API를 호출해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="fd6ed-201">When you need to call into a .NET API that expects a <xref:System.Threading.Tasks.Task%601> to represent the result of an asynchronous computation.</span></span>

<span data-ttu-id="fd6ed-202">주의해야 할 사항:</span><span class="sxs-lookup"><span data-stu-id="fd6ed-202">What to watch out for:</span></span>

- <span data-ttu-id="fd6ed-203">이 호출은 추가 `Task` 개체를 할당하며, 자주 사용되는 경우 오버헤드가 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-203">This call will allocate an additional `Task` object, which can increase overhead if it is used often.</span></span>

### <a name="asyncparallel"></a><span data-ttu-id="fd6ed-204">비동기.병렬</span><span class="sxs-lookup"><span data-stu-id="fd6ed-204">Async.Parallel</span></span>

<span data-ttu-id="fd6ed-205">비동기 계산 시퀀스를 병렬로 실행하도록 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-205">Schedules a sequence of asynchronous computations to be executed in parallel.</span></span> <span data-ttu-id="fd6ed-206">매개 `maxDegreesOfParallelism` 변수를 지정하여 병렬 처리 정도를 선택적으로 조정/조절할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-206">The degree of parallelism can be optionally tuned/throttled by specifying the `maxDegreesOfParallelism` parameter.</span></span>

<span data-ttu-id="fd6ed-207">서명:</span><span class="sxs-lookup"><span data-stu-id="fd6ed-207">Signature:</span></span>

```fsharp
computations: seq<Async<'T>> - ?maxDegreesOfParallelism: int -> Async<'T[]>
```

<span data-ttu-id="fd6ed-208">사용하는 시기:</span><span class="sxs-lookup"><span data-stu-id="fd6ed-208">When to use it:</span></span>

- <span data-ttu-id="fd6ed-209">계산 집합을 동시에 실행해야 하고 실행 순서에 의존하지 않는 경우.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-209">If you need to run a set of computations at the same time and have no reliance on their order of execution.</span></span>
- <span data-ttu-id="fd6ed-210">모두 완료될 때까지 병렬로 예약된 계산의 결과가 필요하지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="fd6ed-210">If you don't require results from computations scheduled in parallel until they have all completed.</span></span>

<span data-ttu-id="fd6ed-211">주의해야 할 사항:</span><span class="sxs-lookup"><span data-stu-id="fd6ed-211">What to watch out for:</span></span>

- <span data-ttu-id="fd6ed-212">모든 계산이 완료된 후에만 결과 값 배열에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-212">You can only access the resulting array of values once all computations have finished.</span></span>
- <span data-ttu-id="fd6ed-213">계산은 실행되지만 결국 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-213">Computations will be run however they end up getting scheduled.</span></span> <span data-ttu-id="fd6ed-214">즉, 실행 순서에 의존할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-214">This means you cannot rely on their order of their execution.</span></span>

### <a name="asyncsequential"></a><span data-ttu-id="fd6ed-215">비동기.순차적</span><span class="sxs-lookup"><span data-stu-id="fd6ed-215">Async.Sequential</span></span>

<span data-ttu-id="fd6ed-216">전달되는 순서대로 실행되도록 비동기 계산 시퀀스를 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-216">Schedules a sequence of asynchronous computations to be executed in the order that they are passed.</span></span> <span data-ttu-id="fd6ed-217">첫 번째 계산은 다음 계산을 실행한 다음 다음 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-217">The first computation will be executed, then the next, and so on.</span></span> <span data-ttu-id="fd6ed-218">계산은 병렬로 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-218">No computations will be executed in parallel.</span></span>

<span data-ttu-id="fd6ed-219">서명:</span><span class="sxs-lookup"><span data-stu-id="fd6ed-219">Signature:</span></span>

```fsharp
computations: seq<Async<'T>> -> Async<'T[]>
```

<span data-ttu-id="fd6ed-220">사용하는 시기:</span><span class="sxs-lookup"><span data-stu-id="fd6ed-220">When to use it:</span></span>

- <span data-ttu-id="fd6ed-221">여러 계산을 순서대로 실행해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="fd6ed-221">If you need to execute multiple computations in order.</span></span>

<span data-ttu-id="fd6ed-222">주의해야 할 사항:</span><span class="sxs-lookup"><span data-stu-id="fd6ed-222">What to watch out for:</span></span>

- <span data-ttu-id="fd6ed-223">모든 계산이 완료된 후에만 결과 값 배열에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-223">You can only access the resulting array of values once all computations have finished.</span></span>
- <span data-ttu-id="fd6ed-224">계산은 이 함수에 전달되는 순서대로 실행되며, 이는 결과가 반환되기 전에 더 많은 시간이 경과한다는 것을 의미할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-224">Computations will be run in the order that they are passed to this function, which can mean that more time will elapse before the results are returned.</span></span>

### <a name="asyncawaittask"></a><span data-ttu-id="fd6ed-225">애싱크.대기 작업</span><span class="sxs-lookup"><span data-stu-id="fd6ed-225">Async.AwaitTask</span></span>

<span data-ttu-id="fd6ed-226">주어진 <xref:System.Threading.Tasks.Task%601> 계산이 완료될 때까지 대기하고 결과를`Async<'T>`</span><span class="sxs-lookup"><span data-stu-id="fd6ed-226">Returns an asynchronous computation that waits for the given <xref:System.Threading.Tasks.Task%601> to complete and returns its result as an `Async<'T>`</span></span>

<span data-ttu-id="fd6ed-227">서명:</span><span class="sxs-lookup"><span data-stu-id="fd6ed-227">Signature:</span></span>

```fsharp
task: Task<'T>  -> Async<'T>
```

<span data-ttu-id="fd6ed-228">사용 시기:</span><span class="sxs-lookup"><span data-stu-id="fd6ed-228">When to use:</span></span>

- <span data-ttu-id="fd6ed-229">F# 비동기 계산 내에서 를 <xref:System.Threading.Tasks.Task%601> 반환 하는 .NET API를 사용 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-229">When you are consuming a .NET API that returns a <xref:System.Threading.Tasks.Task%601> within an F# asynchronous computation.</span></span>

<span data-ttu-id="fd6ed-230">주의해야 할 사항:</span><span class="sxs-lookup"><span data-stu-id="fd6ed-230">What to watch out for:</span></span>

- <span data-ttu-id="fd6ed-231">예외는 작업 <xref:System.AggregateException> 병렬 라이브러리의 규칙에 따라 래핑되며 F# 비동기가 일반적으로 예외를 표시하는 방법과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-231">Exceptions are wrapped in <xref:System.AggregateException> following the convention of the Task Parallel Library, and this is different from how F# async generally surfaces exceptions.</span></span>

### <a name="asynccatch"></a><span data-ttu-id="fd6ed-232">비동기.Catch</span><span class="sxs-lookup"><span data-stu-id="fd6ed-232">Async.Catch</span></span>

<span data-ttu-id="fd6ed-233">을 반환하는 지정된 `Async<'T>`을 실행하는 비동기 계산을 `Async<Choice<'T, exn>>`만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-233">Creates an asynchronous computation that executes a given `Async<'T>`, returning an `Async<Choice<'T, exn>>`.</span></span> <span data-ttu-id="fd6ed-234">지정된 `Async<'T>` 값이 성공적으로 완료되면 a가 `Choice1Of2` 결과 값과 함께 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-234">If the given `Async<'T>` completes successfully, then a `Choice1Of2` is returned with the resultant value.</span></span> <span data-ttu-id="fd6ed-235">완료되기 전에 예외가 throw되면 발생한 `Choice2of2` 예외와 함께 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-235">If an exception is thrown before it completes, then a `Choice2of2` is returned with the raised exception.</span></span> <span data-ttu-id="fd6ed-236">자체가 많은 계산으로 구성된 비동기 계산에 사용되고 이러한 계산 중 하나가 예외를 throw하면 포괄 계산이 완전히 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-236">If it is used on an asynchronous computation that is itself composed of many computations, and one of those computations throws an exception, the encompassing computation will be stopped entirely.</span></span>

<span data-ttu-id="fd6ed-237">서명:</span><span class="sxs-lookup"><span data-stu-id="fd6ed-237">Signature:</span></span>

```fsharp
computation: Async<'T> -> Async<Choice<'T, exn>>
```

<span data-ttu-id="fd6ed-238">사용 시기:</span><span class="sxs-lookup"><span data-stu-id="fd6ed-238">When to use:</span></span>

- <span data-ttu-id="fd6ed-239">예외와 함께 실패할 수 있는 비동기 작업을 수행 하 고 호출자에서 해당 예외를 처리 하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-239">When you are performing asynchronous work that may fail with an exception and you want to handle that exception in the caller.</span></span>

<span data-ttu-id="fd6ed-240">주의해야 할 사항:</span><span class="sxs-lookup"><span data-stu-id="fd6ed-240">What to watch out for:</span></span>

- <span data-ttu-id="fd6ed-241">결합된 또는 시퀀싱된 비동기 계산을 사용하는 경우 "내부" 계산 중 하나가 예외를 throw하면 포괄 계산이 완전히 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-241">When using combined or sequenced asynchronous computations, the encompassing computation will fully stop if one of its "internal" computations throws an exception.</span></span>

### <a name="asyncignore"></a><span data-ttu-id="fd6ed-242">비동기.무시</span><span class="sxs-lookup"><span data-stu-id="fd6ed-242">Async.Ignore</span></span>

<span data-ttu-id="fd6ed-243">지정된 계산을 실행하고 결과를 무시하는 비동기 계산을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-243">Creates an asynchronous computation that runs the given computation and ignores its result.</span></span>

<span data-ttu-id="fd6ed-244">서명:</span><span class="sxs-lookup"><span data-stu-id="fd6ed-244">Signature:</span></span>

```fsharp
computation: Async<'T> -> Async<unit>
```

<span data-ttu-id="fd6ed-245">사용 시기:</span><span class="sxs-lookup"><span data-stu-id="fd6ed-245">When to use:</span></span>

- <span data-ttu-id="fd6ed-246">결과가 필요하지 않은 비동기 계산이 있는 경우</span><span class="sxs-lookup"><span data-stu-id="fd6ed-246">When you have an asynchronous computation whose result is not needed.</span></span> <span data-ttu-id="fd6ed-247">이는 비동기 코드의 `ignore` 코드와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-247">This is analogous to the `ignore` code for non-asynchronous code.</span></span>

<span data-ttu-id="fd6ed-248">주의해야 할 사항:</span><span class="sxs-lookup"><span data-stu-id="fd6ed-248">What to watch out for:</span></span>

- <span data-ttu-id="fd6ed-249">사용하려는 경우 또는 필요한 `Async.Start` `Async<unit>`다른 함수를 사용하려면 결과를 삭제해도 되는지 고려하십시오.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-249">If you must use this because you wish to use `Async.Start` or another function that requires `Async<unit>`, consider if discarding the result is okay to do.</span></span> <span data-ttu-id="fd6ed-250">형식 시그니처에 맞게 결과를 삭제하는 것은 일반적으로 수행되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-250">Discarding results just to fit a type signature should not generally be done.</span></span>

### <a name="asyncrunsynchronously"></a><span data-ttu-id="fd6ed-251">비동기.실행 동기</span><span class="sxs-lookup"><span data-stu-id="fd6ed-251">Async.RunSynchronously</span></span>

<span data-ttu-id="fd6ed-252">비동기 계산을 실행 하 고 호출 스레드에서 해당 결과를 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-252">Runs an asynchronous computation and awaits its result on the calling thread.</span></span> <span data-ttu-id="fd6ed-253">이 호출이 차단중입니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-253">This call is blocking.</span></span>

<span data-ttu-id="fd6ed-254">서명:</span><span class="sxs-lookup"><span data-stu-id="fd6ed-254">Signature:</span></span>

```fsharp
computation: Async<'T> - timeout: ?int - cancellationToken: ?CancellationToken -> 'T
```

<span data-ttu-id="fd6ed-255">사용하는 시기:</span><span class="sxs-lookup"><span data-stu-id="fd6ed-255">When to use it:</span></span>

- <span data-ttu-id="fd6ed-256">필요한 경우 실행 항목의 진입점에서 응용 프로그램에서 한 번만 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-256">If you need it, use it only once in an application - at the entry point for an executable.</span></span>
- <span data-ttu-id="fd6ed-257">성능에 신경 쓰지 않고 다른 비동기 작업 집합을 한 번에 실행하려는 경우</span><span class="sxs-lookup"><span data-stu-id="fd6ed-257">When you don't care about performance and want to execute a set of other asynchronous operations at once.</span></span>

<span data-ttu-id="fd6ed-258">주의해야 할 사항:</span><span class="sxs-lookup"><span data-stu-id="fd6ed-258">What to watch out for:</span></span>

- <span data-ttu-id="fd6ed-259">호출은 `Async.RunSynchronously` 실행이 완료될 때까지 호출 스레드를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-259">Calling `Async.RunSynchronously` blocks the calling thread until the execution completes.</span></span>

### <a name="asyncstart"></a><span data-ttu-id="fd6ed-260">비동기.시작</span><span class="sxs-lookup"><span data-stu-id="fd6ed-260">Async.Start</span></span>

<span data-ttu-id="fd6ed-261">을 반환하는 `unit`스레드 풀에서 비동기 계산을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-261">Starts an asynchronous computation in the thread pool that returns `unit`.</span></span> <span data-ttu-id="fd6ed-262">그 결과를 기다리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-262">Doesn't wait for its result.</span></span> <span data-ttu-id="fd6ed-263">중첩 된 계산은 `Async.Start` 해당 계산이라고 하는 상위 계산과 는 완전히 독립적으로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-263">Nested computations started with `Async.Start` are started completely independently of the parent computation that called them.</span></span> <span data-ttu-id="fd6ed-264">수명은 상위 계산에 연결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-264">Their lifetime is not tied to any parent computation.</span></span> <span data-ttu-id="fd6ed-265">상위 계산이 취소되면 하위 계산이 취소되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-265">If the parent computation is canceled, no child computations are cancelled.</span></span>

<span data-ttu-id="fd6ed-266">서명:</span><span class="sxs-lookup"><span data-stu-id="fd6ed-266">Signature:</span></span>

```fsharp
computation: Async<unit> - cancellationToken: ?CancellationToken -> unit
```

<span data-ttu-id="fd6ed-267">다음과 같은 경우에만 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-267">Use only when:</span></span>

- <span data-ttu-id="fd6ed-268">결과를 생성하지 않거나 하나를 처리해야 하는 비동기 계산이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-268">You have an asynchronous computation that doesn't yield a result and/or require processing of one.</span></span>
- <span data-ttu-id="fd6ed-269">비동기 계산이 완료되는 시기를 알 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-269">You don't need to know when an asynchronous computation completes.</span></span>
- <span data-ttu-id="fd6ed-270">비동기 계산이 실행되는 스레드는 신경 쓰지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-270">You don't care which thread an asynchronous computation runs on.</span></span>
- <span data-ttu-id="fd6ed-271">작업으로 인한 예외를 인식하거나 보고할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-271">You don't have any need to be aware of or report exceptions resulting from the task.</span></span>

<span data-ttu-id="fd6ed-272">주의해야 할 사항:</span><span class="sxs-lookup"><span data-stu-id="fd6ed-272">What to watch out for:</span></span>

- <span data-ttu-id="fd6ed-273">시작된 계산으로 인해 발생하는 `Async.Start` 예외는 호출자에게 전파되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-273">Exceptions raised by computations started with `Async.Start` aren't propagated to the caller.</span></span> <span data-ttu-id="fd6ed-274">호출 스택이 완전히 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-274">The call stack will be completely unwound.</span></span>
- <span data-ttu-id="fd6ed-275">호출로 `Async.Start` 시작된 효과있는 `printfn`작업(예: 호출)은 프로그램 실행의 주 스레드에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-275">Any effectful work (such as calling `printfn`) started with `Async.Start` won't cause the effect to happen on the main thread of a program's execution.</span></span>

## <a name="interoperate-with-net"></a><span data-ttu-id="fd6ed-276">.NET과 상호 운용</span><span class="sxs-lookup"><span data-stu-id="fd6ed-276">Interoperate with .NET</span></span>

<span data-ttu-id="fd6ed-277">[비동기/await-style](../../../standard/async.md)프로그래밍을 사용하는 .NET 라이브러리 또는 C# 코드베이스로 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-277">You may be working with a .NET library or C# codebase that uses [async/await](../../../standard/async.md)-style asynchronous programming.</span></span> <span data-ttu-id="fd6ed-278">C# 및 대부분의 .NET 라이브러리는 <xref:System.Threading.Tasks.Task%601> <xref:System.Threading.Tasks.Task> 이 형식과 형식을 `Async<'T>`핵심 추상화로 사용하기 때문에 이 두 방법 사이의 경계를 비동기로 교차해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-278">Because C# and the majority of .NET libraries use the <xref:System.Threading.Tasks.Task%601> and <xref:System.Threading.Tasks.Task> types as their core abstractions rather than `Async<'T>`, you must cross a boundary between these two approaches to asynchrony.</span></span>

### <a name="how-to-work-with-net-async-and-taskt"></a><span data-ttu-id="fd6ed-279">.NET 비동기 및 작업 방법`Task<T>`</span><span class="sxs-lookup"><span data-stu-id="fd6ed-279">How to work with .NET async and `Task<T>`</span></span>

<span data-ttu-id="fd6ed-280">.NET 비동기 라이브러리 및 사용(즉, 반환 값이 있는 비동기 계산)을 사용하는 <xref:System.Threading.Tasks.Task%601> 코드베이스로 작업하는 것은 간단하며 F#에 대한 기본 제공 지원이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-280">Working with .NET async libraries and codebases that use <xref:System.Threading.Tasks.Task%601> (that is, async computations that have return values) is straightforward and has built-in support with F#.</span></span>

<span data-ttu-id="fd6ed-281">이 함수를 `Async.AwaitTask` 사용하여 .NET 비동기 계산을 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-281">You can use the `Async.AwaitTask` function to await a .NET asynchronous computation:</span></span>

```fsharp
let getValueFromLibrary param =
    async {
        let! value = DotNetLibrary.GetValueAsync param |> Async.AwaitTask
        return value
    }
```

<span data-ttu-id="fd6ed-282">이 함수를 `Async.StartAsTask` 사용하여 .NET 호출자에게 비동기 계산을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-282">You can use the `Async.StartAsTask` function to pass an asynchronous computation to a .NET caller:</span></span>

```fsharp
let computationForCaller param =
    async {
        let! result = getAsyncResult param
        return result
    } |> Async.StartAsTask
```

### <a name="how-to-work-with-net-async-and-task"></a><span data-ttu-id="fd6ed-283">.NET 비동기 및 작업 방법`Task`</span><span class="sxs-lookup"><span data-stu-id="fd6ed-283">How to work with .NET async and `Task`</span></span>

<span data-ttu-id="fd6ed-284">값을 반환하지 않는 <xref:System.Threading.Tasks.Task> .NET 비동기 계산을 사용하는 API를 사용하여 작업하려면 다음을 `Async<'T>` 다음으로 <xref:System.Threading.Tasks.Task>변환하는 추가 함수를 추가해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-284">To work with APIs that use <xref:System.Threading.Tasks.Task> (that is, .NET async computations that do not return a value), you may need to add an additional function that will convert an `Async<'T>` to a <xref:System.Threading.Tasks.Task>:</span></span>

```fsharp
module Async =
    // Async<unit> -> Task
    let startTaskFromAsyncUnit (comp: Async<unit>) =
        Async.StartAsTask comp :> Task
```

<span data-ttu-id="fd6ed-285">입력으로 `Async.AwaitTask` 받아들이는 이미 있습니다. <xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="fd6ed-285">There is already an `Async.AwaitTask` that accepts a <xref:System.Threading.Tasks.Task> as input.</span></span> <span data-ttu-id="fd6ed-286">이 함수와 이전에 `startTaskFromAsyncUnit` 정의된 함수를 사용하면 <xref:System.Threading.Tasks.Task> F# 비동기 계산에서 형식을 시작하고 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-286">With this and the previously defined `startTaskFromAsyncUnit` function, you can start and await <xref:System.Threading.Tasks.Task> types from an F# async computation.</span></span>

## <a name="relationship-to-multi-threading"></a><span data-ttu-id="fd6ed-287">다중 스레딩과의 관계</span><span class="sxs-lookup"><span data-stu-id="fd6ed-287">Relationship to multi-threading</span></span>

<span data-ttu-id="fd6ed-288">이 문서 전체에서 스레딩이 언급되어 있지만 기억해야 할 두 가지 중요한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-288">Although threading is mentioned throughout this article, there are two important things to remember:</span></span>

1. <span data-ttu-id="fd6ed-289">현재 스레드에서 명시적으로 시작하지 않는 한 비동기 계산과 스레드 사이에는 연관성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-289">There is no affinity between an asynchronous computation and a thread, unless explicitly started on the current thread.</span></span>
1. <span data-ttu-id="fd6ed-290">F#의 비동기 프로그래밍은 멀티 스레딩에 대한 추상화가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-290">Asynchronous programming in F# is not an abstraction for multi-threading.</span></span>

<span data-ttu-id="fd6ed-291">예를 들어 계산은 작업의 특성에 따라 실제로 호출자의 스레드에서 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-291">For example, a computation may actually run on its caller's thread, depending on the nature of the work.</span></span> <span data-ttu-id="fd6ed-292">계산은 스레드 간에 "점프"하여 "대기 중"(예: 네트워크 호출이 전송 중일 때) 기간 사이에 유용한 작업을 수행하는 데 약간의 시간 동안 스레드를 대여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-292">A computation could also "jump" between threads, borrowing them for a small amount of time to do useful work in between periods of "waiting" (such as when a network call is in transit).</span></span>

<span data-ttu-id="fd6ed-293">F#은 현재 스레드에서 비동기 계산을 시작하는 몇 가지 기능을 제공하지만(또는 현재 스레드에 명시적으로 적용되지 않음) 일반적으로 비동기는 특정 스레딩 전략과 연결되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ed-293">Although F# provides some abilities to start an asynchronous computation on the current thread (or explicitly not on the current thread), asynchrony generally is not associated with a particular threading strategy.</span></span>

## <a name="see-also"></a><span data-ttu-id="fd6ed-294">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fd6ed-294">See also</span></span>

- [<span data-ttu-id="fd6ed-295">F# 비동기 프로그래밍 모델</span><span class="sxs-lookup"><span data-stu-id="fd6ed-295">The F# Asynchronous Programming Model</span></span>](https://www.microsoft.com/research/publication/the-f-asynchronous-programming-model)
- [<span data-ttu-id="fd6ed-296">Jet.com의 F# 비동기 가이드</span><span class="sxs-lookup"><span data-stu-id="fd6ed-296">Jet.com's F# Async Guide</span></span>](https://medium.com/jettech/f-async-guide-eb3c8a2d180a)
- [<span data-ttu-id="fd6ed-297">재미와 이익의 비동기 프로그래밍 가이드에 대한 F #</span><span class="sxs-lookup"><span data-stu-id="fd6ed-297">F# for fun and profit's Asynchronous Programming guide</span></span>](https://fsharpforfunandprofit.com/posts/concurrency-async-and-parallel/)
- [<span data-ttu-id="fd6ed-298">C # 및 F #의 비동기 : C의 비동기 gotchas #</span><span class="sxs-lookup"><span data-stu-id="fd6ed-298">Async in C# and F#: Asynchronous gotchas in C#</span></span>](http://tomasp.net/blog/csharp-async-gotchas.aspx/)
