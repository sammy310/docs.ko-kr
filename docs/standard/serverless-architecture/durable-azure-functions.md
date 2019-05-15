---
title: 지 속성 Azure functions-서버 리스 앱
description: 지 속성 Azure functions 코드에서 상태 저장 워크플로 사용 하도록 설정 하려면 Azure Functions 런타임을 확장 합니다.
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: f7ee74926d6658042120113b49dc763383881423
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65643409"
---
# <a name="durable-azure-functions"></a>지속 가능한 Azure Functions

Azure Functions를 사용 하 여 서버 리스 응용 프로그램을 만들 때 작업 상태 비저장 방식으로 실행 하려면 일반적으로 디자인 됩니다. 이 디자인 선택 이유가 되므로 플랫폼 눈금으로 어려워집니다 코드에서 실행 되 고 어떤 서버가 인지 알고 있어야 합니다. 또한 특정된 시점에서 활성 상태인 인스턴스 개수를 확인 하기 어려운 됩니다. 그러나는 알 수 하는 프로세스의 현재 상태를 필요로 하는 응용 프로그램의 클래스가 있습니다. 프로세스를 온라인 상점으로 주문을 제출 하는 것이 좋습니다. 체크 아웃 작업 프로세스의 상태를 파악 해야 하는 여러 작업으로 구성 된 워크플로 수 있습니다. 이러한 정보는 고객이 자신의 계정에도 신용 카드를 처리 하면 크레딧은 있으면 제품 재고를 포함할 수 있습니다. 자체 내부 워크플로 서비스나 심지어 타사 시스템에서 이러한 작업 수입니다.

다양 한 패턴을 지 원하는 응용 프로그램 상태 내부 및 외부 시스템 간의 조정을 통해 오늘날 존재 합니다. 중앙 집중식된 큐 시스템, 분산된 키-값 저장소 또는 해당 상태를 관리 하는 공유 데이터베이스를 사용 하는 솔루션에서 제공 하는 일반적인 경우 그러나 이들은 이제 프로 비전 하 고 관리 해야 하는 모든 추가 리소스입니다. 서버 리스 환경에서 코드는 이러한 리소스를 사용 하 여 수동으로 조정 하는 것이 불편 해질 수 있습니다. Azure Functions Durable Functions를 호출 하는 상태 저장 함수를 만들기 위한 대안을 제공 합니다.

Durable Functions는 코드에서 상태 저장 워크플로 정의 사용 하도록 설정 하는 Azure Functions 런타임은 확장 판입니다. 작업으로 워크플로 세분화 하 여 지 속성 함수 확장 수 상태 관리, 진행 상황 검사점을 만들 및 서버에서 함수 호출의 분포를 처리 합니다. 백그라운드에서 사용 하 여 Azure Storage 계정을 실행 기록 유지, 작업 함수를 예약 하 고 응답을 검색 하면 합니다. 서버 리스 코드는 저장소 계정에 보관 된 정보 상호 작용 하지 않습니다 및 하지 않는 경우 일반적으로는 개발자가 상호 작용 해야 합니다.

## <a name="triggering-a-stateful-workflow"></a>상태 저장 워크플로 트리거

지 속성 함수의 상태 저장 워크플로 수 나눌 두 가지 기본 구성 요소 오케스트레이션 및 작업 트리거입니다. 트리거 및 바인딩은 입력을 시작, 수신 및 반환 결과 때 알림을 받도록 서버 리스 함수를 사용 하도록 설정 하려면 Azure Functions에서 사용 하는 핵심 구성 요소입니다.

### <a name="working-with-the-orchestration-client"></a>오케스트레이션 클라이언트 사용

오케스트레이션은 Azure Functions에서 트리거된 작업의 다른 스타일을 비교할 때 고유 합니다. Durable Functions 시간 걸릴 수 있습니다 하거나 완료 하는 일도는 함수를 실행할 수 있습니다. 실행 중인 오케스트레이션의 상태를 확인 하는 일을 할 필요를 사용 하 여 먼저 종료를 하거나 외부 이벤트 알림을 보내도록 해당 유형의 동작에 제공 됩니다.

지 속성 함수 확장은 이러한 경우 다음을 제공 합니다.는 `DurableOrchestrationClient` 클래스와 상호 작용할 수 있도록 함수를 오케스트레이션 합니다. 사용 하 여 오케스트레이션 클라이언트에 대 한 액세스를 얻게 된 `OrchestrationClientAttribute` 바인딩. 일반적으로 포함이 특성이 다른 트리거 유형과 같은 `HttpTrigger` 또는 `ServiceBusTrigger`합니다. 원본 함수가 트리거되면 오케스트레이션 클라이언트는 오 케 스트레이 터 함수를 시작 하려면 사용할 수 있습니다.

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

### <a name="the-orchestrator-function"></a>오 케 스트레이 터 함수

해당 함수가 Azure Functions 표시에서 OrchestrationTriggerAttribute 사용 하 여 함수에 주석 지정으로 오 케 스트레이 터 함수를 합니다. 이 상태 저장 워크플로 구성 하는 다양 한 작업을 관리 하는 일을 담당 합니다.

오 케 스트레이 터 함수를 만들 수 없는 경우는 OrchestrationTriggerAttribute 아닌 바인딩을 사용 합니다. 이 특성 매개 변수 형식의 DurableOrchestrationContext만 사용할 수 있습니다. 다른 입력이 없는 함수 시그니처에서 입력의 deserialization 지원 되지 않으므로 사용할 수 있습니다. 오케스트레이션 클라이언트는 GetInput 제공한 입력을 가져오는\<T\> 메서드를 사용 해야 합니다.

또한 오케스트레이션 함수의 반환 형식 중 하나 여야 합니다 void, 작업 또는 JSON 직렬화 가능 값입니다.

> *간단한 설명을 위해 오류 처리 코드가 생략 했습니다.*

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

오케스트레이션의 여러 인스턴스가 동시에 실행 되 고 시작 수 있습니다. 호출을 `StartNewAsync` 메서드는 `DurableOrchestrationClient` 오케스트레이션의 새 인스턴스를 시작 합니다. 메서드는 반환을 `Task<string>` 오케스트레이션 시작 되었을 때 완료 합니다. 형식의 예외가 `TimeoutException` 오케스트레이션 30 초 이내 시작 되지 않은 경우 throw를 가져옵니다.

완료 된 `Task<string>` 에서 `StartNewAsync` 오케스트레이션 인스턴스의 고유 ID를 포함 해야 합니다. 해당 특정 오케스트레이션에 대 한 작업을 호출 하려면이 인스턴스 ID는 사용할 수 있습니다. 오케스트레이션 상태에 대 한 쿼리 또는 이벤트 알림을 받을 수 있습니다.

### <a name="the-activity-functions"></a>작업 함수

작업 함수는 워크플로를 만들려면 오케스트레이션 함수 내에서 함께 구성 되는 개별 작업입니다. 대부분의 실제 작업이 수행 됩니다 여기서는 다음과 같습니다. 장기 실행 중인 프로세스 및 더 큰 솔루션 퍼즐 조각을 비즈니스 논리를 나타내기 때문입니다.

합니다 `ActivityTriggerAttribute` 함수 매개 변수 형식의 주석을 추가 하는 데 사용 됩니다 `DurableActivityContext`합니다. 주석을 사용 하 여 함수는 작업 함수를 사용 하도록 런타임에 알립니다. 작업 함수 입력된 값은 사용해 서 검색 됩니다 합니다 `GetInput<T>` 메서드는 `DurableActivityContext` 매개 변수입니다.

비슷하게 오케스트레이션 함수 작업 함수의 반환 형식 중 하나 여야 합니다 void, 작업 또는 JSON 직렬화 가능 값입니다.

작업 함수 내에서 throw 된 처리 되지 않은 예외는 호출 하는 오 케 스트레이 터 함수에 전송 가져오고 표시는 `TaskFailedException`합니다. 이 시점에서 오류가 발견 되 고 오 케 스트레이 터, 로그인 및 작업을 다시 시도할 수 있습니다.

```csharp
[FunctionName("CheckAndReserveInventory")]
public static bool CheckAndReserveInventory([ActivityTrigger] DurableActivityContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    // Connect to inventory system and try to reserve items
    return true;
}
```

## <a name="recommended-resources"></a>권장 되는 리소스

* [지 속성 함수](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
* [지 속성 함수의 바인딩](https://docs.microsoft.com/azure/azure-functions/durable-functions-bindings)
* [지 속성 함수의 인스턴스 관리](https://docs.microsoft.com/azure/azure-functions/durable-functions-instance-management)

>[!div class="step-by-step"]
>[이전](event-grid.md)
>[다음](orchestration-patterns.md)
