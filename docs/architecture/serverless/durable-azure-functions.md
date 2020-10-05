---
title: 지속 가능한 Azure Functions - 서버리스 앱
description: 지속 가능한 Azure Functions는 코드에서 상태 저장 워크플로를 사용하도록 Azure Functions 런타임을 확장합니다.
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 1498b5a19bc92b7db16f7422a35ac3afffb82b60
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91171795"
---
# <a name="durable-azure-functions"></a>지속 가능한 Azure Functions

Azure Functions를 사용하여 서버리스 애플리케이션을 만드는 경우 일반적으로 작업은 상태 비저장 방식으로 실행되도록 디자인됩니다. 이 디자인을 선택하는 이유는 플랫폼이 크기 조정될 때 코드가 실행되는 서버를 파악하기 어렵기 때문입니다. 또한 지정된 지점에서 활성 상태인 인스턴스 수를 파악하기 어렵습니다. 그러나 프로세스의 현재 상태를 알고 있어야 하는 애플리케이션의 클래스가 있습니다. 온라인 상점에 주문을 제출하는 프로세스를 가정해 보겠습니다. 체크 아웃 작업은 프로세스의 상태를 알고 있어야 하는 여러 작업으로 구성된 워크플로일 수 있습니다. 이러한 정보에는 제품 인벤토리, 고객이 계정에 크레딧을 보유하고 있는지 여부, 또한 신용 카드 처리 결과가 포함될 수 있습니다. 이러한 작업은 자체 내부 워크플로 또는 타사 시스템의 서비스일 수도 있습니다.

현재, 내부 및 외부 시스템 간의 애플리케이션 상태를 조정하는 데 도움이 되는 다양한 패턴이 있습니다. 이는 중앙 집중식 큐 시스템, 분산 키-값 저장소 또는 공유 데이터베이스를 사용하여 해당 상태를 관리하는 솔루션에서 흔히 발견됩니다. 그러나 이들은 모두 이제 프로비전하고 관리해야 하는 추가 리소스입니다. 서버리스 환경에서는 이러한 리소스를 수동으로 조정하기 위해 코드가 복잡해질 수 있습니다. Azure Functions는 Durable Functions라는 상태 저장 함수를 만드는 대안을 제공합니다.

Durable Functions는 코드에서 상태 저장 워크플로를 정의할 수 있도록 하는 Azure Functions 런타임 확장입니다. Durable Functions 확장은 워크플로를 작업으로 분리하여 상태를 관리하고, 진행률 검사점을 만들고, 서버 전체에서 함수 호출 분산을 처리할 수 있습니다. 백그라운드에서는 Azure Storage 계정을 사용하여 실행 기록을 유지하고, 작업 함수를 예약하고, 응답을 검색합니다. 서버리스 코드는 해당 저장소 계정에서 지속형 정보와 상호 작용해서는 안 되며 일반적으로 개발자가 상호 작용해야 하는 것은 아닙니다.

## <a name="triggering-a-stateful-workflow"></a>상태 저장 워크플로 트리거

Durable Functions의 상태 저장 워크플로는 두 개의 기본 구성 요소인 오케스트레이션 및 작업 트리거로 나눌 수 있습니다. 트리거 및 바인딩은 서버리스 함수에 서버를 시작하고 입력을 수신하고 결과를 반환할 때를 알리기 위해 Azure Functions에서 사용하는 핵심 구성 요소입니다.

### <a name="working-with-the-orchestration-client"></a>오케스트레이션 클라이언트 작업

오케스트레이션은 Azure Functions에서 트리거되는 작업의 다른 스타일과 비교할 때 독특합니다. Durable Functions를 사용하면 작업을 완료하는 데 몇 시간 또는 며칠 정도 걸릴 수 있는 함수를 실행할 수 있습니다. 이러한 유형의 동작에서는 실행 중인 오케스트레이션의 상태를 확인하거나, 사전에 종료하거나, 외부 이벤트에 대한 알림을 보낼 수 있어야 합니다.

이러한 경우 Durable Functions 확장은 오케스트레이션 함수와 상호 작용할 수 있게 하는 `DurableOrchestrationClient` 클래스를 제공합니다. `OrchestrationClientAttribute` 바인딩을 사용하여 오케스트레이션 클라이언트에 액세스할 수 있습니다. 일반적으로 이 특성은 `HttpTrigger` 또는 `ServiceBusTrigger`와 같은 다른 트리거 형식에 포함됩니다. 원본 함수가 트리거되면 오케스트레이션 클라이언트를 사용하여 오케스트레이터 함수를 시작할 수 있습니다.

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

### <a name="the-orchestrator-function"></a>오케스트레이터 함수

Azure Functions에서 함수에 OrchestrationTriggerAttribute 주석을 추가하면 해당 함수를 오케스트레이터 함수로 표시하는 것입니다. 이 함수는 상태 저장 워크플로를 구성하는 다양 한 작업을 관리합니다.

오케스트레이터 함수는 OrchestrationTriggerAttribute 이외의 바인딩을 사용할 수 없습니다. 이 특성은 DurableOrchestrationContext의 매개 변수 형식에만 사용할 수 있습니다. 함수 시그니처의 입력 역직렬화는 지원되지 않으므로 다른 입력을 사용할 수 없습니다. 오케스트레이션 클라이언트에서 제공하는 입력을 가져오려면 GetInput\<T\> 메서드를 사용해야 합니다.

또한 오케스트레이션 함수의 반환 형식은 void, Task 또는 JSON 직렬화 가능한 값이어야 합니다.

> *간결성을 위해 오류 처리 코드를 생략*

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

오케스트레이션의 여러 인스턴스를 동시에 시작하고 실행할 수 있습니다. `DurableOrchestrationClient`에서 `StartNewAsync` 메서드를 호출하면 오케스트레이션의 새 인스턴스가 시작됩니다. 이 메서드는 오케스트레이션이 시작되면 완료되는 `Task<string>`를 반환합니다. 오케스트레이션이 30초 이내에 시작되지 않으면 `TimeoutException` 형식의 예외가 throw됩니다.

`StartNewAsync`에서 완료된 `Task<string>`는 오케스트레이션 인스턴스의 고유 ID를 포함해야 합니다. 이 인스턴스 ID는 특정 오케스트레이션에 대한 작업을 호출하는 데 사용할 수 있습니다. 오케스트레이션에 대해 상태 또는 전송 이벤트 알림을 쿼리할 수 있습니다.

### <a name="the-activity-functions"></a>활동 함수

활동 함수는 워크플로를 만들기 위해 오케스트레이션 함수 내에 함께 구성된 개별 작업입니다. 여기서 실제 작업이 대부분 수행됩니다. 이들은 비즈니스 논리, 장기 실행 프로세스 및 더 큰 솔루션에 대한 퍼즐 조각을 나타냅니다.

`ActivityTriggerAttribute`는 `DurableActivityContext` 형식의 함수 매개 변수에 주석을 추가하는 데 사용됩니다. 주석을 사용하면 해당 함수가 활동 함수로 사용될 것임을 런타임에 알립니다. 활동 함수에 대한 입력 값은 `DurableActivityContext` 매개 변수의 `GetInput<T>` 메서드를 사용하여 검색됩니다.

오케스트레이션 함수와 마찬가지로 활동 함수의 반환 형식은 void, Task 또는 JSON 직렬화 가능한 값이어야 합니다.

활동 함수 내에서 throw되는 처리되지 않은 예외는 호출 오케스트레이터 함수로 전송되고 `TaskFailedException`으로 표시됩니다. 이 지점에서 오류를 포착하여 오케스트레이터에 기록할 수 있으며 작업을 다시 시도할 수 있습니다.

```csharp
[FunctionName("CheckAndReserveInventory")]
public static bool CheckAndReserveInventory([ActivityTrigger] DurableActivityContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    // Connect to inventory system and try to reserve items
    return true;
}
```

## <a name="recommended-resources"></a>권장되는 리소스

- [지속성 함수](/azure/azure-functions/durable-functions-overview)
- [Durable Functions의 바인딩](/azure/azure-functions/durable-functions-bindings)
- [Durable Functions에서 인스턴스 관리](/azure/azure-functions/durable-functions-instance-management)

>[!div class="step-by-step"]
>[이전](event-grid.md)
>[다음](orchestration-patterns.md)
