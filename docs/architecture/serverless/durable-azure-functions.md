---
title: 지속 가능한 Azure Functions - 서버리스 앱
description: 지속 가능한 Azure Functions는 코드에서 상태 저장 워크플로를 사용하도록 Azure Functions 런타임을 확장합니다.
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 2c0ad086640409ac187c3aa882add4d6b39b6ff9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522854"
---
# <a name="durable-azure-functions"></a><span data-ttu-id="2a888-103">지속 가능한 Azure Functions</span><span class="sxs-lookup"><span data-stu-id="2a888-103">Durable Azure functions</span></span>

<span data-ttu-id="2a888-104">Azure Functions를 사용하여 서버리스 애플리케이션을 만드는 경우 일반적으로 작업은 상태 비저장 방식으로 실행되도록 디자인됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-104">When creating serverless applications with Azure Functions, your operations will typically be designed to run in a stateless manner.</span></span> <span data-ttu-id="2a888-105">이 디자인을 선택하는 이유는 플랫폼이 크기 조정될 때 코드가 실행되는 서버를 파악하기 어렵기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-105">The reason for this design choice is because as the platform scales, it becomes difficult to know what servers the code is running on.</span></span> <span data-ttu-id="2a888-106">또한 지정된 지점에서 활성 상태인 인스턴스 수를 파악하기 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-106">It also becomes difficult to know how many instances are active at any given point.</span></span> <span data-ttu-id="2a888-107">그러나 프로세스의 현재 상태를 알고 있어야 하는 애플리케이션의 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-107">However, there are classes of applications that require the current state of a process to be known.</span></span> <span data-ttu-id="2a888-108">온라인 상점에 주문을 제출하는 프로세스를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-108">Consider the process of submitting an order to an online store.</span></span> <span data-ttu-id="2a888-109">체크 아웃 작업은 프로세스의 상태를 알고 있어야 하는 여러 작업으로 구성된 워크플로일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-109">The checkout operation might be a workflow that is composed of multiple operations that need to know the state of the process.</span></span> <span data-ttu-id="2a888-110">이러한 정보에는 제품 인벤토리, 고객이 계정에 크레딧을 보유하고 있는지 여부, 또한 신용 카드 처리 결과가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-110">Such information may include the product inventory, if the customer has any credits on their account, and also the results of processing the credit card.</span></span> <span data-ttu-id="2a888-111">이러한 작업은 자체 내부 워크플로 또는 타사 시스템의 서비스일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-111">These operations could easily be their own internal workflows or even services from third-party systems.</span></span>

<span data-ttu-id="2a888-112">현재, 내부 및 외부 시스템 간의 애플리케이션 상태를 조정하는 데 도움이 되는 다양한 패턴이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-112">Various patterns exist today that assist with the coordination of application state between internal and external systems.</span></span> <span data-ttu-id="2a888-113">이는 중앙 집중식 큐 시스템, 분산 키-값 저장소 또는 공유 데이터베이스를 사용하여 해당 상태를 관리하는 솔루션에서 흔히 발견됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-113">It's common to come across solutions that rely on centralized queuing systems, distributed key-value stores, or shared databases to manage that state.</span></span> <span data-ttu-id="2a888-114">그러나 이들은 모두 이제 프로비전하고 관리해야 하는 추가 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-114">However, these are all additional resources that now need to be provisioned and managed.</span></span> <span data-ttu-id="2a888-115">서버리스 환경에서는 이러한 리소스를 수동으로 조정하기 위해 코드가 복잡해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-115">In a serverless environment, your code could become cumbersome trying to coordinate with these resources manually.</span></span> <span data-ttu-id="2a888-116">Azure Functions는 Durable Functions라는 상태 저장 함수를 만드는 대안을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-116">Azure Functions offers an alternative for creating stateful functions called Durable Functions.</span></span>

<span data-ttu-id="2a888-117">Durable Functions는 코드에서 상태 저장 워크플로를 정의할 수 있도록 하는 Azure Functions 런타임 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-117">Durable Functions is an extension to the Azure Functions runtime that enables the definition of stateful workflows in code.</span></span> <span data-ttu-id="2a888-118">Durable Functions 확장은 워크플로를 작업으로 분리하여 상태를 관리하고, 진행률 검사점을 만들고, 서버 전체에서 함수 호출 분산을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-118">By breaking down workflows into activities, the Durable Functions extension can manage state, create progress checkpoints, and handle the distribution of function calls across servers.</span></span> <span data-ttu-id="2a888-119">백그라운드에서는 Azure Storage 계정을 사용하여 실행 기록을 유지하고, 작업 함수를 예약하고, 응답을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-119">In the background, it makes use of an Azure Storage account to persist execution history, schedule activity functions and retrieve responses.</span></span> <span data-ttu-id="2a888-120">서버리스 코드는 해당 저장소 계정에서 지속형 정보와 상호 작용해서는 안 되며 일반적으로 개발자가 상호 작용해야 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-120">Your serverless code should never interact with persisted information in that storage account, and is typically not something with which developers need to interact.</span></span>

## <a name="triggering-a-stateful-workflow"></a><span data-ttu-id="2a888-121">상태 저장 워크플로 트리거</span><span class="sxs-lookup"><span data-stu-id="2a888-121">Triggering a stateful workflow</span></span>

<span data-ttu-id="2a888-122">Durable Functions의 상태 저장 워크플로는 두 개의 기본 구성 요소인 오케스트레이션 및 작업 트리거로 나눌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-122">Stateful workflows in Durable Functions can be broken down into two intrinsic components; orchestration and activity triggers.</span></span> <span data-ttu-id="2a888-123">트리거 및 바인딩은 서버리스 함수에 서버를 시작하고 입력을 수신하고 결과를 반환할 때를 알리기 위해 Azure Functions에서 사용하는 핵심 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-123">Triggers and bindings are core components used by Azure Functions to enable your serverless functions to be notified when to start, receive input, and return results.</span></span>

### <a name="working-with-the-orchestration-client"></a><span data-ttu-id="2a888-124">오케스트레이션 클라이언트 작업</span><span class="sxs-lookup"><span data-stu-id="2a888-124">Working with the Orchestration client</span></span>

<span data-ttu-id="2a888-125">오케스트레이션은 Azure Functions에서 트리거되는 작업의 다른 스타일과 비교할 때 독특합니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-125">Orchestrations are unique when compared to other styles of triggered operations in Azure Functions.</span></span> <span data-ttu-id="2a888-126">Durable Functions를 사용하면 작업을 완료하는 데 몇 시간 또는 며칠 정도 걸릴 수 있는 함수를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-126">Durable Functions enables the execution of functions that may take hours or even days to complete.</span></span> <span data-ttu-id="2a888-127">이러한 유형의 동작에서는 실행 중인 오케스트레이션의 상태를 확인하거나, 사전에 종료하거나, 외부 이벤트에 대한 알림을 보낼 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-127">That type of behavior comes with the need to able to check the status of a running orchestration, preemptively terminate, or send notifications of external events.</span></span>

<span data-ttu-id="2a888-128">이러한 경우 Durable Functions 확장은 오케스트레이션 함수와 상호 작용할 수 있게 하는 `DurableOrchestrationClient` 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-128">For such cases, the Durable Functions extension provides the `DurableOrchestrationClient` class that allows you to interact with orchestrated functions.</span></span> <span data-ttu-id="2a888-129">`OrchestrationClientAttribute` 바인딩을 사용하여 오케스트레이션 클라이언트에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-129">You get access to the orchestration client by using the `OrchestrationClientAttribute` binding.</span></span> <span data-ttu-id="2a888-130">일반적으로 이 특성은 `HttpTrigger` 또는 `ServiceBusTrigger`와 같은 다른 트리거 형식에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-130">Generally, you would include this attribute with another trigger type, such as an `HttpTrigger` or `ServiceBusTrigger`.</span></span> <span data-ttu-id="2a888-131">원본 함수가 트리거되면 오케스트레이션 클라이언트를 사용하여 오케스트레이터 함수를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-131">Once the source function has been triggered, the orchestration client can be used to start an orchestrator function.</span></span>

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

### <a name="the-orchestrator-function"></a><span data-ttu-id="2a888-132">오케스트레이터 함수</span><span class="sxs-lookup"><span data-stu-id="2a888-132">The orchestrator function</span></span>

<span data-ttu-id="2a888-133">Azure Functions에서 함수에 OrchestrationTriggerAttribute 주석을 추가하면 해당 함수를 오케스트레이터 함수로 표시하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-133">Annotating a function with the OrchestrationTriggerAttribute in Azure Functions marks that function as an orchestrator function.</span></span> <span data-ttu-id="2a888-134">이 함수는 상태 저장 워크플로를 구성하는 다양 한 작업을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-134">It's responsible for managing the various activities that make up your stateful workflow.</span></span>

<span data-ttu-id="2a888-135">오케스트레이터 함수는 OrchestrationTriggerAttribute 이외의 바인딩을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-135">Orchestrator functions are unable to make use of bindings other than the OrchestrationTriggerAttribute.</span></span> <span data-ttu-id="2a888-136">이 특성은 DurableOrchestrationContext의 매개 변수 형식에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-136">This attribute can only be used with a parameter type of DurableOrchestrationContext.</span></span> <span data-ttu-id="2a888-137">함수 시그니처의 입력 역직렬화는 지원되지 않으므로 다른 입력을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-137">No other inputs can be used since deserialization of inputs in the function signature isn't supported.</span></span> <span data-ttu-id="2a888-138">오케스트레이션 클라이언트에서 제공하는 입력을 가져오려면 GetInput\<T\> 메서드를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-138">To get inputs provided by the orchestration client, the GetInput\<T\> method must be used.</span></span>

<span data-ttu-id="2a888-139">또한 오케스트레이션 함수의 반환 형식은 void, Task 또는 JSON 직렬화 가능한 값이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-139">Also, the return types of orchestration functions must be either void, Task, or a JSON serializable value.</span></span>

> <span data-ttu-id="2a888-140">*간결성을 위해 오류 처리 코드를 생략*</span><span class="sxs-lookup"><span data-stu-id="2a888-140">*Error handling code has been left out for brevity*</span></span>

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

<span data-ttu-id="2a888-141">오케스트레이션의 여러 인스턴스를 동시에 시작하고 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-141">Multiple instances of an orchestration can be started and running at the same time.</span></span> <span data-ttu-id="2a888-142">`StartNewAsync`에서 `DurableOrchestrationClient` 메서드를 호출하면 오케스트레이션의 새 인스턴스가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-142">Calling the `StartNewAsync` method on the `DurableOrchestrationClient` launches a new instance of the orchestration.</span></span> <span data-ttu-id="2a888-143">이 메서드는 오케스트레이션이 시작되면 완료되는 `Task<string>`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-143">The method returns a `Task<string>` that completes when the orchestration has started.</span></span> <span data-ttu-id="2a888-144">오케스트레이션이 30초 이내에 시작되지 않으면 `TimeoutException` 형식의 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-144">An exception of type `TimeoutException` gets thrown if the orchestration hasn't started within 30 seconds.</span></span>

<span data-ttu-id="2a888-145">`Task<string>`에서 완료된 `StartNewAsync`는 오케스트레이션 인스턴스의 고유 ID를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-145">The completed `Task<string>` from `StartNewAsync` should contain the unique ID of the orchestration instance.</span></span> <span data-ttu-id="2a888-146">이 인스턴스 ID는 특정 오케스트레이션에 대한 작업을 호출하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-146">This instance ID can be used to invoke operations on that specific orchestration.</span></span> <span data-ttu-id="2a888-147">오케스트레이션에 대해 상태 또는 전송 이벤트 알림을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-147">The orchestration can be queried for the status or sent event notifications.</span></span>

### <a name="the-activity-functions"></a><span data-ttu-id="2a888-148">활동 함수</span><span class="sxs-lookup"><span data-stu-id="2a888-148">The activity functions</span></span>

<span data-ttu-id="2a888-149">활동 함수는 워크플로를 만들기 위해 오케스트레이션 함수 내에 함께 구성된 개별 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-149">Activity functions are the discrete operations that get composed together within an orchestration function to create the workflow.</span></span> <span data-ttu-id="2a888-150">여기서 실제 작업이 대부분 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-150">Here is where most of actual work would take place.</span></span> <span data-ttu-id="2a888-151">이들은 비즈니스 논리, 장기 실행 프로세스 및 더 큰 솔루션에 대한 퍼즐 조각을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-151">They represent the business logic, long running processes, and the puzzle pieces to a larger solution.</span></span>

<span data-ttu-id="2a888-152">`ActivityTriggerAttribute`는 `DurableActivityContext` 형식의 함수 매개 변수에 주석을 추가하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-152">The `ActivityTriggerAttribute` is used to annotate a function parameter of type `DurableActivityContext`.</span></span> <span data-ttu-id="2a888-153">주석을 사용하면 해당 함수가 활동 함수로 사용될 것임을 런타임에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-153">Using the annotation informs the runtime that the function is intended to be used as an activity function.</span></span> <span data-ttu-id="2a888-154">활동 함수에 대한 입력 값은 `GetInput<T>` 매개 변수의 `DurableActivityContext` 메서드를 사용하여 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-154">Input values to activity functions are retrieved using the `GetInput<T>` method of the `DurableActivityContext` parameter.</span></span>

<span data-ttu-id="2a888-155">오케스트레이션 함수와 마찬가지로 활동 함수의 반환 형식은 void, Task 또는 JSON 직렬화 가능한 값이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-155">Similar to orchestration functions, the return types of activity functions must be either void, Task, or a JSON serializable value.</span></span>

<span data-ttu-id="2a888-156">활동 함수 내에서 throw되는 처리되지 않은 예외는 호출 오케스트레이터 함수로 전송되고 `TaskFailedException`으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-156">Any unhandled exceptions that get thrown within activity functions will get sent up to the calling orchestrator function and presented as a `TaskFailedException`.</span></span> <span data-ttu-id="2a888-157">이 지점에서 오류를 포착하여 오케스트레이터에 기록할 수 있으며 작업을 다시 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a888-157">At this point, the error can be caught and logged in the orchestrator, and the activity can be retried.</span></span>

```csharp
[FunctionName("CheckAndReserveInventory")]
public static bool CheckAndReserveInventory([ActivityTrigger] DurableActivityContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    // Connect to inventory system and try to reserve items
    return true;
}
```

## <a name="recommended-resources"></a><span data-ttu-id="2a888-158">권장되는 리소스</span><span class="sxs-lookup"><span data-stu-id="2a888-158">Recommended resources</span></span>

- [<span data-ttu-id="2a888-159">지속성 함수</span><span class="sxs-lookup"><span data-stu-id="2a888-159">Durable Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
- [<span data-ttu-id="2a888-160">Durable Functions의 바인딩</span><span class="sxs-lookup"><span data-stu-id="2a888-160">Bindings for Durable Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/durable-functions-bindings)
- [<span data-ttu-id="2a888-161">Durable Functions에서 인스턴스 관리</span><span class="sxs-lookup"><span data-stu-id="2a888-161">Manage instances in Durable Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/durable-functions-instance-management)

>[!div class="step-by-step"]
><span data-ttu-id="2a888-162">[이전](event-grid.md)
>[다음](orchestration-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="2a888-162">[Previous](event-grid.md)
[Next](orchestration-patterns.md)</span></span>
