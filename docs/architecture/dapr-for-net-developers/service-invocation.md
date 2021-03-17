---
title: 6Apr 서비스 호출 빌딩 블록
description: 서비스 호출 빌딩 블록에 대 한 설명, 해당 기능, 이점 및 적용 방법
author: amolenk
ms.date: 02/17/2021
ms.openlocfilehash: f6d5f10ae476d85a9925c4fa387a16d575cacf6a
ms.sourcegitcommit: d623f686701b94bef905ec5e93d8b55d031c5d6f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2021
ms.locfileid: "103624099"
---
# <a name="the-dapr-service-invocation-building-block"></a>6Apr 서비스 호출 빌딩 블록

분산 시스템에서 한 서비스는 비즈니스 작업을 완료 하기 위해 다른 서비스와 통신 해야 하는 경우가 많습니다. [6Apr 서비스 호출 빌딩 블록](https://docs.dapr.io/developing-applications/building-blocks/service-invocation/service-invocation-overview/) 은 서비스 간 통신을 간소화 하는 데 도움이 됩니다.

## <a name="what-it-solves"></a>해결 방법

분산 응용 프로그램에서 서비스 간의 호출은 쉽게 나타날 수 있지만 관련 된 많은 과제가 있습니다. 예를 들어:

- 다른 서비스를 찾을 수 있습니다.
- 서비스 주소를 지정 하 여 서비스를 안전 하 게 호출 하는 방법입니다.
- 단기 [일시적인 오류가](/aspnet/aspnet/overview/developing-apps-with-windows-azure/building-real-world-cloud-apps-with-windows-azure/transient-fault-handling) 발생할 경우 재시도를 처리 하는 방법입니다.

마지막으로, 분산 응용 프로그램에서 다양 한 서비스를 작성할 때 서비스 호출 그래프를 통해 정보를 캡처하는 것은 프로덕션 문제를 진단 하는 데 중요 합니다.

서비스 호출 빌딩 블록은 서비스에 대 한 [역방향 프록시로](https://kemptechnologies.com/reverse-proxy/reverse-proxy/) 서 사이드카를 사용 하 여 이러한 문제를 해결 합니다.

## <a name="how-it-works"></a>작동 방식

예부터 살펴보겠습니다. "서비스 A"와 "Service B"의 두 가지 서비스를 고려 합니다. 서비스 A는 `catalog/items` 서비스 B에서 API를 호출 해야 합니다. 서비스 A는 서비스 B에 대 한 종속성을 사용 하 고이에 대 한 직접 호출을 수행할 수 있지만, 서비스 A는 대신 사이드카에서 서비스 호출 API를 호출 합니다. 그림 6-1은 작업을 보여 줍니다.

![Eapr 서비스 호출 작동 방법](./media/service-invocation/service-invocation-flow.png)

**그림 6-1**. Eapr 서비스 호출의 작동 방식입니다.

위의 그림에서 설명 하는 단계를 확인 합니다.

1. 서비스 A는 `catalog/items` 사이드카 서비스에서 서비스 호출 API를 호출 하 여 서비스 B의 끝점에 대 한 호출을 수행 합니다.

    > [!NOTE]
    > 사이드카는 플러그형 이름 확인 메커니즘을 사용 하 여 서비스 B의 주소를 확인 합니다. 자체 호스팅 모드에서는 [mdn](https://www.ionos.com/digitalguide/server/know-how/multicast-dns/) 를 사용 하 여이를 찾습니다. Kubernetes 모드로 실행 되는 경우 Kubernetes DNS 서비스는 주소를 결정 합니다.  

1. 사이드카 서비스는 서비스 B 사이드카에 요청을 전달 합니다.

1. Service B 사이드카는 `catalog/items` Service b API에 대 한 실제 요청을 수행 합니다.

1. 서비스 B가 요청을 실행 하 고 사이드카 응답을 다시 반환 합니다.

1. 서비스 B 사이드카는 응답을 서비스 A 사이드카로 다시 전달 합니다.

1. 사이드카 서비스는 다시 서비스 A에 대 한 응답을 반환 합니다.

호출이 사이드카을 통해 전달 되기 때문에는 다음과 같은 몇 가지 유용한 교차 잘라내기 동작을 삽입할 수 있습니다.

- 오류 발생 시 자동으로 호출을 다시 시도 합니다.
- 자동 인증서 롤오버를 비롯 한 상호 (mTLS) 인증을 사용 하 여 서비스를 안전 하 게 호출 합니다.
- 클라이언트에서 액세스 제어 정책을 사용 하 여 수행할 수 있는 작업을 제어 합니다.
- 서비스 간의 모든 호출에 대 한 추적 및 메트릭을 캡처하여 정보 및 진단을 제공 합니다.

모든 응용 프로그램은 사이드카에 기본 제공 되는 네이티브 **호출** API를 사용 하 여 d 4 월을 호출할 수 있습니다. API는 HTTP 또는 gRPC를 사용 하 여 호출할 수 있습니다. 다음 URL을 사용 하 여 HTTP API를 호출 합니다.

``` http
http://localhost:<dapr-port>/v1.0/invoke/<application-id>/method/<method-name>
```

- `<dapr-port>` d 4에서 수신 대기 하는 HTTP 포트입니다.
- `<application-id>` 호출할 서비스의 응용 프로그램 ID입니다.
- `<method-name>` 원격 서비스에서 호출할 메서드의 이름입니다.

다음 예제에서는  `catalog/items` 의 ' GET ' 끝점을 호출 합니다 `Service B` .

```console
curl http://localhost:3500/v1.0/invoke/serviceb/method/catalog/items
```

> [!NOTE]
> Eapr Api를 사용 하면 HTTP 또는 gRPC를 지 원하는 모든 응용 프로그램 스택에서 4Apr 빌딩 블록을 사용할 수 있습니다. 따라서 서비스 호출 빌딩 블록은 프로토콜 간의 다리 역할을 할 수 있습니다. 서비스는 HTTP, gRPC 또는 둘의 조합을 사용 하 여 서로 통신할 수 있습니다.

다음 섹션에서는 .NET SDK를 사용 하 여 서비스 호출을 간소화 하는 방법을 배웁니다.

## <a name="use-the-dapr-net-sdk"></a>Dapr .NET SDK 사용

Dapr [.NET SDK](https://github.com/dapr/dotnet-sdk) 는 .net 개발자에 게 dapr와 상호 작용 하는 직관적이 고 언어별 방법을 제공 합니다. SDK는 개발자에 게 원격 서비스 호출을 호출 하는 세 가지 방법을 제공 합니다.

1. HttpClient를 사용 하 여 HTTP 서비스 호출
1. DaprClient를 사용 하 여 HTTP 서비스 호출
1. DaprClient를 사용 하 여 gRPC 서비스 호출

### <a name="invoke-http-services-using-httpclient"></a>HttpClient를 사용 하 여 HTTP 서비스 호출

HTTP 끝점을 호출 하는 기본 방법은와 함께 Fapr의 다양 한 통합을 사용 하는 것입니다 `HttpClient` . 다음 예제에서는 `submit` 응용 프로그램의 메서드를 호출 하 여 주문을 전송 합니다 `orderservice` .

```csharp
var httpClient = DaprClient.CreateHttpClient();
await httpClient.PostAsJsonAsync("http://orderservice/submit", order);
```

이 예에서는를 `DaprClient.CreateHttpClient` 반환 하는 데 사용 되는 인스턴스를 반환 `HttpClient` 합니다. 반환 되는는 `HttpClient` 나가는 요청의 uri를 다시 작성 하는 특수 한 4Apr 메시지 처리기를 사용 합니다. 호스트 이름은 호출할 서비스의 응용 프로그램 ID로 해석 됩니다. 실제로 호출 되는 다시 작성 된 요청은 다음과 같습니다.

```http
http://127.0.0.1:3500/v1/invoke/orderservice/method/submit
```

이 예제에서는의 기본 값을 사용 `http://127.0.0.1:<dapr-http-port>/` 합니다. 의 값은 `dapr-http-port` 환경 변수에서 가져옵니다 `DAPR_HTTP_PORT` . 설정 되지 않은 경우 기본 포트 번호가 `3500` 사용 됩니다.

또는에 대 한 호출에서 사용자 지정 끝점을 구성할 수 있습니다 `DaprClient.CreateHttpClient` .

```csharp
var httpClient = DaprClient.CreateHttpClient(daprEndpoint = "localhost:4000");
```

응용 프로그램 ID를 지정 하 여 기본 주소를 직접 설정할 수도 있습니다. 이렇게 하면를 호출할 때 상대 Uri를 사용할 수 있습니다.

```csharp
var httpClient = DaprClient.CreateHttpClient("orderservice");
await httpClient.PostAsJsonAsync("/submit");
```

`HttpClient`개체는 수명이 긴 것으로 예상 됩니다. `HttpClient`응용 프로그램의 수명 동안 단일 인스턴스를 다시 사용할 수 있습니다. 다음 시나리오에서는 `OrderServiceClient` 클래스가 Eapr 인스턴스를 재사용 하는 방법을 보여 줍니다 `HttpClient` .  

```csharp
public void ConfigureServices(IServiceCollection services)
{
    // ...
    services.AddSingleton<IOrderServiceClient, OrderServiceClient>(
        _ => new OrderServiceClient(DaprClient.CreateInvokeHttpClient("orderservice")));
}
```

위의 코드 조각에서는 `OrderServiceClient` ASP.NET Core 종속성 주입 시스템을 사용 하 여 singleton으로 등록 됩니다. 구현 팩터리는를 `HttpClient` 호출 하 여 새 인스턴스를 만듭니다 `DaprClient.CreateInvokeHttpClient` . 그런 다음 새로 만든을 사용 하 여 `HttpClient` 개체를 인스턴스화합니다 `OrderServiceClient` . 를 `OrderServiceClient` singleton으로 등록 하면 응용 프로그램의 수명 동안 다시 사용 됩니다.

자체에는 `OrderServiceClient` 특별 한 apr 코드가 없습니다. 이 경우에는 Eapr 서비스 호출이 사용 되는 경우에도 다른 HttpClient와 마찬가지로

```csharp
public class OrderServiceClient : IOrderServiceClient
{
    private readonly HttpClient _httpClient;

    public OrderServiceClient(HttpClient httpClient)
    {
        _httpClient = httpClient ?? throw new ArgumentNullException(nameof(httpClient));
    }

    public async Task SubmitOrder(Order order)
    {
        var response = await _httpClient.PostAsJsonAsync("submit", order);
        response.EnsureSuccessStatusCode();
    }
}
```

다음과 같은 다양 한 이점이 있는 HttpClient 클래스를 사용 하는 경우

- HttpClient는 대부분의 개발자가 이미 코드에서 사용 하는 잘 알려진 클래스입니다. 서비스 호출에 대해 HttpClient를 사용 하면 개발자가 기존 기술을 재사용할 수 있습니다.
- HttpClient는 사용자 지정 헤더와 같은 고급 시나리오를 지원 하 고 요청 및 응답 메시지에 대 한 모든 권한을 지원 합니다.
- .NET 5에서 HttpClient는 System.Text.Js을 사용 하 여 자동 serialization 및 deserialization을 지원 합니다.
- HttpClient는 [Refit](https://github.com/reactiveui/refit), [RestSharp](https://restsharp.dev/getting-started/getting-started.html#basic-usage), 등의 많은 기존 프레임 워크 및 [라이브러리와 통합 됩니다.](https://github.com/App-vNext/Polly)

### <a name="invoke-http-services-using-daprclient"></a>DaprClient를 사용 하 여 HTTP 서비스 호출

HttpClient는 HTTP 의미 체계를 사용 하 여 서비스를 호출 하는 기본 방법 이지만 메서드 패밀리를 사용할 수도 있습니다 `DaprClient.InvokeMethodAsync` . 다음 예제에서는 `submit` 응용 프로그램의 메서드를 호출 하 여 주문을 전송 합니다 `orderservice` .

``` csharp
var daprClient = new DaprClientBuilder().Build();
try
{
    var confirmation =
        await daprClient.InvokeMethodAsync<Order, OrderConfirmation>(
            "orderservice", "submit", order);
}
catch (InvocationException ex)
{
    // Handle error
}
```

세 번째 인수인 개체인는 `order` 내부적으로 직렬화 되 `System.Text.JsonSerializer` 고 요청 페이로드로 전송 됩니다. .NET SDK는 사이드카에 대 한 호출을 처리 합니다. 또한 개체에 대 한 응답을 deserialize `OrderConfirmation` 합니다. HTTP 메서드가 지정 되지 않았기 때문에 요청은 HTTP POST로 실행 됩니다.

다음 예제에서는를 지정 하 여 HTTP GET 요청을 수행 하는 방법을 보여 줍니다 `HttpMethod` .

```csharp
var catalogItems = await daprClient.InvokeMethodAsync<IEnumerable<CatalogItem>>(HttpMethod.Get, "catalogservice", "items");
```

일부 시나리오에서는 요청 메시지에 대해 더 많은 제어가 필요할 수 있습니다. 예를 들어 요청 헤더를 지정 해야 하거나 페이로드에 대 한 사용자 지정 serializer를 사용 하려는 경우를 예로 들 수 있습니다. `DaprClient.CreateInvokeMethodRequest` 을 만듭니다 `HttpRequestMessage` . 다음 예제에서는 요청 메시지에 HTTP 권한 부여 헤더를 추가 하는 방법을 보여 줍니다.

```csharp
var request = daprClient.CreateInvokeMethodRequest("orderservice", "submit", order);
request.Headers.Authorization = new AuthenticationHeaderValue("bearer", token);
```

이제에는 `HttpRequestMessage` 다음과 같은 속성 집합이 있습니다.

- Url = `http://127.0.0.1:3500/v1.0/invoke/orderservice/method/submit`
- HttpMethod = POST
- Content =  `JsonContent` JSON 직렬화를 포함 하는 개체입니다. `order`
- 헤더. Authorization = "전달자 \<token> "

원하는 방식으로 요청을 설정한 후에는를 사용 하 여 요청을 `DaprClient.InvokeMethodAsync` 보냅니다.

```csharp
var orderConfirmation = await daprClient.InvokeMethodAsync<OrderConfirmation>(request);
```

`DaprClient.InvokeMethodAsync` 요청이 성공 하는 경우 개체에 대 한 응답을 deserialize `OrderConfirmation` 합니다. 또는를 사용 하 여 `DaprClient.InvokeMethodWithResponseAsync` 내부에 대 한 전체 액세스 권한을 얻을 수 있습니다 `HttpResponseMessage` .

```csharp
var response = await daprClient.InvokeMethodWithResponseAsync(request);
response.EnsureSuccessStatusCode();

var orderConfirmation = response.Content.ReadFromJsonAsync<OrderConfirmation>();
```

> [!NOTE]
> HTTP를 사용 하 여 서비스를 호출 하는 경우 이전 섹션에서 제공 하는 Eapr HttpClient 통합 사용을 고려 하는 것이 좋습니다. HttpClient를 사용 하면 기존 프레임 워크 및 라이브러리와의 통합과 같은 추가 혜택을 얻을 수 있습니다.

### <a name="invoke-grpc-services-using-daprclient"></a>DaprClient를 사용 하 여 gRPC 서비스 호출

DaprClient는 `InvokeMethodGrpcAsync` gRPC 끝점을 호출 하기 위한 메서드 패밀리를 제공 합니다. HTTP 메서드와의 주요 차이점은 JSON 대신 Protobuf serializer를 사용 하는 것입니다. 다음 예제에서는 `submitOrder` 최대 gRPC의 메서드를 호출 합니다 `orderservice` .

```csharp
var daprClient = new DaprClientBuilder().Build();
try
{
    var confirmation = await daprClient.InvokeMethodGrpcAsync<Order, OrderConfirmation>("orderservice", "submitOrder", order);
}
catch (InvocationException ex)
{
    // Handle error
}
```

위의 예제에서 DaprClient는 `order` [Protobuf](https://developers.google.com/protocol-buffers) 를 사용 하 여 지정 된 개체를 직렬화 하 고 결과를 grpc 요청 본문으로 사용 합니다. 마찬가지로 응답 본문은 Protobuf deserialize 되어 호출자에 게 반환 됩니다. Protobuf는 일반적으로 HTTP 서비스 호출에 사용 되는 JSON 페이로드 보다 더 나은 성능을 제공 합니다.

## <a name="reference-application-eshopondapr"></a>참조 응용 프로그램: eShopOnDapr

Microsoft의 원래 [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) 마이크로 서비스 reference 아키텍처는 HTTP/REST 및 grpc 서비스를 혼합 하 여 사용 했습니다. GRPC를 사용 하는 것은 [집계 서비스](../cloud-native/service-to-service-communication.md#service-aggregator-pattern) 와 핵심 백 엔드 서비스 간의 통신으로 제한 되었습니다. 그림 6-2은 아키텍처를 보여 줍니다.

![eShopOnContainers에서 gRPC 및 HTTP/REST 호출](./media/service-invocation/eshop-on-containers.png)

**그림 6-2**. eShopOnContainers에서 gRPC 및 HTTP/REST 호출.

위의 그림에서 설명 하는 단계를 확인 합니다.

1. 프런트 엔드는 HTTP/REST를 사용 하 여 [API 게이트웨이](/azure/architecture/microservices/design/gateway) 를 호출 합니다.

1. API 게이트웨이는 HTTP/REST를 사용 하 여 간단한 [CRUD](https://www.sumologic.com/glossary/crud/) (만들기, 읽기, 업데이트, 삭제) 요청을 핵심 백 엔드 서비스에 직접 전달 합니다.

1. API 게이트웨이는 여러 백 엔드 서비스에 대 한 조정 된 호출을 포함 하는 복잡 한 요청을 웹 쇼핑 집계 서비스에 전달 합니다.

1. 집계 서비스는 gRPC를 사용 하 여 코어 백 엔드 서비스를 호출 합니다.

최근에 업데이트 된 eShopOnDapr 구현에서 사이드카는 서비스 및 API 게이트웨이에 추가 됩니다. 그림 6-3에서는 업데이트 된 아키텍처를 보여 줍니다.

![eShopOnContainers의 사이드카를 사용 하 여 gRPC 및 HTTP/REST 호출](./media/service-invocation/eshop-on-dapr.png)

**그림 6-3**. D 4를 사용 하 여 eShop 아키텍처를 업데이트 했습니다.

이전 그림의 업데이트 된 단계를 확인 합니다.

1. 프런트 엔드는 여전히 HTTP/REST를 사용 하 여 API 게이트웨이를 호출 합니다.

1. API 게이트웨이는 해당 사이드카에 HTTP 요청을 전달 합니다.

1. API 게이트웨이 사이드카는 집계 또는 백 엔드 서비스의 사이드카 요청을 보냅니다.

1. 집계 서비스는 Dapr .NET SDK를 사용 하 여 사이드카 아키텍처를 통해 백 엔드 서비스를 호출 합니다.

사이드카는 gRPC와의 호출을 구현 합니다. 따라서 HTTP/REST 의미 체계를 사용 하 여 원격 서비스를 호출 하는 경우에도 gRPC를 사용 하 여 전송 부분이 계속 구현 됩니다.

EShopOnDapr reference 응용 프로그램은 Eapr 서비스 호출 빌딩 블록을 활용 합니다. 이러한 이점에는 서비스 검색, 자동 mTLS 및 관찰성이 포함 됩니다.

### <a name="forward-http-requests-using-envoy-and-dapr"></a>엔보이 및 d 4를 사용 하 여 HTTP 요청 전달

원래 및 업데이트 된 eShop 응용 프로그램은 모두 [엔보이 프록시](https://www.envoyproxy.io/) 를 API 게이트웨이로 활용 합니다. 엔보이는 최신 분산 응용 프로그램에서 널리 사용 되는 오픈 소스 프록시와 통신 버스입니다. Lyft에서 시작 되는 엔보이는 [클라우드 네이티브 컴퓨팅 파운데이션](https://www.cncf.io/)에서 소유 하 고 유지 관리 합니다.

원래 eShopOnContainers 구현에서 엔보이 API 게이트웨이는 들어오는 HTTP 요청을 집계 또는 백 엔드 서비스에 직접 전달 했습니다. 새 eShopOnDapr에서 엔보이 프록시는 요청을 Eapr 사이드카에 전달 합니다. 사이드카는 서비스 호출, mTLS 및 관찰성를 제공 합니다.

엔보이는 YAML 정의 파일을 사용 하 여 프록시의 동작을 제어 하도록 구성 됩니다. 엔보이가 사이드카 컨테이너에 HTTP 요청을 전달 하도록 설정 하려면 `dapr` 클러스터가 구성에 추가 됩니다. 클러스터 구성에는 사이드카에서 수신 대기 하는 HTTP 포트를 가리키는 호스트가 포함 되어 있습니다.

``` yaml
clusters:
- name: dapr
  connect_timeout: 0.25s
  type: strict_dns
  hosts:
  - socket_address:
    address: 127.0.0.1
    port_value: 3500
```

사이드카에 대 한 호출로 들어오는 요청을 다시 작성 하도록 엔보이 경로 구성이 업데이트 됩니다 (키/값 쌍에 대 한 주의를 기울여야 함 `prefix_rewrite` ).

``` yaml
- name: "c-short"
  match:
    prefix: "/c/"
  route:
    auto_host_rewrite: true
    prefix_rewrite: "/v1.0/invoke/catalog-api/method/"
    cluster: dapr
```

프런트 엔드 클라이언트에서 카탈로그 항목 목록을 검색 하려는 시나리오를 고려 합니다. 카탈로그 API는 카탈로그 항목을 가져오기 위한 끝점을 제공 합니다.

``` csharp
[Route("api/v1/[controller]")]
[ApiController]
public class CatalogController : ControllerBase
{
    [HttpGet("items")]
    public async Task<IActionResult> ItemsAsync(
        [FromQuery] int pageSize = 10,
        [FromQuery] int pageIndex = 0)
    {
        // ...
    }
```

첫째, 프런트 엔드는 엔보이 API 게이트웨이에 대 한 직접 HTTP 호출을 수행 합니다.

```
GET http://<api-gateway>/c/api/v1/catalog/items?pageSize=20
```

엔보이 프록시가 경로와 일치 하 고, HTTP 요청을 다시 작성 하 고,이를 `invoke` 해당 사이드카의 API에 전달 합니다.

```
GET http://127.0.0.1:3500/v1.0/invoke/catalog-api/method/api/v1/catalog/items?pageSize=20
```

사이드카는 서비스 검색을 처리 하 고 요청을 카탈로그 API 사이드카로 라우팅합니다. 마지막으로 사이드카는 카탈로그 API를 호출 하 여 요청을 실행 하 고, 카탈로그 항목을 인출 하 고, 응답을 반환 합니다.

```
GET http://localhost/api/v1/catalog/items?pageSize=20
```

### <a name="make-aggregated-service-calls-using-the-net-sdk"></a>.NET SDK를 사용 하 여 집계 된 서비스 호출 만들기

EShop 프런트 엔드에서의 대부분 호출은 간단한 CRUD 호출입니다. API 게이트웨이는 처리를 위해 단일 서비스로이를 전달 합니다. 그러나 일부 시나리오에서는 여러 백 엔드 서비스가 함께 작동 하 여 요청을 완료 해야 합니다. 이러한 보다 복잡 한 호출의 경우 eShop는 웹 쇼핑 집계 서비스를 사용 하 여 여러 서비스에 걸쳐 워크플로를 중재 합니다. 그림 6-4에서는 시장 바구니에 항목을 추가 하는 처리 순서를 보여 줍니다.

![바구니 시퀀스 다이어그램 업데이트](./media/service-invocation/complex-call.png)

**그림 6-4** 쇼핑 바구니 순서를 업데이트 합니다.

집계 서비스는 먼저 카탈로그 API에서 카탈로그 항목을 검색 합니다. 그런 다음 항목 가용성 및 가격의 유효성을 검사 합니다. 마지막으로, 집계 서비스는 바구니 API를 호출 하 여 업데이트 된 쇼핑 바구니를 저장 합니다.

집계 서비스에는 시장 `BasketController` 바구니를 업데이트 하기 위한 끝점을 제공 하는가 포함 되어 있습니다.

``` csharp
[Route("api/v1/[controller]")]
[Authorize]
[ApiController]
public class BasketController : ControllerBase
{
    private readonly ICatalogService _catalog;
    private readonly IBasketService _basket;

    [HttpPost]
    [HttpPut]
    public async Task<ActionResult<BasketData>> UpdateAllBasketAsync(
        [FromBody] UpdateBasketRequest data, [FromHeader] string authorization)
    {
        // Get the item details from the catalog API.
        var catalogItems = await _catalog.GetCatalogItemsAsync(
            data.Items.Select(x => x.ProductId));

        // Check item availability and prices; store results in basket object.
        var basket = CreateValidatedBasket(data, catalogItems);

        // Save the shopping basket.
        await _basket.UpdateAsync(basket, authorization);

        return basket;
    }

    // ...
}
```

`UpdateAllBasketAsync`메서드는 특성을 사용 하 여 들어오는 요청의 *권한 부여* 헤더를 가져옵니다 `FromHeader` . *권한 부여* 헤더에는 보호 된 백 엔드 서비스를 호출 하는 데 필요한 액세스 토큰이 포함 되어 있습니다.

바구니 업데이트 요청을 받은 후 집계 서비스는 카탈로그 API를 호출 하 여 항목 세부 정보를 가져옵니다. 바구니 컨트롤러는 삽입 된 개체를 사용 하 여 `ICatalogService` 해당 호출을 수행 하 고 카탈로그 API와 통신 합니다. 인터페이스의 원래 구현은 gRPC를 사용 하 여 호출을 수행 합니다. 업데이트 된 구현에서는 HttpClient 지원과 함께 Eapr 서비스 호출을 사용 합니다.

``` csharp
public class CatalogService : ICatalogService
{
    private readonly HttpClient _httpClient;

    public CatalogService(HttpClient httpClient)
    {
        _httpClient = httpClient ?? throw new ArgumentNullException(nameof(httpClient));
    }

    public Task<IEnumerable<CatalogItem>> GetCatalogItemsAsync(IEnumerable<int> ids)
    {
        var requestUri = $"api/v1/catalog/items?ids={string.Join(",", ids)}";

        return _httpClient.GetFromJsonAsync<IEnumerable<CatalogItem>>(requestUri);
    }

    // ...
}
```

서비스 호출을 호출 하는 데 필요한 구체적인 코드는 없습니다. 모든 통신은 표준 HttpClient 개체를 사용 하 여 수행 됩니다.

다음 메서드의 클래스에는 6Apr HttpClient가 삽입 됩니다 `CatalogService` `Startup.ConfigureServices` .

```csharp
services.AddSingleton<ICatalogService, CatalogService>(
    _ => new CatalogService(DaprClient.CreateInvokeHttpClient("catalog-api")));
```

집계 서비스에서 수행 하는 다른 호출은 바구니 API에 대 한 것입니다. 승인 된 요청만 허용 합니다. 액세스 토큰은 호출이 성공 하도록 *권한 부여* 요청 헤더에 전달 됩니다.

``` csharp
public class BasketService : IBasketService
{
    public Task UpdateAsync(BasketData currentBasket, string accessToken)
    {
        var request = new HttpRequestMessage(HttpMethod.Post, "api/v1/basket")
        {
            Content = JsonContent.Create(currentBasket)
        };
        request.Headers.Authorization = new AuthenticationHeaderValue(accessToken);

        var response = await _httpClient.SendAsync(request);
        response.EnsureSuccessStatusCode();
    }

    // ...
}
```

이 예제에서는 표준 HttpClient 기능만 사용 하 여 서비스를 호출 합니다. 이를 통해 HttpClient를 이미 잘 알고 있는 개발자가 기존 기술을 재사용할 수 있습니다. 이 기능을 사용 하면 기존 HttpClient 코드에서 변경 하지 않고도 Eapr 서비스 호출을 사용할 수도 있습니다.

## <a name="summary"></a>요약

이 장에서는 서비스 호출 빌딩 블록에 대해 알아보았습니다. Dapr 사이드카에 대 한 직접 HTTP 호출을 수행 하 고 Dapr .NET SDK를 사용 하 여 원격 메서드를 호출 하는 방법을 살펴보았습니다.

Dapr .NET SDK는 원격 메서드를 호출 하는 여러 가지 방법을 제공 합니다. HttpClient 지원은 기존 기술을 다시 사용 하려는 개발자에 게 유용 하며 기존의 많은 프레임 워크 및 라이브러리와 호환 됩니다. DaprClient는 HTTP 또는 gRPC 의미 체계를 사용 하 여 Eapr 서비스 호출 API를 직접 사용 하는 지원을 제공 합니다.

EShopOnDapr reference 아키텍처는 eShopOnContainers 서비스 호출을 사용 하 여 원래 솔루션을 현대화 하는 방법을 보여 줍니다. D 4를 eShop에 추가 하면 자동 재시도, mTLS를 사용 하는 메시지 암호화 및 향상 된 관찰성 같은 이점이 제공 됩니다.

### <a name="references"></a>참조

- [6apr 서비스 호출 빌딩 블록](https://docs.dapr.io/developing-applications/building-blocks/service-invocation/)

- [분산 클라우드-네이티브 응용 프로그램 모니터링](../cloud-native/observability-patterns.md)

> [!div class="step-by-step"]
> [이전](state-management.md)
> [다음](publish-subscribe.md)
