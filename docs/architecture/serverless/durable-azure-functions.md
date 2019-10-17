---
title: 내구성이 있는 Azure 함수-서버 리스 앱
description: 지속적인 Azure 함수는 코드에서 상태 저장 워크플로를 사용 하도록 Azure Functions 런타임을 확장 합니다.
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 2c0ad086640409ac187c3aa882add4d6b39b6ff9
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522854"
---
# <a name="durable-azure-functions"></a><span data-ttu-id="a88a8-103">지속 가능한 Azure Functions</span><span class="sxs-lookup"><span data-stu-id="a88a8-103">Durable Azure functions</span></span>

<span data-ttu-id="a88a8-104">Azure Functions를 사용 하 여 서버를 사용 하지 않는 응용 프로그램을 만드는 경우 일반적으로 작업은 상태 비저장 방식으로 실행 되도록 설계 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-104">When creating serverless applications with Azure Functions, your operations will typically be designed to run in a stateless manner.</span></span> <span data-ttu-id="a88a8-105">이 디자인을 선택 하는 이유는 플랫폼이 확장 될 때 코드가 실행 되는 서버를 파악 하기 어렵기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-105">The reason for this design choice is because as the platform scales, it becomes difficult to know what servers the code is running on.</span></span> <span data-ttu-id="a88a8-106">또한 지정 된 지점에서 활성 상태인 인스턴스 수를 파악 하기 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-106">It also becomes difficult to know how many instances are active at any given point.</span></span> <span data-ttu-id="a88a8-107">그러나 프로세스의 현재 상태를 알고 있어야 하는 응용 프로그램의 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-107">However, there are classes of applications that require the current state of a process to be known.</span></span> <span data-ttu-id="a88a8-108">온라인 스토어에 주문을 제출 하는 프로세스를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-108">Consider the process of submitting an order to an online store.</span></span> <span data-ttu-id="a88a8-109">체크 아웃 작업은 프로세스의 상태를 알고 있어야 하는 여러 작업으로 구성 된 워크플로 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-109">The checkout operation might be a workflow that is composed of multiple operations that need to know the state of the process.</span></span> <span data-ttu-id="a88a8-110">이러한 정보에는 제품 인벤토리에 포함 될 수 있으며, 고객이 계정에 크레딧을 보유 하 고 있는 경우 신용 카드를 처리 하는 결과도 여기에 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-110">Such information may include the product inventory, if the customer has any credits on their account, and also the results of processing the credit card.</span></span> <span data-ttu-id="a88a8-111">이러한 작업은 자체 내부 워크플로 또는 타사 시스템의 서비스 일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-111">These operations could easily be their own internal workflows or even services from third-party systems.</span></span>

<span data-ttu-id="a88a8-112">현재 내부 및 외부 시스템 간의 응용 프로그램 상태를 조정 하는 데 도움이 되는 다양 한 패턴이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-112">Various patterns exist today that assist with the coordination of application state between internal and external systems.</span></span> <span data-ttu-id="a88a8-113">이는 중앙 집중식 큐 시스템, 분산 키-값 저장소 또는 공유 데이터베이스를 사용 하 여 해당 상태를 관리 하는 솔루션에서 일반적으로 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-113">It's common to come across solutions that rely on centralized queuing systems, distributed key-value stores, or shared databases to manage that state.</span></span> <span data-ttu-id="a88a8-114">그러나 이제 프로 비전 하 고 관리 해야 하는 모든 추가 리소스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-114">However, these are all additional resources that now need to be provisioned and managed.</span></span> <span data-ttu-id="a88a8-115">서버를 사용 하지 않는 환경에서는 코드를 사용 하 여 이러한 리소스를 수동으로 조정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-115">In a serverless environment, your code could become cumbersome trying to coordinate with these resources manually.</span></span> <span data-ttu-id="a88a8-116">Azure Functions는 Durable Functions 이라는 상태 저장 함수를 만드는 대안을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-116">Azure Functions offers an alternative for creating stateful functions called Durable Functions.</span></span>

<span data-ttu-id="a88a8-117">Durable Functions은 코드에서 상태 저장 워크플로를 정의할 수 있도록 하는 Azure Functions 런타임에 대 한 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-117">Durable Functions is an extension to the Azure Functions runtime that enables the definition of stateful workflows in code.</span></span> <span data-ttu-id="a88a8-118">Durable Functions 확장은 워크플로를 작업으로 분리 하 여 상태를 관리 하 고, 진행률 검사점을 만들고, 서버 전체에서 함수 호출의 분포를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-118">By breaking down workflows into activities, the Durable Functions extension can manage state, create progress checkpoints, and handle the distribution of function calls across servers.</span></span> <span data-ttu-id="a88a8-119">백그라운드에서는 Azure Storage 계정을 사용 하 여 실행 기록을 유지 하 고, 작업 함수를 예약 하 고, 응답을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-119">In the background, it makes use of an Azure Storage account to persist execution history, schedule activity functions and retrieve responses.</span></span> <span data-ttu-id="a88a8-120">서버를 사용 하지 않는 코드는 해당 저장소 계정에서 지속형 정보와 상호 작용 해서는 안 되며 일반적으로 개발자가 상호 작용 해야 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-120">Your serverless code should never interact with persisted information in that storage account, and is typically not something with which developers need to interact.</span></span>

## <a name="triggering-a-stateful-workflow"></a><span data-ttu-id="a88a8-121">상태 저장 워크플로 트리거</span><span class="sxs-lookup"><span data-stu-id="a88a8-121">Triggering a stateful workflow</span></span>

<span data-ttu-id="a88a8-122">Durable Functions의 상태 저장 워크플로는 두 개의 기본 구성 요소로 나눌 수 있습니다. 오케스트레이션 및 작업 트리거</span><span class="sxs-lookup"><span data-stu-id="a88a8-122">Stateful workflows in Durable Functions can be broken down into two intrinsic components; orchestration and activity triggers.</span></span> <span data-ttu-id="a88a8-123">트리거 및 바인딩은 서버를 시작 하 고 입력을 수신 하 고 결과를 반환할 때 서버를 사용 하지 않는 함수를 알리도록 설정 하기 위해 Azure Functions에서 사용 하는 핵심 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-123">Triggers and bindings are core components used by Azure Functions to enable your serverless functions to be notified when to start, receive input, and return results.</span></span>

### <a name="working-with-the-orchestration-client"></a><span data-ttu-id="a88a8-124">오케스트레이션 클라이언트 작업</span><span class="sxs-lookup"><span data-stu-id="a88a8-124">Working with the Orchestration client</span></span>

<span data-ttu-id="a88a8-125">오케스트레이션은 Azure Functions에서 트리거된 작업의 다른 스타일과 비교할 때 고유 합니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-125">Orchestrations are unique when compared to other styles of triggered operations in Azure Functions.</span></span> <span data-ttu-id="a88a8-126">Durable Functions를 사용 하면 작업을 완료 하는 데 몇 시간 또는 며칠 정도 걸릴 수 있는 함수를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-126">Durable Functions enables the execution of functions that may take hours or even days to complete.</span></span> <span data-ttu-id="a88a8-127">이러한 유형의 동작은 실행 중인 오케스트레이션의 상태를 확인 하거나, 미리 종료 하거나, 외부 이벤트에 대 한 알림을 보낼 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-127">That type of behavior comes with the need to able to check the status of a running orchestration, preemptively terminate, or send notifications of external events.</span></span>

<span data-ttu-id="a88a8-128">이러한 경우 Durable Functions 확장은 오케스트레이션 함수와 상호 작용할 수 있도록 하는 @no__t 0 클래스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-128">For such cases, the Durable Functions extension provides the `DurableOrchestrationClient` class that allows you to interact with orchestrated functions.</span></span> <span data-ttu-id="a88a8-129">@No__t-0 바인딩을 사용 하 여 오케스트레이션 클라이언트에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-129">You get access to the orchestration client by using the `OrchestrationClientAttribute` binding.</span></span> <span data-ttu-id="a88a8-130">일반적으로 `HttpTrigger` 또는 `ServiceBusTrigger`과 같은 다른 트리거 형식에이 특성을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-130">Generally, you would include this attribute with another trigger type, such as an `HttpTrigger` or `ServiceBusTrigger`.</span></span> <span data-ttu-id="a88a8-131">원본 함수가 트리거된 후에는 orchestration 클라이언트를 사용 하 여 orchestrator 함수를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-131">Once the source function has been triggered, the orchestration client can be used to start an orchestrator function.</span></span>

```csharp
[FunctionName("KickOff")]
public static async Task<HttpResponseMessage> Run(
    [HttpTrigger(AuthorizationLevel.Function, "POST")]HttpRequestMessage req,
    [OrchestrationClient ] DurableOrchestrationClient<orchestrationClient>)
{
    OrderRequestData data = await req.Content.ReadAsAsync<OrderRequestData>();

    string instanceId = await orchestrationClient.StartNewAsync("PlaceOrder", data);

    return orchestrationClient.CreateCheckStatusResponse(req, instanceId);
}
```

### <a name="the-orchestrator-function"></a><span data-ttu-id="a88a8-132">Orchestrator 함수</span><span class="sxs-lookup"><span data-stu-id="a88a8-132">The orchestrator function</span></span>

<span data-ttu-id="a88a8-133">Azure Functions의 OrchestrationTriggerAttribute를 사용 하 여 함수에 주석을 달아 오 케 스트레이 터 함수로 함수를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-133">Annotating a function with the OrchestrationTriggerAttribute in Azure Functions marks that function as an orchestrator function.</span></span> <span data-ttu-id="a88a8-134">상태 저장 워크플로를 구성 하는 다양 한 작업을 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-134">It's responsible for managing the various activities that make up your stateful workflow.</span></span>

<span data-ttu-id="a88a8-135">Orchestrator 함수는 OrchestrationTriggerAttribute 이외의 바인딩을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-135">Orchestrator functions are unable to make use of bindings other than the OrchestrationTriggerAttribute.</span></span> <span data-ttu-id="a88a8-136">이 특성은 DurableOrchestrationContext의 매개 변수 형식에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-136">This attribute can only be used with a parameter type of DurableOrchestrationContext.</span></span> <span data-ttu-id="a88a8-137">함수 시그니처의 입력 deserialization은 지원 되지 않으므로 다른 입력을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-137">No other inputs can be used since deserialization of inputs in the function signature isn't supported.</span></span> <span data-ttu-id="a88a8-138">Orchestration 클라이언트에서 제공 하는 입력을 가져오려면 GetInput @ no__t-0T @ no__t-1 메서드를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-138">To get inputs provided by the orchestration client, the GetInput\<T\> method must be used.</span></span>

<span data-ttu-id="a88a8-139">또한 오케스트레이션 함수의 반환 형식은 void, Task 또는 JSON serializable 값 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-139">Also, the return types of orchestration functions must be either void, Task, or a JSON serializable value.</span></span>

> <span data-ttu-id="a88a8-140">*오류 처리 코드를 간결 하 게 유지 했습니다.*</span><span class="sxs-lookup"><span data-stu-id="a88a8-140">*Error handling code has been left out for brevity*</span></span>

```csharp
[FunctionName("PlaceOrder")]
public static async Task<string> PlaceOrder([OrchestrationTrigger] DurableOrchestrationContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    await context.CallActivityAsync<bool>("CheckAndReserveInventory", orderData);
    await context.CallActivityAsync<string>("ProcessPayment", orderData);

    string trackingNumber = await context.CallActivityAsync<string>("ScheduleShipping", orderData);
    await context.CallActivityAsync<string>("EmailCustomer", trackingNumber);

    return trackingNumber;
}
```

<span data-ttu-id="a88a8-141">오케스트레이션의 여러 인스턴스를 동시에 시작 하 고 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-141">Multiple instances of an orchestration can be started and running at the same time.</span></span> <span data-ttu-id="a88a8-142">@No__t-1에서 `StartNewAsync` 메서드를 호출 하면 오케스트레이션의 새 인스턴스가 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-142">Calling the `StartNewAsync` method on the `DurableOrchestrationClient` launches a new instance of the orchestration.</span></span> <span data-ttu-id="a88a8-143">메서드는 오케스트레이션이 시작 될 때 완료 되는 `Task<string>`을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-143">The method returns a `Task<string>` that completes when the orchestration has started.</span></span> <span data-ttu-id="a88a8-144">오케스트레이션이 30 초 내에 시작 되지 않은 경우 `TimeoutException` 형식의 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-144">An exception of type `TimeoutException` gets thrown if the orchestration hasn't started within 30 seconds.</span></span>

<span data-ttu-id="a88a8-145">@No__t-1에서 완료 된 `Task<string>`은 오케스트레이션 인스턴스의 고유 ID를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-145">The completed `Task<string>` from `StartNewAsync` should contain the unique ID of the orchestration instance.</span></span> <span data-ttu-id="a88a8-146">이 인스턴스 ID는 특정 오케스트레이션에 대 한 작업을 호출 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-146">This instance ID can be used to invoke operations on that specific orchestration.</span></span> <span data-ttu-id="a88a8-147">오케스트레이션은 상태 또는 송신 이벤트 알림에 대해 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-147">The orchestration can be queried for the status or sent event notifications.</span></span>

### <a name="the-activity-functions"></a><span data-ttu-id="a88a8-148">작업 함수</span><span class="sxs-lookup"><span data-stu-id="a88a8-148">The activity functions</span></span>

<span data-ttu-id="a88a8-149">활동 함수는 워크플로를 만들기 위해 오케스트레이션 함수 내에 함께 구성 된 불연속 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-149">Activity functions are the discrete operations that get composed together within an orchestration function to create the workflow.</span></span> <span data-ttu-id="a88a8-150">다음은 대부분의 실제 작업을 수행 하는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-150">Here is where most of actual work would take place.</span></span> <span data-ttu-id="a88a8-151">비즈니스 논리, 장기 실행 프로세스 및 더 큰 솔루션에 대 한 퍼즐 조각을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-151">They represent the business logic, long running processes, and the puzzle pieces to a larger solution.</span></span>

<span data-ttu-id="a88a8-152">@No__t-0은 `DurableActivityContext` 형식의 함수 매개 변수에 주석을 추가 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-152">The `ActivityTriggerAttribute` is used to annotate a function parameter of type `DurableActivityContext`.</span></span> <span data-ttu-id="a88a8-153">주석을 사용 하면 함수가 활동 함수로 사용 될 것 이라는 것을 런타임에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-153">Using the annotation informs the runtime that the function is intended to be used as an activity function.</span></span> <span data-ttu-id="a88a8-154">작업 함수에 대 한 입력 값은 `DurableActivityContext` 매개 변수의 `GetInput<T>` 메서드를 사용 하 여 검색 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-154">Input values to activity functions are retrieved using the `GetInput<T>` method of the `DurableActivityContext` parameter.</span></span>

<span data-ttu-id="a88a8-155">오케스트레이션 함수와 마찬가지로 작업 함수의 반환 형식은 void, Task 또는 JSON serializable 값 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-155">Similar to orchestration functions, the return types of activity functions must be either void, Task, or a JSON serializable value.</span></span>

<span data-ttu-id="a88a8-156">작업 함수 내에서 throw 되는 처리 되지 않은 예외는 호출 오 케 스트레이 터 함수로 전송 되 고 `TaskFailedException`으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-156">Any unhandled exceptions that get thrown within activity functions will get sent up to the calling orchestrator function and presented as a `TaskFailedException`.</span></span> <span data-ttu-id="a88a8-157">이 시점에서 오류를 catch 하 여 오 케 스트레이 터에 기록할 수 있으며 작업을 다시 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a88a8-157">At this point, the error can be caught and logged in the orchestrator, and the activity can be retried.</span></span>

```csharp
[FunctionName("CheckAndReserveInventory")]
public static bool CheckAndReserveInventory([ActivityTrigger] DurableActivityContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    // Connect to inventory system and try to reserve items
    return true;
}
```

## <a name="recommended-resources"></a><span data-ttu-id="a88a8-158">권장 리소스</span><span class="sxs-lookup"><span data-stu-id="a88a8-158">Recommended resources</span></span>

- [<span data-ttu-id="a88a8-159">Durable Functions</span><span class="sxs-lookup"><span data-stu-id="a88a8-159">Durable Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
- [<span data-ttu-id="a88a8-160">Durable Functions에 대 한 바인딩</span><span class="sxs-lookup"><span data-stu-id="a88a8-160">Bindings for Durable Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/durable-functions-bindings)
- [<span data-ttu-id="a88a8-161">Durable Functions에서 인스턴스 관리</span><span class="sxs-lookup"><span data-stu-id="a88a8-161">Manage instances in Durable Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/durable-functions-instance-management)

>[!div class="step-by-step"]
><span data-ttu-id="a88a8-162">[이전](event-grid.md)
>[다음](orchestration-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="a88a8-162">[Previous](event-grid.md)
[Next](orchestration-patterns.md)</span></span>
