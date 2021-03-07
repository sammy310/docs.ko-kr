---
title: 6Apr 서비스 호출 빌딩 블록
description: 서비스 호출 빌딩 블록에 대 한 설명, 해당 기능, 이점 및 적용 방법
author: amolenk
ms.date: 02/07/2021
ms.openlocfilehash: 2b64aa1e9b079a3fefe120e687cd6d395981c633
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401843"
---
# <a name="the-dapr-service-invocation-building-block"></a><span data-ttu-id="a9595-103">6Apr 서비스 호출 빌딩 블록</span><span class="sxs-lookup"><span data-stu-id="a9595-103">The Dapr service invocation building block</span></span>

<span data-ttu-id="a9595-104">분산 시스템에서 한 서비스는 비즈니스 작업을 완료 하기 위해 다른 서비스와 통신 해야 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-104">Across a distributed system, one service often needs to communicate with another to complete a business operation.</span></span> <span data-ttu-id="a9595-105">[6Apr 서비스 호출 빌딩 블록](https://docs.dapr.io/developing-applications/building-blocks/service-invocation/service-invocation-overview/) 은 서비스 간 통신을 간소화 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-105">The [Dapr service invocation building block](https://docs.dapr.io/developing-applications/building-blocks/service-invocation/service-invocation-overview/) can help streamline the communication between services.</span></span>

## <a name="what-it-solves"></a><span data-ttu-id="a9595-106">해결 방법</span><span class="sxs-lookup"><span data-stu-id="a9595-106">What it solves</span></span>

<span data-ttu-id="a9595-107">분산 응용 프로그램에서 서비스 간의 호출은 쉽게 나타날 수 있지만 관련 된 많은 과제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-107">Making calls between services in a distributed application may appear easy, but there are many challenges involved.</span></span> <span data-ttu-id="a9595-108">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-108">For example:</span></span>

- <span data-ttu-id="a9595-109">다른 서비스를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-109">Where the other services are located.</span></span>
- <span data-ttu-id="a9595-110">서비스 주소를 지정 하 여 서비스를 안전 하 게 호출 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-110">How to call a service securely, given the service address.</span></span>
- <span data-ttu-id="a9595-111">단기 [일시적인 오류가](/aspnet/aspnet/overview/developing-apps-with-windows-azure/building-real-world-cloud-apps-with-windows-azure/transient-fault-handling) 발생할 경우 재시도를 처리 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-111">How to handle retries when short-lived [transient errors](/aspnet/aspnet/overview/developing-apps-with-windows-azure/building-real-world-cloud-apps-with-windows-azure/transient-fault-handling) occur.</span></span>

<span data-ttu-id="a9595-112">마지막으로, 분산 응용 프로그램에서 다양 한 서비스를 작성할 때 서비스 호출 그래프를 통해 정보를 캡처하는 것은 프로덕션 문제를 진단 하는 데 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-112">Lastly, as distributed applications compose many different services, capturing insights across service call graphs are critical to diagnosing production issues.</span></span>

<span data-ttu-id="a9595-113">서비스 호출 빌딩 블록은 서비스에 대 한 [역방향 프록시로](https://kemptechnologies.com/reverse-proxy/reverse-proxy/) 서 사이드카를 사용 하 여 이러한 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-113">The service invocation building block addresses these challenges by using a Dapr sidecar as a [reverse proxy](https://kemptechnologies.com/reverse-proxy/reverse-proxy/) for your service.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="a9595-114">작동 방법</span><span class="sxs-lookup"><span data-stu-id="a9595-114">How it works</span></span>

<span data-ttu-id="a9595-115">예부터 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-115">Let's start with an example.</span></span> <span data-ttu-id="a9595-116">"서비스 A"와 "Service B"의 두 가지 서비스를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-116">Consider two services, "Service A" and "Service B".</span></span> <span data-ttu-id="a9595-117">서비스 A는 `catalog/items` 서비스 B에서 API를 호출 해야 합니다. 서비스 A는 서비스 B에 대 한 종속성을 사용 하 고이에 대 한 직접 호출을 수행할 수 있지만, 서비스 A는 대신 사이드카에서 서비스 호출 API를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-117">Service A needs to call the `catalog/items` API on Service B. While Service A could take a dependency on Service B and make a direct call to it, Service A instead invokes the service invocation API on the Dapr sidecar.</span></span> <span data-ttu-id="a9595-118">그림 6-1은 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-118">Figure 6-1 shows the operation.</span></span>

![Eapr 서비스 호출 작동 방법](./media/service-invocation/service-invocation-flow.png)

<span data-ttu-id="a9595-120">**그림 6-1**.</span><span class="sxs-lookup"><span data-stu-id="a9595-120">**Figure 6-1**.</span></span> <span data-ttu-id="a9595-121">Eapr 서비스 호출의 작동 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-121">How Dapr service invocation works.</span></span>

<span data-ttu-id="a9595-122">위의 그림에서 설명 하는 단계를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-122">Note the steps from the previous figure:</span></span>

1. <span data-ttu-id="a9595-123">서비스 A는 `catalog/items` 사이드카 서비스에서 서비스 호출 API를 호출 하 여 서비스 B의 끝점에 대 한 호출을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-123">Service A makes a call to the `catalog/items` endpoint in Service B by invoking the service invocation API on the Service A sidecar.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a9595-124">사이드카는 플러그형 이름 확인 메커니즘을 사용 하 여 서비스 B의 주소를 확인 합니다. 자체 호스팅 모드에서는 [mdn](https://www.ionos.com/digitalguide/server/know-how/multicast-dns/) 를 사용 하 여이를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-124">The sidecar uses a pluggable name resolution mechanism to resolve the address of Service B. In self-hosted mode, Dapr uses [mDNS](https://www.ionos.com/digitalguide/server/know-how/multicast-dns/) to find it.</span></span> <span data-ttu-id="a9595-125">Kubernetes 모드로 실행 되는 경우 Kubernetes DNS 서비스는 주소를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-125">When running in Kubernetes mode, the Kubernetes DNS service determines the address.</span></span>  

1. <span data-ttu-id="a9595-126">사이드카 서비스는 서비스 B 사이드카에 요청을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-126">The Service A sidecar forwards the request to the Service B sidecar.</span></span>

1. <span data-ttu-id="a9595-127">Service B 사이드카는 `catalog/items` Service b API에 대 한 실제 요청을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-127">The Service B sidecar makes the actual `catalog/items` request against the Service B API.</span></span>

1. <span data-ttu-id="a9595-128">서비스 B가 요청을 실행 하 고 사이드카 응답을 다시 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-128">Service B executes the request and returns a response back to its sidecar.</span></span>

1. <span data-ttu-id="a9595-129">서비스 B 사이드카는 응답을 서비스 A 사이드카로 다시 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-129">The Service B sidecar forwards the response back to the Service A sidecar.</span></span>

1. <span data-ttu-id="a9595-130">사이드카 서비스는 다시 서비스 A에 대 한 응답을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-130">The Service A sidecar returns the response back to Service A.</span></span>

<span data-ttu-id="a9595-131">호출이 사이드카을 통해 전달 되기 때문에는 다음과 같은 몇 가지 유용한 교차 잘라내기 동작을 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-131">Because the calls flow through sidecars, Dapr can inject some useful cross-cutting behaviors:</span></span>

- <span data-ttu-id="a9595-132">오류 발생 시 자동으로 호출을 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-132">Automatically retry calls upon failure.</span></span>
- <span data-ttu-id="a9595-133">자동 인증서 롤오버를 비롯 한 상호 (mTLS) 인증을 사용 하 여 서비스를 안전 하 게 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-133">Make calls between services secure with mutual (mTLS) authentication, including automatic certificate rollover.</span></span>
- <span data-ttu-id="a9595-134">클라이언트에서 액세스 제어 정책을 사용 하 여 수행할 수 있는 작업을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-134">Control what operations clients can do using access control policies.</span></span>
- <span data-ttu-id="a9595-135">서비스 간의 모든 호출에 대 한 추적 및 메트릭을 캡처하여 정보 및 진단을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-135">Capture traces and metrics for all calls between services to provide insights and diagnostics.</span></span>

<span data-ttu-id="a9595-136">모든 응용 프로그램은 사이드카에 기본 제공 되는 네이티브 **호출** API를 사용 하 여 d 4 월을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-136">Any application can invoke a Dapr sidecar by using the native **invoke** API built into Dapr.</span></span> <span data-ttu-id="a9595-137">API는 HTTP 또는 gRPC를 사용 하 여 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-137">The API can be called with either HTTP or gRPC.</span></span> <span data-ttu-id="a9595-138">다음 URL을 사용 하 여 HTTP API를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-138">Use the following URL to call the HTTP API:</span></span>

``` http
http://localhost:<dapr-port>/v1.0/invoke/<application-id>/method/<method-name>
```

- <span data-ttu-id="a9595-139">`<dapr-port>` d 4에서 수신 대기 하는 HTTP 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-139">`<dapr-port>` the HTTP port that Dapr is listening on.</span></span>
- <span data-ttu-id="a9595-140">`<application-id>` 호출할 서비스의 응용 프로그램 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-140">`<application-id>` application ID of the service to call.</span></span>
- <span data-ttu-id="a9595-141">`<method-name>` 원격 서비스에서 호출할 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-141">`<method-name>` name of the method to invoke on the remote service.</span></span>

<span data-ttu-id="a9595-142">다음 예제에서는  `catalog/items` 의 ' GET ' 끝점을 호출 합니다 `Service B` .</span><span class="sxs-lookup"><span data-stu-id="a9595-142">In the following example, a *curl* call is made to the `catalog/items` 'GET' endpoint of `Service B`:</span></span>

```console
curl http://localhost:3500/v1.0/invoke/serviceb/method/catalog/items
```

> [!NOTE]
> <span data-ttu-id="a9595-143">Eapr Api를 사용 하면 HTTP 또는 gRPC를 지 원하는 모든 응용 프로그램 스택에서 4Apr 빌딩 블록을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-143">The Dapr APIs enable any application stack that supports HTTP or gRPC to use Dapr building blocks.</span></span> <span data-ttu-id="a9595-144">따라서 서비스 호출 빌딩 블록은 프로토콜 간의 다리 역할을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-144">Therefore, the service invocation building block can act as a bridge between protocols.</span></span> <span data-ttu-id="a9595-145">서비스는 HTTP, gRPC 또는 둘의 조합을 사용 하 여 서로 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-145">Services can communicate with each other using HTTP, gRPC or a combination of both.</span></span>

<span data-ttu-id="a9595-146">다음 섹션에서는 .NET SDK를 사용 하 여 서비스 호출을 간소화 하는 방법을 배웁니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-146">In the next section, you'll learn how to use the .NET SDK to simplify service invocation calls.</span></span>

## <a name="use-the-dapr-net-sdk"></a><span data-ttu-id="a9595-147">Dapr .NET SDK 사용</span><span class="sxs-lookup"><span data-stu-id="a9595-147">Use the Dapr .NET SDK</span></span>

<span data-ttu-id="a9595-148">Dapr [.NET SDK](https://github.com/dapr/dotnet-sdk) 는 .net 개발자에 게 dapr와 상호 작용 하는 직관적이 고 언어별 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-148">The Dapr [.NET SDK](https://github.com/dapr/dotnet-sdk) provides .NET developers with an intuitive and language-specific way to interact with Dapr.</span></span> <span data-ttu-id="a9595-149">SDK는 개발자에 게 원격 서비스 호출을 호출 하는 세 가지 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-149">The SDK offers developers three ways of making remote service invocation calls:</span></span>

1. <span data-ttu-id="a9595-150">HttpClient를 사용 하 여 HTTP 서비스 호출</span><span class="sxs-lookup"><span data-stu-id="a9595-150">Invoke HTTP services using HttpClient</span></span>
1. <span data-ttu-id="a9595-151">DaprClient를 사용 하 여 HTTP 서비스 호출</span><span class="sxs-lookup"><span data-stu-id="a9595-151">Invoke HTTP services using DaprClient</span></span>
1. <span data-ttu-id="a9595-152">DaprClient를 사용 하 여 gRPC 서비스 호출</span><span class="sxs-lookup"><span data-stu-id="a9595-152">Invoke gRPC services using DaprClient</span></span>

### <a name="invoke-http-services-using-httpclient"></a><span data-ttu-id="a9595-153">HttpClient를 사용 하 여 HTTP 서비스 호출</span><span class="sxs-lookup"><span data-stu-id="a9595-153">Invoke HTTP services using HttpClient</span></span>

<span data-ttu-id="a9595-154">HTTP 끝점을 호출 하는 기본 방법은와 함께 Fapr의 다양 한 통합을 사용 하는 것입니다 `HttpClient` .</span><span class="sxs-lookup"><span data-stu-id="a9595-154">The preferred way to call an HTTP endpoint is to use Dapr's rich integration with `HttpClient`.</span></span> <span data-ttu-id="a9595-155">다음 예제에서는 `submit` 응용 프로그램의 메서드를 호출 하 여 주문을 전송 합니다 `orderservice` .</span><span class="sxs-lookup"><span data-stu-id="a9595-155">The following example submits an order by calling the `submit` method of the `orderservice` application:</span></span>

```csharp
var httpClient = DaprClient.CreateHttpClient();
await httpClient.PostAsJsonAsync("http://orderservice/submit", order);
```

<span data-ttu-id="a9595-156">이 예에서는를 `DaprClient.CreateHttpClient` 반환 하는 데 사용 되는 인스턴스를 반환 `HttpClient` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-156">In the example, `DaprClient.CreateHttpClient` returns an `HttpClient` instance that is used to perform Dapr service invocation.</span></span> <span data-ttu-id="a9595-157">반환 되는는 `HttpClient` 나가는 요청의 uri를 다시 작성 하는 특수 한 4Apr 메시지 처리기를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-157">The returned `HttpClient` uses a special Dapr message handler that rewrites URIs of outgoing requests.</span></span> <span data-ttu-id="a9595-158">호스트 이름은 호출할 서비스의 응용 프로그램 ID로 해석 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-158">The host name is interpreted as the application ID of the service to call.</span></span> <span data-ttu-id="a9595-159">실제로 호출 되는 다시 작성 된 요청은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-159">The rewritten request that's actually being called is:</span></span>

```http
http://127.0.0.1:3500/v1/invoke/orderservice/method/submit
```

<span data-ttu-id="a9595-160">이 예제에서는의 기본 값을 사용 `http://127.0.0.1:<dapr-http-port>/` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-160">This example uses the default value for the Dapr HTTP endpoint, which is `http://127.0.0.1:<dapr-http-port>/`.</span></span> <span data-ttu-id="a9595-161">의 값은 `dapr-http-port` 환경 변수에서 가져옵니다 `DAPR_HTTP_PORT` .</span><span class="sxs-lookup"><span data-stu-id="a9595-161">The value of `dapr-http-port` is taken from the `DAPR_HTTP_PORT` environment variable.</span></span> <span data-ttu-id="a9595-162">설정 되지 않은 경우 기본 포트 번호가 `3500` 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-162">If it's not set, the default port number `3500` is used.</span></span>

<span data-ttu-id="a9595-163">또는에 대 한 호출에서 사용자 지정 끝점을 구성할 수 있습니다 `DaprClient.CreateHttpClient` .</span><span class="sxs-lookup"><span data-stu-id="a9595-163">Alternatively, you can configure a custom endpoint in the call to `DaprClient.CreateHttpClient`:</span></span>

```csharp
var httpClient = DaprClient.CreateHttpClient(daprEndpoint = "localhost:4000");
```

<span data-ttu-id="a9595-164">응용 프로그램 ID를 지정 하 여 기본 주소를 직접 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-164">You can also directly set the base address by specifying the application ID.</span></span> <span data-ttu-id="a9595-165">이렇게 하면를 호출할 때 상대 Uri를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-165">This makes it possible to use relative URIs when making a call:</span></span>

```csharp
var httpClient = DaprClient.CreateHttpClient("orderservice");
await httpClient.PostAsJsonAsync("/submit");
```

<span data-ttu-id="a9595-166">`HttpClient`개체는 수명이 긴 것으로 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-166">The `HttpClient` object is intended to be long-lived.</span></span> <span data-ttu-id="a9595-167">`HttpClient`응용 프로그램의 수명 동안 단일 인스턴스를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-167">A single `HttpClient` instance can be reused for the lifetime of the application.</span></span> <span data-ttu-id="a9595-168">다음 시나리오에서는 `OrderServiceClient` 클래스가 Eapr 인스턴스를 재사용 하는 방법을 보여 줍니다 `HttpClient` .</span><span class="sxs-lookup"><span data-stu-id="a9595-168">The next scenario demonstrates how an `OrderServiceClient` class reuses a Dapr `HttpClient` instance:</span></span>  

```csharp
public void ConfigureServices(IServiceCollection services)
{
    // ...
    services.AddSingleton<IOrderServiceClient, OrderServiceClient>(
        _ => new OrderServiceClient(DaprClient.CreateInvokeHttpClient("orderservice")));
}
```

<span data-ttu-id="a9595-169">위의 코드 조각에서는 `OrderServiceClient` ASP.NET Core 종속성 주입 시스템을 사용 하 여 singleton으로 등록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-169">In the snippet above, the `OrderServiceClient` is registered as a singleton with the ASP.NET Core dependency injection system.</span></span> <span data-ttu-id="a9595-170">구현 팩터리는를 `HttpClient` 호출 하 여 새 인스턴스를 만듭니다 `DaprClient.CreateInvokeHttpClient` .</span><span class="sxs-lookup"><span data-stu-id="a9595-170">An implementation factory creates a new `HttpClient` instance by calling `DaprClient.CreateInvokeHttpClient`.</span></span> <span data-ttu-id="a9595-171">그런 다음 새로 만든을 사용 하 여 `HttpClient` 개체를 인스턴스화합니다 `OrderServiceClient` .</span><span class="sxs-lookup"><span data-stu-id="a9595-171">It then uses the newly created `HttpClient` to instantiate the `OrderServiceClient` object.</span></span> <span data-ttu-id="a9595-172">를 `OrderServiceClient` singleton으로 등록 하면 응용 프로그램의 수명 동안 다시 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-172">By registering the `OrderServiceClient` as a singleton, it will be reused for the lifetime of the application.</span></span>

<span data-ttu-id="a9595-173">자체에는 `OrderServiceClient` 특별 한 apr 코드가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-173">The `OrderServiceClient` itself has no Dapr-specific code.</span></span> <span data-ttu-id="a9595-174">이 경우에는 Eapr 서비스 호출이 사용 되는 경우에도 다른 HttpClient와 마찬가지로</span><span class="sxs-lookup"><span data-stu-id="a9595-174">Even though Dapr service invocation is used under the hood, you can treat the Dapr HttpClient like any other HttpClient:</span></span>

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

<span data-ttu-id="a9595-175">다음과 같은 다양 한 이점이 있는 HttpClient 클래스를 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="a9595-175">Using the HttpClient class with Dapr service invocation has many benefits:</span></span>

- <span data-ttu-id="a9595-176">HttpClient는 대부분의 개발자가 이미 코드에서 사용 하는 잘 알려진 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-176">HttpClient is a well-known class that many developers already use in their code.</span></span> <span data-ttu-id="a9595-177">서비스 호출에 대해 HttpClient를 사용 하면 개발자가 기존 기술을 재사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-177">Using HttpClient for Dapr service invocation allows developers to reuse their existing skills.</span></span>
- <span data-ttu-id="a9595-178">HttpClient는 사용자 지정 헤더와 같은 고급 시나리오를 지원 하 고 요청 및 응답 메시지에 대 한 모든 권한을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-178">HttpClient supports advanced scenarios, such as custom headers, and full control over request and response messages.</span></span>
- <span data-ttu-id="a9595-179">.NET 5에서 HttpClient는 System.Text.Js을 사용 하 여 자동 serialization 및 deserialization을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-179">In .NET 5, HttpClient supports automatic serialization and deserialization using System.Text.Json.</span></span>
- <span data-ttu-id="a9595-180">HttpClient는 [Refit](https://github.com/reactiveui/refit), [RestSharp](https://restsharp.dev/getting-started/getting-started.html#basic-usage), 등의 많은 기존 프레임 워크 및 [라이브러리와 통합 됩니다.](https://github.com/App-vNext/Polly)</span><span class="sxs-lookup"><span data-stu-id="a9595-180">HttpClient integrates with many existing frameworks and libraries, such as [Refit](https://github.com/reactiveui/refit), [RestSharp](https://restsharp.dev/getting-started/getting-started.html#basic-usage), and [Polly](https://github.com/App-vNext/Polly).</span></span>

### <a name="invoke-http-services-using-daprclient"></a><span data-ttu-id="a9595-181">DaprClient를 사용 하 여 HTTP 서비스 호출</span><span class="sxs-lookup"><span data-stu-id="a9595-181">Invoke HTTP services using DaprClient</span></span>

<span data-ttu-id="a9595-182">HttpClient는 HTTP 의미 체계를 사용 하 여 서비스를 호출 하는 기본 방법 이지만 메서드 패밀리를 사용할 수도 있습니다 `DaprClient.InvokeMethodAsync` .</span><span class="sxs-lookup"><span data-stu-id="a9595-182">While HttpClient is the preferred way to invoke services using HTTP semantics, you can also use the `DaprClient.InvokeMethodAsync` family of methods.</span></span> <span data-ttu-id="a9595-183">다음 예제에서는 `submit` 응용 프로그램의 메서드를 호출 하 여 주문을 전송 합니다 `orderservice` .</span><span class="sxs-lookup"><span data-stu-id="a9595-183">The following example submits an order by calling the `submit` method of the `orderservice` application:</span></span>

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

<span data-ttu-id="a9595-184">세 번째 인수인 개체인는 `order` 내부적으로 직렬화 되 `System.Text.JsonSerializer` 고 요청 페이로드로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-184">The third argument, an `order` object, is serialized internally (with `System.Text.JsonSerializer`) and sent as the request payload.</span></span> <span data-ttu-id="a9595-185">.NET SDK는 사이드카에 대 한 호출을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-185">The .NET SDK takes care of the call to the sidecar.</span></span> <span data-ttu-id="a9595-186">또한 개체에 대 한 응답을 deserialize `OrderConfirmation` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-186">It also deserializes the response to an `OrderConfirmation` object.</span></span> <span data-ttu-id="a9595-187">HTTP 메서드가 지정 되지 않았기 때문에 요청은 HTTP POST로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-187">Because no HTTP method is specified, the request is executed as an HTTP POST.</span></span>

<span data-ttu-id="a9595-188">다음 예제에서는를 지정 하 여 HTTP GET 요청을 수행 하는 방법을 보여 줍니다 `HttpMethod` .</span><span class="sxs-lookup"><span data-stu-id="a9595-188">The next example demonstrates how you can make an HTTP GET request by specifying the `HttpMethod`:</span></span>

```csharp
var catalogItems = await daprClient.InvokeMethodAsync<IEnumerable<CatalogItem>>(HttpMethod.Get, "catalogservice", "items");
```

<span data-ttu-id="a9595-189">일부 시나리오에서는 요청 메시지에 대해 더 많은 제어가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-189">For some scenarios, you may require more control over the request message.</span></span> <span data-ttu-id="a9595-190">예를 들어 요청 헤더를 지정 해야 하거나 페이로드에 대 한 사용자 지정 serializer를 사용 하려는 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-190">For example, when you need to specify request headers, or you want to use a custom serializer for the payload.</span></span> <span data-ttu-id="a9595-191">`DaprClient.CreateInvokeMethodRequest` 을 만듭니다 `HttpRequestMessage` .</span><span class="sxs-lookup"><span data-stu-id="a9595-191">`DaprClient.CreateInvokeMethodRequest` creates an `HttpRequestMessage`.</span></span> <span data-ttu-id="a9595-192">다음 예제에서는 요청 메시지에 HTTP 권한 부여 헤더를 추가 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-192">The following example demonstrates how to add an HTTP authorization header to a request message:</span></span>

```csharp
var request = daprClient.CreateInvokeMethodRequest("orderservice", "submit", order);
request.Headers.Authorization = new AuthenticationHeaderValue("bearer", token);
```

<span data-ttu-id="a9595-193">이제에는 `HttpRequestMessage` 다음과 같은 속성 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-193">The `HttpRequestMessage` now has the following properties set:</span></span>

- <span data-ttu-id="a9595-194">Url = `http://127.0.0.1:3500/v1.0/invoke/orderservice/method/submit`</span><span class="sxs-lookup"><span data-stu-id="a9595-194">Url = `http://127.0.0.1:3500/v1.0/invoke/orderservice/method/submit`</span></span>
- <span data-ttu-id="a9595-195">HttpMethod = POST</span><span class="sxs-lookup"><span data-stu-id="a9595-195">HttpMethod = POST</span></span>
- <span data-ttu-id="a9595-196">Content =  `JsonContent` JSON 직렬화를 포함 하는 개체입니다. `order`</span><span class="sxs-lookup"><span data-stu-id="a9595-196">Content =  `JsonContent` object containing the JSON-serialized `order`</span></span>
- <span data-ttu-id="a9595-197">헤더. Authorization = "전달자 \<token> "</span><span class="sxs-lookup"><span data-stu-id="a9595-197">Headers.Authorization = "bearer \<token>"</span></span>

<span data-ttu-id="a9595-198">원하는 방식으로 요청을 설정한 후에는를 사용 하 여 요청을 `DaprClient.InvokeMethodAsync` 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-198">Once you've got the request set up the way you want, use `DaprClient.InvokeMethodAsync` to send it:</span></span>

```csharp
var orderConfirmation = await daprClient.InvokeMethodAsync<OrderConfirmation>(request);
```

<span data-ttu-id="a9595-199">`DaprClient.InvokeMethodAsync` 요청이 성공 하는 경우 개체에 대 한 응답을 deserialize `OrderConfirmation` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-199">`DaprClient.InvokeMethodAsync` deserializes the response to an `OrderConfirmation` object if the request is successful.</span></span> <span data-ttu-id="a9595-200">또는를 사용 하 여 `DaprClient.InvokeMethodWithResponseAsync` 내부에 대 한 전체 액세스 권한을 얻을 수 있습니다 `HttpResponseMessage` .</span><span class="sxs-lookup"><span data-stu-id="a9595-200">Alternatively, you can use `DaprClient.InvokeMethodWithResponseAsync` to get full access to the underlying `HttpResponseMessage`:</span></span>

```csharp
var response = await daprClient.InvokeMethodWithResponseAsync(request);
response.EnsureSuccessStatusCode();

var orderConfirmation = response.Content.ReadFromJsonAsync<OrderConfirmation>();
```

> [!NOTE]
> <span data-ttu-id="a9595-201">HTTP를 사용 하 여 서비스를 호출 하는 경우 이전 섹션에서 제공 하는 Eapr HttpClient 통합 사용을 고려 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-201">For service invocation calls using HTTP, it's worth considering using the Dapr HttpClient integration presented in the previous section.</span></span> <span data-ttu-id="a9595-202">HttpClient를 사용 하면 기존 프레임 워크 및 라이브러리와의 통합과 같은 추가 혜택을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-202">Using HttpClient gives you additional benefits such as integration with existing frameworks and libraries.</span></span>

### <a name="invoke-grpc-services-using-daprclient"></a><span data-ttu-id="a9595-203">DaprClient를 사용 하 여 gRPC 서비스 호출</span><span class="sxs-lookup"><span data-stu-id="a9595-203">Invoke gRPC services using DaprClient</span></span>

<span data-ttu-id="a9595-204">DaprClient는 `InvokeMethodGrpcAsync` gRPC 끝점을 호출 하기 위한 메서드 패밀리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-204">DaprClient provides a family of `InvokeMethodGrpcAsync` methods for calling gRPC endpoints.</span></span> <span data-ttu-id="a9595-205">HTTP 메서드와의 주요 차이점은 JSON 대신 Protobuf serializer를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-205">The main difference with the HTTP methods is the use of a Protobuf serializer instead of JSON.</span></span> <span data-ttu-id="a9595-206">다음 예제에서는 `submitOrder` 최대 gRPC의 메서드를 호출 합니다 `orderservice` .</span><span class="sxs-lookup"><span data-stu-id="a9595-206">The following example invokes the `submitOrder` method of the `orderservice` over gRPC.</span></span>

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

<span data-ttu-id="a9595-207">위의 예제에서 DaprClient는 `order` [Protobuf](https://developers.google.com/protocol-buffers) 를 사용 하 여 지정 된 개체를 직렬화 하 고 결과를 grpc 요청 본문으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-207">In the example above, DaprClient serializes the given `order` object using [Protobuf](https://developers.google.com/protocol-buffers) and uses the result as the gRPC request body.</span></span> <span data-ttu-id="a9595-208">마찬가지로 응답 본문은 Protobuf deserialize 되어 호출자에 게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-208">Likewise, the response body is Protobuf deserialized and returned to the caller.</span></span> <span data-ttu-id="a9595-209">Protobuf는 일반적으로 HTTP 서비스 호출에 사용 되는 JSON 페이로드 보다 더 나은 성능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-209">Protobuf typically provides better performance than the JSON payloads used in HTTP service invocation.</span></span>

## <a name="reference-application-eshopondapr"></a><span data-ttu-id="a9595-210">참조 응용 프로그램: eShopOnDapr</span><span class="sxs-lookup"><span data-stu-id="a9595-210">Reference application: eShopOnDapr</span></span>

<span data-ttu-id="a9595-211">Microsoft의 원래 [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) 마이크로 서비스 reference 아키텍처는 HTTP/REST 및 grpc 서비스를 혼합 하 여 사용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-211">The original [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) microservice reference architecture from Microsoft used a mix of HTTP/REST and gRPC services.</span></span> <span data-ttu-id="a9595-212">GRPC를 사용 하는 것은 [집계 서비스](../cloud-native/service-to-service-communication.md#service-aggregator-pattern) 와 핵심 백 엔드 서비스 간의 통신으로 제한 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-212">The use of gRPC was limited to communication between an [aggregator service](../cloud-native/service-to-service-communication.md#service-aggregator-pattern) and core back-end services.</span></span> <span data-ttu-id="a9595-213">그림 6-2은 아키텍처를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-213">Figure 6-2 show the architecture:</span></span>

![eShopOnContainers에서 gRPC 및 HTTP/REST 호출](./media/service-invocation/eshop-on-containers.png)

<span data-ttu-id="a9595-215">**그림 6-2**.</span><span class="sxs-lookup"><span data-stu-id="a9595-215">**Figure 6-2**.</span></span> <span data-ttu-id="a9595-216">eShopOnContainers에서 gRPC 및 HTTP/REST 호출.</span><span class="sxs-lookup"><span data-stu-id="a9595-216">gRPC and HTTP/REST calls in eShopOnContainers.</span></span>

<span data-ttu-id="a9595-217">위의 그림에서 설명 하는 단계를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-217">Note the steps from the previous figure:</span></span>

1. <span data-ttu-id="a9595-218">프런트 엔드는 HTTP/REST를 사용 하 여 [API 게이트웨이](/azure/architecture/microservices/design/gateway) 를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-218">The front end calls the [API gateway](/azure/architecture/microservices/design/gateway) using HTTP/REST.</span></span>

1. <span data-ttu-id="a9595-219">API 게이트웨이는 HTTP/REST를 사용 하 여 간단한 [CRUD](https://www.sumologic.com/glossary/crud/) (만들기, 읽기, 업데이트, 삭제) 요청을 핵심 백 엔드 서비스에 직접 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-219">The API gateway forwards simple [CRUD](https://www.sumologic.com/glossary/crud/) (Create, Read, Update, Delete) requests directly to a core back-end service using HTTP/REST.</span></span>

1. <span data-ttu-id="a9595-220">API 게이트웨이는 여러 백 엔드 서비스에 대 한 조정 된 호출을 포함 하는 복잡 한 요청을 웹 쇼핑 집계 서비스에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-220">The API gateway forwards complex requests that involve coordinated calls to multiple back-end services to the web shopping aggregator service.</span></span>

1. <span data-ttu-id="a9595-221">집계 서비스는 gRPC를 사용 하 여 코어 백 엔드 서비스를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-221">The aggregator service uses gRPC to call core back-end services.</span></span>

<span data-ttu-id="a9595-222">최근에 업데이트 된 eShopOnDapr 구현에서 사이드카는 서비스 및 API 게이트웨이에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-222">In the recently updated eShopOnDapr implementation, Dapr sidecars are added to the services and API gateway.</span></span> <span data-ttu-id="a9595-223">그림 6-3에서는 업데이트 된 아키텍처를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-223">Figure 6-3 show the updated architecture:</span></span>

![eShopOnContainers의 사이드카를 사용 하 여 gRPC 및 HTTP/REST 호출](./media/service-invocation/eshop-on-dapr.png)

<span data-ttu-id="a9595-225">**그림 6-3**.</span><span class="sxs-lookup"><span data-stu-id="a9595-225">**Figure 6-3**.</span></span> <span data-ttu-id="a9595-226">D 4를 사용 하 여 eShop 아키텍처를 업데이트 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-226">Updated eShop architecture using Dapr.</span></span>

<span data-ttu-id="a9595-227">이전 그림의 업데이트 된 단계를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-227">Note the updated steps from the previous figure:</span></span>

1. <span data-ttu-id="a9595-228">프런트 엔드는 여전히 HTTP/REST를 사용 하 여 API 게이트웨이를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-228">The front end still uses HTTP/REST to call the API gateway.</span></span>

1. <span data-ttu-id="a9595-229">API 게이트웨이는 해당 사이드카에 HTTP 요청을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-229">The API gateway forwards HTTP requests to its Dapr sidecar.</span></span>

1. <span data-ttu-id="a9595-230">API 게이트웨이 사이드카는 집계 또는 백 엔드 서비스의 사이드카 요청을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-230">The API gateway sidecar sends the request to the sidecar of the aggregator or back-end service.</span></span>

1. <span data-ttu-id="a9595-231">집계 서비스는 Dapr .NET SDK를 사용 하 여 사이드카 아키텍처를 통해 백 엔드 서비스를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-231">The aggregator service uses the Dapr .NET SDK to call back-end services through their sidecar architecture.</span></span>

<span data-ttu-id="a9595-232">사이드카는 gRPC와의 호출을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-232">Dapr implements calls between sidecars with gRPC.</span></span> <span data-ttu-id="a9595-233">따라서 HTTP/REST 의미 체계를 사용 하 여 원격 서비스를 호출 하는 경우에도 gRPC를 사용 하 여 전송 부분이 계속 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-233">So even if you're invoking a remote service with HTTP/REST semantics, a part of the transport is still implemented using gRPC.</span></span>

<span data-ttu-id="a9595-234">EShopOnDapr reference 응용 프로그램은 Eapr 서비스 호출 빌딩 블록을 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-234">The eShopOnDapr reference application benefits from the Dapr service invocation building block.</span></span> <span data-ttu-id="a9595-235">이러한 이점에는 서비스 검색, 자동 mTLS 및 관찰성이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-235">The benefits include service discovery, automatic mTLS, and observability.</span></span>

### <a name="forward-http-requests-using-envoy-and-dapr"></a><span data-ttu-id="a9595-236">엔보이 및 d 4를 사용 하 여 HTTP 요청 전달</span><span class="sxs-lookup"><span data-stu-id="a9595-236">Forward HTTP requests using Envoy and Dapr</span></span>

<span data-ttu-id="a9595-237">원래 및 업데이트 된 eShop 응용 프로그램은 모두 [엔보이 프록시](https://www.envoyproxy.io/) 를 API 게이트웨이로 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-237">Both the original and updated eShop application leverage the [Envoy proxy](https://www.envoyproxy.io/) as an API gateway.</span></span> <span data-ttu-id="a9595-238">엔보이는 최신 분산 응용 프로그램에서 널리 사용 되는 오픈 소스 프록시와 통신 버스입니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-238">Envoy is an open-source proxy and communication bus that is popular across modern distributed applications.</span></span> <span data-ttu-id="a9595-239">Lyft에서 시작 되는 엔보이는 [클라우드 네이티브 컴퓨팅 파운데이션](https://www.cncf.io/)에서 소유 하 고 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-239">Originating from Lyft, Envoy is owned and maintained by the [Cloud-Native Computing Foundation](https://www.cncf.io/).</span></span>

<span data-ttu-id="a9595-240">원래 eShopOnContainers 구현에서 엔보이 API 게이트웨이는 들어오는 HTTP 요청을 집계 또는 백 엔드 서비스에 직접 전달 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-240">In the original eShopOnContainers implementation, the Envoy API gateway forwarded incoming HTTP requests directly to aggregator or back-end services.</span></span> <span data-ttu-id="a9595-241">새 eShopOnDapr에서 엔보이 프록시는 요청을 Eapr 사이드카에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-241">In the new eShopOnDapr, the Envoy proxy forwards the request to a Dapr sidecar.</span></span> <span data-ttu-id="a9595-242">사이드카는 서비스 호출, mTLS 및 관찰성를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-242">The sidecar provides service invocation, mTLS, and observability.</span></span>

<span data-ttu-id="a9595-243">엔보이는 YAML 정의 파일을 사용 하 여 프록시의 동작을 제어 하도록 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-243">Envoy is configured using a YAML definition file to control the proxy's behavior.</span></span> <span data-ttu-id="a9595-244">엔보이가 사이드카 컨테이너에 HTTP 요청을 전달 하도록 설정 하려면 `dapr` 클러스터가 구성에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-244">To enable Envoy to forward HTTP requests to a Dapr sidecar container, a `dapr` cluster is added to the configuration.</span></span> <span data-ttu-id="a9595-245">클러스터 구성에는 사이드카에서 수신 대기 하는 HTTP 포트를 가리키는 호스트가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-245">The cluster configuration contains a host that points to the HTTP port on which the Dapr sidecar is listening:</span></span>

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

<span data-ttu-id="a9595-246">사이드카에 대 한 호출로 들어오는 요청을 다시 작성 하도록 엔보이 경로 구성이 업데이트 됩니다 (키/값 쌍에 대 한 주의를 기울여야 함 `prefix_rewrite` ).</span><span class="sxs-lookup"><span data-stu-id="a9595-246">The Envoy routes configuration is updated to rewrite incoming requests as calls to the Dapr sidecar (pay close attention to the `prefix_rewrite` key/value pair):</span></span>

``` yaml
- name: "c-short"
  match:
    prefix: "/c/"
  route:
    auto_host_rewrite: true
    prefix_rewrite: "/v1.0/invoke/catalog-api/method/"
    cluster: dapr
```

<span data-ttu-id="a9595-247">프런트 엔드 클라이언트에서 카탈로그 항목 목록을 검색 하려는 시나리오를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-247">Consider a scenario where the front-end client wants to retrieve a list of catalog items.</span></span> <span data-ttu-id="a9595-248">카탈로그 API는 카탈로그 항목을 가져오기 위한 끝점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-248">The Catalog API provides an endpoint for getting the catalog items:</span></span>

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

<span data-ttu-id="a9595-249">첫째, 프런트 엔드는 엔보이 API 게이트웨이에 대 한 직접 HTTP 호출을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-249">First, the front end makes a direct HTTP call to the Envoy API gateway.</span></span>

```
GET http://<api-gateway>/c/api/v1/catalog/items?pageSize=20
```

<span data-ttu-id="a9595-250">엔보이 프록시가 경로와 일치 하 고, HTTP 요청을 다시 작성 하 고,이를 `invoke` 해당 사이드카의 API에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-250">The Envoy proxy matches the route, rewrites the HTTP request, and forwards it to the `invoke` API of its Dapr sidecar:</span></span>

```
GET http://127.0.0.1:3500/v1.0/invoke/catalog-api/method/api/v1/catalog/items?pageSize=20
```

<span data-ttu-id="a9595-251">사이드카는 서비스 검색을 처리 하 고 요청을 카탈로그 API 사이드카로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-251">The sidecar handles service discovery and routes the request to the Catalog API sidecar.</span></span> <span data-ttu-id="a9595-252">마지막으로 사이드카는 카탈로그 API를 호출 하 여 요청을 실행 하 고, 카탈로그 항목을 인출 하 고, 응답을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-252">Finally, the sidecar calls the Catalog API to execute the request, fetch catalog items, and return a response:</span></span>

```
GET http://localhost/api/v1/catalog/items?pageSize=20
```

### <a name="make-aggregated-service-calls-using-the-net-sdk"></a><span data-ttu-id="a9595-253">.NET SDK를 사용 하 여 집계 된 서비스 호출 만들기</span><span class="sxs-lookup"><span data-stu-id="a9595-253">Make aggregated service calls using the .NET SDK</span></span>

<span data-ttu-id="a9595-254">EShop 프런트 엔드에서의 대부분 호출은 간단한 CRUD 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-254">Most calls from the eShop front end are simple CRUD calls.</span></span> <span data-ttu-id="a9595-255">API 게이트웨이는 처리를 위해 단일 서비스로이를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-255">The API gateway forwards them to a single service for processing.</span></span> <span data-ttu-id="a9595-256">그러나 일부 시나리오에서는 여러 백 엔드 서비스가 함께 작동 하 여 요청을 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-256">Some scenarios, however, require multiple back-end services to work together to complete a request.</span></span> <span data-ttu-id="a9595-257">이러한 보다 복잡 한 호출의 경우 eShop는 웹 쇼핑 집계 서비스를 사용 하 여 여러 서비스에 걸쳐 워크플로를 중재 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-257">For these more complex calls, eShop uses the web shopping aggregator service to mediate the workflow across multiple services.</span></span> <span data-ttu-id="a9595-258">그림 6-4에서는 시장 바구니에 항목을 추가 하는 처리 순서를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-258">Figure 6-4 show the processing sequence of adding an item to your shopping basket:</span></span>

![바구니 시퀀스 다이어그램 업데이트](./media/service-invocation/complex-call.png)

<span data-ttu-id="a9595-260">**그림 6-4**</span><span class="sxs-lookup"><span data-stu-id="a9595-260">**Figure 6-4**.</span></span> <span data-ttu-id="a9595-261">쇼핑 바구니 순서를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-261">Update shopping basket sequence.</span></span>

<span data-ttu-id="a9595-262">집계 서비스는 먼저 카탈로그 API에서 카탈로그 항목을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-262">The aggregator service first retrieves catalog items from the Catalog API.</span></span> <span data-ttu-id="a9595-263">그런 다음 항목 가용성 및 가격의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-263">It then validates item availability and pricing.</span></span> <span data-ttu-id="a9595-264">마지막으로, 집계 서비스는 바구니 API를 호출 하 여 업데이트 된 쇼핑 바구니를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-264">Finally, the aggregator service saves the updated shopping basket by calling the Basket API.</span></span>

<span data-ttu-id="a9595-265">집계 서비스에는 시장 `BasketController` 바구니를 업데이트 하기 위한 끝점을 제공 하는가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-265">The aggregator service contains a `BasketController` that provides an endpoint for updating the shopping basket:</span></span>

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

<span data-ttu-id="a9595-266">`UpdateAllBasketAsync`메서드는 특성을 사용 하 여 들어오는 요청의 *권한 부여* 헤더를 가져옵니다 `FromHeader` .</span><span class="sxs-lookup"><span data-stu-id="a9595-266">The `UpdateAllBasketAsync` method gets the *Authorization* header of the incoming request using a `FromHeader` attribute.</span></span> <span data-ttu-id="a9595-267">*권한 부여* 헤더에는 보호 된 백 엔드 서비스를 호출 하는 데 필요한 액세스 토큰이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-267">The *Authorization* header contains the access token that is needed to call protected back-end services.</span></span>

<span data-ttu-id="a9595-268">바구니 업데이트 요청을 받은 후 집계 서비스는 카탈로그 API를 호출 하 여 항목 세부 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-268">After receiving a request to update the basket, the aggregator service calls the Catalog API to get the item details.</span></span> <span data-ttu-id="a9595-269">바구니 컨트롤러는 삽입 된 개체를 사용 하 여 `ICatalogService` 해당 호출을 수행 하 고 카탈로그 API와 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-269">The Basket controller uses an injected `ICatalogService` object to make that call and communicate with the Catalog API.</span></span> <span data-ttu-id="a9595-270">인터페이스의 원래 구현은 gRPC를 사용 하 여 호출을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-270">The original implementation of the interface used gRPC to make the call.</span></span> <span data-ttu-id="a9595-271">업데이트 된 구현에서는 HttpClient 지원과 함께 Eapr 서비스 호출을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-271">The updated implementation uses Dapr service invocation with HttpClient support:</span></span>

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

<span data-ttu-id="a9595-272">서비스 호출을 호출 하는 데 필요한 구체적인 코드는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-272">Notice how no Dapr specific code is required to make the service invocation call.</span></span> <span data-ttu-id="a9595-273">모든 통신은 표준 HttpClient 개체를 사용 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-273">All communication is done using the standard HttpClient object.</span></span>

<span data-ttu-id="a9595-274">다음 메서드의 클래스에는 6Apr HttpClient가 삽입 됩니다 `CatalogService` `Startup.ConfigureServices` .</span><span class="sxs-lookup"><span data-stu-id="a9595-274">The Dapr HttpClient is injected into the `CatalogService` class in the `Startup.ConfigureServices` method:</span></span>

```csharp
services.AddSingleton<ICatalogService, CatalogService>(
    _ => new CatalogService(DaprClient.CreateInvokeHttpClient("catalog-api")));
```

<span data-ttu-id="a9595-275">집계 서비스에서 수행 하는 다른 호출은 바구니 API에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-275">The other call made by the aggregator service is to the Basket API.</span></span> <span data-ttu-id="a9595-276">승인 된 요청만 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-276">It only allows authorized requests.</span></span> <span data-ttu-id="a9595-277">액세스 토큰은 호출이 성공 하도록 *권한 부여* 요청 헤더에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-277">The access token is passed along in an *Authorization* request header to ensure the call succeeds:</span></span>

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

<span data-ttu-id="a9595-278">이 예제에서는 표준 HttpClient 기능만 사용 하 여 서비스를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-278">In this example too, only standard HttpClient functionality is used to call the service.</span></span> <span data-ttu-id="a9595-279">이를 통해 HttpClient를 이미 잘 알고 있는 개발자가 기존 기술을 재사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-279">This allows developers who are already familiar with HttpClient to reuse their existing skills.</span></span> <span data-ttu-id="a9595-280">이 기능을 사용 하면 기존 HttpClient 코드에서 변경 하지 않고도 Eapr 서비스 호출을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-280">It even enables existing HttpClient code to use Dapr service invocation without making any changes.</span></span>

## <a name="summary"></a><span data-ttu-id="a9595-281">요약</span><span class="sxs-lookup"><span data-stu-id="a9595-281">Summary</span></span>

<span data-ttu-id="a9595-282">이 장에서는 서비스 호출 빌딩 블록에 대해 알아보았습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-282">In this chapter, you learned about the service invocation building block.</span></span> <span data-ttu-id="a9595-283">Dapr 사이드카에 대 한 직접 HTTP 호출을 수행 하 고 Dapr .NET SDK를 사용 하 여 원격 메서드를 호출 하는 방법을 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-283">You saw how to invoke remote methods both by making direct HTTP calls to the Dapr sidecar, and by using the Dapr .NET SDK.</span></span>

<span data-ttu-id="a9595-284">Dapr .NET SDK는 원격 메서드를 호출 하는 여러 가지 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-284">The Dapr .NET SDK provides multiple ways to invoke remote methods.</span></span> <span data-ttu-id="a9595-285">HttpClient 지원은 기존 기술을 다시 사용 하려는 개발자에 게 유용 하며 기존의 많은 프레임 워크 및 라이브러리와 호환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-285">HttpClient support is great for developers wanting to reuse existing skills and is compatible with many existing frameworks and libraries.</span></span> <span data-ttu-id="a9595-286">DaprClient는 HTTP 또는 gRPC 의미 체계를 사용 하 여 Eapr 서비스 호출 API를 직접 사용 하는 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-286">DaprClient offers support for directly using the Dapr service invocation API using either HTTP or gRPC semantics.</span></span>

<span data-ttu-id="a9595-287">EShopOnDapr reference 아키텍처는 eShopOnContainers 서비스 호출을 사용 하 여 원래 솔루션을 현대화 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-287">The eShopOnDapr reference architecture shows how the original eShopOnContainers solution is modernized by using Dapr service invocation.</span></span> <span data-ttu-id="a9595-288">D 4를 eShop에 추가 하면 자동 재시도, mTLS를 사용 하는 메시지 암호화 및 향상 된 관찰성 같은 이점이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9595-288">Adding Dapr to eShop provides benefits such as automatic retries, message encryption using mTLS, and improved observability.</span></span>

### <a name="references"></a><span data-ttu-id="a9595-289">참조</span><span class="sxs-lookup"><span data-stu-id="a9595-289">References</span></span>

- [<span data-ttu-id="a9595-290">6apr 서비스 호출 빌딩 블록</span><span class="sxs-lookup"><span data-stu-id="a9595-290">Dapr service invocation building block</span></span>](https://docs.dapr.io/developing-applications/building-blocks/service-invocation/)

- [<span data-ttu-id="a9595-291">분산 클라우드-네이티브 응용 프로그램 모니터링</span><span class="sxs-lookup"><span data-stu-id="a9595-291">Monitoring distributed cloud-native applications</span></span>](../cloud-native/observability-patterns.md)

> [!div class="step-by-step"]
> <span data-ttu-id="a9595-292">[이전](state-management.md)
> [다음](publish-subscribe.md)</span><span class="sxs-lookup"><span data-stu-id="a9595-292">[Previous](state-management.md)
[Next](publish-subscribe.md)</span></span>
