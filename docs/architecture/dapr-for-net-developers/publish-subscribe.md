---
title: D Apr 게시 & 구독 구성 블록
description: 빌드 블록 구독 및이를 적용 하는 방법에 대 한 자세한 내용은 &
author: edwinvw
ms.date: 02/17/2021
ms.openlocfilehash: 11898430d897ec85b7e367fa0e93ca912279784b
ms.sourcegitcommit: d623f686701b94bef905ec5e93d8b55d031c5d6f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2021
ms.locfileid: "103623826"
---
# <a name="the-dapr-publish--subscribe-building-block"></a>D Apr 게시 & 구독 구성 블록

[게시-구독 패턴](/azure/architecture/patterns/publisher-subscriber) ("pub/sub" 라고도 함)은 잘 알려져 있고 널리 사용 되는 메시징 패턴입니다. 설계자는 일반적으로 분산 응용 프로그램에이를 수용 합니다. 그러나이를 구현 하는 것은 복잡할 수 있습니다. 여러 메시징 제품 간에 미묘한 기능 차이가 종종 있습니다. D p 4는 pub/sub 기능 구현을 크게 간소화 하는 빌딩 블록을 제공 합니다.

## <a name="what-it-solves"></a>해결 방법

Publish-Subscribe 패턴의 주요 이점은 **느슨한 결합** 이며, 때로는 [임시](/azure/architecture/guide/technology-choices/messaging#decoupling)분리 라고도 합니다. 메시지 ( **구독자**)를 사용 하는 서비스에서 메시지 ( **게시자**)를 전송 하는 서비스를 분리 하는 패턴입니다. 게시자와 구독자는 모두 서로를 인식 하지 못합니다. 둘 다 메시지를 배포 하는 중앙 집중식 **메시지 브로커** 에 종속 됩니다.

그림 7-1에는 pub/sub 패턴의 상위 수준 아키텍처가 나와 있습니다.

![Pub/sub 패턴](./media/publish-subscribe/pub-sub-pattern.png)

**그림 7-1**. Pub/sub 패턴입니다.

위의 그림에서 패턴의 단계를 확인 합니다.

1. 게시자는 메시지 브로커로 메시지를 보냅니다.
1. 구독자는 메시지 브로커의 구독에 바인딩합니다.
1. 메시지 broker는 메시지의 복사본을 관심이 있는 구독으로 전달 합니다.
1. 구독자는 구독에서 메시지를 사용 합니다.

대부분의 메시지 브로커는 받은 후 메시지를 유지할 수 있는 큐 메커니즘을 캡슐화 합니다. 이를 통해 메시지 broker는 메시지를 저장 하 여 **내구성** 을 보장 합니다. 게시자가 메시지를 보낼 때 구독자를 즉시 사용할 수 없거나 온라인 상태가 아니어도 됩니다. 구독자는 사용할 수 있게 되 면 메시지를 받고 처리 합니다.  D 4는 메시지 배달에 대 한 **최소 한 번** 의 의미 체계를 보장 합니다. 메시지를 게시 한 후에는 관심 있는 모든 구독자에 게 한 번 이상 배달 됩니다.

 > 서비스에서 메시지를 한 번만 처리할 수 있는 경우에는 [멱 등 성 검사](/azure/architecture/microservices/design/api-design#idempotent-operations) 를 제공 하 여 동일한 메시지가 여러 번 처리 되지 않도록 해야 합니다. 이러한 논리를 코딩할 수 있지만 Azure Service Bus와 같은 일부 메시지 브로커는 기본 제공 *중복 검색* 메시징 기능을 제공 합니다.

상용 및 오픈 소스 모두에서 사용할 수 있는 여러 가지 메시지 broker 제품이 있습니다. 각에는 장점과 단점이 있습니다. 사용자의 작업은 적절 한 broker에 시스템 요구 사항을 일치 시키는 것입니다. 선택한 후에는 메시지 브로커에서 응용 프로그램을 분리 하는 것이 가장 좋습니다. *추상화* 내에 broker를 래핑하여이 기능을 달성할 수 있습니다. 추상화는 메시지를 캡슐화 하 고 일반 pub/sub 작업을 코드에 노출 합니다. 코드는 실제 메시지 브로커가 아닌 추상화와 통신 합니다. 의사 결정을 내릴 때 추상화 및 해당 기본 구현을 작성 하 고 유지 관리 해야 합니다. 이 방법에는 복잡 하 고 반복적 이며 오류가 발생할 수 있는 사용자 지정 코드가 필요 합니다.

D Apr 게시 & 구독 빌딩 블록은 메시징 추상화 및 구현을 제공 합니다. 작성 해야 하는 사용자 지정 코드는 미리 빌드된 후에는 Eapr 빌딩 블록 내에 캡슐화 됩니다. 이를 바인딩하고 사용 합니다. 메시징 배관 코드를 작성 하는 대신 사용자와 팀은 고객에 게 가치를 더하는 비즈니스 기능을 만드는 데 주력 합니다.

## <a name="how-it-works"></a>작동 방식

D Apr 게시 & 구독 구성 요소는 메시지를 보내고 받기 위한 플랫폼 독립적인 API 프레임 워크를 제공 합니다. 서비스는 명명 된 [항목](/azure/service-bus-messaging/service-bus-queues-topics-subscriptions#topics-and-subscriptions)에 메시지를 게시 합니다. 서비스는 항목을 구독 하 여 메시지를 사용 합니다.

서비스는 사이드카에서 pub/sub API를 호출 합니다. 그런 다음 사이드카은 특정 메시지 브로커 제품을 캡슐화 하는 미리 정의 된 Eapr pub/sub 구성 요소에 대 한 호출을 수행 합니다. 그림 7-2에서는 4 월 pub/sub 메시징 스택을 보여 줍니다.

![Pub/sub stack](./media/publish-subscribe/pub-sub-buildingblock.png)

**그림 7-2**. 6Apr pub/sub 스택입니다.

여러 가지 방법으로 4 월 게시 & 구독 빌딩 블록을 호출할 수 있습니다.

가장 낮은 수준에서 모든 프로그래밍 플랫폼은 **NATIVE API** 를 사용 하 여 HTTP 또는 grpc를 통해 빌딩 블록을 호출할 수 있습니다. 메시지를 게시 하려면 다음 API 호출을 수행 합니다.

``` http
http://localhost:<dapr-port>/v1.0/publish/<pub-sub-name>/<topic>
```

위의 호출에는 몇 가지 다양 한 4 가지 특정 URL 세그먼트가 있습니다.

- `<dapr-port>` 은 (는) 사이드카에서 수신 대기 하는 포트 번호를 제공 합니다.
- `<pub-sub-name>` 선택한 Wapr pub/sub 구성 요소의 이름을 제공 합니다.
- `<topic>` 메시지를 게시할 토픽의 이름을 제공 합니다.

*말아* 명령줄 도구를 사용 하 여 메시지를 게시 하면 다음과 같은 작업을 수행해 볼 수 있습니다.

``` curl
curl -X POST http://localhost:3500/v1.0/publish/pubsub/newOrder \
  -H "Content-Type: application/json" \
  -d '{ "orderId": "1234", "productId": "5678", "amount": 2 }'
```

항목을 구독 하 여 메시지를 받습니다. 시작 시에는 필요한 구독을 식별 하 고 만들기 위해 잘 알려진 끝점에서 응용 프로그램을 호출 합니다.

``` http
http://localhost:<appPort>/dapr/subscribe
```

- `<appPort>` 응용 프로그램이 수신 대기 하는 포트의 사이드카를에 알립니다.

이 끝점을 직접 구현할 수 있습니다. 그러나 Eapr는 보다 직관적인 방법을 제공 합니다. 이 기능은이 장의 뒷부분에서 다룹니다.

호출의 응답에는 응용 프로그램에서 구독할 항목의 목록이 포함 됩니다. 각에는 토픽에서 메시지를 받을 때 호출할 끝점이 포함 되어 있습니다. 응답의 예는 다음과 같습니다.

```json
[
  {
    "pubsubname": "pubsub",
    "topic": "newOrder",
    "route": "/orders"
  },
  {
    "pubsubname": "pubsub",
    "topic": "newProduct",
    "route": "/productCatalog/products"
  }
]
```

JSON 응답에서 응용 프로그램이 항목 및를 구독 하려고 하는 것을 볼 수 있습니다 `newOrder` `newProduct` . 각각에 대해 끝점과를 등록 `/orders` `/productCatalog/products` 합니다. 두 구독 모두에 대해 응용 프로그램은 이름이 인 Eapr 구성 요소에 바인딩합니다 `pubsub` .

그림 7-3에서는 예제의 흐름을 보여 줍니다.

![예: d 4를 사용 하 여 pub/sub flow](media/publish-subscribe/pub-sub-flow.png)

**그림 7-3**. t 4를 사용 하는 pub/sub flow.

위의 그림에서 흐름을 확인 합니다.

1. Service B에 대 한 Bapr 사이드카는 `/dapr/subscribe` 서비스 b (소비자)에서 끝점을 호출 합니다. 서비스는 만들려는 구독을 사용 하 여 응답 합니다.
1. Service B의 Bapr 사이드카는 메시지 브로커에 요청 된 구독을 만듭니다.
1. 서비스 A는 사이드카 서비스의 끝점에서 메시지를 게시 `/v1.0/publish/<pub-sub-name>/<topic>` 합니다.
1. 사이드카 서비스는 메시지를 메시지 브로커에 게시 합니다.
1. 메시지 브로커가 Service B 사이드카 메시지의 복사본을 보냅니다.
1. 서비스 B 사이드카는 서비스 B의 구독 (이 경우)에 해당 하는 끝점을 호출 합니다 `/orders` . 서비스는 HTTP 상태 코드를 사용 하 여 응답 `200 OK` 하므로 사이드카은 메시지를 처리 하는 것으로 간주 합니다.

이 예제에서는 메시지가 성공적으로 처리 됩니다. 하지만 Service B에서 요청을 처리 하는 동안 문제가 발생 하면 응답을 사용 하 여 메시지에 대해 수행할 작업을 지정할 수 있습니다. HTTP 상태 코드를 반환 하면 `404` 오류가 기록 되 고 메시지가 삭제 됩니다. 또는 이외의 다른 상태 코드를 사용 하 여 `200` `404` 경고를 기록 하 고 메시지를 다시 시도 합니다. 또는 서비스 B는 응답 본문에 JSON 페이로드를 포함 하 여 메시지에 대해 수행 해야 하는 작업을 명시적으로 지정할 수 있습니다.

```json
{
  "status": "<status>"
}
```

다음 표에서는 사용 가능한 값을 보여 줍니다 `status` .

| 상태           | 작업                                                       |
| ---------------- | ------------------------------------------------------------ |
| SUCCESS          | 메시지는 성공적으로 처리 되 고 삭제 된 것으로 간주 됩니다. |
| 다시 시도            | 메시지를 다시 시도 합니다.                                      |
| DROP             | 경고가 기록 되 고 메시지가 삭제 됩니다.              |
| 기타 모든 상태 | 메시지를 다시 시도 합니다.                                      |

### <a name="competing-consumers"></a>경쟁 소비자

토픽을 구독 하는 응용 프로그램을 확장 하는 경우 경쟁 소비자를 처리 해야 합니다. 하나의 응용 프로그램 인스턴스만 토픽에 전송 된 메시지를 처리 해야 합니다. 다행히 4는 이러한 문제를 처리 합니다. 동일한 응용 프로그램 id를 사용 하는 서비스의 여러 인스턴스가 토픽을 구독할 경우, d 4는 각 메시지를 하나에만 배달 합니다.

### <a name="sdks"></a>SDK

네이티브 기본 Api에 대 한 HTTP 호출을 수행 하는 것은 시간이 많이 걸리고 추상적입니다. 호출은 HTTP 수준에서 제공 되므로 serialization 및 HTTP 응답 코드와 같은 배관 문제를 처리 해야 합니다. 다행히 직관적인 방법이 있습니다. D 4는 인기 있는 개발 플랫폼에 대 한 몇 가지 언어별 Sdk를 제공 합니다. 이 문서를 작성할 당시에는 Go, Node.js, Python, .NET, Java 및 JavaScript를 사용할 수 있습니다.

## <a name="use-the-dapr-net-sdk"></a>Dapr .NET SDK 사용

.NET 개발자를 위해 [dapr .NET SDK](https://www.nuget.org/packages/Dapr.Client) 는 dapr를 사용 하는 보다 생산적인 방법을 제공 합니다. SDK는 `DaprClient` Dapr 기능을 직접 호출할 수 있는 클래스를 노출 합니다. 직관적이 고 사용 하기 쉽습니다.

메시지를 게시 하기 위해는 `DaprClient` 메서드를 노출 `PublishEventAsync` 합니다.

```csharp
var data = new OrderData
{
  orderId = "123456",
  productId = "67890",
  amount = 2
};

var daprClient = new DaprClientBuilder().Build();

await daprClient.PublishEventAsync<OrderData>("pubsub", "newOrder", data);
```

- 첫 번째 인수는 `pubsub` 메시지 브로커 구현을 제공 하는 Eapr 구성 요소의 이름입니다. 구성 요소에 대해서는이 챕터의 뒷부분에서 다룹니다.
- 두 번째 인수는 `neworder` 메시지를 보낼 토픽의 이름을 제공 합니다.
- 세 번째 인수는 메시지의 페이로드입니다.
- 메서드의 제네릭 형식 매개 변수를 사용 하 여 .NET 형식의 메시지를 지정할 수 있습니다.

메시지를 수신 하려면 등록 된 항목에 대해 끝점을 구독에 바인딩합니다. AspNetCore library for Eapr를 사용 하면이를 편리 하 게 사용할 수 있습니다. 예를 들어 기존 ASP.NET WebAPI action 메서드가 있다고 가정 합니다 `CreateOrder` .

```csharp
[HttpPost("/orders")]
public async Task<ActionResult> CreateOrder(Order order)
```

 > [AspNetCore](https://www.nuget.org/packages/Dapr.AspNetCore) NuGet 패키지에 대 한 참조를 프로젝트에 추가 하 여 eapr ASP.NET Core 통합을 사용 해야 합니다.

이 작업 메서드를 토픽에 바인딩하려면 특성을 사용 하 여 데코 레이트 합니다 `Topic` .

```csharp
[Topic("pubsub", "newOrder")]
[HttpPost("/orders")]
public async Task<ActionResult> CreateOrder(Order order)
```

이 특성을 사용 하 여 두 가지 주요 요소를 지정 합니다.

- 대상으로 할 수 있는 (이 경우)에 해당 하는 d 4의 pub/sub 구성 요소 `pubsub` 입니다.
- 구독할 항목입니다 (이 경우 `newOrder` ).

그런 다음 해당 항목에 대 한 메시지를 받을 때 해당 작업 메서드를 호출 합니다.

또한 ASP.NET Core를 사용 하도록 설정 하 여 Eapr를 사용 해야 합니다. Dapr .NET SDK는 클래스에서 호출할 수 있는 몇 가지 확장 메서드를 제공 합니다 `Startup` .

`ConfigureServices`메서드에서 다음 확장 메서드를 추가 해야 합니다.

```csharp
public void ConfigureServices(IServiceCollection services)
{
    // ...
    services.AddControllers().AddDapr();
}
```

확장 메서드에 확장 메서드를 추가 하면 `AddDapr` `AddControllers` 필요한 서비스를 등록 하 여 MVC 파이프라인에 6apr를 통합 합니다. 또한 `DaprClient` 인스턴스를 종속성 주입 컨테이너에 등록 하 고이를 서비스에 삽입할 수 있습니다.

`Configure`메서드에서 다음 미들웨어 구성 요소를 추가 하 여 d 4를 사용 하도록 설정 해야 합니다.

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    // ...
    app.UseCloudEvents();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapSubscribeHandler();
        // ...
    });
}
```

에 대 한 `UseCloudEvents` 호출은 **CloudEvents** 미들웨어를 ASP.NET Core 미들웨어 파이프라인에 추가 합니다. 이 미들웨어는 CloudEvents 구조화 된 형식을 사용 하는 요청을 래핑 해제 하므로 수신 메서드에서 이벤트 페이로드를 직접 읽을 수 있습니다.

> [CloudEvents](https://cloudevents.io/) 는 표준화 된 메시징 형식으로, 플랫폼 간 이벤트 정보를 설명 하는 일반적인 방법을 제공 합니다. CloudEvents을 채택 합니다. CloudEvents에 대 한 자세한 내용은 [CloudEvents 사양](https://github.com/cloudevents/spec/tree/v1.0)을 참조 하십시오.

`MapSubscribeHandler`끝점 라우팅 구성에서를 호출 하면 응용 프로그램에 대 한 4 월 구독 끝점이 추가 됩니다. 이 끝점은에 대 한 요청에 응답 `/dapr/subscribe` 합니다. 이 끝점을 호출 하면 특성을 사용 하 여 데코레이팅된 모든 WebAPI 작업 메서드가 자동으로 검색 되 `Topic` 고,이에 대 한 구독을 만들도록 요청 합니다.

## <a name="pubsub-components"></a>Pub/sub 구성 요소

이 경우에는 메시지의 실제 전송을 처리 하는 4 개의 [pub/sub 구성 요소](https://github.com/dapr/components-contrib/tree/master/pubsub) 몇 가지를 사용할 수 있습니다. 각는 pub/sub 기능을 구현 하기 위해 특정 메시지 브로커 제품을 캡슐화 합니다. 작성 시 다음 pub/sub 구성 요소를 사용할 수 있습니다.

- Apache Kafka
- Azure Event Hubs
- Azure Service Bus
- AWS SNS/SQS
- GCP Pub/Sub
- Hazelcast
- MQTT
- NAT
- Pulsar
- RabbitMQ
- Redis 스트림

> [!NOTE]
> Azure cloud stack에는 메시징 기능 (Azure Service Bus) 및 이벤트 스트리밍 (Azure Event Hub) 가용성이 모두 있습니다.

이러한 구성 요소는 [GitHub의 구성 요소-참여 저장소](https://github.com/dapr/components-contrib/tree/master/pubsub)에서 커뮤니티에 의해 만들어집니다. 아직 지원 되지 않는 메시지 브로커에 대 한 사용자 고유의 Bapr 구성 요소를 작성 하는 것이 좋습니다.

### <a name="configure-pubsub-components"></a>Pub/sub 구성 요소 구성

Eapr 구성 파일을 사용 하 여 사용할 pub/sub 구성 요소를 지정할 수 있습니다. 이 구성에는 여러 필드가 포함 되어 있습니다. `name`필드는 사용 하려는 pub/sub 구성 요소를 지정 합니다. 메시지를 보내거나 받을 때이 이름을 지정 해야 합니다 (앞에서 설명한 것 처럼 `PublishEventAsync` 메서드 시그니처에서).

아래에 RabbitMQ message broker 구성 요소를 구성 하는 데 사용할 수 있는 4 가지 구성 파일의 예가 나와 있습니다.

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: pubsub-rq
spec:
  type: pubsub.rabbitmq
  version: v1
  metadata:
  - name: host
    value: "amqp://localhost:5672"
  - name: durable
    value: true
```

이 예제에서는 블록에서 메시지 broker 관련 구성을 지정할 수 있는 것을 볼 수 있습니다 `metadata` . 이 경우 RabbitMQ는 영 속 큐를 만들도록 구성 됩니다. 그러나 RabbitMQ 구성 요소에는 더 많은 구성 옵션이 있습니다. 각 구성 요소의 구성에는 가능한 필드의 고유한 집합이 있습니다. 각 [pub/sub 구성 요소의](https://docs.dapr.io/operations/components/setup-pubsub/supported-pubsub/)설명서에서 사용할 수 있는 필드를 읽을 수 있습니다.

코드에서 토픽을 구독 하는 프로그래밍 방식 옆의 경우에는 항목을 구독 하는 선언적 방법도 제공 합니다. 이 방법은 응용 프로그램 코드에서 Aapr 종속성을 제거 합니다. 따라서 기존 응용 프로그램은 코드를 변경 하지 않고 토픽을 구독할 수도 있습니다. 다음 예에서는 구독을 구성 하기 위한 4Apr 구성 파일을 보여 줍니다.

```yaml
apiVersion: dapr.io/v1alpha1
kind: Subscription
metadata:
  name: newOrder-subscription
spec:
  pubsubname: pubsub
  topic: newOrder
  route: /orders
scopes:
- ServiceB
- ServiceC
```

모든 구독에서 여러 요소를 지정 해야 합니다.

- 사용할 수 있는 (이 경우)에 해당 하는 d 4의 pub/sub 구성 요소의 이름 `pubsub` 입니다.
- 구독할 항목의 이름입니다 (이 경우 `newOrder` ).
- 이 항목에 대해 호출 해야 하는 API 작업입니다 (이 경우 `/orders` ).
- [범위](https://docs.dapr.io/developing-applications/building-blocks/pubsub/pubsub-scopes/) 는 토픽을 게시 하 고 구독할 수 있는 서비스를 지정할 수 있습니다.

## <a name="reference-application-eshopondapr"></a>참조 응용 프로그램: eShopOnDapr

함께 제공 되는 [eShopOnDapr](https://github.com/dotnet-architecture/eShopOnDapr) 앱은 4apr를 구현 하는 마이크로 서비스 응용 프로그램을 생성 하는 종단 간 참조 아키텍처를 제공 합니다. eShopOnDapr은 몇 년 전에 만들어진 널리 사용 되는 [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) 앱의 진화입니다. 두 버전 모두 마이크로 서비스에서 [통합 이벤트](https://devblogs.microsoft.com/cesardelatorre/domain-events-vs-integration-events-in-domain-driven-design-and-microservices-architectures/#integration-events) 를 전달 하기 위해 pub/sub 패턴을 사용 합니다. 통합 이벤트는 다음과 같습니다.

- 사용자가 쇼핑 바구니를 체크 아웃 하는 경우
- 주문에 대 한 지불에 성공한 경우
- 구매 유예 기간이 만료 된 경우

EShopOnContainers의 이벤트는 다음 인터페이스를 기반으로 합니다 `IEventBus` .

```csharp
public interface IEventBus
{
    void Publish(IntegrationEvent integrationEvent);

    void Subscribe<T, THandler>()
        where TEvent : IntegrationEvent
        where THandler : IIntegrationEventHandler<T>;
}
```

이 인터페이스의 구체적 구현은 RabbitMQ 및 Azure Service Bus에 대해 eShopOnContainers에 있습니다. 각 구현에는 이해 하기 어렵고 유지 관리가 어려운 많은 사용자 지정 배관 코드가 포함 되었습니다.

최신 eShopOnDapr는 i 4를 사용 하 여 pub/sub 동작을 크게 간소화 합니다. 예를 들어 `IEventBus` 인터페이스는 단일 메서드로 줄었습니다.

```csharp
public interface IEventBus
{
    Task PublishAsync(IntegrationEvent integrationEvent);
}
```

### <a name="publish-events"></a>이벤트 게시

업데이트 된 eShopOnDapr에서 단일 구현에서는 `DaprEventBus` 모든 지원 메시지 broker를 지원할 수 있습니다. 다음 코드 블록은 단순화 된 Publish 메서드를 보여 줍니다. `PublishAsync`메서드가 Capr 클라이언트를 사용 하 여 이벤트를 게시 하는 방법에 유의 하십시오.

```csharp
public class DaprEventBus : IEventBus
{
    private const string PubSubName = "pubsub";

    private readonly DaprClient _daprClient;
    private readonly ILogger<DaprEventBus> _logger;

    public DaprEventBus(DaprClient daprClient, ILogger<DaprEventBus> logger)
    {
        _daprClient = daprClient ?? throw new ArgumentNullException(nameof(daprClient));
        _logger = logger ?? throw new ArgumentNullException(nameof(logger));
    }

    public async Task PublishAsync(IntegrationEvent integrationEvent)
    {
        var topicName = integrationEvent.GetType().Name;

        // Dapr uses System.Text.Json which does not support serialization of a
        // polymorphic type hierarchy by default. Using object as the type
        // parameter causes all properties to be serialized.
        await _daprClient.PublishEventAsync<object>(PubSubName, topicName, integrationEvent);
    }
}
```

코드 조각에서 볼 수 있듯이 토픽 이름은 이벤트 형식의 이름에서 파생 됩니다. 모든 eShop 서비스는 추상화를 사용 하기 때문에 중요 `IEventBus` 한 응용 프로그램 코드를 *변경 하지* 않아도 되는 수정 따라.

> [!IMPORTANT]
> Dapr SDK는를 사용 하 여 `System.Text.Json` 메시지를 serialize/deserialize 합니다. 그러나에서는 `System.Text.Json` 기본적으로 파생 클래스의 속성을 serialize 하지 않습니다. EShop 코드에서 이벤트는 종종 `IntegrationEvent` 통합 이벤트의 기본 클래스인로 명시적으로 선언 됩니다. 이러한 작업은 구체적 이벤트 유형이 비즈니스 논리에 따라 런타임에 동적으로 결정 되기 때문에 수행 됩니다. 결과적으로 이벤트는 파생 클래스가 아닌 기본 클래스의 형식 정보를 사용 하 여 serialize 됩니다. `System.Text.Json`이 경우 파생 클래스의 모든 속성을 강제로 serialize 하려면 코드에서를 `object` 제네릭 형식 매개 변수로 사용 합니다. 자세한 내용은 [.net 설명서](../../standard/serialization/system-text-json-polymorphism.md)를 참조 하십시오.

D 4를 사용 하 여 인프라 코드를 **크게 간소화할** 수 있습니다. 서로 다른 메시지 브로커를 구분할 필요가 없습니다. 이 추상화는 d 4에서 제공 됩니다. 필요한 경우 메시지 브로커를 쉽게 교환 하거나 여러 메시지 브로커 구성 요소를 구성할 수 있습니다.

### <a name="subscribe-to-events"></a>이벤트 구독

이전 eShopOnContainers 앱에는 각 메시지 브로커에 대 한 구독 구현을 처리 하는 *subscriptionmanagers* 가 포함 되어 있습니다. 각 관리자는 구독 이벤트를 처리 하기 위한 복잡 한 메시지 브로커 관련 코드를 포함 합니다. 이벤트를 수신 하려면 각 서비스에서 각 이벤트 형식에 대해 명시적으로 처리기를 등록 해야 합니다.

eShopOnDapr는 ASP.NET Core 라이브러리를 사용 하 여 이벤트 구독을 위한 통로를 간소화 합니다. 각 이벤트는 컨트롤러의 동작 메서드에서 처리 됩니다. `Topic`특성은 작업 메서드를 구독할 해당 항목의 이름으로 데코 레이트 합니다. 에서 가져온 코드 조각은 `PaymentService` 다음과 같습니다.

```csharp
[Route("api/v1/[controller]")]
[ApiController]
public class IntegrationEventController : ControllerBase
{
    private const string DAPR_PUBSUB_NAME = "pubsub";

    private readonly IServiceProvider _serviceProvider;

    public IntegrationEventController(IServiceProvider serviceProvider)
    {
        _serviceProvider = serviceProvider;
    }

    [HttpPost("OrderStatusChangedToValidated")]
    [Topic(DAPR_PUBSUB_NAME, "OrderStatusChangedToValidatedIntegrationEvent")]
    public async Task OrderStarted(OrderStatusChangedToValidatedIntegrationEvent integrationEvent)
    {
        var handler = _serviceProvider.GetRequiredService<OrderStatusChangedToValidatedIntegrationEventHandler>();
        await handler.Handle(integrationEvent);
    }
}
```

특성에서 `Topic` 이벤트의 .net 형식 이름이 토픽 이름으로 사용 됩니다. 이벤트를 처리 하기 위해 이전 eShopOnContainers 코드 베이스에 이미 있던 이벤트 처리기가 호출 됩니다. 이전 예제에서 토픽 으로부터 받은 메시지는 `OrderStatusChangedToValidatedIntegrationEvent` 기존 이벤트 처리기를 호출 합니다 `OrderStatusChangedToValidatedIntegrationEventHandler` . D 4에서 구독 및 메시지 브로커에 대 한 기본 시작을 구현 하므로 많은 양의 원본 코드가 사용 되지 않고 코드 베이스에서 제거 되었습니다. 이 코드의 대부분은 이해 하 고 유지 관리 하기 어렵습니다.

### <a name="use-pubsub-components"></a>Pub/sub 구성 요소 사용

EShopOnDapr 리포지토리 내에서 폴더는 `deployment` 및의 다양 한 배포 모드를 사용 하 여 응용 프로그램을 배포 하기 위한 파일을 포함 `Docker Compose` `Kubernetes` 합니다. 폴더는 폴더를 `dapr` 포함 하는 이러한 각 폴더 내에 있습니다 `components` . 이 폴더에는 `eshop-pubsub.yaml` 응용 프로그램이 pub/sub 동작에 사용할 수 있도록 하는 Eapr pub/sub 구성 요소의 구성이 포함 된 파일이 저장 됩니다. 앞의 코드 조각에서 살펴본 것 처럼 사용 되는 pub/sub 구성 요소의 이름은 `pubsub` 입니다. `eshop-pubsub.yaml`폴더에 있는 파일의 내용은 `deployment/compose/dapr/components` 다음과 같습니다.

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: pubsub
  namespace: default
spec:
  type: pubsub.nats
  version: v1
  metadata:
  - name: natsURL
    value: nats://demo.nats.io:4222
```

위의 구성은이 예에 대 한 원하는 [nat 메시지 브로커](https://nats.io/) 를 지정 합니다. 메시지 브로커를 변경 하려면 RabbitMQ 또는 Azure Service Bus와 같은 다른 메시지 브로커를 구성 하 고 yaml 파일을 업데이트 하기만 하면 됩니다. D 4를 사용 하면 메시지 브로커를 전환할 때 중요 하지 않은 서비스 코드가 변경 되지 않습니다.

마지막으로 "응용 프로그램에서 여러 메시지 broker가 필요한 이유는 무엇 인가요?" 라는 메시지가 표시 될 수 있습니다. 시스템이 서로 다른 특성을 가진 워크 로드를 처리 하는 경우가 많습니다. 한 이벤트는 하루에 한 번만 발생 하지만 또 다른 이벤트는 초당 5000 회 발생 합니다. 메시징 트래픽을 다른 메시지 브로커로 분할 하면 이점을 누릴 수 있습니다. Eapr를 사용 하면 각각 다른 이름을 가진 여러 pub/sub 구성 요소 구성을 추가할 수 있습니다.

## <a name="summary"></a>요약

Pub/sub 패턴을 사용 하면 분산 응용 프로그램에서 서비스를 분리할 수 있습니다. 응용 프로그램에서이 동작을 구현 하는 과정을 간소화 하는 & 구독 빌딩 블록을 만듭니다.

이 경우에는 특정 *토픽* 에 메시지를 게시할 수 있습니다. 또한 빌딩 블록은 서비스를 쿼리하여 구독할 항목을 결정 합니다.

HTTP를 통해 또는 Dapr 용 .NET SDK와 같은 언어별 Sdk 중 하나를 사용 하 여 Dapr pub/sub를 기본적으로 사용할 수 있습니다. .NET SDK는 ASP.NET core 플랫폼과 긴밀 하 게 통합 됩니다.

Eapr를 사용 하면 지원 되는 메시지 브로커 제품을 응용 프로그램에 연결할 수 있습니다. 그런 다음 응용 프로그램에 코드를 변경할 필요 없이 메시지 브로커를 교환할 수 있습니다.

> [!div class="step-by-step"]
> [이전](service-invocation.md)
> [다음](bindings.md)
