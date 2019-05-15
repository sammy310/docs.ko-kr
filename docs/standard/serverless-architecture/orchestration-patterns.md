---
title: 오케스트레이션 패턴-서버 리스 앱
description: Azure Durable functions pr
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 18e13c5355490ef4a019ceda459114bdb6bfd539
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65638798"
---
# <a name="orchestration-patterns"></a>오케스트레이션 패턴

Durable Functions 쉽게 서버 리스 환경에서 불연속, 장기 실행 작업으로 구성 되는 상태 저장 워크플로 만들 수 있습니다. Durable Functions 실행 기록을 워크플로 및 정기적으로 검사점의 진행률을 추적할 수, 있으므로 인계 몇 가지 흥미로운 패턴을 구현 합니다.

## <a name="function-chaining"></a>함수 체 이닝

일반적인 순차적 프로세스에서 작업을 특정 순서로 하나씩 차례 실행 해야 합니다. 필요에 따라 예정 된 작업에는 이전 함수에서 일부 출력이 필요할 수 있습니다. 작업 순서에 대 한이 종속성이 실행 함수 체인을 만듭니다.

Durable Functions를 사용 하 여이 워크플로 패턴을 구현 하는 혜택 검사점 작업을 수행 하는 기능에서 제공 됩니다. 서버가 손상 된 경우, 네트워크 시간 초과 또는 다른 문제가 발생, 지 속성 함수의 마지막으로 알려진된 상태에서 복원 하 고 다른 서버에 하는 경우에 워크플로 실행 합니다. 계속 합니다.

```csharp
[FunctionName("PlaceOrder")]
public static async Task<string> PlaceOrder([OrchestrationTrigger] DurableOrchestrationContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    await context.CallActivityAsync<bool>("CheckAndReserveInventory", orderData);
    await context.CallActivityAsync<bool>("ProcessPayment", orderData);

    string trackingNumber = await context.CallActivityAsync<string>("ScheduleShipping", orderData);
    await context.CallActivityAsync<string>("EmailCustomer", trackingNumber);

    return trackingNumber;
}
```

위의 코드 샘플에는 `CallActivityAsync` 함수는 데이터 센터의 가상 머신에서 지정된 된 활동 실행을 담당 합니다. Await 반환 하 고 기본 작업 완료 되 면 실행 기록 테이블에 기록 됩니다. 오 케 스트레이 터 함수에서 코드를 만들 수 있습니다 작업 병렬 라이브러리 및 async/await 키워드는 친숙 한 구문을 사용 합니다.

다음 코드는 항목의 간단한 예는 `ProcessPayment` 메서드는 다음과 같을 수 있습니다.

```csharp
[FunctionName("ProcessPayment")]
public static bool ProcessPayment([ActivityTrigger] DurableActivityContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    ApplyCoupons(orderData);
    if(IssuePaymentRequest(orderData)) {
        return true;
    }

    return false;
}
```

## <a name="asynchronous-http-apis"></a>비동기 HTTP Api

워크플로 일부 경우에는 데 비교적 오랜 기간을 사용 하는 활동을 포함할 수 있습니다. 미디어의 백업 파일을 blob 저장소로 시작 하는 프로세스를 가정해 보겠습니다. 크기 및 미디어 파일의 수량에 따라이 백업 프로세스를 완료 하는 데 시간이 걸릴 수 있습니다.

이 시나리오에서는 `DurableOrchestrationClient`의 실행 중인 워크플로의 상태를 확인 하는 기능이 유용 합니다. 사용 하는 경우는 `HttpTrigger` 워크플로 시작 하는 `CreateCheckStatusResponse` 의 인스턴스를 반환 하도록 메서드를 사용할 수 있습니다 `HttpResponseMessage`합니다. 이 응답 페이로드에 실행 중인 프로세스의 상태를 확인 하는 URI 사용 하 여 클라이언트를 제공 합니다.

```csharp
[FunctionName("OrderWorkflow")]
public static async Task<HttpResponseMessage> Run(
    [HttpTrigger(AuthorizationLevel.Function, "POST")]HttpRequestMessage req,
    [OrchestrationClient ] DurableOrchestrationClient orchestrationClient)
{
    OrderRequestData data = await req.Content.ReadAsAsync<OrderRequestData>();

    string instanceId = await orchestrationClient.StartNewAsync("PlaceOrder", data);

    return orchestrationClient.CreateCheckStatusResponse(req, instanceId);
}
```

아래 샘플 결과 응답 페이로드의 구조를 보여 줍니다.

```json
{
    "id": "instanceId",
    "statusQueryGetUri": "http://host/statusUri",
    "sendEventPostUri": "http://host/eventUri",
    "terminatePostUri": "http://host/terminateUri"
}
```

기본 HTTP 클라이언트를 사용 하 여 GET 요청 수 statusQueryGetUri의 uri 실행 중인 워크플로의 상태를 조사 합니다. 반환 된 상태 응답에는 다음 코드와 유사 해야 합니다.

```json
{
    "runtimeStatus": "Running",
    "input": {
        "$type": "DurableFunctionsDemos.OrderRequestData, DurableFunctionsDemos"
    },
    "output": null,
    "createdTime": "2018-01-01T00:22:05Z",
    "lastUpdatedTime": "2018-01-01T00:22:09Z"
}
```

프로세스 계속 되 면 상태 응답을 변경 됩니다 **실패** 하거나 **Completed**합니다. 성공적으로 완료 되는 **출력** 페이로드의 속성에 반환 된 데이터가 포함 됩니다.

## <a name="monitoring"></a>모니터링

Azure Functions는 단순 되풀이 작업의 경우 다음을 제공 합니다.는 `TimerTrigger` 예약 될 수 있는 CRON 식을 기반으로 합니다. 타이머 작업을 간단 하 고 단기 적합 하지만 보다 유연한 일정 계획 필요한 시나리오가 있을 수 있습니다. 이 시나리오는 모니터링 패턴 및 지 속성 함수는 데 도움이 하는 경우입니다.

유연한 일정 간격, 수명 관리 및 단일 오케스트레이션 함수에서 여러 모니터링 프로세스의 생성에 대 한 지 속성 함수의 수 있습니다. 이 기능에 대해 하나의 사용 사례는 특정 임계값이 충족 되 면 완료 하는 주식 가격 변경에 대 한 감시자를 만들려면 수 있습니다.

```csharp
[FunctionName("CheckStockPrice")]
public static async Task CheckStockPrice([OrchestrationTrigger] DurableOrchestrationContext context)
{
    StockWatcherInfo stockInfo = context.GetInput<StockWatcherInfo>();
    const int checkIntervalSeconds = 120;
    StockPrice initialStockPrice = null;

    DateTime fireAt;
    DateTime exitTime = context.CurrentUtcDateTime.Add(stockInfo.TimeLimit);

    while (context.CurrentUtcDateTime < exitTime)
    {
        StockPrice currentStockPrice = await context.CallActivityAsync<StockPrice>("GetStockPrice", stockInfo);

        if (initialStockPrice == null)
        {
            initialStockPrice = currentStockPrice;
            fireAt = context.CurrentUtcDateTime.AddSeconds(checkIntervalSeconds);
            await context.CreateTimer(fireAt, CancellationToken.None);
            continue;
        }

        decimal percentageChange = (initialStockPrice.Price - currentStockPrice.Price) /
                               ((initialStockPrice.Price + currentStockPrice.Price) / 2);

        if (Math.Abs(percentageChange) >= stockInfo.PercentageChange)
        {
            // Change threshold detected
            await context.CallActivityAsync("NotifyStockPercentageChange", currentStockPrice);
            break;
        }

        // Sleep til next polling interval
        fireAt = context.CurrentUtcDateTime.AddSeconds(checkIntervalSeconds);
        await context.CreateTimer(fireAt, CancellationToken.None);
    }
}
```

`DurableOrchestrationContext``CreateTimer` 메서드 주가 기본 변경을 확인 하는 루프의 다음 호출에 대 한 일정을 설정 합니다. `DurableOrchestrationContext` 역시는 `CurrentUtcDateTime` 속성을 UTC의 현재 날짜/시간 값을 가져옵니다. 대신이 속성을 사용 하는 것이 좋습니다 `DateTime.UtcNow` 테스트용 모형을 만들 쉽게 때문입니다.

## <a name="recommended-resources"></a>권장 되는 리소스

* [Azure Durable Functions](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
* [.NET Core 및 .NET Standard의 유닛 테스트](../../core/testing/index.md)

>[!div class="step-by-step"]
>[이전](durable-azure-functions.md)
>[다음](serverless-business-scenarios.md)
