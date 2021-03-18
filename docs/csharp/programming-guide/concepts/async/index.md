---
title: C#의 비동기 프로그래밍
description: async, await 및 Task를 사용하여 비동기 프로그래밍을 지원하는 C# 언어에 대해 간략히 설명합니다.<T>
ms.date: 06/04/2020
ms.openlocfilehash: ffc2289f3b5abfe3865e1a096ee91e2e649a6427
ms.sourcegitcommit: d623f686701b94bef905ec5e93d8b55d031c5d6f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2021
ms.locfileid: "103624242"
---
# <a name="asynchronous-programming-with-async-and-await"></a><span data-ttu-id="6fa11-103">async 및 await를 사용한 비동기 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="6fa11-103">Asynchronous programming with async and await</span></span>

<span data-ttu-id="6fa11-104">[TAP(Task 비동기 프로그래밍) 모델](task-asynchronous-programming-model.md)은 비동기 코드에 대한 추상화를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-104">The [Task asynchronous programming model (TAP)](task-asynchronous-programming-model.md) provides an abstraction over asynchronous code.</span></span> <span data-ttu-id="6fa11-105">항상 그렇듯이 코드는 일련의 명령문으로 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-105">You write code as a sequence of statements, just like always.</span></span> <span data-ttu-id="6fa11-106">다음 명령문이 시작되기 전에 각 명령문이 완료되는 것처럼 해당 코드를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-106">You can read that code as though each statement completes before the next begins.</span></span> <span data-ttu-id="6fa11-107">이러한 명령문 중 일부에서 작업을 시작하고 진행 중인 작업을 나타내는 <xref:System.Threading.Tasks.Task>를 반환할 수 있으므로 컴파일러는 여러 가지 변환을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-107">The compiler performs many transformations because some of those statements may start work and return a <xref:System.Threading.Tasks.Task> that represents the ongoing work.</span></span>

<span data-ttu-id="6fa11-108">이 구문의 목표는 일련의 명령문처럼 읽지만 외부 리소스 할당과 작업 완료 시점에 따라 훨씬 더 복잡한 순서로 실행되는 코드를 사용하도록 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-108">That's the goal of this syntax: enable code that reads like a sequence of statements, but executes in a much more complicated order based on external resource allocation and when tasks complete.</span></span> <span data-ttu-id="6fa11-109">사람이 비동기 작업이 포함된 프로세스에 대한 지침을 제공하는 방법과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-109">It's analogous to how people give instructions for processes that include asynchronous tasks.</span></span> <span data-ttu-id="6fa11-110">이 문서에서는 `async` 및 `await` 키워드를 사용하여 일련의 비동기 명령이 포함된 코드를 쉽게 추론하는 방법을 알아보기 위해 아침 식사를 준비하기 위한 지침의 예를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-110">Throughout this article, you'll use an example of instructions for making a breakfast to see how the `async` and `await` keywords make it easier to reason about code, that includes a series of asynchronous instructions.</span></span> <span data-ttu-id="6fa11-111">아침 식사를 준비하는 방법을 설명하기 위해 작성하는 지침은 다음 목록과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-111">You'd write the instructions something like the following list to explain how to make a breakfast:</span></span>

1. <span data-ttu-id="6fa11-112">커피 한 잔을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-112">Pour a cup of coffee.</span></span>
1. <span data-ttu-id="6fa11-113">팬을 데운 다음, 계란 프라이 두 개를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-113">Heat up a pan, then fry two eggs.</span></span>
1. <span data-ttu-id="6fa11-114">베이컨 세 조각을 튀깁니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-114">Fry three slices of bacon.</span></span>
1. <span data-ttu-id="6fa11-115">빵 두 조각을 굽습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-115">Toast two pieces of bread.</span></span>
1. <span data-ttu-id="6fa11-116">토스트에 버터와 잼을 바릅니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-116">Add butter and jam to the toast.</span></span>
1. <span data-ttu-id="6fa11-117">오렌지 주스 한잔을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-117">Pour a glass of orange juice.</span></span>

<span data-ttu-id="6fa11-118">요리에 대한 경험이 있는 경우 이러한 지침은 **비동기적으로** 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-118">If you have experience with cooking, you'd execute those instructions **asynchronously**.</span></span> <span data-ttu-id="6fa11-119">계란 프라이를 위해 팬을 데우기 시작한 다음, 베이컨을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-119">You'd start warming the pan for eggs, then start the bacon.</span></span> <span data-ttu-id="6fa11-120">토스터에 빵을 넣고 계란 프라이를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-120">You'd put the bread in the toaster, then start the eggs.</span></span> <span data-ttu-id="6fa11-121">프로세스의 각 단계에서 작업을 시작한 다음, 주의가 필요한 작업에 주의를 돌립니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-121">At each step of the process, you'd start a task, then turn your attention to tasks that are ready for your attention.</span></span>

<span data-ttu-id="6fa11-122">아침을 요리하는 것은 병렬로 수행되지 않는 비동기 작업의 좋은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-122">Cooking breakfast is a good example of asynchronous work that isn't parallel.</span></span> <span data-ttu-id="6fa11-123">한 사람(또는 스레드)이 이러한 모든 작업을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-123">One person (or thread) can handle all these tasks.</span></span> <span data-ttu-id="6fa11-124">아침 식사 비유를 계속하면 첫 번째 작업이 완료되기 전에 다음 작업을 시작하여 한 사람이 비동기적으로 아침 식사를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-124">Continuing the breakfast analogy, one person can make breakfast asynchronously by starting the next task before the first completes.</span></span> <span data-ttu-id="6fa11-125">누군가 보고 있는지 여부에 관계없이 요리는 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-125">The cooking progresses whether or not someone is watching it.</span></span> <span data-ttu-id="6fa11-126">계란 프라이를 위해 팬을 데우기 시작하자마자 베이컨을 튀기기 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-126">As soon as you start warming the pan for the eggs, you can begin frying the bacon.</span></span> <span data-ttu-id="6fa11-127">베이컨 튀김이 시작되면 토스터에 빵을 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-127">Once the bacon starts, you can put the bread into the toaster.</span></span>

<span data-ttu-id="6fa11-128">병렬 알고리즘의 경우 여러 요리사(또는 스레드)가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-128">For a parallel algorithm, you'd need multiple cooks (or threads).</span></span> <span data-ttu-id="6fa11-129">한 사람은 계란을 만들고 또 한 사람은 베이컨을 만드는 방식으로 진행될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-129">One would make the eggs, one the bacon, and so on.</span></span> <span data-ttu-id="6fa11-130">즉 각각은 하나의 작업에만 집중할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-130">Each one would be focused on just that one task.</span></span> <span data-ttu-id="6fa11-131">각 요리사(또는 스레드)는 베이컨이 뒤집을 준비가 되거나 토스트가 나올 때까지 동기적으로 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-131">Each cook (or thread) would be blocked synchronously waiting for bacon to be ready to flip, or the toast to pop.</span></span>

<span data-ttu-id="6fa11-132">이제 C# 문으로 작성된 동일한 명령을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-132">Now, consider those same instructions written as C# statements:</span></span>

:::code language="csharp" source="snippets/index/AsyncBreakfast-starter/Program.cs" highlight="8-27":::

:::image type="content" source="media/synchronous-breakfast.png" alt-text="동기 아침 식사":::

<span data-ttu-id="6fa11-134">동기적으로 준비된 아침 식사에는 대략 30분이 걸렸는데, 총계는 개별 작업의 합계이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-134">The synchronously prepared breakfast, took roughly 30 minutes because the total is the sum of each individual task.</span></span>

> [!NOTE]
> <span data-ttu-id="6fa11-135">`Coffee`, `Egg`, `Bacon`, `Toast` 및 `Juice` 클래스는 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-135">The `Coffee`, `Egg`, `Bacon`, `Toast`, and `Juice` classes are empty.</span></span> <span data-ttu-id="6fa11-136">해당 클래스는 데모 목적의 마커 클래스일 뿐이며 속성을 포함하지 않고 다른 용도로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-136">They are simply marker classes for the purpose of demonstration, contain no properties, and serve no other purpose.</span></span>

<span data-ttu-id="6fa11-137">컴퓨터에서는 사람들이 수행하는 것과 같은 방식으로 이러한 명령을 해석하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-137">Computers don't interpret those instructions the same way people do.</span></span> <span data-ttu-id="6fa11-138">다음 명령문으로 이동하기 전에 작업이 완료될 때까지 컴퓨터는 각 명령문에서 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-138">The computer will block on each statement until the work is complete before moving on to the next statement.</span></span> <span data-ttu-id="6fa11-139">이로 인해 불만족스러운 아침 식사를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-139">That creates an unsatisfying breakfast.</span></span> <span data-ttu-id="6fa11-140">이전 작업이 완료될 때까지 이후 작업을 시작할 수 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-140">The later tasks wouldn't be started until the earlier tasks had completed.</span></span> <span data-ttu-id="6fa11-141">아침 식사를 만드는 데 훨씬 더 오래 걸리고, 일부 음식은 식은 채로 제공되었을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-141">It would take much longer to create the breakfast, and some items would have gotten cold before being served.</span></span>

<span data-ttu-id="6fa11-142">컴퓨터에서 위의 명령을 비동기적으로 실행하게 하려면 비동기 코드를 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-142">If you want the computer to execute the above instructions asynchronously, you must write asynchronous code.</span></span>

<span data-ttu-id="6fa11-143">이러한 문제는 현재 작성하는 프로그램에 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-143">These concerns are important for the programs you write today.</span></span> <span data-ttu-id="6fa11-144">클라이언트 프로그램을 작성할 때 UI에서 사용자 입력에 응답해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-144">When you write client programs, you want the UI to be responsive to user input.</span></span> <span data-ttu-id="6fa11-145">웹에서 데이터를 다운로드하는 동안 애플리케이션에서 휴대폰이 중지된 것처럼 표시하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-145">Your application shouldn't make a phone appear frozen while it's downloading data from the web.</span></span> <span data-ttu-id="6fa11-146">서버 프로그램을 작성하는 경우 스레드가 차단되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-146">When you write server programs, you don't want threads blocked.</span></span> <span data-ttu-id="6fa11-147">이러한 스레드는 다른 요청을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-147">Those threads could be serving other requests.</span></span> <span data-ttu-id="6fa11-148">비동기 대안이 있을 때 동기 코드를 사용하면 비용이 적게 드는 규모 확장 기능이 저하됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-148">Using synchronous code when asynchronous alternatives exist hurts your ability to scale out less expensively.</span></span> <span data-ttu-id="6fa11-149">차단된 스레드에 대한 비용을 지불합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-149">You pay for those blocked threads.</span></span>

<span data-ttu-id="6fa11-150">성공적인 최신 애플리케이션에는 비동기 코드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-150">Successful modern applications require asynchronous code.</span></span> <span data-ttu-id="6fa11-151">언어 지원 없이 비동기 코드를 작성하는 경우 콜백, 완료 이벤트 또는 코드의 원래 의도를 모호하게 하는 다른 수단이 필요했습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-151">Without language support, writing asynchronous code required callbacks, completion events, or other means that obscured the original intent of the code.</span></span> <span data-ttu-id="6fa11-152">동기 코드의 이점은 단계별 작업을 통해 쉽게 검사하고 이해할 수 있다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-152">The advantage of the synchronous code is that its step-by-step actions make it easy to scan and understand.</span></span> <span data-ttu-id="6fa11-153">기존의 비동기 모델에서는 코드의 기본 동작이 아니라 코드의 비동기적 특성에 집중할 수 밖에 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-153">Traditional asynchronous models forced you to focus on the asynchronous nature of the code, not on the fundamental actions of the code.</span></span>

## <a name="dont-block-await-instead"></a><span data-ttu-id="6fa11-154">차단하는 대신 대기</span><span class="sxs-lookup"><span data-stu-id="6fa11-154">Don't block, await instead</span></span>

<span data-ttu-id="6fa11-155">앞의 코드에서는 동기 코드를 구성하여 비동기 작업을 수행하는 잘못된 사례를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-155">The preceding code demonstrates a bad practice: constructing synchronous code to perform asynchronous operations.</span></span> <span data-ttu-id="6fa11-156">작성한 대로 이 코드는 실행되는 스레드에서 다른 작업을 수행하지 못하도록 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-156">As written, this code blocks the thread executing it from doing any other work.</span></span> <span data-ttu-id="6fa11-157">작업이 진행되는 동안에는 중단되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-157">It won't be interrupted while any of the tasks are in progress.</span></span> <span data-ttu-id="6fa11-158">마치 빵을 넣은 후 토스터를 쳐다보는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-158">It would be as though you stared at the toaster after putting the bread in.</span></span> <span data-ttu-id="6fa11-159">토스트가 나오기 전까지 아무하고도 대화하지 않을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-159">You'd ignore anyone talking to you until the toast popped.</span></span>

<span data-ttu-id="6fa11-160">먼저 이 코드를 업데이트하여 작업이 실행되는 동안 스레드가 차단되지 않도록 하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-160">Let's start by updating this code so that the thread doesn't block while tasks are running.</span></span> <span data-ttu-id="6fa11-161">`await` 키워드는 작업을 차단하지 않는 방식으로 시작한 다음, 해당 작업이 완료되면 실행을 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-161">The `await` keyword provides a non-blocking way to start a task, then continue execution when that task completes.</span></span> <span data-ttu-id="6fa11-162">간단한 비동기 버전의 아침 식사 준비 코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-162">A simple asynchronous version of the make a breakfast code would look like the following snippet:</span></span>

:::code language="csharp" source="snippets/index/AsyncBreakfast-V2/Program.cs" ID="SnippetMain":::

> [!IMPORTANT]
> <span data-ttu-id="6fa11-163">총 경과 시간은 초기 동기 버전과 거의 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-163">The total elapsed time is roughly the same as the initial synchronous version.</span></span> <span data-ttu-id="6fa11-164">이 코드에서는 아직 비동기 프로그래밍의 몇 가지 주요 기능을 활용하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-164">The code has yet to take advantage of some of the key features of asynchronous programming.</span></span>

> [!TIP]
> <span data-ttu-id="6fa11-165">`FryEggsAsync`, `FryBaconAsync` 및 `ToastBreadAsync`의 메서드 본문은 각각 `Task<Egg>`, `Task<Bacon>` 및 `Task<Toast>`를 반환하도록 모두 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-165">The method bodies of the `FryEggsAsync`, `FryBaconAsync`, and `ToastBreadAsync` have all been updated to return `Task<Egg>`, `Task<Bacon>`, and `Task<Toast>` respectively.</span></span> <span data-ttu-id="6fa11-166">이 메서드들은 원래 버전에서 “Async” 접미사를 포함하도록 이름이 바뀌었습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-166">The methods are renamed from their original version to include the "Async" suffix.</span></span> <span data-ttu-id="6fa11-167">해당 구현은 이 문서의 뒷부분에 나오는 [최종 버전](#final-version)의 일부로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-167">Their implementations are shown as part of the [final version](#final-version) later in this article.</span></span>

<span data-ttu-id="6fa11-168">이 코드는 계란이나 베이컨을 요리하는 동안 차단되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-168">This code doesn't block while the eggs or the bacon are cooking.</span></span> <span data-ttu-id="6fa11-169">하지만 이 코드는 다른 작업을 시작하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-169">This code won't start any other tasks though.</span></span> <span data-ttu-id="6fa11-170">토스트가 토스터에 넣어져 나올 때까지 쳐다보고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-170">You'd still put the toast in the toaster and stare at it until it pops.</span></span> <span data-ttu-id="6fa11-171">그러나 적어도 주의를 끌려고 하는 누구에게나 응답할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-171">But at least, you'd respond to anyone that wanted your attention.</span></span> <span data-ttu-id="6fa11-172">여러 주문을 받는 식당에서 요리사는 첫 번째 요리를 하는 동안 또 다른 아침 식사 준비를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-172">In a restaurant where multiple orders are placed, the cook could start another breakfast while the first is cooking.</span></span>

<span data-ttu-id="6fa11-173">시작했지만 아직 완료되지 않은 작업을 기다리는 동안 아침 식사 작업 스레드가 차단되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-173">Now, the thread working on the breakfast isn't blocked while awaiting any started task that hasn't yet finished.</span></span> <span data-ttu-id="6fa11-174">일부 애플리케이션의 경우 이 변경만으로 충분합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-174">For some applications, this change is all that's needed.</span></span> <span data-ttu-id="6fa11-175">GUI 애플리케이션은 이 변경만으로도 사용자에게 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-175">A GUI application still responds to the user with just this change.</span></span> <span data-ttu-id="6fa11-176">그러나 지금 시나리오에서는 더 많은 작업이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-176">However, for this scenario, you want more.</span></span> <span data-ttu-id="6fa11-177">각 구성 요소 작업이 순차적으로 실행되지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-177">You don't want each of the component tasks to be executed sequentially.</span></span> <span data-ttu-id="6fa11-178">이전 작업이 완료되기를 기다리기 전에 각 구성 요소 작업을 시작하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-178">It's better to start each of the component tasks before awaiting the previous task's completion.</span></span>

## <a name="start-tasks-concurrently"></a><span data-ttu-id="6fa11-179">동시에 작업 시작</span><span class="sxs-lookup"><span data-stu-id="6fa11-179">Start tasks concurrently</span></span>

<span data-ttu-id="6fa11-180">대부분의 시나리오에서는 독립적인 몇 가지 작업을 즉시 시작하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-180">In many scenarios, you want to start several independent tasks immediately.</span></span> <span data-ttu-id="6fa11-181">그런 다음, 각 작업이 완료되면 준비된 다른 작업을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-181">Then, as each task finishes, you can continue other work that's ready.</span></span> <span data-ttu-id="6fa11-182">아침 식사 비유에서 이는 아침 식사를 더 빨리 준비하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-182">In the breakfast analogy, that's how you get breakfast done more quickly.</span></span> <span data-ttu-id="6fa11-183">모든 것을 거의 동시에 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-183">You also get everything done close to the same time.</span></span> <span data-ttu-id="6fa11-184">이에 따라 따뜻한 아침 식사가 준비됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-184">You'll get a hot breakfast.</span></span>

<span data-ttu-id="6fa11-185"><xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 및 관련 형식은 진행 중인 작업을 추론하는 데 사용할 수 있는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-185">The <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> and related types are classes you can use to reason about tasks that are in progress.</span></span> <span data-ttu-id="6fa11-186">이를 통해 아침 식사를 준비하는 방법과 더 비슷한 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-186">That enables you to write code that more closely resembles the way you'd actually create breakfast.</span></span> <span data-ttu-id="6fa11-187">계란, 베이컨 및 토스트 요리를 동시에 시작할 수 있을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-187">You'd start cooking the eggs, bacon, and toast at the same time.</span></span> <span data-ttu-id="6fa11-188">각 요리에 필요한 작업이 있으므로 해당 작업에 주의를 기울이고, 다음 작업을 처리한 다음, 주의가 필요한 다른 작업을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-188">As each requires action, you'd turn your attention to that task, take care of the next action, then await for something else that requires your attention.</span></span>

<span data-ttu-id="6fa11-189">작업을 시작하고, 해당 작업을 나타내는 <xref:System.Threading.Tasks.Task> 개체를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-189">You start a task and hold on to the <xref:System.Threading.Tasks.Task> object that represents the work.</span></span> <span data-ttu-id="6fa11-190">결과를 사용하기 전에 각 작업을 기다립니다(`await`).</span><span class="sxs-lookup"><span data-stu-id="6fa11-190">You'll `await` each task before working with its result.</span></span>

<span data-ttu-id="6fa11-191">아침 식사 코드를 이처럼 변경해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-191">Let's make these changes to the breakfast code.</span></span> <span data-ttu-id="6fa11-192">첫 번째 단계는 작업을 기다리지 않고 시작될 때 해당 작업을 저장하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-192">The first step is to store the tasks for operations when they start, rather than awaiting them:</span></span>

```csharp
Coffee cup = PourCoffee();
Console.WriteLine("coffee is ready");

Task<Egg> eggsTask = FryEggsAsync(2);
Egg eggs = await eggsTask;
Console.WriteLine("eggs are ready");

Task<Bacon> baconTask = FryBaconAsync(3);
Bacon bacon = await baconTask;
Console.WriteLine("bacon is ready");

Task<Toast> toastTask = ToastBreadAsync(2);
Toast toast = await toastTask;
ApplyButter(toast);
ApplyJam(toast);
Console.WriteLine("toast is ready");

Juice oj = PourOJ();
Console.WriteLine("oj is ready");
Console.WriteLine("Breakfast is ready!");
```

<span data-ttu-id="6fa11-193">다음으로, 아침 식사를 제공하기 전에 베이컨과 달걀에 대한 `await` 문을 메서드 끝으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-193">Next, you can move the `await` statements for the bacon and eggs to the end of the method, before serving breakfast:</span></span>

```csharp
Coffee cup = PourCoffee();
Console.WriteLine("coffee is ready");

Task<Egg> eggsTask = FryEggsAsync(2);
Task<Bacon> baconTask = FryBaconAsync(3);
Task<Toast> toastTask = ToastBreadAsync(2);

Toast toast = await toastTask;
ApplyButter(toast);
ApplyJam(toast);
Console.WriteLine("toast is ready");
Juice oj = PourOJ();
Console.WriteLine("oj is ready");

Egg eggs = await eggsTask;
Console.WriteLine("eggs are ready");
Bacon bacon = await baconTask;
Console.WriteLine("bacon is ready");

Console.WriteLine("Breakfast is ready!");
```

:::image type="content" source="media/asynchronous-breakfast.png" alt-text="비동기 아침 식사":::

<span data-ttu-id="6fa11-195">비동기적으로 준비된 아침 식사에는 대략 20분이 걸렸는데, 일부 작업이 동시에 실행되었기 때문에 이렇게 시간을 절약할 수 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-195">The asynchronously prepared breakfast took roughly 20 minutes, this time savings is because some tasks ran concurrently.</span></span>

<span data-ttu-id="6fa11-196">앞의 코드가 더 잘 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-196">The preceding code works better.</span></span> <span data-ttu-id="6fa11-197">모든 비동기 작업을 한 번에 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-197">You start all the asynchronous tasks at once.</span></span> <span data-ttu-id="6fa11-198">결과가 필요할 때만 각 작업을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-198">You await each task only when you need the results.</span></span> <span data-ttu-id="6fa11-199">앞의 코드는 다른 마이크로서비스를 요청한 다음, 결과를 단일 페이지로 결합하는 웹 애플리케이션의 코드와 비슷할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-199">The preceding code may be similar to code in a web application that makes requests of different microservices, then combines the results into a single page.</span></span> <span data-ttu-id="6fa11-200">모든 요청을 즉시 수행한 다음, 이러한 모든 작업을 기다리고(`await`) 웹 페이지를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-200">You'll make all the requests immediately, then `await` all those tasks and compose the web page.</span></span>

## <a name="composition-with-tasks"></a><span data-ttu-id="6fa11-201">작업 구성</span><span class="sxs-lookup"><span data-stu-id="6fa11-201">Composition with tasks</span></span>

 <span data-ttu-id="6fa11-202">토스트를 제외한 모든 아침 식사가 동시에 준비되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-202">You have everything ready for breakfast at the same time except the toast.</span></span> <span data-ttu-id="6fa11-203">토스트를 만드는 것은 비동기 작업(빵 굽기)과 동기 작업(버터와 잼 바르기)의 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-203">Making the toast is the composition of an asynchronous operation (toasting the bread), and synchronous operations (adding the butter and the jam).</span></span> <span data-ttu-id="6fa11-204">이 코드를 업데이트하면 중요한 개념을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-204">Updating this code illustrates an important concept:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6fa11-205">동기 작업이 뒤따르는 비동기 작업으로 구성된 작업은 비동기 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-205">The composition of an asynchronous operation followed by synchronous work is an asynchronous operation.</span></span> <span data-ttu-id="6fa11-206">즉 작업의 일부가 비동기이면 전체 작업이 비동기입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-206">Stated another way, if any portion of an operation is asynchronous, the entire operation is asynchronous.</span></span>

<span data-ttu-id="6fa11-207">이전 코드에서는 <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601> 개체를 사용하여 실행 중인 작업을 유지할 수 있음을 보여 주었습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-207">The preceding code showed you that you can use <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> objects to hold running tasks.</span></span> <span data-ttu-id="6fa11-208">결과를 사용하기 전에 각 작업을 기다립니다(`await`).</span><span class="sxs-lookup"><span data-stu-id="6fa11-208">You `await` each task before using its result.</span></span> <span data-ttu-id="6fa11-209">다음 단계는 다른 작업의 결합을 나타내는 메서드를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-209">The next step is to create methods that represent the combination of other work.</span></span> <span data-ttu-id="6fa11-210">아침 식사를 제공하기 전에 빵을 구운 후에 버터와 잼을 바르는 것을 나타내는 작업을 기다리려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-210">Before serving breakfast, you want to await the task that represents toasting the bread before adding butter and jam.</span></span> <span data-ttu-id="6fa11-211">이 작업은 다음 코드를 사용하여 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-211">You can represent that work with the following code:</span></span>

:::code language="csharp" source="snippets/index/AsyncBreakfast-V3/Program.cs" ID="SnippetComposeToastTask":::

<span data-ttu-id="6fa11-212">앞의 메서드에서 해당 시그니처에는 `async` 한정자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-212">The preceding method has the `async` modifier in its signature.</span></span> <span data-ttu-id="6fa11-213">이 경우 이 메서드에서 비동기 작업이 포함된 `await` 문을 포함하고 있다고 컴파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-213">That signals to the compiler that this method contains an `await` statement; it contains asynchronous operations.</span></span> <span data-ttu-id="6fa11-214">이 메서드는 빵을 구운 다음, 버터와 잼을 바르는 작업을 나타내며,</span><span class="sxs-lookup"><span data-stu-id="6fa11-214">This method represents the task that toasts the bread, then adds butter and jam.</span></span> <span data-ttu-id="6fa11-215">이러한 세 가지 작업의 구성을 나타내는 <xref:System.Threading.Tasks.Task%601>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-215">This method returns a <xref:System.Threading.Tasks.Task%601> that represents the composition of those three operations.</span></span> <span data-ttu-id="6fa11-216">이제 main 코드 블록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-216">The main block of code now becomes:</span></span>

:::code language="csharp" source="snippets/index/AsyncBreakfast-V3/Program.cs" ID="SnippetMain":::

<span data-ttu-id="6fa11-217">앞의 변경에서는 비동기 코드를 사용하는 데 있어 중요한 기술을 보여 주었습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-217">The previous change illustrated an important technique for working with asynchronous code.</span></span> <span data-ttu-id="6fa11-218">작업을 반환하는 새 메서드로 구분하여 작업을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-218">You compose tasks by separating the operations into a new method that returns a task.</span></span> <span data-ttu-id="6fa11-219">해당 작업을 기다리는 시기를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-219">You can choose when to await that task.</span></span> <span data-ttu-id="6fa11-220">다른 작업을 동시에 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-220">You can start other tasks concurrently.</span></span>

## <a name="asynchronous-exceptions"></a><span data-ttu-id="6fa11-221">비동기 예외</span><span class="sxs-lookup"><span data-stu-id="6fa11-221">Asynchronous exceptions</span></span>

<span data-ttu-id="6fa11-222">이 시점까지 이러한 모든 작업이 성공적으로 완료된다고 암시적으로 가정했습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-222">Up to this point, you've implicitly assumed that all these tasks complete successfully.</span></span> <span data-ttu-id="6fa11-223">비동기 메서드는 동기 메서드와 마찬가지로 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-223">Asynchronous methods throw exceptions, just like their synchronous counterparts.</span></span> <span data-ttu-id="6fa11-224">예외 및 오류 처리에 대한 비동기 지원은 일반적인 비동기 지원과 같은 목표를 달성하려고 합니다. 즉, 일련의 동기 문처럼 읽는 코드를 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-224">Asynchronous support for exceptions and error handling strives for the same goals as asynchronous support in general: You should write code that reads like a series of synchronous statements.</span></span> <span data-ttu-id="6fa11-225">작업은 성공적으로 완료될 수 없는 경우 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-225">Tasks throw exceptions when they can't complete successfully.</span></span> <span data-ttu-id="6fa11-226">시작된 작업이 `awaited`인 경우 클라이언트 코드에서 해당 예외를 catch할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-226">The client code can catch those exceptions when a started task is `awaited`.</span></span> <span data-ttu-id="6fa11-227">예를 들어 토스트를 만드는 동안 토스터에 불이 난다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-227">For example, let's assume that the toaster catches fire while making the toast.</span></span> <span data-ttu-id="6fa11-228">`ToastBreadAsync` 메서드를 다음 코드와 일치하도록 수정하여 이 상황을 시뮬레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-228">You can simulate that by modifying the `ToastBreadAsync` method to match the following code:</span></span>

```csharp
private static async Task<Toast> ToastBreadAsync(int slices)
{
    for (int slice = 0; slice < slices; slice++)
    {
        Console.WriteLine("Putting a slice of bread in the toaster");
    }
    Console.WriteLine("Start toasting...");
    await Task.Delay(2000);
    Console.WriteLine("Fire! Toast is ruined!");
    throw new InvalidOperationException("The toaster is on fire");
    await Task.Delay(1000);
    Console.WriteLine("Remove toast from toaster");

    return new Toast();
}
```

> [!NOTE]
> <span data-ttu-id="6fa11-229">연결할 수 없는 코드에 대해 앞의 코드를 컴파일하면 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-229">You'll get a warning when you compile the preceding code regarding unreachable code.</span></span> <span data-ttu-id="6fa11-230">토스터에 불이 나면 작업이 정상적으로 진행되지 않으므로 이는 의도적입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-230">That's intentional, because once the toaster catches fire, operations won't proceed normally.</span></span>

<span data-ttu-id="6fa11-231">이러한 변경을 수행한 후 애플리케이션을 실행하면 다음 텍스트와 유사하게 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-231">Run the application after making these changes, and you'll output similar to the following text:</span></span>

```console
Pouring coffee
coffee is ready
Warming the egg pan...
putting 3 slices of bacon in the pan
cooking first side of bacon...
Putting a slice of bread in the toaster
Putting a slice of bread in the toaster
Start toasting...
Fire! Toast is ruined!
flipping a slice of bacon
flipping a slice of bacon
flipping a slice of bacon
cooking the second side of bacon...
cracking 2 eggs
cooking the eggs ...
Put bacon on plate
Put eggs on plate
eggs are ready
bacon is ready
Unhandled exception. System.InvalidOperationException: The toaster is on fire
   at AsyncBreakfast.Program.ToastBreadAsync(Int32 slices) in Program.cs:line 65
   at AsyncBreakfast.Program.MakeToastWithButterAndJamAsync(Int32 number) in Program.cs:line 36
   at AsyncBreakfast.Program.Main(String[] args) in Program.cs:line 24
   at AsyncBreakfast.Program.<Main>(String[] args)
```

<span data-ttu-id="6fa11-232">토스터에 불이 난 시점과 예외가 관찰된 시점 사이에 완료되는 작업이 꽤 많습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-232">Notice that there's quite a few tasks completing between when the toaster catches fire and the exception is observed.</span></span> <span data-ttu-id="6fa11-233">비동기적으로 실행되는 작업에서 예외를 throw하면 해당 Task가 ‘오류’ 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-233">When a task that runs asynchronously throws an exception, that Task is ***faulted***.</span></span> <span data-ttu-id="6fa11-234">Task 개체는 <xref:System.Threading.Tasks.Task.Exception?displayProperty=nameWithType> 속성에서 throw된 예외를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-234">The Task object holds the exception thrown in the <xref:System.Threading.Tasks.Task.Exception?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="6fa11-235">오류 상태인 작업이 대기되면 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-235">Faulted tasks throw an exception when they're awaited.</span></span>

<span data-ttu-id="6fa11-236">이해해야 할 두 가지 중요한 메커니즘이 있습니다. 하나는 예외가 오류 상태인 작업에 저장되는 방식이고 다른 하나는 코드가 오류 상태인 작업을 대기할 때 예외가 패키지 해제되었다가 다시 throw되는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-236">There are two important mechanisms to understand: how an exception is stored in a faulted task, and how an exception is unpackaged and rethrown when code awaits a faulted task.</span></span>

<span data-ttu-id="6fa11-237">비동적으로 실행되는 코드가 예외를 throw하면 해당 예외는 `Task`에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-237">When code running asynchronously throws an exception, that exception is stored in the `Task`.</span></span> <span data-ttu-id="6fa11-238">비동기 작업 중에는 둘 이상의 예외가 throw될 수 있으므로 <xref:System.Threading.Tasks.Task.Exception?displayProperty=nameWithType> 속성은 <xref:System.AggregateException?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-238">The <xref:System.Threading.Tasks.Task.Exception?displayProperty=nameWithType> property is an <xref:System.AggregateException?displayProperty=nameWithType> because more than one exception may be thrown during asynchronous work.</span></span> <span data-ttu-id="6fa11-239">throw된 모든 예외는 <xref:System.AggregateException.InnerExceptions?displayProperty=nameWithType> 컬렉션에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-239">Any exception thrown is added to the <xref:System.AggregateException.InnerExceptions?displayProperty=nameWithType> collection.</span></span> <span data-ttu-id="6fa11-240">해당 `Exception` 속성이 null이면 새 `AggregateException`이 만들어지고 throw된 예외는 컬렉션의 첫 번째 항목이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-240">If that `Exception` property is null, a new `AggregateException` is created and the thrown exception is the first item in the collection.</span></span>

<span data-ttu-id="6fa11-241">오류 상태인 작업의 가장 일반적인 시나리오는 `Exception` 속성이 정확히 하나의 예외를 포함하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-241">The most common scenario for a faulted task is that the `Exception` property contains exactly one exception.</span></span> <span data-ttu-id="6fa11-242">코드가 오류 상태인 작업을 `awaits`하면 <xref:System.AggregateException.InnerExceptions?displayProperty=nameWithType> 컬렉션의 첫 번째 예외가 다시 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-242">When code `awaits` a faulted task, the first exception in the <xref:System.AggregateException.InnerExceptions?displayProperty=nameWithType> collection is rethrown.</span></span> <span data-ttu-id="6fa11-243">그렇기 때문에 이 예제의 출력에 `AggregateException` 대신 `InvalidOperationException`이 표시되는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-243">That's why the output from this example shows an `InvalidOperationException` instead of an `AggregateException`.</span></span> <span data-ttu-id="6fa11-244">첫 번째 내부 예외를 추출하면 동기 메서드로 작업하는 것과 최대한 유사하게 비동기 메서드로 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-244">Extracting the first inner exception makes working with asynchronous methods as similar as possible to working with their synchronous counterparts.</span></span> <span data-ttu-id="6fa11-245">시나리오에서 여러 예외를 생성할 수 있는 경우 코드에서 `Exception` 속성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-245">You can examine the `Exception` property in your code when your scenario may generate multiple exceptions.</span></span>

<span data-ttu-id="6fa11-246">계속하기 전에 `ToastBreadAsync` 메서드에서 다음 두 줄을 주석으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-246">Before going on, comment out these two lines in your `ToastBreadAsync` method.</span></span> <span data-ttu-id="6fa11-247">또 다른 불이 시작되기를 원치는 않으니까요.</span><span class="sxs-lookup"><span data-stu-id="6fa11-247">You don't want to start another fire:</span></span>

```csharp
Console.WriteLine("Fire! Toast is ruined!");
throw new InvalidOperationException("The toaster is on fire");
```

## <a name="await-tasks-efficiently"></a><span data-ttu-id="6fa11-248">효율적인 작업 대기</span><span class="sxs-lookup"><span data-stu-id="6fa11-248">Await tasks efficiently</span></span>

<span data-ttu-id="6fa11-249">`Task` 클래스의 메서드를 사용하여 앞의 코드 끝에 있는 일련의 `await` 문을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-249">The series of `await` statements at the end of the preceding code can be improved by using methods of the `Task` class.</span></span> <span data-ttu-id="6fa11-250">이러한 API 중 하나인 <xref:System.Threading.Tasks.Task.WhenAll%2A>은 다음 코드와 같이 인수 목록의 모든 작업이 완료되면 완료된 <xref:System.Threading.Tasks.Task>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-250">One of those APIs is <xref:System.Threading.Tasks.Task.WhenAll%2A>, which returns a <xref:System.Threading.Tasks.Task> that completes when all the tasks in its argument list have completed, as shown in the following code:</span></span>

```csharp
await Task.WhenAll(eggsTask, baconTask, toastTask);
Console.WriteLine("eggs are ready");
Console.WriteLine("bacon is ready");
Console.WriteLine("toast is ready");
Console.WriteLine("Breakfast is ready!");
```

<span data-ttu-id="6fa11-251">또 다른 옵션으로, 인수가 완료되면 완료된 `Task<Task>`를 반환하는 <xref:System.Threading.Tasks.Task.WhenAny%2A>를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-251">Another option is to use <xref:System.Threading.Tasks.Task.WhenAny%2A>, which returns a `Task<Task>` that completes when any of its arguments completes.</span></span> <span data-ttu-id="6fa11-252">반환된 작업은 이미 완료되었음을 알고 있으므로 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-252">You can await the returned task, knowing that it has already finished.</span></span> <span data-ttu-id="6fa11-253">다음 코드에서는 <xref:System.Threading.Tasks.Task.WhenAny%2A>를 사용하여 첫 번째 작업이 완료될 때까지 기다린 다음, 결과를 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-253">The following code shows how you could use <xref:System.Threading.Tasks.Task.WhenAny%2A> to await the first task to finish and then process its result.</span></span> <span data-ttu-id="6fa11-254">완료된 작업의 결과가 처리되면 완료된 작업을 `WhenAny`에 전달된 작업 목록에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-254">After processing the result from the completed task, you remove that completed task from the list of tasks passed to `WhenAny`.</span></span>

```csharp
var breakfastTasks = new List<Task> { eggsTask, baconTask, toastTask };
while (breakfastTasks.Count > 0)
{
    Task finishedTask = await Task.WhenAny(breakfastTasks);
    if (finishedTask == eggsTask)
    {
        Console.WriteLine("eggs are ready");
    }
    else if (finishedTask == baconTask)
    {
        Console.WriteLine("bacon is ready");
    }
    else if (finishedTask == toastTask)
    {
        Console.WriteLine("toast is ready");
    }
    breakfastTasks.Remove(finishedTask);
}
```

<span data-ttu-id="6fa11-255">변경 내용을 모두 적용한 후 코드의 최종 버전은 다음과 같습니다. <a id="final-version"></a></span><span class="sxs-lookup"><span data-stu-id="6fa11-255">After all those changes, the final version of the code looks like this: <a id="final-version"></a></span></span>
:::code language="csharp" source="snippets/index/AsyncBreakfast-final/Program.cs" highlight="9-40":::

:::image type="content" source="media/whenany-async-breakfast.png" alt-text="모든 비동기 아침 식사의 경우":::

<span data-ttu-id="6fa11-257">비동기적으로 준비된 아침 식사의 최종 버전에는 대략 15분이 걸렸는데, 일부 작업을 동시에 실행하고 코드가 여러 작업을 한 번에 모니터링하고 필요한 경우에만 작업을 수행했기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-257">The final version of the asynchronously prepared breakfast took roughly 15 minutes because some tasks ran concurrently, and the code monitored multiple tasks at once and only take action when it was needed.</span></span>

<span data-ttu-id="6fa11-258">이 최종 코드는 비동기입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-258">This final code is asynchronous.</span></span> <span data-ttu-id="6fa11-259">이 코드는 아침 식사를 요리하는 방법을 더 정확하게 반영하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-259">It more accurately reflects how a person would cook a breakfast.</span></span> <span data-ttu-id="6fa11-260">앞의 코드를 이 문서의 첫 번째 코드 샘플과 비교해 보세요.</span><span class="sxs-lookup"><span data-stu-id="6fa11-260">Compare the preceding code with the first code sample in this article.</span></span> <span data-ttu-id="6fa11-261">핵심 작업은 코드를 읽어 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-261">The core actions are still clear from reading the code.</span></span> <span data-ttu-id="6fa11-262">이 코드는 이 문서의 시작 부분에 나와 있는 아침 식사 준비 지침을 읽는 것과 동일한 방식으로 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-262">You can read this code the same way you'd read those instructions for making a breakfast at the beginning of this article.</span></span> <span data-ttu-id="6fa11-263">`async` 및 `await` 언어 기능을 사용하면 모든 사용자가 작성된 이러한 지침을 따를 수 있습니다. 가능한 한 작업을 시작하지만 작업이 완료될 때까지 기다리는 것을 차단하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa11-263">The language features for `async` and `await` provide the translation every person makes to follow those written instructions: start tasks as you can and don't block waiting for tasks to complete.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6fa11-264">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6fa11-264">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6fa11-265">비동기 프로그램의 실제 시나리오 살펴보기</span><span class="sxs-lookup"><span data-stu-id="6fa11-265">Explore real world scenarios for asynchronous programs</span></span>](../../../async.md)
